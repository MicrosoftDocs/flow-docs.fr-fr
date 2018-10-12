---
title: Ajouter un workflow à la demande à un flux de processus métier
description: ''
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 07/12/2018
ms.topic: article
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
ms.openlocfilehash: aa061d5e2f668e8950a6cdab89992996f64c6fe8
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689614"
---
# <a name="add-an-on-demand-workflow-to-a-business-process-flow"></a>Ajouter un workflow à la demande à un flux de processus métier

Vous pouvez déclencher des workflows à la demande depuis un flux de processus métier. Par exemple, vous pouvez ajouter un workflow à la demande à un flux de processus métier afin qu’une activité, comme une tâche ou un e-mail, soit créée chaque fois qu’une phase est terminée. 

Un workflow est activé selon l’endroit où vous le placez sur le concepteur de flux de processus métier.
- Processus de phase à la demande. Quand le workflow est déposé sur une phase de flux de processus métier, il est déclenché à l’entrée ou à la sortie de la phase. 
- Processus globaux à la demande. Quand le workflow est déposé sur la zone **Workflow global**, il est déclenché au moment de l’activation ou de l’archivage du processus (quand le statut passe à l’état appliqué, terminé, réactivé ou abandonné). 

Les exigences suivantes s’appliquent quand vous ajoutez un workflow à un flux de processus métier.
- Pour les workflows ajoutés à une phase : vous ne pouvez utiliser des workflows actifs à la demande que pour l’entité de la phase où vous ajoutez les workflows.  
- Pour les workflows globaux : vous ne pouvez utiliser des workflows actifs à la demande que pour l’entité principale du flux de processus métier.

## <a name="add-an-on-demand-workflow-to-a-business-process-flow-stage"></a>Ajouter un workflow à la demande à une phase du flux de processus métier

Vous ajoutez un workflow à la demande à partir du concepteur de flux de processus métier en faisant glisser le composant de workflow vers une phase du processus ou vers la section des workflows globaux. 

Sur le site [PowerApps](https://web.powerapps.com), sélectionnez **Basé sur des modèles** (en bas à gauche du volet de navigation). 

Ouvrez le concepteur de flux de processus métier. Vous pouvez effectuer cette opération de deux manières.
- Si le flux de processus métier est déjà ajouté à une application, accédez à **Applications**. Ensuite, en regard de l’application de votre choix, sélectionnez **...**, puis sélectionnez **Modifier**. Dans le concepteur d’applications, sélectionnez le flux de processus métier, puis sélectionnez ![Ouvrir le concepteur de flux de processus métier](media/dynamics365-open-designer.PNG).  
- Sinon, ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation.md#solution-explorer). Ensuite, dans le volet de navigation gauche, sélectionnez **Processus**, puis sélectionnez le flux de processus métier de votre choix. 

Décidez si vous souhaitez que le workflow à la demande soit déclenché par un des événements de flux de processus métier suivants. 
- Processus de phase à la demande. Déclenche le workflow à l’entrée ou à la sortie de la phase. 
- Processus globaux à la demande. Déclenche le workflow au moment de l’activation ou de l’archivage du processus (quand le statut passe à l’état appliqué, terminé, réactivé ou abandonné). 

Dans l’exemple ci-dessous, un workflow à la demande nommé **My on demand workflow** est ajouté à la **phase 1** du flux de processus métier. 

1. Développez la phase 1 pour faire apparaître la section **Processus déclenché**. 
2. Sélectionnez l’onglet **Composants** et faites glisser **Workflow** vers la section **Processus déclenché**.
    ![Ajouter un workflow à une phase](media/add-workflow-to-bpf-1.png) Ou bien, vous pouvez faire glisser **Workflow** vers la section **Workflow global** ; cette opération déclenche le workflow au moment de l’activation ou de l’archivage du processus.
 ![Ajouter un workflow au moment de l’activation ou de l’archivage du processus](media/add-workflow-to-bpf-global.png)
3. Dans la zone de recherche de l’onglet **Propriétés**, entrez et recherchez le nom du workflow à la demande que vous souhaitez ajouter à la phase du flux de processus métier, puis sélectionnez **Appliquer**.
    ![Entrer le nom et sélectionner Appliquer](media/add-workflow-to-bpf-2.png)
4. Sous l’onglet **Propriétés**, sous **Déclencheur**, sélectionnez **Entrée de phase** ou **Sortie de phase**.  
    ![Sélectionner le déclencheur du workflow](media/workflow-trigger.png)
   
    Sinon, quand vous déposez le workflow sur la section **Workflow global**, les options de déclencheur sont **Processus appliqué**, **Processus réactivé**, **Processus abandonné** et **Processus terminé**.

5. Sélectionnez **Mettre à jour** dans la barre d’outils du concepteur de flux de processus métier.
 
## <a name="next-steps"></a>Étapes suivantes
[Utiliser des processus de workflow pour automatiser des processus qui ne requièrent pas l’intervention de l’utilisateur](workflow-processes.md) <br/>
[Tutoriel : Créer un flux de processus métier pour standardiser les processus](create-business-process-flow.md) <br/>
[Automatisation des flux de processus métier dans Dynamics 365](https://blogs.msdn.microsoft.com/crm/2017/03/28/business-process-flow-automation-in-dynamics-365/)
