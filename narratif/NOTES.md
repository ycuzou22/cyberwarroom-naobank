### Présentation de Nao Bank

Nao Bank est une banque commerciale fictive française dont le siège social est situé à Nantes. Elle compte environ 1 200 collaborateurs et accompagne près de 350 000 clients particuliers et professionnels à travers ses agences physiques et ses services bancaires numériques. Elle propose différentes prestations financières, notamment la gestion des comptes bancaires, les opérations de paiement, les solutions de financement et les services d'épargne. Son système d'information constitue un élément stratégique de son fonctionnement : il centralise les données des clients, les opérations financières, les communications internes ainsi que les infrastructures informatiques nécessaires à ses activités. En raison de la quantité importante de données sensibles qu'elle traite quotidiennement, Nao Bank représente une cible particulièrement intéressante pour des acteurs malveillants cherchant à perturber ses activités ou à compromettre ses informations.

### Présentation du collectif Naoriste

Les Naoristes sont un collectif hacktiviste fictif composé d'individus partageant une idéologie contestataire à l'égard de certaines institutions financières. Ils reprochent notamment à Nao Bank ses pratiques économiques et son influence dans le secteur financier. Considérant la banque comme un symbole d'un système qu'ils souhaitent dénoncer, ils décident de mener une opération informatique d'envergure contre son infrastructure. Leur objectif principal est de compromettre le système d'information de Nao Bank, de perturber ses services numériques, de prendre le contrôle de certains comptes et de tenter de détruire ses sauvegardes afin de provoquer une interruption majeure de ses activités. Pour atteindre leurs objectifs, les Naoristes préparent une opération combinant reconnaissance informatique, phishing, exploitation de vulnérabilités et complicité interne.


### Fiche d'identité de la taupe – Ondo Ella fils Noé

Ondo Ella fils Noé est un stagiaire analyste au sein du Centre opérationnel de sécurité (SOC) de Nao Bank. Intégré au département cybersécurité, il est chargé de participer à la surveillance des systèmes informatiques, à l'analyse des alertes de sécurité et à l'identification des comportements suspects sur le réseau de la banque. Grâce à ses fonctions, il possède une connaissance de l'environnement informatique et des procédures de surveillance de l'établissement, dans les limites des accès accordés à son statut de stagiaire. Cependant, derrière son apparente implication dans la protection du système d'information, il entretient secrètement des relations avec le collectif hacktiviste Naoriste. Devenu informateur interne, il transmet des renseignements sur l'organisation du SOC et les dispositifs de sécurité de la banque afin de faciliter les opérations du collectif. Sa position au sein de l'équipe de défense lui permet également de participer aux investigations et d'influencer certaines pistes, tout en cherchant à dissimuler sa véritable implication. Son identité constitue ainsi un élément central du scénario CyberWarRoom, puisqu'il représente la menace interne que les joueurs devront découvrir au cours de leur investigation.
Il rejoint Nao Bank dans le but de développer ses compétences en cybersécurité. Au cours de son stage, il développe une certaine frustration envers l'organisation interne et les décisions de la direction. Cette situation est exploitée par le collectif Naoriste, qui parvient progressivement à le manipuler et à le convaincre de participer à son opération. Il devient alors un informateur interne chargé de transmettre des informations sur l'environnement de sécurité de la banque et de perturber discrètement certaines activités de surveillance.

### 3 fausses pistes
Accuser un administrateur système d'être responsable de la compromission.

Faire croire que les activités suspectes proviennent d'un prestataire externe.

Présenter les anomalies du SIEM comme de simples erreurs de configuration.

### 3 indices pour le demasquer 
Des connexions inhabituelles associées à son compte utilisateur.

Des alertes de sécurité suspectes qui n'ont pas été correctement remontées.

Une communication fictive avec un membre du collectif Naoriste retrouvée pendant l'investigation.


### les différents modes 
l'objectif est de créer deux expériences différentes.

### Mode normal
Les joueurs travaillent ensemble pour défendre Nao Bank contre les Naoristes.

### mode traitre
la taupe est secrètement infiltré et tente de manipuler les autres.


### MODE NORMAL

### Défi 1 – Détecter les premiers signes de l'attaque
Ce que les joueurs voient :
Des journaux informatiques présentant des connexions inhabituelles, des informations sur les Naoristes et des activités suspectes sur le réseau.

Ce qu'ils doivent faire :
Analyser les informations disponibles, identifier les premiers signes de reconnaissance informatique et comprendre la menace.

Condition de réussite :
Les joueurs identifient les Naoristes comme origine de la menace et comprennent leur objectif contre Nao Bank.

### Défi 2 – Identifier la compromission du système
Ce que les joueurs voient :
Des alertes de sécurité signalant des connexions suspectes et des activités inhabituelles sur certains comptes utilisateurs.

Ce qu'ils doivent faire :
Examiner les journaux du SIEM, identifier le compte compromis et déterminer les conséquences potentielles de cette intrusion.

Condition de réussite :
Les joueurs identifient le compte suspect, expliquent les anomalies et proposent une mesure de confinement adaptée.

### Défi 3 – Protéger les sauvegardes
Ce que les joueurs voient :
Une alerte critique concernant le serveur de sauvegarde. Un compte à rebours indique qu'une opération malveillante pourrait provoquer une perte de données.

Ce qu'ils doivent faire :
Prioriser la protection des sauvegardes, isoler les systèmes concernés et coordonner la réponse à l'incident.

Condition de réussite :
Les joueurs protègent les sauvegardes et empêchent la propagation de l'attaque.


### MODE TRAITRE

### Défi 1 – Orienter l'enquête sur une mauvaise piste
Ce que les joueurs voient :
Plusieurs alertes de sécurité et des informations concernant différents employés et prestataires de Nao Bank.

Ce qu'ils doivent faire :
Identifier l'origine de l'attaque et confronter les différentes hypothèses.

Intervention de la taupe :
la taupe tente de convaincre l'équipe que l'origine de l'attaque se trouve chez un prestataire externe.

Condition de réussite :
Les joueurs ne se contentent pas des déclarations de leurs collègues et vérifient leurs hypothèses à partir des preuves.

### Défi 2 – Découvrir les incohérences
Ce que les joueurs voient :
Des journaux de connexion, des rapports SOC et des événements qui ne correspondent pas toujours aux explications fournies.

Ce qu'ils doivent faire :
Comparer les informations, rechercher les contradictions et déterminer si une personne interne manipule l'investigation.

Intervention de la taupe :
la taupe tente de minimiser certaines alertes et de détourner l'attention de l'équipe.

Condition de réussite :
Les joueurs découvrent au moins une contradiction vérifiable entre les déclarations de la taupe et les preuves techniques.

### Défi 3 – Démasquer la taupe
Ce que les joueurs voient :
Des communications fictives, des journaux de sécurité et plusieurs éléments compromettants concernant les membres de l'équipe.

Ce qu'ils doivent faire :
Recouper les preuves, identifier l'informateur interne et présenter les éléments justifiant leur accusation.

Intervention de la taupe :
la taupe cherche à défendre sa position et à faire croire que les preuves ont été mal interprétées.

Condition de réussite :
Les joueurs identifient Noé comme la taupe et justifient leur décision avec des preuves concordantes.