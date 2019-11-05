---
title: Ajouter une option avancée et plusieurs actions | Microsoft Docs
description: Développez un Flow pour inclure une option avancée, telle que la définition de la priorité pour le courrier électronique et l’ajout d’une autre action pour le même événement.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/20/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 668e69b1c8f1781cf5720443af8e48409f43d322
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548614"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Ajouter plusieurs actions et options avancées à un Workflow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Personnalisez un Flow en ajoutant une ou plusieurs options avancées et plusieurs actions pour le même déclencheur. Par exemple, ajoutez une option avancée qui envoie un message électronique en tant que priorité haute. En plus d’envoyer un message électronique lorsqu’un élément est ajouté à une liste SharePoint, créez un fichier dans Dropbox contenant les mêmes informations.

## <a name="prerequisites"></a>Conditions préalables
* [Créer un Flow](get-started-logic-flow.md)

## <a name="add-another-action"></a>Ajouter une autre action
Dans cette procédure, vous allez ajouter une action au milieu du fluide. Cette action permet d’enregistrer un fichier dans Dropbox, en l’archivant dans la liste.

1. Dans [Flow.Microsoft.com](https://flow.microsoft.com), sélectionnez **mes flux** dans la barre de navigation supérieure.
2. Dans la liste des flux, sélectionnez le flux que vous souhaitez modifier.
3. Sélectionnez **nouvelle étape**, puis **Ajouter une action**.
   
    ![Ajout réduit](./media/multi-step-logic-flow/add-action.png)
4. Dans la liste des actions possibles, recherchez **créer un fichier**, puis sélectionnez **Dropbox-créer un fichier**.
   
    ![Recherche créer un fichier](./media/multi-step-logic-flow/create-file-search.png)
5. Si vous y êtes invité, fournissez vos informations d’identification Dropbox.
6. Sélectionnez l’icône de dossier sur le côté droit de la zone **chemin d’accès au dossier** .
7. Recherchez et sélectionnez le dossier dans lequel vous souhaitez placer le nouveau fichier.
   
    ![Recherche créer un fichier](./media/multi-step-logic-flow/create-file-folder.png)
8. Entrez le nom du nouveau fichier dans la zone **nom de fichier** . Veillez à ajouter une extension, telle que « . txt », au nom de fichier. Ici, nous allons utiliser **TweetId** dans le nom du fichier pour garantir l’unicité des fichiers. Vous devrez peut-être sélectionner **voir plus** pour trouver le jeton **TweetId** .
9. Ajoutez le texte que vous souhaitez que le fichier contienne en tapant dans la zone **contenu du fichier** . Vous pouvez également ajouter des jetons dans la zone **contenu du fichier** .
   
    ![nom de fichier et contenu](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Si vous attribuez au fichier un nom qui correspond au nom d’un fichier existant (dans le dossier sélectionné), le fichier existant sera remplacé.
   > 
   > 
10. Sélectionnez **mettre à jour le Flow**, situé dans le menu en haut de l’écran.
11. Envoyez un tweet qui contient le mot clé que vous avez spécifié.
    
     Au bout d’une minute, un fichier est créé dans votre compte Dropbox.

## <a name="reorder-or-delete-an-action"></a>Réorganiser ou supprimer une action
* Pour recevoir un courrier électronique une fois le fichier créé dans Dropbox, déplacez l’action Dropbox en faisant glisser sa barre de titre au-dessus de l’action de messagerie. Relâchez l’action Dropbox sur la flèche située entre le déclencheur (**lorsqu’un nouveau Tweet est publié**) et l’action de messagerie. (Le curseur indique si l’action est positionnée correctement.)
  
  > [!NOTE]
  > Vous ne pouvez pas déplacer une étape avant une autre si vous utilisez des sorties de cette étape.
  > 
  > 
  
    ![Supprimer le menu](./media/multi-step-logic-flow/draggingaction.png)
* Pour supprimer une action, sélectionnez les points de suspension (...) près du bord droit de la barre de titre de l’action que vous souhaitez supprimer, sélectionnez **supprimer**, puis sélectionnez **OK**.
  
    ![Supprimer le menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Remarque :** Vous ne pouvez pas supprimer une action si vous utilisez des sorties à partir de celle-ci partout dans le Workflow. Tout d’abord, supprimez ces sorties des champs, puis vous pouvez supprimer l’action.


## <a name="copy-and-paste-actions"></a>Actions copier et coller

Si vous souhaitez dupliquer des actions lors de la conception d’un fluide, vous pouvez les copier et les coller. Par exemple, si vous générez une condition et souhaitez que des actions similaires se trouvent dans le **cas Oui** et dans le **cas** contraire, au lieu de créer à partir de zéro des actions, vous pouvez créer la première action d’un côté, puis la copier de l’autre côté.


### <a name="to-copy-an-action"></a>Pour copier une action
1. Sélectionnez le menu Action (... en haut à droite de l’action).
1. Sélectionnez **copier dans le presse-papiers**. 
1. Sélectionnez la **nouvelle étape** où vous souhaitez que votre action se passe. 

     Notez l’onglet **mon presse-papiers** qui vous permet de choisir parmi toutes les actions que vous avez copiées.
1. Sélectionnez l’élément que vous souhaitez coller.

## <a name="add-advanced-options"></a>Ajouter des options avancées
Commencez avec un Flow qui a une action **Envoyer un message électronique** .

1. Sélectionnez **afficher les options avancées**, situé en bas de la carte **Envoyer un e-mail** .
   
     Vous verrez ensuite les options avancées pour l’envoi d’un e-mail.
   
    ![Déclencheurs SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Sélectionnez **élevé** dans la liste **importance** , puis sélectionnez **Masquer les options avancées** pour masquer les options avancées.
3. Sélectionnez **mettre à jour le Flow**, situé dans le menu en haut de l’écran.
   
     Cette étape enregistre vos modifications.

