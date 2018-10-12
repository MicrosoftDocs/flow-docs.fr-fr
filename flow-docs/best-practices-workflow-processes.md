---
title: Bonnes pratiques pour les processus de workflow dans PowerApps | MicrosoftDocs
description: Comprendre les méthodes recommandées pour utiliser des workflows
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 94c38a54fec91e6a480cd90d0a72f19ca56ae51c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689522"
---
# <a name="best-practices-for-workflow-processes"></a>Bonnes pratiques pour les processus de workflow

Cette rubrique contient de bonnes pratiques pour la création et la gestion de processus de workflow.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Éviter les boucles infinies  
 Il est possible de créer une logique dans un workflow qui lance une boucle infinie, ce qui consomme les ressources serveur et affecte les performances. Une boucle infinie peut notamment se produire si un workflow est configuré pour démarrer quand un attribut est mis à jour, puis que cet attribut est mis à jour dans la logique du workflow. L’action de mise à jour déclenche le même workflow qui met à jour l’enregistrement et déclenche le workflow de façon répétée.  
  
 Les workflows que vous créez incluent une logique pour détecter et arrêter les boucles infinies. Si un processus de workflow est exécuté plus d’un certain nombre de fois sur un enregistrement spécifique dans une courte période de temps, le processus échoue avec l’erreur suivante : **Cette tâche de workflow a été annulée car le workflow qui l’a lancée comprenait une boucle infinie. Corrigez la logique de workflow, puis ressayez**. Le nombre limite de fois est 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Utiliser des modèles de workflow  
 Si vous avez des workflows qui sont similaires et que vous envisagez de créer des workflows qui suivent le même modèle, enregistrez votre workflow dans un modèle de workflow. Ainsi, la prochaine fois que vous devez créer un workflow similaire, opérez à l’aide du modèle ; vous vous épargnerez la saisie de toutes les conditions et actions à partir de zéro.  
  
 Dans la boîte de dialogue **Créer un processus**, choisissez **Nouveau processus à partir d’un modèle existant (sélection à partir d’une liste)**.  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Utiliser des workflows enfants  
 Si vous appliquez la même logique dans différents workflows ou dans des branches conditionnelles, définissez cette logique en tant que workflow enfant afin que vous ne soyez pas obligé de la répliquer manuellement dans chaque workflow ou branche conditionnelle. La gestion de vos workflows s’en trouve simplifiée. Au lieu d’examiner de nombreux workflows qui peuvent appliquer la même logique, vous pouvez simplement mettre à jour un seul workflow.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Supprimer automatiquement les tâches de workflow terminées
Pour les workflows d’arrière-plan (asynchrones), nous vous recommandons de sélectionner l’option **Supprimer automatiquement les tâches de workflow terminées (pour libérer de l’espace disque)** dans la définition des workflows. Le fait de cocher cette case permet au système de supprimer les journaux de workflow relatifs aux exécutions réussies afin d’économiser de l’espace. Notez que les journaux liés aux exécutions de workflow ayant échoué sont toujours enregistrés à des fins de dépannage.  

![Rétention des tâches de workflow](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Conserver les journaux pour les tâches de workflow qui rencontrent des erreurs  
Pour les workflows qui ne s’exécutent pas en arrière-plan (synchrones), nous vous recommandons de sélectionner l’option **Conserver les journaux pour les tâches de workflow qui rencontrent des erreurs** dans la définition des workflows. Quand vous sélectionnez cette option, les journaux liés aux exécutions de workflow ayant échoué sont enregistrés à des fins de dépannage. Les journaux liés aux exécutions de workflows synchrones ayant réussi sont toujours supprimés à des fins d’économie d’espace.   

![Option permettant de conserver les journaux pour les workflows ayant échoué](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limiter le nombre de workflows qui mettent à jour la même entité
L’exécution de plusieurs workflows qui mettent à jour la même entité peut entraîner des problèmes de verrouillage de ressource. Imaginez que plusieurs workflows sont en cours d’exécution et que chaque mise à jour d’opportunité déclenche une mise à jour du compte associé. Quand plusieurs instances de ces workflows sont en cours d’exécution et qu’elles essaient de mettre à jour le même enregistrement de compte simultanément, des problèmes de verrouillage de ressource peuvent survenir. Des échecs de workflow se produisent et un message d’erreur, tel que **Délai d’attente SQL : Impossible d’obtenir un verrou sur la ressource *nom de ressource***, est enregistré. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Utiliser des notes pour effectuer le suivi des modifications  
 Quand vous modifiez des workflows, vous devez utiliser l’onglet Notes et taper ce que vous avez fait et les raisons qui vous ont poussé à le faire. Ainsi, une autre personne peut comprendre les modifications que vous avez apportées.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Vue d’ensemble des processus de workflow](workflow-processes.md)   
 [Configurer des processus de workflow](configure-workflow-steps.md)   
 [Superviser et gérer les processus de workflow](monitor-manage-processes.md)
   
