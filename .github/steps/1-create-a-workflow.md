## Étape 1 : Créer un fichier workflow

_Bienvenue dans "Hello GitHub Actions" ! :wave:_





**Qu'est-ce que _GitHub Actions_ ?** : 


GitHub Actions, c’est comme un robot qui bosse pour toi pendant que tu chill 
Tu peux lui dire de faire plein de trucs tout seul, genre :

tester ton code 

publier ton site direct quand tu pushes 

vérifier les bugs ou les commentaires 

Tout est écrit dans des fichiers que tu mets dans ton repo, donc c’est facile à partager et à réutiliser avec ton équipe.

🧠 Si tu veux creuser un peu plus, check ces ressources 

- La page des fonctionnalités GitHub Actions, voir [GitHub Actions](https://github.com/features/actions).
- La documentation utilisateur "GitHub Actions", voir [GitHub Actions](https://docs.github.com/actions).

**Qu'est-ce qu'un _workflow_ ?** : Un workflow est un processus automatisé configurable qui exécutera un ou plusieurs jobs. Les workflows sont définis dans des fichiers spéciaux dans le répertoire `.github/workflows` et ils s'exécutent en fonction de l'événement que vous choisissez. Pour cet exercice, nous utiliserons un événement `pull_request`.


😵‍💫 – "C’est trop… je comprends rien"


Déjà tu comprends rien ?
T’inquiète, on va faire simple.

En gros, t’as des étapes que tu écris dans un dossier appelé workflow.
Ces étapes (qu’on appelle aussi des "flows") se déclenchent automatiquement quand il se passe un truc.

Genre toi qui allumes la lumière 💡
Ou mieux : toi qui utilises ton cerveau pour la première fois depuis 3 ans 🧠💥

Nous, ce qu’on va utiliser ici, c’est l’événement pull_request.
(traduction : quand quelqu’un propose une modif dans le code)


- Pour en savoir plus sur les workflows, jobs et événements, voir "[Understanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)".
- Si vous voulez en savoir plus sur l'événement `pull_request` avant de l'utiliser, voir "[pull_request](https://docs.github.com/en/developers/webhooks-and-events/webhooks/webhook-events-and-payloads#pull_request)".


vouvoiement activé.

Pour vous aider à commencer, nous avons exécuté un workflow Actions dans votre nouveau dépôt qui, entre autres choses, a créé une branche pour que vous puissiez travailler, appelée `welcome-workflow`.

### :keyboard: Activité : Créer un fichier workflow

1. Ouvrez un nouvel onglet de navigateur et naviguez vers ce même dépôt. Ensuite, travaillez sur les étapes dans votre deuxième onglet pendant que vous lisez les instructions dans cet onglet.
1. Créez une pull request. Celle-ci contiendra tous les changements que vous apporterez tout au long de cette partie du cours.

   Cliquez sur l'onglet **Pull Requests**, cliquez sur **New pull request**, définissez `base: main` et `compare:welcome-workflow`, cliquez sur **Create pull request**, puis cliquez à nouveau sur **Create pull request**.

1. Naviguez vers l'onglet **Code**.
1. Dans le menu déroulant de la branche **main**, cliquez sur la branche **welcome-workflow**.
1. Naviguez vers le dossier `.github/workflows/`, puis sélectionnez **Add file** et cliquez sur **Create new file**.
1. Dans le champ **Name your file**, entrez `welcome.yml`.
1. Ajoutez le contenu suivant au fichier `welcome.yml` :

   ```yaml copy
   name: Post welcome comment
   on:
     pull_request:
       types: [opened]
   permissions:
     pull-requests: write
   ```

1. Pour valider vos changements, cliquez sur **Commit changes**.
1. Tapez un message de commit, sélectionnez **Commit directly to the welcome-workflow branch** et cliquez sur **Commit changes**.
1. Attendez environ 20 secondes, puis actualisez cette page (celle que vous suivez pour les instructions). Un workflow Actions séparé dans le dépôt (pas le workflow que vous avez créé) s'exécutera et remplacera automatiquement le contenu de ce fichier README par les instructions de l'étape suivante.
