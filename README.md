# Hack The Shields - Guide des Contributeurs

Bienvenue dans le dépôt public d'Orion Industries. Ce guide définit les standards techniques requis pour que vos challenges soient validés et intégrés à notre infrastructure automatisée.

## 1. Structure des dossiers

Chaque challenge doit résider dans son propre dossier à la racine du dépôt. Le nom du dossier doit être en minuscules, sans espaces ni caractères spéciaux (utilisez des tirets).

### Type A : Challenge Standard (Fichiers statiques)
Utilisé pour l'OSINT, le Forensic ou la Cryptographie nécessitant uniquement le téléchargement de fichiers.

nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore, solution détaillée et flag
└── files/           # Dossier contenant les fichiers pour les joueurs
    └── document.zip

### Type B : Challenge Conteneurisé (Web, Pwn, Programmation)
Utilisé pour les épreuves nécessitant une instance dynamique (Docker).


nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore, solution détaillée et flag
├── Dockerfile       # Fichier de construction (Obligatoire)
└── src/             # Code source de l'application


## 2. Barème et Configuration des Points

[cite_start]Nous utilisons un système de score dynamique linéaire[cite: 10]. Les valeurs suivantes doivent être scrupuleusement respectées dans le fichier challenge.yml pour assurer la cohérence de la plateforme.

| Difficulté | Initial | Minimum | Decay (Amortissement) |
| :--- | :--- | :--- | :--- |
| **Facile** | 100 | 25 | 7 |
| **Intermédiaire** | 300 | 100 | 7 |
| **Difficile** | 500 | 300 | 7 |

## 3. Catégories Autorisées

Veuillez classer votre challenge dans l'une des catégories suivantes :
* Web
* Cryptographie
* OSINT
* Forensic
* Programmation
* Pwn / Reverse
* Misc

## 4. Workflow de Contribution

Le dépôt utilise une branche `template` pour servir de base de travail.

### Récupération de la base
Clonez le dépôt et récupérez les modèles de base :

git clone [https://github.com/votre-org/challenges-public.git](https://github.com/votre-org/challenges-public.git)
cd challenges-public
git checkout template


### Création de votre branche
Ne travaillez jamais directement sur la branche `template` ou `main`. Créez une branche dédiée à votre projet :

git checkout -b chall/nom-de-votre-challenge


### Soumission
Une fois votre challenge testé localement, poussez votre branche et ouvrez une Pull Request (PR) sur GitHub vers la branche `main`.

git add .
git commit -m "Ajout du challenge [Nom du Challenge]"
git push origin chall/nom-de-votre-challenge


## 5. Règles de sécurité (Docker)

Pour les challenges conteneurisés, respectez les protocoles de sécurité suivants :
* [cite_start]**Utilisateur** : N'utilisez jamais l'utilisateur root pour faire tourner votre application[cite: 6, 19]. [cite_start]Vous devez créer et utiliser un utilisateur `ctf`[cite: 4, 19].
* [cite_start]**Réseau** : Exposez un seul port de communication[cite: 4, 19].
* **Ressources** : Limitez les ressources CPU et mémoire dans la mesure du possible pour garantir la stabilité de l'infrastructure.
