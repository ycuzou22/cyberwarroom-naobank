# Ghost agents — NAOBANK

Les ghost agents simulent l'activité normale des employés de NAOBANK (connexions, fichiers ouverts, mails, navigation). Ce « bruit de fond » légitime rend le scénario crédible : l'équipe SOC doit repérer l'attaque au milieu d'une activité réaliste, et pas sur un réseau vide.

## Solutions existantes étudiées

| Outil | Licence | Linux | Fonctionne seul ? | Verdict |
| --- | --- | --- | --- | --- |
| [GHOSTS](https://github.com/cmu-sei/GHOSTS) (Carnegie Mellon, SEI) | MIT | Oui | Oui, le serveur API est optionnel | **Retenu** |
| [Plugin Human](https://github.com/mitre/human) (MITRE Caldera) | Open source | Oui | Non, il faut un serveur Caldera | Écarté |
| [SOCBED](https://github.com/fkie-cad/socbed) | Open source | Oui | Oui, mais c'est un labo complet de VM | Écarté |

GHOSTS est retenu : c'est la référence open source pour simuler des employés dans les exercices de crise cyber, et son client Linux sait déjà exécuter des commandes, consulter des sites web et se connecter en SSH.

## Langage choisi

**Python 3**, car le serveur de test est sous Linux : Python y est installé par défaut et la bibliothèque standard suffit.

## Fonctionnement du script (en 10 lignes)

1. Le script `ghost_open_file.py` simule une seule action de Camille Roussel.
2. Il utilise le fichier de travail `Dossier_Benoit.txt`.
3. Au démarrage, il crée ce fichier s'il n'existe pas encore.
4. Il entre ensuite dans une boucle sans fin.
5. À chaque tour, il ouvre le fichier en lecture.
6. Il lit son contenu, comme le ferait l'employée.
7. Il referme le fichier.
8. Il affiche l'heure et le nom du fichier ouvert.
9. Il attend 5 minutes.
10. Il recommence, jusqu'à l'arrêt avec Ctrl+C.

## Utilisation

```bash
python3 ghost_open_file.py
```
