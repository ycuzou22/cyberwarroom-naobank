# Tâche 1 : Liste des 10 informations OSINT

| N° | Information publique fictive | Utilité pour les attaquants |
|---:|---|---|
| 1 | Nom du directeur informatique : Jean-Marc Delacroix, sur LinkedIn. | Identifier une personne importante à cibler. |
| 2 | Format des adresses mail : prenom.nom@naobank.fr. | Déduire les adresses mail des employés. |
| 3 | Offre d'emploi mentionnant Microsoft 365. | Identifier les outils utilisés par la banque. |
| 4 | Offre d'emploi mentionnant Linux Server 2022. | Identifier le système utilisé sur certains serveurs. |
| 5 | Publication LinkedIn annonçant l'arrivée d'un nouveau responsable informatique. | Identifier les changements dans l'organisation. |
| 6 | Site officiel : naobank.fr. | Identifier les pages publiques et les services de la banque. |
| 7 | Document PDF public contenant des noms de services internes. | Comprendre l'organisation de la banque. |
| 8 | Publication annonçant un partenariat avec un prestataire informatique fictif. | Identifier un fournisseur lié au système informatique. |
| 9 | Annonce de recrutement d'un administrateur réseau. | Identifier les compétences et technologies recherchées. |
| 10 | Publication annonçant une maintenance informatique le dimanche soir. | Identifier une période d'activité réduite. |

## Présentation du travail OSINT

J'ai préparé 10 informations fictives accessibles publiquement sur Nao Bank. Pour chacune, j'ai indiqué comment un attaquant pourrait utiliser cette information pour préparer son attaque.

Ces informations servent à alimenter notre scénario OSINT.

# Tâche 2 : Écrire le mail de phishing

## Scénario

Une notification urgente concernant le compte Microsoft 365 d'un employé.

## Mail fictif

**EXPÉDITEUR :** support-it@na0bank-security.fr

**OBJET :** URGENT - Expiration de votre compte Microsoft 365

Bonjour,

Le service informatique de Nao Bank vous informe que votre session Microsoft 365 nécessite une vérification.

Une intervention est prévue aujourd'hui afin d'éviter toute interruption de votre accès professionnel.

Merci de prendre connaissance de cette notification et de suivre la procédure indiquée dans notre simulation.

Cordialement,

Service informatique  
Nao Bank

## Les 3 indices qui montrent que le mail est faux

| N° | Indice | Explication |
|---:|---|---|
| 1 | Adresse bizarre | na0bank-security.fr utilise un zéro à la place de la lettre O. |
| 2 | Urgence | Le message insiste sur une intervention immédiate. |
| 3 | Expéditeur suspect | Le domaine ne correspond pas au domaine officiel fictif de Nao Bank. |