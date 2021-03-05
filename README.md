# Commandes pratiques pour Git

Article sur les commandes Git: https://levelup.gitconnected.com/automate-repetitive-tasks-with-custom-git-commands-76a4b71d262f
## Installation

1. Checkout du repo dans un dossier sur l'ordinateur
2. Ajout du path vers le dossier dans le "PATH" des variables d'environnement

## Commandes existantes

`git auto-pr BRANCH "Titre"`

Cette commande crée une Pull request, la merge et supprime la branche originale automatiquement en une seule étape. 

**Paramètres**

1. BRANCH: Nom de la branche vers laquelle faire la Pull request, habituellement master/main ou develop.
2. "Titre": Titre de la Pull request pour Github

`git feature feature-abc`

Cette commande crée une nouvelle branche à partir de `develop`. Le checkout et le pull de `develop` sont faits automatiquement avant la création de la nouvelle branche.

**Paramètres**

1. feature-abc: Nom de la branche pour le feature. Idéalement, ce nom commence par `feature-`.
   
`git hotfix hotfix-abc`

Cette commande crée une nouvelle branche à partir de `main`. Le checkout et le pull de `main` sont faits automatiquement avant la création de la nouvelle branche.

**Paramètres**

1. hotfix-abc: Nom de la branche pour le hotfix. Idéalement, ce nom commence par `hotfix-`.

`git package 1`

Cette commande crée un zip nommé "update.zip" contenant les fichiers modifiés depuis le nombre de commits fourni en paramètre. Utile pour les mises en ligne manuelles par FTP.

**Paramètres**

1. 1: Nombre de commits à partir de HEAD à inclure dans le ZIP. _Si on met 3, les fichiers modifiés dans les 3 derniers commits seront dans le ZIP._

`git pr BRANCH "Titre"`

Cette commande crée une Pull request en une seule étape. Le push sera fait aussi s'il n'avait pas été fait manuellement.

**Paramètres**

1. BRANCH: Nom de la branche vers laquelle faire la Pull request, habituellement master/main ou develop.
2. "Titre": Titre de la Pull request pour Github

`git refresh`

Cette commande met à jour la branche courante avec un pull. La différence avec un simple pull, c'est qu'un stash des fichiers modifiés est créé avant le pull et remis après. Il est donc possible de récupérer la dernière version de Github sans perdre le travail commencé.

**Paramètres**

Aucun.

`git switch-to BRANCH`

Cette commande permet en une ligne de changer de branche et faire un pull pour avoir la dernière version. Un stash ds fichiers modifiés est aussi créé avant le pull et remis après. Il est donc possible de récupérer la dernière version de la nouvelle branche sur Github sans perdre le travail commencé.

**Paramètres**

1. BRANCH: Nom de la branche désirée


## Création d'une commande

1. Créer un fichier nommé comme ceci "git-"+"Nom de la commande". Par exemple, la commande git example aura un fichier git-example.
2. Ajouter les lignes de commande au fichier Bash.
3. Tester la nouvelle commande.
4. Ajouter la documentation dans la section Commandes existantes.