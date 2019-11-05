---
title: Ajouter un flux de travail à la demande à un flux de processus d’entreprise
description: ''
author: MSFTMAN
ms.author: Deonhe
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
ms.service: flow
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 26c79c20-2987-476e-983a-406e0db13034
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ab30f745d6465cff9551854034c25130697144ba
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546117"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Ajouter un flux de travail à la demande à un flux de processus d’entreprise
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Vous pouvez déclencher des workflows à la demande à partir d’un flux de processus d’entreprise. Par exemple, vous pouvez ajouter un flux de travail à la demande à un flux de processus d’entreprise afin qu’une activité, telle qu’une tâche ou un e-mail, soit créée chaque fois qu’une étape est terminée. 

Un flux de travail est activé en fonction de l’emplacement où vous déposez le flux de travail dans le concepteur de flux de processus d’entreprise.
- Processus de phase à la demande. Lorsque le flux de travail est déposé sur une étape de flux de processus d’entreprise, le flux de travail est déclenché à l’entrée ou à la sortie de l’étape. 
- Processus globaux à la demande. Lorsque le flux de travail est déposé dans la zone des **flux de travail globaux** , le flux de travail est déclenché lors de l’activation ou de l’archivage des processus (lorsque l’état passe à un État appliqué, terminé, réactivé ou abandonné). 

Notez la configuration requise suivante lorsque vous ajoutez un flux de travail à un flux de processus d’entreprise.
- Pour les flux de travail ajoutés à une étape : vous pouvez utiliser uniquement des workflows actifs et à la demande créés pour la même entité de la phase où vous ajoutez le flux de travail.  
- Pour les flux de travail globaux : vous pouvez utiliser uniquement des workflows actifs à la demande créés pour l’entité principale du flux de processus d’entreprise.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Ajouter un flux de travail à la demande à une étape de flux de processus d’entreprise

Vous ajoutez un workflow à la demande à partir du concepteur de flux de processus d’entreprise en faisant glisser le composant de workflow vers une étape de processus ou vers la section flux de travail globaux. 

Sur le site [powerapps](https://web.powerapps.com) , sélectionnez basé sur **des modèles** (en bas à gauche du volet de navigation). 

Ouvrez le concepteur de workflow pour les processus d’entreprise. Vous pouvez le faire de deux manières.
- Si le workflow du processus d’entreprise est déjà ajouté à une application, accédez à **applications**, en regard de l’application que vous souhaitez sélectionner **...** , puis sélectionnez **modifier**. Dans le concepteur d’applications, sélectionnez le processus d’entreprise, puis sélectionnez ![ouvrir le concepteur de workflow de processus d’entreprise](media/dynamics365-open-designer.PNG).  
- Sinon, ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer). dans le volet de navigation de gauche, sélectionnez **processus**, puis sélectionnez le processus d’entreprise que vous souhaitez. 

Déterminez si vous souhaitez que le flux de travail à la demande soit déclenché par l’un des événements de flux de processus d’entreprise suivants. 
- Processus de phase à la demande. Déclenche le flux de travail à l’entrée ou à la sortie de l’étape. 
- Processus globaux à la demande. Déclenche le workflow sur l’activation du processus ou l’archivage des processus (lorsque l’état passe à l’État appliqué, terminé, réactivé ou abandonné). 

Dans l’exemple ci-dessous, un flux de travail à la demande appelé **workflow à la** demande est ajouté à l' **étape 1** du flux de processus d’entreprise. 

1. Développez étape 1 pour afficher la section **processus déclenché** . 
2. Sélectionnez l’onglet **composants** , puis faites glisser **Workflow** vers la section **processus déclenché** .
    ![ajouter un flux de travail à une étape](media/add-workflow-to-bpf-1.png) également, vous pouvez faire glisser le **flux** de travail vers la section **flux de travail globaux** , qui déclenche le workflow sur l’activation du processus ou l’archivage des processus.
 ![ajouter Worfklow pour traiter l’activation ou l’archivage](media/add-workflow-to-bpf-global.png)
3. Dans la zone de recherche de l’onglet **Propriétés** , entrez et recherchez le nom du flux de travail à la demande que vous souhaitez ajouter à l’étape de flux de processus d’entreprise, puis sélectionnez **appliquer**.
    ![entrez un nom et sélectionnez appliquer](media/add-workflow-to-bpf-2.png)
4. Sous l’onglet **Propriétés** sous **déclencheur** , sélectionnez entrée de l' **étape** ou **quitter la phase**.  
    ![sélectionner le déclencheur de workflow](media/workflow-trigger.png)
   
    Lorsque vous déposez le flux de travail dans la section **flux de travail globaux** , les options du déclencheur sont **processus appliqué**, processus **réactivé**, **processus abandonné**et **processus terminé**.

5. Sélectionnez **mettre à jour** dans la barre d’outils du concepteur de workflow de processus d’entreprise.
 
## <a name="next-steps"></a>Étapes suivantes
[Utiliser des processus de flux de travail pour automatiser des processus qui ne nécessitent pas d’intervention de l’utilisateur](workflow-processes.md) <br/>
[Didacticiel : créer un workflow de processus d’entreprise pour normaliser les processus](create-business-process-flow.md) <br/>
[Automatisation du déroulement des processus d’entreprise dans Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
