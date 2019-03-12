---
title: Superviser et gérer les processus de workflow avec PowerApps | Microsoft Docs
ms.custom: ''
ms.date: 05/06/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: a987a803-4674-4eb0-87de-caefa003b1eb
caps.latest.revision: 12
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 007caa66731870f359e8cb33ba0919390d3196cd
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462875"
---
# <a name="monitor-and-manage-workflow-processes"></a>Superviser et gérer les processus de workflow

Pour superviser et gérer un processus, vous devez le rechercher, évaluer le statut et effectuer toutes les actions nécessaires pour résoudre les problèmes.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Supervision des workflows d’arrière-plan  
 Les workflows d’arrière-plan génèrent des enregistrements Tâche système qui facilitent le suivi de leur état. Vous pouvez accéder aux informations sur ces tâches système à plusieurs emplacements dans l’application :  
  
 **[Paramètres](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > Tâches système**  
 Cette section indique tous les types de tâches système. Vous devez filtrer les enregistrements sur ceux où **Type de tâche système** a pour valeur **Workflow**.  
  
 **À partir du processus de workflow**  
 Ouvrez la définition de workflow d’arrière-plan et accédez à l’onglet **Session de traitement**. Seules les tâches système pour ce workflow d’arrière-plan sont affichées.  
  
 **À partir de l’enregistrement**  
 Vous pouvez modifier le formulaire d’entité pour que la navigation contienne la relation **Processus en arrière-plan**. Toutes les tâches système ayant été démarrées dans le contexte de l’enregistrement sont affichées.  
  
> [!NOTE]
>  Si une tâche système asynchrone (workflow) échoue plusieurs fois de suite, le système commence à reporter l’exécution de cette tâche à intervalles de temps de plus en plus longs pour permettre à l’administrateur ou au créateur de l’application d’examiner et de résoudre le problème. Une fois que la tâche fonctionne de nouveau, elle recommence à s’exécuter normalement.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Actions sur les workflows d’arrière-plan en cours d’exécution  
 Quand un workflow d’arrière-plan s’exécute, vous disposez des options **Annuler**, **Suspendre** ou **Reporter** pour le workflow. Si vous avez suspendu un workflow, vous pouvez le **Reprendre**.  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Supervision des workflows en temps réel et des actions  
 Les workflows en temps réel et les actions n’utilisent pas les enregistrements Tâche système, car ils se produisent immédiatement. Toutes les erreurs qui se produisent s’affichent dans l’application avec l’en-tête **Erreur du processus métier**.  
  
 Il n’existe aucun journal pour les opérations réussies. Vous pouvez activer la journalisation des erreurs en activant l’option **Conserver les journaux pour les tâches de workflow qui rencontrent des erreurs** dans la zone **Rétention du journal de workflow** en bas de l’onglet **Administration** du processus.  
  
 Pour afficher le journal des erreurs d’un processus spécifique, ouvrez la définition de l’action ou du workflow en temps réel et accédez à l’onglet **Session de traitement**. Seules les erreurs journalisées pour ce processus sont affichées.  
  
 Si vous souhaitez un vue de toutes les erreurs d’un processus, accédez à **Recherche avancée** et créez une vue montrant les erreurs liées à l’entité de la session de traitement.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>Statut des processus de workflow  
 Quand vous affichez une liste de processus de workflow, chaque processus peut avoir l’une des valeurs **État** et **Raison du statut** suivantes :  
  
|État|Raison du statut|  
|-----------|-------------------|  
|Prêt|En attente de ressources|  
|Suspendu(e)|En attente|  
|Verrouillé|En cours<br /><br /> Suspension en cours<br /><br /> Annulation en cours|  
|Terminé|Terminé<br /><br /> Échec<br /><br /> Annulé|  

## <a name="deleting-process-log-records"></a>Suppression d’enregistrements de journal de processus

Si votre organisation utilise des flux de processus métier ou des workflows d’arrière-plan qui s’exécutent souvent, la quantité d’enregistrements de journal de traitement peut devenir suffisamment grande pour provoquer des problèmes de performances et consommer une quantité de stockage significative. Pour supprimer des enregistrements de journal de processus qui n’ont pas été suffisamment enlevés par une des tâches de suppression d’enregistrements en bloc standard, vous pouvez utiliser la fonctionnalité de suppression en bloc à l’aide de tâches système pour créer une tâche de suppression d’enregistrements en bloc personnalisée.

1. Accédez à **Paramètres** > **Gestion des données** > **Suppression en bloc des enregistrements**.
2. À partir de la zone **Suppression en bloc des enregistrements**, sélectionnez **Nouveau**. 
3. Dans la page de démarrage **Assistant Suppression en bloc**, sélectionnez **Suivant**.
4. Dans la liste **Rechercher**, sélectionnez **Tâches système**.
5. Les conditions suivantes sont utilisées pour créer une tâche de suppression d’enregistrements en bloc afin de supprimer des enregistrements de journal de processus. 
 - **Type de tâche système Est égal à Workflow**. Cette condition cible les enregistrements de workflow. 
 - **Statut Est égal à Terminé**. Seuls les workflows terminés peuvent faire l’objet d’une exécution de la tâche.
 - **Raison du statut Est égal à Terminé**. Les tâches ayant réussi, annulées et ayant échoué sont supprimées.
 - **Terminé le Plus de X jours 30**. Utilisez le champ Terminé le pour ne supprimer que les enregistrements de journal de processus de workflow qui datent de plus de 30 jours.
 ![custom-bulk-record-deletion.png](media/custom-bulk-record-deletion.png)
6. Cliquez sur **Suivant**.
7. Définissez la fréquence à laquelle votre tâche de suppression en bloc doit s’exécuter. Vous pouvez planifier votre tâche afin qu’elle s’exécute à des intervalles définis ou créer une tâche de suppression en bloc à usage unique [à l’aide de l’option Immédiatement](#using-the-immediately-option). Dans cet exemple, une tâche périodique est définie pour s’exécuter le 21 mai 2018, puis tous les 30 jours. 
![Options de suppression d’enregistrements en bloc](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Utilisation de l’option Immédiatement

Notez que vous pouvez effectuer une suppression en bloc synchrone immédiate des enregistrements en sélectionnant l’option **Immédiatement**. Cette suppression fait appel à une exécution SQL Server directe au lieu de faire passer chaque enregistrement par le pipeline d’événements de suppression, ce qui peut réduire l’impact sur les performances du système. Il s’agit d’une bonne option si vous souhaitez nettoyer rapidement les enregistrements de workflow supplémentaires en trop ; ainsi, la tâche de suppression en bloc n’a pas besoin d’attendre dans la file d’attente asynchrone pour effectuer son traitement. 

L’option **Immédiatement** est activée quand les conditions suivantes sont remplies : 
- La tâche de suppression en bloc est destinée à l’entité Tâches système.
- Les critères de recherche ont la condition Type de tâche système Est égal à Workflow. 
- L’utilisateur qui crée la tâche de suppression en bloc dispose d’une profondeur globale pour le privilège de suppression sur l’entité AsyncOperation. Le rôle de sécurité administrateur système a ce privilège.  

La suppression en bloc synchrone ne supprime que les enregistrements AsyncOperation qui sont dans l’état terminé. Au maximum, un million d’enregistrements sont traités par appel. Vous devez exécuter la tâche plusieurs fois si votre environnement comporte plusieurs millions d’enregistrement à supprimer.  
  
## <a name="next-steps"></a>Étapes suivantes   
 [Bonnes pratiques pour les processus de workflow](best-practices-workflow-processes.md) <br />

