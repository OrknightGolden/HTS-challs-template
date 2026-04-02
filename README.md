Hack The Shields - Guide des Contributeurs

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
