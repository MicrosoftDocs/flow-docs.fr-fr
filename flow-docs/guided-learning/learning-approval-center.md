---
title: "Créer une demande d’approbation | Microsoft Docs"
description: "Découvrez comment gérer l’approbation des documents et processus."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: 65yz8tqnWe0
courseduration: 4m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 265cab5029ca3166b5e12c42e2ec02730940d4f0
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="create-an-approval-request"></a>Créer une demande d’approbation
Dans une rubrique précédente, vous avez appris à alimenter de façon simple votre flux Twitter à l’aide d’une liste SharePoint. Cette rubrique explique comment créer un scénario plus adapté à l’entreprise en utilisant des approbations. Ainsi, toute personne ayant accès à la liste SharePoint peut tweeter, et l’équipe en charge des médias sociaux peut approuver ou rejeter les tweets. L’équipe conserve le contrôle du compte et du contenu envoyé aux clients. 

## <a name="create-an-approval-request-flow"></a>Créer un flux de demande d’approbation
1. Dans la page d’accueil de **Microsoft Flow**, sélectionnez **Approbations**, **Créer un flux d’approbation**, puis faites défiler vers le bas et sélectionnez le modèle **Postez des éléments de liste sur Twitter après approbation**. 
   
    ![Sélectionner un modèle](./media/learning-approval-center/create-approval.png)
2. Vérifiez les informations d’identification de votre compte pour **SharePoint**, **Approbations** et **Twitter**, puis sélectionnez **Continuer**. 
   
    ![Vérifiez les informations d’identification](./media/learning-approval-center/verify-credentials.png)

Par défaut, ce modèle démarre un processus d’approbation chaque fois qu’un élément est créé dans une liste donnée, puis, si l’élément est approuvé, publie un tweet sur Twitter. Dans le cadre de cette rubrique, vous allez modifier ce processus en ajoutant des étapes qui mettent à jour la liste SharePoint avec la réponse d’approbation, indiquent si l’approbation a été donnée, et ajoutent les commentaires que les approbateurs peut avoir ajoutés au tweet proposé. 

1. Dans la liste SharePoint **TweetsContoso** créée précédemment, ajoutez deux colonnes :
   
   1. Sélectionnez le signe « **+** », puis **Oui/Non**
   2. Entrez l’**ÉtatApprobation**, puis sélectionnez **Créer**
   3. Sélectionnez le signe «**+**», puis choisissez **Une seule ligne de texte**
   4. Entrez **CommentairesApprobateur**, puis sélectionnez **Enregistrer**
      
      ![Ajouter des colonnes](./media/learning-approval-center/new-columns.png)
2. De retour dans **Microsoft Flow**, dans l’action **Lorsqu’un élément est créé**, entrez les valeurs suivantes :
   
   * **Adresse du site** : URL SharePoint de votre équipe
   * **Nom de la liste** : TweetsContoso
     
     ![Site et liste](./media/learning-approval-center/site-address.png)
3. Dans l’action **Démarrer une approbation**, sélectionnez **Modifier** pour afficher tous les champs. 
   
    ![Modifier les champs](./media/learning-approval-center/edit-all-fields.png)
4. Dans **Titre**, entrez **Nouveau tweet pour**, puis sélectionnez **Titre** dans la liste de contenu dynamique. 
   
    ![Titre](./media/learning-approval-center/tweet-title.png)
5. Dans **Affectée à**, entrez et sélectionnez votre nom ou le nom d’un utilisateur de test. 
   
    ![Affectée à](./media/learning-approval-center/tweet-assigned-to.png)
6. Dans **Détails**, supprimez les éléments par défaut et ajoutez les éléments **ContenuTweet**, **DateTweet** et **Créé par NomAffichage** à partir de la liste de contenu dynamique, reliés par les mots **le** et **par**. 
   
    ![Détails](./media/learning-approval-center/tweet-details.png)
7. Dans **Lien vers l’élément**, copiez et collez l’URL de votre liste SharePoint, puis, dans **Description du lien vers l’élément**, entrez **Liste**. 
   
    ![Lien vers l’élément](./media/learning-approval-center/tweet-item-link.png)
8. Dans l’action **Condition**, pointez sur le champ **Si Oui**, sélectionnez le signe plus « **+** », puis choisissez **Ajouter une action**. 
   
    ![Ajouter une action](./media/learning-approval-center/add-an-action.png)
9. Recherchez **Mettre à jour l’élément**, sélectionnez le connecteur **SharePoint**, puis choisissez l’action **SharePoint – Mettre à jour l’élément**.
   
    ![Mettre à jour l’élément dans SharePoint](./media/learning-approval-center/update-item.png)
10. Dans **Adresse du site** et **Nom de la liste**, entrez de nouveau l’URL de votre site et la liste **TweetsContoso**, puis, dans **ID**, entrez un **ID**  de la liste de contenu dynamique. 
    
     ![Site, liste et ID](./media/learning-approval-center/address-list-id.png)
11. Sélectionnez le champ **Titre**, puis, dans la liste de contenu dynamique, recherchez **Titre**. Ajoutez l’élément **Titre** de l’action **Lorsqu’un élément est créé**. 
    
     ![Nouveau titre](./media/learning-approval-center/add-title.png)
12. Sélectionnez **ÉtatApprobation** et définissez la valeur sur **Oui**, puis choisissez **CommentairesApprobateur** et définissez la valeur de **Commentaires** à partir de la liste de contenu dynamique. 
    
     ![État et commentaires](./media/learning-approval-center/approver-status.png)
13. Au bas de la zone **Si Non, *ne rien faire***, sélectionnez **Ajouter une action**.
    
     ![Ajouter une action pour la condition Si Non](./media/learning-approval-center/add-a-no-action.png)
14. En procédant de la même manière que pour la configuration de la condition **Si Oui**, créez une action **SharePoint – Mettre à jour l’élément**, puis configurez les champs avec les mêmes valeurs, à l’exception du paramètre **ÉtatApprobation** que vous définissez sur **Non**. 
    
     ![État = non](./media/learning-approval-center/status-no.png)
15. Sélectionnez l’action **Publier un tweet**, choisissez **Modifier**, puis définissez la valeur de **Texte du tweet** sur **ContenuTweet** à partir de la liste de contenu dynamique.  En haut de la page, sélectionnez **Créer un flux** pour enregistrer votre travail. 
    
     ![Publier et enregistrer](./media/learning-approval-center/post-tweet.png)

Ceci n’est que lune des manières dont Microsoft Flow peut dynamiser la productivité de votre équipe. Votre équipe peut suggérer des idées, proposer des nouveautés pertinentes ou prodiguer des conseils concernant des produits. Quoi qu’il en soit, vous contrôlez toujours ce qui est tweeté aux clients.

Dans la rubrique suivante, nous allons voir ce qui se passe quand un approbateur reçoit une nouvelle demande concernant un tweet proposé. 

