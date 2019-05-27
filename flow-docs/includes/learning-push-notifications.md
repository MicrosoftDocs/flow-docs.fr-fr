---
ms.openlocfilehash: d45bf5974c24a8258f3f4e51e1e4c89b9c74fba7
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64460338"
---
Pour ce flux, vous allez créer une liste **SharePoint** dans laquelle l’équipe Marketing de **Contoso Flooring** stocke ses **publications Twitter** ainsi que leurs dates. À partir de là, vous allez générer un flux qui tweete automatiquement le contenu à la place de l’équipe. 

## <a name="connect-microsoft-flow-services"></a>Connecter les services Microsoft Flow
Dans le cadre de cette rubrique, vous allez utiliser les services **SharePoint** et **Twitter**. Si vous utilisez un service pour la première fois, vous devez commencer par vous y connecter. 

1. Dans Microsoft Flow, sélectionnez l’**icône d’engrenage**, puis **Connexions**,
   
    ![Obtenir la connexion](./media/learning-push-notifications/2-get-connection.png) 
2. Sélectionnez **+ Créer une connexion**.
   
    ![Créer la connexion](./media/learning-push-notifications/3-create-connection.png) 
3. Faites défiler la liste, recherchez Twitter, puis sélectionnez **+**.
   
    ![Cliquez sur le signe plus](./media/learning-push-notifications/4-click-plus.png)
4. Pour autoriser un compte Twitter, entrez votre nom d’utilisateur ou adresse e-mail et votre mot de passe, puis sélectionnez **Autoriser une application**.
   
    ![Créer un ID et un mot de passe](./media/learning-push-notifications/5-create-id-pswd.png)
5. Pour vérifier vos connexions, sélectionnez l’**icône d’engrenage**, puis **Connexions**.
   
    ![Mes connexions](./media/learning-push-notifications/6-my-connections.png)
   
    Vous devez voir votre nouvelle connexion Twitter ainsi que les autres connexions que vous avez créées. 
   
    ![Connexion Twitter](./media/learning-push-notifications/7-twitter-connection.png)

## <a name="build-a-sharepoint-list"></a>Créer une liste SharePoint List
La première chose à faire est de créer une liste SharePoint Online pour Contoso Flooring. 

1. Dans SharePoint Online, sélectionnez **Nouveau**, puis **Liste**.
   
    ![Créer une liste](./media/learning-push-notifications/1-new-list.png)
2. Nommez la liste **TweetsContoso**. 
3. Désactivez la case à cocher **Afficher dans la navigation dans les sites**, puis sélectionnez **Créer**.
   
    ![Créer une liste](./media/learning-push-notifications/2-name-create-list.png)
   
    Lorsque vous sélectionnez **Créer**, SharePoint vous dirige vers votre nouvelle liste.
4. Par défaut, la liste comprend une seule colonne, **Titre**. Ajoutez une colonne et nommez-la **Contenus de tweets**. Le contenu de vos tweets se retrouvera ici. 
   
   1. Sélectionnez le signe plus, puis choisissez **Autres...**
      
       ![Créer une liste](./media/learning-push-notifications/3-add-more-column-types.png)
   2. Sélectionnez **Plusieurs lignes de texte**, puis **OK**.
      
       ![Créer une liste](./media/learning-push-notifications/4-add-column.png)
5. Ajoutez une colonne pour les date et heure de tweet, puis nommez-la **Date de tweet**.
   
   1. Comme pour **Contenus de tweets** ci-dessus, sélectionnez le signe plus, puis **Autres...**
      
       ![Colonne de date et heure](./media/learning-push-notifications/5-date-time-col.png)
   2. Faites défiler jusqu’à **Format date et heure**. Sélectionnez **Date et heure** de façon à ce que les deux valeurs soient incluses.
      
       ![Date et heure](./media/learning-push-notifications/6-date-time-must-do.png)
   3. Sélectionnez **OK**. Vous voyez la liste **TweetsContoso** sur votre site SharePoint, et pouvez y ajouter des éléments.

