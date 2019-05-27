---
title: Ajouter une option avancée et plusieurs actions | Microsoft Docs
description: Développez un flux pour inclure une option avancée (telle que la définition d’un e-mail sur une priorité élevée) et ajoutez une autre action pour le même événement.
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
ms.openlocfilehash: 9dd2aed8b8cdb1f0a8e673c5466291f60baaf41d
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64466519"
---
# <a name="add-multiple-actions-and-advanced-options-to-a-flow"></a>Ajouter plusieurs actions et options avancées à un flux
Personnalisez un flux en ajoutant une ou plusieurs options avancées et plusieurs actions pour le même déclencheur. Par exemple, ajoutez une option avancée qui envoie un e-mail avec une priorité élevée. Outre l’envoi de messages lorsqu’un élément est ajouté à une liste SharePoint, créez un fichier dans le dossier Dropbox qui contient les mêmes informations.

## <a name="prerequisites"></a>Prérequis
* [Créer un flux](get-started-logic-flow.md)

## <a name="add-another-action"></a>Ajouter une autre action
Dans cette procédure, vous allez ajouter une action au milieu du flux. Cette action va enregistrer un fichier dans votre dossier Dropbox en l’archivant dans la liste.

1. Dans [flow.microsoft.com](https://flow.microsoft.com), sélectionnez **Mes flux** dans la barre de navigation supérieure.
2. Dans la liste des flux, sélectionnez le flux que vous voulez modifier.
3. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**.
   
    ![Option Ajouter réduite](./media/multi-step-logic-flow/add-action.png)
4. Dans la liste des actions possibles, recherchez **Créer un fichier**, puis sélectionnez **Dropbox - Créer un fichier**.
   
    ![rechercher créer fichier](./media/multi-step-logic-flow/create-file-search.png)
5. Si vous y êtes invité, fournissez vos informations d’identification Dropbox.
6. Sélectionnez l’icône de dossier située à droite de la zone **Chemin d’accès du dossier**.
7. Recherchez, puis sélectionnez le dossier dans lequel vous souhaitez placer le nouveau fichier.
   
    ![rechercher créer fichier](./media/multi-step-logic-flow/create-file-folder.png)
8. Entrez le nom du nouveau fichier dans la zone **Nom du fichier**. Veillez à ajouter une extension, par exemple « .txt », au nom du fichier. Utilisons dans ce cas l’extension **TweetId** dans le nom du fichier pour garantir que les fichiers soient uniques. Vous devrez peut-être sélectionner **Voir plus** pour trouver le jeton **TweetId**.
9. Ajoutez le texte que vous voulez insérer dans le fichier en le tapant dans la zone **Contenu du fichier**. Vous pouvez également ajouter des jetons dans la zone **Contenu du fichier**.
   
    ![nom de fichier et contenu](./media/multi-step-logic-flow/create-file-name-and-contents.png)
   
   > [!IMPORTANT]
   > Si vous attribuez au fichier un nom qui correspond au nom d’un fichier existant (dans le dossier sélectionné), le fichier existant est remplacé.
   > 
   > 
10. Sélectionnez **Mettre à jour le flux**, qui se trouve dans le menu en haut de l’écran.
11. Envoyez un tweet contenant le mot clé que vous avez spécifié.
    
     En moins d’une minute, un fichier est créé dans votre compte Dropbox.

## <a name="reorder-or-delete-an-action"></a>Réorganiser ou supprimer une action
* Pour recevoir un e-mail une fois que le fichier est créé dans Dropbox, déplacez l’action Dropbox en faisant glisser sa barre de titre au-dessus de l’action de messagerie. Lâchez l’action Dropbox sur la flèche située entre le déclencheur (**Lorsqu’un nouveau tweet est publié**) et l’action de messagerie. (Le curseur indique si l’action est positionnée correctement.)
  
  > [!NOTE]
  > Vous ne pouvez pas déplacer une étape avant une autre si vous utilisez des sorties de cette étape.
  > 
  > 
  
    ![Supprimer le menu](./media/multi-step-logic-flow/draggingaction.png)
* Pour supprimer une action, sélectionnez les points de suspension (...) près du bord droit de la barre de titre de l’action que vous souhaitez supprimer, sélectionnez **Supprimer**, puis **OK**.
  
    ![Supprimer le menu](./media/multi-step-logic-flow/deletemenu.png)
  
     **Remarque :** Vous ne pouvez pas supprimer une action si vous utilisez des sorties à partir de celui-ci n’importe où dans le flux. En premier lieu, supprimez ces sorties des champs, puis supprimez l’action.

## <a name="add-advanced-options"></a>Ajouter des options avancées
Commencez par un flux disposant d’une action **Envoyer un e-mail**.

1. Sélectionnez **Afficher les options avancées**, qui se trouve en bas de la carte **Envoyer un e-mail**.
   
     Les options avancées s’affichent alors pour l’envoi d’un e-mail.
   
    ![Déclencheurs SharePoint](./media/multi-step-logic-flow/advanced.png)
2. Sélectionnez **Haute** dans la liste **Importance**, puis sélectionnez **Masquer les options avancées** pour masquer les options avancées.
3. Sélectionnez **Mettre à jour le flux**, qui se trouve dans le menu en haut de l’écran.
   
     Cette étape enregistre vos modifications.

