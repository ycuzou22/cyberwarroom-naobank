# Ghost agents — NAOBANK

Les ghost agents simulent l'activité normale des employés de NAOBANK (connexions, fichiers ouverts, mails, navigation). Ce « bruit de fond » légitime rend le scénario crédible : l'équipe SOC doit repérer l'attaque au milieu d'une activité réaliste, et pas sur un réseau vide.

## Solution retenue : GHOSTS (open source)

| Outil | Licence | Linux | Fonctionne seul ? | Verdict |
| --- | --- | --- | --- | --- |
| [GHOSTS](https://github.com/cmu-sei/GHOSTS) (Carnegie Mellon, SEI) | MIT | Oui, client « Universal » | Oui, le serveur API est optionnel | **Retenu** |


Rôle de Python : le client GHOSTS est écrit en .NET, mais on ne le modifie pas. Python sert à **générer automatiquement la timeline de chaque employé** à partir de sa journée type (tâche 1). Python est disponible par défaut sur le serveur de test Linux et ne demande aucune bibliothèque externe.

## Fonctionnement (en 10 lignes)

1. Chaque employé a un profil JSON dans `profiles/` (horaires, fichiers de travail, fréquence).
2. `generate_timeline.py` lit ce profil.
3. Il convertit les horaires de Paris en heures UTC, le format attendu par GHOSTS.
4. Il écrit une timeline GHOSTS dans `timelines/<user>.timeline.json`.
5. Avec `--create-files`, il crée aussi les faux documents de l'employé.
6. On copie la timeline dans `config/timeline.json` du client GHOSTS, sur le poste de l'employé.
7. Le client GHOSTS, lancé sous le compte de l'employé (jamais en root), lit la timeline.
8. Pendant les horaires de travail, il ouvre un des fichiers au hasard (`cat`), environ toutes les 5 minutes (±20 %).
9. Ces accès sont visibles par l'agent Wazuh du poste (journal des commandes, contrôle d'intégrité des fichiers).
10. Ensuite, on ajoutera les autres actions de la journée type (navigation, SSH, mails) dans le même générateur.

## Prototype : une seule action (ouvrir un fichier toutes les 5 minutes)

```bash
# 1. Générer la timeline de Camille et créer ses faux documents
python3 generate_timeline.py profiles/c.roussel.json --create-files

# 2. Installer le client GHOSTS Linux (runtime .NET requis) puis copier la timeline
cp timelines/c.roussel.timeline.json ~/ghosts/config/timeline.json

# 3. Lancer le client sous le compte de l'employé
cd ~/ghosts && dotnet Ghosts.Client.Universal.dll
```

Timeline produite pour Camille (extrait) :

```json
{
    "HandlerType": "Bash",
    "UtcTimeOn": "07:50:00",
    "UtcTimeOff": "17:05:00",
    "Loop": true,
    "HandlerArgs": { "execution-probability": "100", "delay-jitter": "20" },
    "TimeLineEvents": [
        {
            "Command": "random",
            "CommandArgs": [
                "cat '/home/c.roussel/naobank/Dossier_Benoit.txt'",
                "cat '/home/c.roussel/naobank/Simulation_Martin.txt'",
                "cat '/home/c.roussel/naobank/Objectifs_S46.txt'"
            ],
            "DelayAfter": 300000
        }
    ]
}
```

## Contenu du dossier

| Fichier | Rôle |
| --- | --- |
| `generate_timeline.py` | Génère la timeline GHOSTS d'un employé |
| `profiles/c.roussel.json` | Profil de Camille Roussel (exemple) |
| `timelines/c.roussel.timeline.json` | Timeline générée, prête pour GHOSTS |

## Points à vérifier sur le serveur de test

- La version du runtime .NET demandée par la release GHOSTS téléchargée (`dotnet --version`).
- Les heures UTC sont calculées à la date de génération : il faut regénérer la timeline au changement d'heure (été/hiver).
