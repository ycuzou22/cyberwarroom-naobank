## 12/11/2026 — Tony — Ghost agents

### Tâche 1 : faux employés (fait)
- 10 faux employés définis pour NAOBANK (DG, DSI, directrice d'agence, conseillère, chargé d'affaires, analyste crédit, risk manager, secrétaire, comptable, juriste).
- Pour chacun : personnalité, horaires de connexion, mails envoyés (heure, destinataire, objet, pièce jointe) et sites consultés.
- Les mails internes se répondent entre eux (dossiers Ferrand, Benoît, Securit-Ops) pour produire des fils cohérents.
- Comptes AD et mots de passe fictifs ajoutés, certains volontairement faibles pour le scénario.
- Document de référence : Google Doc « NAOBANK — Journées types des employés (v2) ».
- Reste à faire : valider la liste des employés avec Kilian.

### Tâche 2 : choix de la technique (fait)
- Solutions étudiées : GHOSTS (CMU SEI), plugin Human de MITRE Caldera, SOCBED.
- Solution retenue : GHOSTS, open source (licence MIT), client Linux disponible, fonctionne sans serveur central.
- Langage choisi : Python 3, car le serveur de test est sous Linux.
- Fonctionnement du script décrit en 10 lignes dans `ghost-agents/README.md`.

### Tâche 3 : prototype (fait)
- Script `ghost-agents/ghost_open_file.py` : simule une seule action, l'ouverture du fichier `Dossier_Benoit.txt` toutes les 5 minutes.
- Testé : le fichier est créé, ouvert, et l'heure s'affiche à chaque ouverture.
- Poussé sur la branche `infra/readme-choix-tech`, pull request ouverte vers `main`, en attente de relecture.