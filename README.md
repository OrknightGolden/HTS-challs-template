Hack The Shields - Guide des ContributeursBienvenue dans le dépôt public d'Orion Industries. Ce guide définit les standards techniques requis pour que vos challenges soient validés et intégrés à notre infrastructure automatisée.1. Structure des dossiersChaque challenge doit résider dans son propre dossier à la racine du dépôt. Le nom du dossier doit être en minuscules, sans espaces ni caractères spéciaux (utilisez des tirets).Type A : Challenge Standard (Fichiers statiques)Utilisé pour l'OSINT, le Forensic ou la Cryptographie nécessitant uniquement le téléchargement de fichiers.nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore, solution détaillée et flag
└── files/           # Dossier contenant les fichiers pour les joueurs
    └── document.zip
Type B : Challenge Conteneurisé (Web, Pwn, Programmation)Utilisé pour les épreuves nécessitant une instance dynamique (Docker).nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore, solution détaillée et flag
├── Dockerfile       # Fichier de construction (Obligatoire)
└── src/             # Code source de l'application
2. Barème et Configuration des PointsNous utilisons un système de score dynamique linéaire. Les valeurs suivantes doivent être scrupuleusement respectées dans le fichier challenge.yml.DifficultéInitialMinimumDecay (Amortissement)Facile100257Intermédiaire3001007Difficile50030073. Catégories AutoriséesVeuillez utiliser l'une des catégories suivantes :WebCryptographieOSINTForensicProgrammationPwn / ReverseMisc4. Workflow de ContributionLe dépôt utilise une branche template pour servir de base de travail.Récupération de la base :Clonez le dépôt et récupérez les modèles.git clone [https://github.com/votre-org/challenges-public.git](https://github.com/votre-org/challenges-public.git)
cd challenges-public
git checkout template
Création de votre branche :Ne travaillez jamais directement sur la branche template ou main.git checkout -b chall/nom-de-votre-challenge
Soumission :Une fois votre challenge testé localement, poussez votre branche et ouvrez une Pull Request (PR) sur GitHub vers la branche main.git add .
git commit -m "Ajout du challenge [Nom du Challenge]"
git push origin chall/nom-de-votre-challenge
5. Règles de sécurité (Docker)Pour les challenges conteneurisés :N'utilisez jamais l'utilisateur root pour faire tourner votre application. Créez un utilisateur ctf.Exposez un seul port.Limitez les ressources dans la mesure du possible.Hack The Shields - Guide des Contributeurs

Bienvenue dans le dépôt public des challenges d'Orion Industries. Ce guide explique comment structurer vos créations pour qu'elles soient automatiquement intégrées à notre infrastructure.

1. Structure d'un Challenge

Chaque challenge doit être isolé dans son propre dossier, nommé de manière concise (ex: web-portal-bypass). L'arborescence dépend du type de challenge :

Challenge Standard (Fichiers uniquement : OSINT, Forensic, Crypto)

nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore et Write-up (interne)
└── files/           # Fichiers à donner aux joueurs
    └── preuve.png


Challenge Conteneurisé (Web, Pwn, Programmation)

nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore et Write-up
├── Dockerfile       # Fichier de construction (Obligatoire)
└── src/             # Code source de l'application


2. Barème des Points

Nous utilisons un système de "Dynamic Scoring" (Linear). Voici les valeurs à respecter impérativement dans votre challenge.yml :

Niveau

Initial

Minimum

Decay

Facile

100

25

7

Intermédiaire

300

100

7

Difficile

500

300

7

3. Catégories autorisées

Web

Cryptographie

OSINT

Forensic

Programmation

Pwn / Reverse

Misc

4. Workflow de Contribution (Git)

Pour proposer un challenge, suivez ces étapes :

Récupérer le Template :
Clonez le dépôt et placez-vous sur la branche template pour voir la structure.

git clone [https://github.com/votre-org/votre-repo.git](https://github.com/votre-org/votre-repo.git)
cd votre-repo
git checkout template


Créer votre Branche :
Créez une branche avec le nom de votre challenge.

git checkout -b chall/nom-de-votre-challenge


Développer et Push :
Une fois votre dossier prêt, ajoutez vos fichiers et poussez votre branche.

git add .
git commit -m "Ajout du challenge [Nom]"
git push origin chall/nom-de-votre-challenge


Pull Request :
Allez sur GitHub et ouvrez une "Pull Request" vers la branche main. L'équipe technique d'Orion passera en revue votre code avant validation.

Note importante : Assurez-vous que votre Dockerfile expose un port valide et que le flag dans challenge.yml correspond exactement à celui du challenge.Hack The Shields - Guide des ContributeursBienvenue dans le dépôt public des challenges d'Orion Industries. Ce guide explique comment structurer vos créations pour qu'elles soient automatiquement intégrées à notre infrastructure.1. Structure d'un ChallengeChaque challenge doit être isolé dans son propre dossier, nommé de manière concise (ex: web-portal-bypass). L'arborescence dépend du type de challenge :Challenge Standard (Fichiers uniquement : OSINT, Forensic, Crypto)nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore et Write-up (interne)
└── files/           # Fichiers à donner aux joueurs
    └── preuve.png
Challenge Conteneurisé (Web, Pwn, Programmation)nom-du-challenge/
├── challenge.yml    # Configuration CTFd
├── contexte.txt     # Lore et Write-up
├── Dockerfile       # Fichier de construction (Obligatoire)
└── src/             # Code source de l'application
2. Barème des PointsNous utilisons un système de "Dynamic Scoring" (Linear). Voici les valeurs à respecter impérativement dans votre challenge.yml :NiveauInitialMinimumDecayFacile100257Intermédiaire3001007Difficile50030073. Catégories autoriséesWebCryptographieOSINTForensicProgrammationPwn / ReverseMisc4. Workflow de Contribution (Git)Pour proposer un challenge, suivez ces étapes :Récupérer le Template :Clonez le dépôt et placez-vous sur la branche template pour voir la structure.git clone [https://github.com/votre-org/votre-repo.git](https://github.com/votre-org/votre-repo.git)
cd votre-repo
git checkout template
Créer votre Branche :Créez une branche avec le nom de votre challenge.git checkout -b chall/nom-de-votre-challenge
Développer et Push :Une fois votre dossier prêt, ajoutez vos fichiers et poussez votre branche.git add .
git commit -m "Ajout du challenge [Nom]"
git push origin chall/nom-de-votre-challenge
Pull Request :Allez sur GitHub et ouvrez une "Pull Request" vers la branche main. L'équipe technique d'Orion passera en revue votre code avant validation.Note importante : Assurez-vous que votre Dockerfile expose un port valide et que le flag dans challenge.yml correspond exactement à celui du challenge.
