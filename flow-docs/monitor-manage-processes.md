---
title: Surveiller et gérer les processus de flux de travail avec PowerApps | MicrosoftDocs
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
ms.openlocfilehash: 00d20d361dd7b3db9f55d6b975c472bea0c4160e
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73549003"
---
# <a name="monitor-and-manage-workflow-processes"></a>Surveiller et gérer les processus de flux de travail
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Pour surveiller et gérer les processus, vous devez localiser le processus, évaluer l’État et effectuer toutes les actions nécessaires pour résoudre les problèmes.  
  
<a name="BKMK_MonitorAsyncWorkflows"></a>   
## <a name="monitoring-background-workflows"></a>Surveillance des flux de travail en arrière-plan  
 Les flux de travail en arrière-plan génèrent des enregistrements de travaux système pour suivre leur état. Vous pouvez accéder à des informations sur ces tâches système à plusieurs emplacements de l’application :  
  
 **[Paramètres](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > les tâches système**  
 Cela inclut tous les types de travaux système. Vous devrez filtrer les enregistrements sur ceux pour lesquels le **type de tâche système** est **Workflow**.  
  
 **À partir du processus de workflow**  
 Ouvrez la définition de flux de travail en arrière-plan et accédez à l’onglet **session de processus** . Cette opération affiche uniquement les travaux système pour ce flux de travail en arrière-plan.  
  
 **À partir de l’enregistrement**  
 Vous pouvez modifier le formulaire d’entité afin que la navigation inclue la relation **processus en arrière-plan** . Cette opération affiche toutes les tâches système qui ont été démarrées dans le contexte de l’enregistrement.  
  
> [!NOTE]
>  En cas d’échec d’une tâche système asynchrone (flux de travail) plusieurs fois consécutives, le système commence à retarder l’exécution de ce travail pendant des intervalles de temps plus longs et plus longs afin que l’administrateur ou le créateur de l’application puissent examiner et résoudre le problème. Une fois le travail relancé, il reprend l’exécution normalement.  
  
<a name="BKMK_ActionsOnRunningWorkflows"></a>   
### <a name="actions-on-running-background-workflows"></a>Actions sur l’exécution des flux de travail en arrière-plan  
 Lorsqu’un flux de travail en arrière-plan est en cours d’exécution, vous avez le choix entre **Annuler**, **suspendre**ou **reporter** le flux de travail. Si vous avez déjà suspendu un workflow, vous pouvez le **reprendre** .  
  
<a name="BKMK_MonitorSyncWorkflows"></a>   
## <a name="monitoring-real-time-workflows-and-actions"></a>Surveillance des flux de travail et des actions en temps réel  
 Les workflows et les actions en temps réel n’utilisent pas les enregistrements de travaux système, car ils se produisent immédiatement. Toutes les erreurs qui se produisent sont affichées à l’utilisateur dans l’application avec l’en-tête **Erreur du processus d’entreprise**.  
  
 Il n’existe aucun journal pour les opérations réussies. Vous pouvez activer la journalisation des erreurs en activant l’option **conserver les journaux des tâches de workflow qui ont rencontré des erreurs** dans la zone **rétention du journal de workflow** en bas de l’onglet **administration** du processus.  
  
 Pour afficher le journal des erreurs d’un processus spécifique, ouvrez le flux de travail en temps réel ou la définition de l’action, puis accédez à l’onglet processus de la **session** . Cette opération affiche uniquement les erreurs journalisées pour ce processus.  
  
 Si vous souhaitez obtenir une vue de toutes les erreurs pour un processus quelconque, accédez à **recherche avancée** et créez une vue présentant les erreurs sur l’entité de session de processus.  
  
<a name="BKMK_StatusOfWorkflowProcesses"></a>   
## <a name="status-of-workflow-processes"></a>État des processus de workflow  
 Lorsque vous affichez une liste de processus de flux de travail, un processus individuel peut avoir l’un des **États** et les valeurs de **raison** d’état suivants :  
  
|Département|Motif de l’État|  
|-----------|-------------------|  
|Mondialisables|En attente de ressources|  
|Provisoire|En|  
|Fermée|En cours<br /><br /> Suspension<br /><br /> Annulation|  
|Procédé|A réussi<br /><br /> Défectueux<br /><br /> Annulée|  

## <a name="deleting-process-log-records"></a>Suppression des enregistrements de journal de processus

Si votre organisation utilise des flux de travail en arrière-plan ou des flux de processus d’entreprise qui s’exécutent fréquemment, la quantité d’enregistrements de journal de processus peut devenir suffisamment importante pour provoquer des problèmes de performances et consommer de grandes quantités de stockage. Pour supprimer les enregistrements de journal de processus qui ne sont pas suffisamment supprimés par l’un des travaux de suppression d’enregistrements en bloc standard, vous pouvez utiliser la fonctionnalité de suppression en bloc des travaux système pour créer une tâche de suppression d’enregistrements en bloc personnalisée.

1. Accédez à **paramètres** > **gestion des données** > la **suppression des enregistrements en bloc**.
2. Dans la zone de **Suppression d’enregistrement en bloc** , sélectionnez **nouveau**. 
3. Dans la page de démarrage de l' **Assistant de suppression en bloc** , sélectionnez **suivant**.
4. Dans la liste **Rechercher** , sélectionnez **travaux système**.
5. Les conditions suivantes sont utilisées pour créer une tâche de suppression d’enregistrement en bloc afin de supprimer les enregistrements de journal de processus. 
 - Le **type de tâche système est égal à Workflow**. Cela cible les enregistrements de flux de travail. 
 - L' **État est égal à terminé**. Seuls les workflows terminés sont valides pour l’exécution de la tâche.
 - La raison de l' **État est égale à réussite**. Supprimer les travaux ayant réussi, annulé et ayant échoué.
 - **Terminé depuis plus de X jours 30**. Utilisez le champ terminé le pour supprimer uniquement les enregistrements de journal de processus de workflow datant de plus de 30 jours.
 ![Custom-Bulk-record-Deletion. png](media/custom-bulk-record-deletion.png)
6. Cliquez sur **suivant**.
7. Définissez la fréquence à laquelle votre tâche de suppression en bloc s’exécutera. Vous pouvez planifier l’exécution de votre travail à intervalles définis ou créer une tâche de suppression en bloc unique [à l’aide de l’option immédiatement](#using-the-immediately-option). Dans cet exemple, une tâche périodique est définie pour s’exécuter le 21 mai, 2018 et tous les 30 jours. 
![les options de suppression d’enregistrement en bloc](media/custom-bulk-record-delete-options.png)

### <a name="using-the-immediately-option"></a>Utilisation de l’option immédiatement

Notez que vous avez la possibilité d’effectuer une suppression en bloc synchrone immédiate des enregistrements en sélectionnant l’option **immédiatement** . Cette suppression s’effectue avec l’exécution directe SQL Server au lieu de passer chaque enregistrement via le pipeline de suppression d’événements, ce qui peut réduire l’impact sur les performances du système. C’est une bonne option si vous souhaitez nettoyer rapidement les enregistrements de flux de travail supplémentaires au lieu de la tâche de suppression en bloc en attente dans la file d’attente asynchrone à des fins de traitement. 

L’option **immédiatement** est activée lorsque les conditions suivantes sont remplies : 
- La tâche de suppression en bloc est pour l’entité travaux système.
- Le critère de recherche a la condition le type de tâche système est égal à Workflow. 
- L’utilisateur qui crée la tâche de suppression en bloc a une profondeur globale pour le privilège supprimer sur l’entité AsyncOperation. Le rôle de sécurité administrateur système dispose de ce privilège.  

La suppression en bloc synchrone supprime uniquement les enregistrements AsyncOperation dans l’état terminé. Un maximum de 1 million enregistrements sont traités pour chaque appel. Vous devrez exécuter le travail plusieurs fois si votre environnement contient plus de 1 million enregistrements à supprimer.  
  
## <a name="next-steps"></a>Étapes suivantes   
 [Meilleures pratiques pour les processus de flux de travail](best-practices-workflow-processes.md) <br />

