## Étape 5 : Déclencher le workflow

_Vous avez maintenant ajouté un workflow entièrement fonctionnel à votre dépôt ! :smile:_

Le script shell dans le workflow s'exécutera chaque fois qu'une nouvelle pull request est ouverte.

**Voir votre _action_ en action** : Le statut de chaque exécution de workflow qui est déclenchée est affiché dans la pull request avant qu'elle soit mergée : cherchez **All checks have passed** quand vous essayez les étapes ci-dessous. Vous pouvez aussi voir une liste de tous les workflows qui sont en cours d'exécution, ou qui ont fini de s'exécuter, dans l'onglet **Actions** de votre dépôt. De là, vous pouvez cliquer sur chaque exécution de workflow pour voir plus de détails et accéder aux fichiers de log.

![Une capture d'écran de l'onglet Actions montrant une liste d'exécutions de workflow.](https://user-images.githubusercontent.com/16547949/62388049-4e64e600-b52a-11e9-8bf5-db0c5452360f.png)

### :keyboard: Activité : Déclencher le workflow

1. Créez une nouvelle branche nommée `test-workflow`.
1. Apportez un changement, comme ajouter un emoji à votre fichier README.md, et validez le changement directement sur votre nouvelle branche.
1. Dans l'onglet **Pull requests**, créez une pull request qui mergera `test-workflow` dans `main`.
1. Observez le workflow qui s'exécute dans la section des vérifications de la pull request.
1. Remarquez le commentaire que le workflow ajoute à la pull request.
1. Attendez environ 20 secondes, puis actualisez cette page (celle que vous suivez pour les instructions). Un autre workflow s'exécutera et remplacera le contenu de ce fichier README par les instructions de l'étape suivante.