## <a name="build-the-flow"></a>Générer le flux
Votre liste étant établie, vous pouvez générer le flux.

### <a name="choose-a-trigger"></a>Choisir un déclencheur
1. Dans Microsoft Flow, accédez à **Mes flux**, puis sélectionnez **Créer entièrement**.
   
    ![Créer entièrement](./media/learning-push-notifications/8-create-from-blank.png)
2. Sélectionnez **Lors de la création d’un élément**.
   
    ![Ajouter un déclencheur](./media/learning-push-notifications/9-add-trigger.png)
   
    Nous voulons que le déclencheur se déclenche lors de l’ajout d’une ligne avec un contenu de tweet.
3. Sélectionnez votre site SharePoint, puis la liste que vous avez établie précédemment, **TweetsContoso**.
   
    ![Élément créé](./media/learning-push-notifications/11-set-trigger.png)

Voilà pour le déclencheur.

### <a name="add-an-action-to-delay-posting"></a>Ajouter une action pour différer la publication
1. Sélectionnez **+ Nouvelle étape**, puis **Ajouter une action**. 
   
    ![Ajouter une étape et une action](./media/learning-push-notifications/12-add-step-and-action.png)
2. Dans le service **Planification**, sélectionnez **Différer jusqu’à**. 
   
    ![Différer jusqu’à](./media/learning-push-notifications/13-delay-until-schedule.png)  
3. Définissez la valeur de délai.
   
   1. Cliquez ou appuyez dans le champ **Horodatage**. 
   2. Lorsque la zone de contenu dynamique s’ouvre, faites défiler vers le bas, et vous voyez les trois colonnes de la liste SharePoint : **Titre**, **Date de Tweet**, et **contenu du Tweet**.
   3. Sélectionnez **Date de tweet**. 
      
       ![Horodatage Différer jusqu’à](./media/learning-push-notifications/14-delay-until-timestamp.png)
      
       Désormais, quand quelqu’un ajoute un élément à votre liste SharePoint, cela a pour effet de différer toute action jusqu’à la date et l’heure définies dans la colonne **Date de tweet**.
      
       ![Horodatage dynamique](./media/learning-push-notifications/15-dynamic-timestamp.png)

### <a name="add-an-action-to-post-a-tweet"></a>Ajouter une action pour publier un tweet
Vous allez maintenant ajouter une action au flux à exécuter aux date et heure spécifiées dans la colonne **Date de tweet**.

1. Sélectionnez **+ Nouvelle étape**, **Ajouter une action**, puis recherchez **Twitter**.
   
    ![Ajouter un tweet](./media/learning-push-notifications/16-add-tweet.png) 
2. Choisissez l’action, **Twitter - Publier un tweet**.
   
    ![Publier un tweet](./media/learning-push-notifications/17-post-tweet.png) 
3. Cliquez ou appuyez dans le champ **Texte du tweet**, puis, dans la zone de contenu dynamique, sélectionnez **Contenus de tweets**. Voici la séquence que vous avez créée. 
   
    ![Contenu de Date de tweet](./media/learning-push-notifications/18-tweet-date-content.png)
4. Sélectionnez **Créer un flux...**.
   
    ![Créer un flux](./media/learning-push-notifications/19-tiny-create.png) 
5. Sélectionnez **Terminé**.
   
    ![Cliquez sur Terminé](./media/learning-push-notifications/19-click-done.png)
   
    Désormais, le flux est créé.
   
    ![Flux est créé](./media/learning-push-notifications/20-flow-is-done.png)
   
    Lors de la création d’un élément dans votre liste SharePoint, le flux diffère la publication jusqu’à la date prédéfinie. À cette date, le flux publie sur Twitter le texte figurant dans la colonne **Contenu du tweet** de votre liste.

## <a name="next-lesson"></a>Leçon suivante
La leçon suivante explique comment **exécuter des flux selon un calendrier** en utilisant un déclencheur nommé **périodicité**.

