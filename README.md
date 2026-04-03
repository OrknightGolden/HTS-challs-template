# Hack The Shields - Modèles de Création de Challenges

Bienvenue dans l'espace public d'Orion Industries. Ce dépôt contient les modèles officiels pour créer et proposer vos propres challenges pour notre CTF.

Pour des raisons de sécurité et pour garantir l'anonymat des soumissions (ainsi que le secret des flags), **les propositions de challenges ne se font pas sur GitHub**.

## 1. Comment proposer un challenge ?

1. **Téléchargez les modèles** : Clonez ce dépôt ou téléchargez-le en ZIP. Vous y trouverez deux dossiers de base (`template_standard` et `template_container`).
2. **Créez votre challenge** : Copiez le modèle qui correspond à votre besoin, renommez le dossier (sans espaces) et construisez votre épreuve à l'intérieur.
3. **Configurez le YAML** : Remplissez scrupuleusement le fichier `challenge.yml` en respectant nos barèmes (voir ci-dessous).
4. **Zippez votre dossier** : Compressez le dossier complet de votre challenge au format `.zip`.
5. **Soumettez votre création** : Envoyez votre archive via notre portail sécurisé : [LIEN_VERS_VOTRE_GOOGLE_FORM]

## 2. Choix du Modèle

### Modèle Standard (Fichiers statiques)
Utilisé pour l'OSINT, le Forensic, la Stéganographie ou la Cryptographie nécessitant uniquement le téléchargement de fichiers par les joueurs.

### Modèle Conteneurisé (Docker)
Utilisé pour les épreuves nécessitant une instance dynamique (Web, Pwn, Programmation). 
**Règles strictes pour Docker :**
* N'utilisez jamais l'utilisateur root pour faire tourner votre application. Créez un utilisateur `ctf`.
* N'exposez qu'un seul port.
* Fournissez un code source propre dans le sous-dossier `src/`.

## 3. Barème des Points

Nous utilisons un système de score dynamique. Les valeurs suivantes doivent être respectées dans votre fichier `challenge.yml`.

| Difficulté | Initial | Minimum | Decay (Amortissement) |
| :--- | :--- | :--- | :--- |
| **Facile** | 100 | 25 | 7 |
| **Intermédiaire** | 300 | 100 | 7 |
| **Difficile** | 500 | 300 | 7 |

## 4. Catégories Autorisées

* Web
* Cryptographie
* OSINT
* Forensic
* Stéganographie
* Programmation
* Reverse Engineering
* Misc

L'équipe technique d'Orion analysera votre soumission et l'intégrera à l'infrastructure si elle respecte ces standards. Bonne création !
