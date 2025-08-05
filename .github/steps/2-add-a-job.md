## Étape 2 : Ajouter un job à votre fichier workflow

_Excellent travail ! :tada: Vous avez ajouté un fichier workflow !_

Voici ce que signifient les entrées dans le fichier `welcome.yml`, sur la branche `welcome-workflow` :

- `name: Post welcome comment` donne un nom à votre workflow. Ce nom apparaîtra dans l'onglet Actions de votre dépôt.
- `on: pull_request: types: [opened]` indique que votre workflow s'exécutera chaque fois que quelqu'un ouvre une pull request dans votre dépôt.
- `permissions` attribue au workflow les permissions pour opérer sur le dépôt
- `pull-requests: write` donne au workflow la permission d'écrire sur les pull requests. C'est nécessaire pour créer le commentaire de bienvenue.

Ensuite, nous devons spécifier les jobs à exécuter.

**Qu'est-ce qu'un _job_ ?** : Un job est un ensemble d'étapes dans un workflow qui s'exécutent sur le même runner (un runner est un serveur qui exécute vos workflows quand ils sont déclenchés). Les workflows ont des jobs, et les jobs ont des étapes. Les étapes sont exécutées dans l'ordre et sont dépendantes les unes des autres. Vous ajouterez des étapes à votre workflow plus tard dans le cours. Pour en savoir plus sur les jobs, voir "[Jobs](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#jobs)".

Dans l'activité suivante, vous ajouterez un job "build" à votre workflow. Vous spécifierez `ubuntu-latest` comme runner de job le plus rapide et le moins cher disponible. Si vous voulez en savoir plus sur pourquoi nous utiliserons ce runner, voir l'explication du code pour la ligne `runs-on: ubuntu-latest` dans l'article "[Understanding the workflow file](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions#understanding-the-workflow-file)".

### :keyboard: Activité : Ajouter un job à votre fichier workflow

1. Dans un onglet de navigateur séparé, assurez-vous d'être sur la branche `welcome-workflow` et ouvrez votre fichier `.github/workflows/welcome.yml`.
1. Modifiez le fichier et mettez à jour son contenu vers :

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
   ```

1. Cliquez sur **Commit changes** en haut à droite de l'éditeur de workflow.
1. Tapez un message de commit et validez vos changements directement sur la branche `welcome-workflow`.
1. Attendez environ 20 secondes, puis actualisez cette page (celle que vous suivez pour les instructions). Un autre workflow s'exécutera et remplacera le contenu de ce fichier README par les instructions de l'étape suivante.
