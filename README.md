<div align="center">

# 🏦 CyberWarRoom — Nao Bank

**Scénario de gestion de crise cyber · Ydays 2026/2027**

![Statut](https://img.shields.io/badge/statut-en%20conception-orange)
![Labo](https://img.shields.io/badge/labo-CyberWarRoom-0B1020)
![Campus](https://img.shields.io/badge/Ynov-Campus%20Nantes-1BA6C0)

*Il est 3 h 12. Nao Bank est attaquée. Vous êtes dans la salle ?*

</div>

---

## 📖 Le pitch

Les joueurs incarnent la **cellule de crise de Nao Bank**, une banque fictive prise pour cible par **Naoriste**, un collectif d'activistes déterminé à la détruire.
Face à eux : une attaque réaliste, un SOC qui surveille en direct, une taupe dans l'équipe… et un compte à rebours.

## ⚔️ La kill chain

| # | Étape | Description |
|:-:|---|---|
| 1 | 🔍 OSINT | Collecte d'informations publiques sur la banque |
| 2 | 🎣 Phishing | Faux mail Microsoft 365 envoyé aux employés |
| 3 | 📡 Scan réseau | Cartographie et recherche de ports ouverts |
| 4 | 📬 Compromission | Prise de contrôle d'une boîte mail et d'un compte 365 |
| 5 | 💣 Destruction | Rançongiciel, DDoS et attaque des sauvegardes |

## 🎮 Les formats

| Format | Durée | Public |
|---|:-:|---|
| **Formation** | 1 h | Étudiants en cybersécurité, en cellule de crise |
| **Démo JPO** | 10 min | Tout public, lors des Journées Portes Ouvertes |

## 👥 L'équipe

| Pôle | Mission |
|---|---|
| 🛡️ **SOC** | Détecter l'attaque dans le SIEM |
| 💀 **Hack** | Construire la kill chain |
| 🖥️ **Infra** | Monter le labo et son réseau |
| 📝 **Narratif & Data** | Écrire l'histoire et les fausses données |

## 📁 Structure du dépôt

```
cyberwarroom-naobank/
├── README.md          # Présentation du projet
├── CONTRIBUTING.md    # Règles de contribution (branches, commits, PR)
├── .gitignore         # Bloque les secrets et fichiers .env
├── narratif/          # Trame, personnages, modes de jeu
├── attaque/           # Kill chain et playbooks MITRE ATT&CK
├── soc/               # Règles de détection du SIEM
├── infra/             # VM, réseau et scripts de déploiement
├── ghost-agents/      # Simulation d'activité des faux employés
└── fake-data/         # Faux mails, documents et profils
    └── mails/
```

## 🤝 Contribuer

1. Crée une branche au format `pôle/sujet`, par exemple `soc/regles-detection`.
2. Fais tes commits en suivant la convention du projet.
3. Ouvre une pull request : elle doit être relue par une autre personne avant d'être fusionnée.

Tous les détails sont dans [`CONTRIBUTING.md`](CONTRIBUTING.md).

---

> [!WARNING]
> **Projet pédagogique.** Toutes les entreprises, personnes et données sont fictives. Le labo est isolé de tout réseau réel.