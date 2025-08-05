## Étape 3 : Ajouter une étape à votre fichier workflow

_Excellent travail en ajoutant un job à votre workflow ! :dancer:_

Les workflows ont des jobs, et les jobs ont des étapes. Maintenant nous allons ajouter une étape à votre workflow.

**Que sont les _étapes_ ?** : Les étapes d'Actions s'exécutent - dans l'ordre où elles sont spécifiées, de haut en bas - quand un job de workflow est traité. Chaque étape doit réussir pour que l'étape suivante s'exécute.

Chaque étape consiste soit en un script shell qui est exécuté, soit en une référence à une action qui est exécutée. Quand nous parlons d'une action (avec un "a" minuscule) dans ce contexte, nous entendons une unité de code réutilisable. Vous pouvez en savoir plus sur les actions dans "[Finding and customizing actions](https://docs.github.com/en/actions/learn-github-actions/finding-and-customizing-actions)", mais pour l'instant nous utiliserons un script shell dans notre étape de workflow.

Mettez à jour votre workflow pour qu'il poste un commentaire sur les nouvelles pull requests. Il le fera en utilisant un script [bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) et [GitHub CLI](https://cli.github.com/).

### :keyboard: Activité : Ajouter une étape à votre fichier workflow

1. Tout en travaillant sur la branche `welcome-workflow`, ouvrez votre fichier `welcome.yml`.
1. Mettez à jour le contenu du fichier vers :

   ```yaml copy
   name: Post welcome comment
   on:
     pull_request:
       types: [opened]
   permissions:
     pull-requests: write
   jobs:
     build:
       name: Post welcome comment
       runs-on: ubuntu-latest
       steps:
         - run: gh pr comment $PR_URL --body "Welcome to the repository!"
           env:
             GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
             PR_URL: ${{ github.event.pull_request.html_url }}
   ```

   **Note :** L'étape que vous avez ajoutée utilise GitHub CLI (`gh`) pour ajouter un commentaire quand une pull request est ouverte. Pour permettre à GitHub CLI de poster un commentaire, nous définissons la variable d'environnement `GITHUB_TOKEN` à la valeur du secret `GITHUB_TOKEN`, qui est un token d'accès d'installation, créé quand le workflow s'exécute. Pour plus d'informations, voir "[Automatic token authentication](https://docs.github.com/en/actions/security-guides/automatic-token-authentication)". Nous définissons la variable d'environnement `PR_URL` à l'URL de la pull request nouvellement créée, et nous l'utilisons dans la commande `gh`.
   
1. Cliquez sur **Commit changes** en haut à droite de l'éditeur de workflow.
1. Tapez votre message de commit et validez vos changements directement sur votre branche.
1. Attendez environ 20 secondes, puis actualisez cette page (celle que vous suivez pour les instructions). Un autre workflow s'exécutera et remplacera le contenu de ce fichier README par les instructions de l'étape suivante.
