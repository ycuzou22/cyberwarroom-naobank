# infra/ : labo Nao Bank (Proxmox + Ansible)

Déploiement automatisé du labo : 5 VLANs, 9 machines, pare-feu pfSense.

## Prérequis
- Hôte Proxmox VE (32 Go de RAM minimum), bridge `vmbr1` en mode « VLAN aware »
- Modèles (templates) à préparer une fois : `tpl-debian-13` (serveurs mail, fichiers, sauvegarde) et `tpl-ubuntu-2204` (SIEM), tous deux avec cloud-init, `tpl-win11`, `tpl-kali`, `tpl-pfsense`
- Poste de contrôle avec Ansible >= 2.15 et la collection `community.general`
- Un jeton API Proxmox, stocké dans un fichier chiffré avec `ansible-vault`

```bash
ansible-galaxy collection install community.general
cp ansible/group_vars/vault.example.yml ansible/group_vars/vault.yml
ansible-vault encrypt ansible/group_vars/vault.yml
```

## Utilisation
```bash
cd ansible
ansible-playbook playbooks/01_create_vms.yml --ask-vault-pass   # clone, VLAN, RAM, CPU, démarrage
ansible-playbook playbooks/02_configure.yml  --ask-vault-pass   # rôles par groupe
```

## Plan réseau
| VLAN | Nom | Réseau | Machines |
|---|---|---|---|
| 10 | PROD | 192.168.10.0/24 | PC-EMP-01, 02, 03 |
| 20 | SRV | 192.168.20.0/24 | SRV-MAIL, SRV-FICHIERS |
| 30 | BACKUP | 192.168.30.0/24 | SRV-SAUVEGARDE |
| 40 | SOC | 192.168.40.0/24 | SIEM-ELASTIC |
| 99 | ATTAQUANT | 192.168.99.0/24 | ATTAQUANT |

Règles de pare-feu : voir `pfsense/regles.md`. Tableur complet : `docs/NaoBank_Labo_VLAN.xlsx`.

## État d'avancement (squelette à compléter)
- Les playbooks et rôles sont une base de départ, ils n'ont pas encore été exécutés sur le labo.
- Postes Windows : modèle préparé à la main, installation de l'Elastic Agent manuelle pour l'instant.
- Fleet Server : création de la politique et du jeton d'enrôlement dans Kibana, puis renseigner `elastic_enrollment_token` dans le vault.
- Postfix : TLS et port 587 (submission) à finaliser.
- Redimensionnement des disques : à ajouter au playbook 01.
- pfSense : configuration des interfaces VLAN et des règles à faire dans l'interface (ou import d'un `config.xml`).
