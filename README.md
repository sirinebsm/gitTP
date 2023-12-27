1. Comprendre les bases de GitHub :

    Repository (dépôt) : C'est l'endroit où vos fichiers sont stockés. Créez-en un pour votre TP.
    Commit : C'est une sauvegarde de vos modifications. Chaque commit a un message expliquant les changements effectués.
    Branches : Des versions alternatives de votre projet. Utilisez-les pour travailler sur des fonctionnalités spécifiques sans affecter la branche principale.

2. Créer un compte GitHub :

    Rendez-vous sur GitHub et créez un compte si vous n'en avez pas.
    Connectez-vous à votre compte.

   
3.Préparation de l'environnement Git:

1. Création de clé SSH
     a. Utilisez la commande suivante pour générer votre clé SSH :
     ssh-keygen -t rsa -b 4096 -C votreadresse@email.com
   
     b. Copiez votre clé publique SSH en utilisant la commande suivante :
     cat ~/.ssh/id_rsa.pub
     c. Connectez-vous à votre compte sur le dépôt distant (par exemple, GitHub) et
     ajoutez votre clé publique SSH dans les paramètres de votre compte.
     

3. Configuration de Git

    Configurez votre nom et votre adresse e-mail pour que vos commits soient
    correctement identifiés :
    git config --global user.name "Votre Nom"
    git config --global user.email votre@email.com

3.Connexion SSH aux dépôts distants
     Pour tester votre connexion SSH, exécutez la commande suivante. Assurez-vous de
     remplacer `git@github.com` par l'adresse du serveur distant où vous hébergerez vos
     dépôts :
      ssh -T git@github.com


3. Créer un nouveau dépôt (repository) :

    Cliquez sur le bouton "New" (Nouveau) pour créer un nouveau repository.
    Donnez-lui un nom et une description, puis choisissez les options appropriées.
    Initialisez avec un README si vous voulez ajouter des informations sur votre TP.

4. Cloner votre dépôt :

   Utilisez la commande git clone <lien-du-dépôt> dans votre terminal pour copier votre dépôt en local.
   
   Vous devriez maintenant avoir cloné avec succès votre projet sur votre machine locale.
   Accèdez avec:
   cd mon-projet

5. Ajouter, modifier et valider vos fichiers :

    Créez ou modifiez des fichiers dans votre dépôt local.
    Utilisez git status pour voir les changements.
    Utilisez git add <fichier> pour ajouter des fichiers à la zone de staging.
    Utilisez git commit -m "Message de votre commit" pour valider les changements.*
   
    Exemple de mon projet <gitTP>:
   1. Travailler avec les fichiers
  Créez un fichier appelé `index.html` dans votre répertoire de projet et ajoutez-y du
  contenu :
  touch index.html
  echo "Contenu de votre fichier" > index.html
  Utilisez les commandes suivantes pour ajouter le fichier à l'index (staging) et valider
  votre premier commit :
  git add index.html
  git commit -m "Premier commit : ajout de index.html"

   2. Historique des commits
  Visualisez l'historique des commits de votre projet avec la commande suivante :
  git log
  Pour afficher les différences entre deux commits, utilisez la commande suivante :
  git diff commit_id_1 commit_id_2

6. Pousser vos modifications sur GitHub :

    Utilisez git push origin <nom-de-la-branche> pour envoyer vos commits vers GitHub.

7. Travailler avec des branches :

    Créez une nouvelle branche avec git checkout -b <nom-de-la-branche>.
    Faites des modifications spécifiques sur cette branche.
    Fusionnez cette branche avec la principale lorsque vous avez terminé.

8. Collaboration :

    Ajoutez des collaborateurs à votre projet en utilisant les paramètres du dépôt.
    Pour fusionner le travail d'autres personnes dans votre projet, utilisez les pull requests.
   
   Exemple de mon projet <gitTP>:
   1.Créez une nouvelle branche pour travailler sur une fonctionnalité spécifique de votre
   projet :
   git branch ma-fonctionnalite
   git checkout ma-fonctionnalite

   2. Effectuez des modifications dans votre dépôt local, ajoutez-les à l'index, faites un
   commit, puis poussez les modifications vers le dépôt distant :
   git add .
   git commit -m "Modification de ma-fonctionnalite"
   git push origin ma-fonctionnalite
   
  

9. Gérer les conflits :

    Parfois, les modifications de différentes branches entrent en conflit. Résolvez-les en modifiant manuellement les fichiers.
    Exemple de mon projet <gitTP>:
    Simulez un conflit en modifiant la même ligne dans deux branches différentes, puis
    fusionnez les branches et résolvez le conflit :
    git checkout ma-fonctionnalite
    git commit -am "Modification dans ma-fonctionnalite"
    git checkout master
    git commit -am "Modification dans master"
    git merge ma-fonctionnalite
    git add .
    git commit -m "Résolution du conflit"

10. Explorer les fonctionnalités avancées :

    Découvrez les actions GitHub, les problèmes, les wikis, les projets, etc., pour améliorer la gestion de votre projet.
    
11.Utilisation de Gitflow

    1. Initialisation de Gitflow :
    git flow init
    2. Création d'une nouvelle fonctionnalité :
    git flow feature start ma-fonctionnalite
    3. Création d'une nouvelle version :
    git flow release start ma-version
    4. Lorsque vous avez terminé, fusionnez la branche de fonctionnalité dans la branche de
    développement en utilisant GitFlow :
    git flow feature finish nouvelle-fonctionnalite
    5. Création d'un correctif :
    git flow hotfix start mon-correctif
