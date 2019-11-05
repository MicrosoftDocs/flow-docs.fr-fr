---
title: Découvrez comment automatiser et exécuter des tâches répétitives avec des flux de bouton | Microsoft Docs
description: Présentation des flux de bouton.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/30/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 403c3d7cc116555ab26d5e4168587de5e5a6720f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547539"
---
# <a name="introducing-button-flows"></a>Présentation des flux de bouton
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-are-button-flows"></a>Que sont les flux de bouton ?
Il y a de nombreuses tâches répétitives que nous souhaitons que nous puissions exécuter en appuyant simplement sur un bouton. Par exemple, vous devrez peut-être envoyer rapidement par courrier électronique à votre équipe pour lui rappeler de rejoindre la synchronisation quotidienne de l’équipe, ou vous pouvez démarrer une nouvelle version de Visual Studio Online de votre base de code une fois que vous êtes informé qu’il n’y a plus d’archivages planifiés pour la journée. Les flux de bouton vous permettent d’accomplir ces tâches et de nombreuses autres tâches simplement en appuyant sur un bouton sur votre appareil mobile.

**Remarque** Vous pouvez créer des flux de bouton à partir de votre appareil mobile ou à partir du portail de flux.  
  image de vue d’ensemble ![](./media/introduction-to-button-flows/buttons-montage.png)  

## <a name="why-create-buttons"></a>Pourquoi créer des boutons ?
Créez des boutons pour pouvoir facilement exécuter des tâches répétitives, à tout moment, à l’aide de votre appareil mobile. L’exécution de boutons vous fait gagner du temps et, étant donné que les tâches qu’ils effectuent sont automatisées, il y aura moins d’erreurs que si vous les avez effectuées manuellement.  

## <a name="create-a-button"></a>Créer un bouton
### <a name="prerequisites"></a>Conditions préalables
* Accès au Flow. Votre administrateur peut vous fournir un accès.
* Un compte disposant des autorisations nécessaires pour utiliser les connecteurs pour créer votre bouton. Par exemple, vous aurez besoin d’un compte Dropbox pour créer un bouton qui accède à Dropbox.

### <a name="from-the-portal"></a>À partir du portail
Dans cette procédure pas à pas, nous allons créer un bouton qui démarre une build Visual Studio Online (VSO) et envoie des notifications pour vous avertir quand la génération démarre :  

1. Sélectionnez la liste déroulante **Afficher** et choisissez la catégorie de **bouton** . Cela permet de filtrer la liste des modèles à ceux qui peuvent être utilisés dans les flux de bouton.  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-1.png)   
2. Sélectionnez le modèle **déclencher une nouvelle build dans VSO dans** la liste des modèles.  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-2.png)  
3. Sélectionnez le bouton **utiliser ce modèle** dans la page **déclencher une nouvelle build dans VSO** .   
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-3.png)  
4. Si vous n’êtes pas connecté, vous êtes invité à le faire à ce stade :  
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/create-button-4.png)  
5. Une fois que vous êtes connecté à Flow, vous êtes invité à vous connecter aux connecteurs utilisés dans le modèle que vous avez sélectionné. Dans cet exemple, à l’étape 2 ci-dessus, nous avons sélectionné le modèle **déclencher une nouvelle build dans VSO** . nous devons donc nous connecter à VSO (et à tous les autres connecteurs que vous utilisez) si vous n’êtes pas déjà connecté :  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-pre-req-1.png)    
6. Sélectionnez le bouton **accepter** si vous acceptez d’autoriser le passage à accéder à votre compte VSO.  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-5.png)   
   **Remarque** Vous devez autoriser chaque connecteur de la même façon. Le concepteur doit apparaître comme ceci lorsque vous êtes prêt à passer à l’étape suivante. Sélectionnez le bouton **Continuer** pour vous déplacer :  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-6.png)   
7. Vous êtes maintenant prêt à configurer les propriétés de la build que vous souhaitez démarrer :    
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/create-button-7.png)  
8. Sélectionnez ou entrez le **nom du compte**, le **nom du projet**, l’ID de définition de **Build**, la **branche source** et, éventuellement, les **paramètres**, dans la carte **de la file d’attente d’une nouvelle build** :    
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-8.png)  
9. Ensuite, configurez les propriétés de la notification push sur la carte **Envoyer une notification push** . Par défaut, cette notification push est configurée pour envoyer un lien HTML vers une page Web qui affiche l’état de la build :  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-9.png)  
10. Sélectionnez le bouton **créer un Flow** pour enregistrer votre workflow : ![image de présentation](./media/introduction-to-button-flows/create-button-10.png)  
11. Ce message de réussite doit s’afficher dans quelques instants :  
    ![Image de vue d’ensemble](./media/introduction-to-button-flows/create-button-11.png)  

Félicitations, vous avez créé un Flow. Vous pouvez maintenant exécuter ce bouton à tout moment, n’importe où, à partir de l’onglet **boutons** de l’application Flow. Appuyez simplement sur le bouton et il s’exécutera ! L’application Microsoft Flow mobile est disponible pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

### <a name="from-your-mobile-device"></a>À partir de votre appareil mobile
**Remarque**: bien que cette procédure pas à pas affiche les écrans d’un appareil Android, les écrans et l’expérience sur un appareil iOS sont similaires.

