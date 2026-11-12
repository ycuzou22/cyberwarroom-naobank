# Règles de pare-feu pfSense (strict nécessaire)

Règles appliquées sur l'interface d'entrée de chaque VLAN. Pare-feu à état : le trafic retour est automatique. Tout le reste est bloqué et journalisé.

| N° | Interface (source) | Destination | Protocole / Ports | Action |
|---|---|---|---|---|
| 1 | PROD | 192.168.20.10 (SRV-MAIL) | TCP 587, 993 | Autoriser |
| 2 | PROD | 192.168.20.11 (SRV-FICHIERS) | TCP 445 | Autoriser |
| 3 | PROD | 192.168.40.10 (SIEM-ELASTIC) | TCP 8220, 9200 | Autoriser |
| 4 | SRV | 192.168.40.10 (SIEM-ELASTIC) | TCP 8220, 9200 | Autoriser |
| 5 | BACKUP | 192.168.40.10 (SIEM-ELASTIC) | TCP 8220, 9200 | Autoriser |
| 6 | BACKUP | 192.168.20.10, 192.168.20.11 | TCP 22 | Autoriser |
| 7 | ATTAQUANT | 192.168.20.10 (SRV-MAIL) | TCP 25 | Autoriser |
| 8 | Toutes | Toutes | Tous | Bloquer + journaliser |

Interfaces pfSense (trunk 802.1Q) : VLAN 10 `192.168.10.1/24`, VLAN 20 `192.168.20.1/24`, VLAN 30 `192.168.30.1/24`, VLAN 40 `192.168.40.1/24`, VLAN 99 `192.168.99.1/24`.
