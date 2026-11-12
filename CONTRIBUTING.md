# 🤝 Guide de contribution — CyberWarRoom

Merci de participer au projet Nao Bank ! Ce guide explique comment travailler ensemble sur le dépôt.
**À lire avant ta première contribution.**

---

## 📋 Le cycle de travail en 5 étapes

1. **Récupère la dernière version** de `main`.
2. **Crée ta branche** en suivant la convention ci-dessous.
3. **Travaille et commit** avec des messages clairs.
4. **Ouvre une pull request** vers `main`.
5. **Attends la relecture** d'une autre personne avant de fusionner.

```bash
git checkout main
git pull
git checkout -b soc/regles-detection
# ... tu travailles ...
git add .
git commit -m "[ADD] Règle de détection des connexions depuis l'étranger"
git push -u origin soc/regles-detection
```

---

## 🌿 Nommage des branches

**Format :** `pôle/sujet-en-minuscules`

| Pôle | Préfixe | Exemple |
|---|---|---|
| 🛡️ SOC | `soc/` | `soc/regles-detection` |
| 💀 Hack | `hack/` | `hack/kill-chain-phishing` |
| 🖥️ Infra | `infra/` | `infra/schema-reseau` |
| 👻 Ghost agents | `ghost/` | `ghost/script-connexion` |
| 📝 Narratif | `narratif/` | `narratif/personnage-taupe` |
| 📄 Fake data | `data/` | `data/faux-mails` |
| ⚙️ Repo, CI, docs | `chore/` | `chore/readme` |

**Règles :**

- tout en minuscules ;
- des tirets `-` entre les mots, jamais d'espaces ni d'accents ;
- une branche = un seul sujet ;
- on ne travaille **jamais directement sur `main`**.

---

## ✍️ Messages de commit

**Format :** `[TAG] Description courte de ce que fait le commit`

| Tag | Quand l'utiliser | Exemple |
|---|---|---|
| `[ADD]` | Ajout d'un fichier ou d'une fonctionnalité | `[ADD] Fiche du personnage de la taupe` |
| `[UPDATE]` | Modification ou amélioration d'un contenu existant | `[UPDATE] Ajout de l'étape 3 dans la kill chain` |
| `[FIX]` | Correction d'une erreur | `[FIX] Mauvaise adresse IP du serveur de mail` |
| `[DEL]` | Suppression d'un fichier ou d'un contenu | `[DEL] Ancien schéma réseau` |
| `[DOCS]` | Documentation, README, guides | `[DOCS] Guide d'installation du SIEM` |
| `[MERGE]` | Fusion de branches | `[MERGE] Intégration de main dans soc/regles-detection` |

**Règles :**

- la description commence par une majuscule, sans point final ;
- elle dit **ce que fait** le commit, pas ce que tu as fait dans ta journée ;
- 72 caractères maximum ;
- un commit = un changement logique. Mieux vaut plusieurs petits commits qu'un énorme.

| ❌ À éviter | ✅ À faire |
|---|---|
| `modif` | `[UPDATE] Durée des étapes de la kill chain` |
| `fix bug` | `[FIX] Ghost agent qui plante au démarrage` |
| `ajout de plein de trucs` | Plusieurs commits séparés |

---

## 🔍 Pull requests et relecture

### Ouvrir une pull request

1. Pousse ta branche sur GitHub.
2. Clique sur **Compare & pull request**.
3. Donne-lui un titre au même format qu'un commit, par exemple `[ADD] Règles de détection du SOC`.
4. Dans la description, explique en 2 ou 3 phrases **ce que tu as fait et pourquoi**.
5. Ajoute un **relecteur** : de préférence le référent de ton pôle.

### La règle d'or

> **Toute pull request doit être relue et approuvée par une autre personne avant d'être fusionnée.**
> Personne ne fusionne sa propre pull request.

Cette règle est appliquée automatiquement par GitHub : la branche `main` est protégée.

### Pour le relecteur

- Vérifie que le contenu correspond au titre.
- Vérifie qu'il n'y a **aucun secret** : mot de passe, clé, token.
- Vérifie qu'il n'y a **aucune donnée réelle** : vrais noms, vraies adresses, vraies entreprises.
- Laisse un commentaire si quelque chose n'est pas clair, puis **Approve** quand tout est bon.

---

## 🚫 Interdits absolus

| Interdit | Pourquoi |
|---|---|
| Pousser des mots de passe, clés ou fichiers `.env` | Une fois sur GitHub, un secret est compromis, même supprimé ensuite |
| Mettre des données réelles | Le projet est 100 % fictif |
| Pousser des vidéos ou des images de VM | Trop lourd : utilise le canal Teams prévu |
| Forcer un push sur `main` | L'historique de tout le monde serait cassé |

---

## 🆘 Besoin d'aide ?

Bloqué plus de 15 minutes ? Pose ta question dans le canal **🙋 Help** sur Teams, ou demande à ton tuteur.
Demander de l'aide n'est pas un échec, c'est la règle.