Dans l’application Flow :

1. Sélectionnez l’onglet **Parcourir** et faites défiler jusqu’à la catégorie de **bouton** .  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-1.png)  
2. Sélectionnez le lien **Afficher tout** . Cela permet d’afficher tous les modèles de bouton prêts à l’emploi.     
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-2.png)  
3. Sélectionner le modèle **Envoyer un e-mail pour rappeler à votre équipe de rejoindre une réunion**    
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-3.png)  
4. Sélectionnez le lien **utiliser ce modèle** en bas de la page.    
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-4.png)  
5. Vous devez vous connecter à tous les services utilisés par ce modèle :    
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/create-button-from-mobile-5.png)  
6. Sélectionnez le lien **suivant** après vous être connecté à tous les services.      
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-6.png)  
7. Sélectionnez le lien **créer** . Vous pouvez également consulter le Flow et apporter les modifications nécessaires pour personnaliser l’e-mail, par exemple.        
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-7.png)  
8. Après quelques instants, le déroulement du bouton est créé. Sélectionnez **afficher mon Flow**:   
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-8.png)  
9. Afficher tous vos flux sous l’onglet **mes flux**  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-9.png)  

Félicitations, vous avez créé un Flow. Vous pouvez maintenant exécuter ce bouton à tout moment, n’importe où, à partir de l’onglet **boutons** de l’application Flow. Appuyez simplement sur le bouton et il s’exécutera ! L’application Flow est actuellement disponible sur les appareils mobiles Android et iOS.  

![Image de vue d’ensemble](./media/introduction-to-button-flows/create-button-from-mobile-10.png)  

## <a name="trigger-a-button-flow"></a>Déclencher un workflow de bouton
Maintenant que vous avez créé un workflow de bouton, il est temps de l’exécuter. Étant donné que vous pouvez uniquement exécuter des flux de bouton à partir de l’application de flux, assurez-vous d’avoir installé Flow sur votre appareil mobile Android ou iOS.  

1. À présent, lancez l’application de Flow, appuyez sur l’onglet **boutons** situé en bas de la page, puis appuyez sur le *bouton* qui représente le déroulement du bouton que vous souhaitez déclencher :  
   image de vue d’ensemble ![](./media/introduction-to-button-flows/trigger-button-1.png)   
2. Consultez la progression de l’exécution du workflow :  
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/trigger-button-2.png)   
3. Enfin, la page est mise à jour, ce qui indique que le déroulement du bouton est terminé :  
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/trigger-button-3.png)   

C’est tout ce qu’il faut faire pour exécuter un fluide. 

Vous devez maintenant recevoir la notification push, indiquant que le message électronique a été envoyé.  

## <a name="monitor-your-button-flow-runs"></a>Surveiller vos exécutions de workflow de bouton
Vous pouvez surveiller les flux de bouton à partir de l’onglet **activité** de l’application Flow :   
image de vue d’ensemble ![](./media/introduction-to-button-flows/create-button-from-mobile-13.png)  

**Remarque**: Appuyez sur n’importe quelle activité pour examiner les résultats de l’exécution et en savoir plus sur l’exécution.  

![Image de vue d’ensemble](./media/introduction-to-button-flows/activity-details-1.png)  

## <a name="manage-button-flows"></a>Gérer les flux de bouton
Vous avez le contrôle total de vos flux de bouton pour pouvoir activer/désactiver, modifier ou supprimer un bouton à tout moment, en tout lieu. À partir de l’application mobile ou du portail Flow, sélectionnez **mes flux** pour commencer à gérer vos flux.    

Sous l’onglet **mes flux** de l’application Flow :

1. Sélectionnez le Flow que vous souhaitez gérer :    
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/trigger-button-4.png)   
2. Vous pouvez appuyer sur l’une de ces options, en fonction de ce que vous souhaitez accomplir :    
   ![Image de vue d’ensemble](./media/introduction-to-button-flows/manage-flow-1.png)  
3. Appuyez sur **supprimer le Flow** pour supprimer un fluide.  

**Remarque** L’historique des exécutions est supprimé lorsque vous supprimez un flow :   
image de vue d’ensemble ![](./media/introduction-to-button-flows/manage-flow-2.png)   

1. Appuyez sur **mettre à jour** une fois que vous avez fini de modifier un workflow de bouton pour enregistrer vos modifications :   
   image de vue d’ensemble ![](./media/introduction-to-button-flows/manage-flow-3.png)   
2. Appuyez sur **historique d’exécution** pour afficher les résultats de toutes les exécutions d’un déroulement de bouton particulier :    
   image de vue d’ensemble ![](./media/introduction-to-button-flows/manage-flow-4.png)  
3. Si vous désactivez un Flow, il n’est plus disponible sous l’onglet **boutons** :    
   image de vue d’ensemble ![](./media/introduction-to-button-flows/manage-flow-5.png)  

## <a name="next-steps"></a>Étapes suivantes
* [Partager des flux de bouton](share-buttons.md).
* Apprenez à utiliser les [jetons de déclencheur de bouton](introduction-to-button-trigger-tokens.md) pour envoyer des données en temps réel lorsque vos flux de bouton sont exécutés.
* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).

