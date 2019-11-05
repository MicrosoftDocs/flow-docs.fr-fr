---
title: Meilleures pratiques pour la gestion des processus de flux de travail | MicrosoftDocs
description: Comprendre les méthodes recommandées pour utiliser les flux de travail
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 34e34c33-003a-494f-858c-3d34aacb308c
caps.latest.revision: 10
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: ad9935b171568b62376232f450a62dbda4752cac
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546012"
---
# <a name="best-practices-for-workflow-processes"></a>Meilleures pratiques pour les processus de flux de travail
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cette rubrique contient les meilleures pratiques pour la création et la gestion des processus de flux de travail.  
  
<a name="BKMK_AvoidInfiniteLoops"></a>   
## <a name="avoid-infinite-loops"></a>Évitez les boucles infinies  
 Il est possible de créer une logique dans un flux de travail qui initie une boucle infinie, qui consomme les ressources du serveur et affecte les performances. Une boucle infinie peut généralement se produire si vous avez un flux de travail configuré pour démarrer lorsqu’un attribut est mis à jour, puis il met à jour cet attribut dans la logique du flux de travail. L’action mettre à jour déclenche le même flux de travail qui met à jour l’enregistrement et déclenche à nouveau le flux de travail, puis de nouveau.  
  
 Les flux de travail que vous créez incluent la logique permettant de détecter et d’arrêter les boucles infinies. Si un processus de workflow est exécuté plus d’un certain nombre de fois sur un enregistrement spécifique dans un laps de temps réduit, le processus échoue avec l’erreur suivante : **ce travail de workflow a été annulé, car le workflow qui l’a démarré a inclus une boucle infinie. Corrigez la logique du flux de travail et réessayez**. La limite des heures est de 16.  
  
<a name="BKMK_UseWorkflowTemplates"></a>   
## <a name="use-workflow-templates"></a>Utiliser des modèles de flux de travail  
 Si vous avez des flux de travail similaires et que vous prévoyez de créer plus de flux de travail qui suivent le même modèle, enregistrez votre workflow en tant que modèle de flux de travail. De cette façon, la prochaine fois que vous aurez besoin de créer un flux de travail similaire, créez le workflow à l’aide du modèle et évitez d’entrer toutes les conditions et les actions à partir de zéro.  
  
 Dans la boîte de dialogue **créer un processus** , choisissez **nouveau processus à partir d’un modèle existant (sélectionner dans la liste)** .  
  
<a name="BKMK_UseChildWorkflows"></a>   
## <a name="use-child-workflows"></a>Utiliser des flux de travail enfants  
 Si vous appliquez la même logique dans des flux de travail différents ou dans des branches conditionnelles, définissez cette logique en tant que flux de travail enfant afin de ne pas avoir à répliquer cette logique manuellement dans chaque flux de travail ou branche conditionnelle. Cela permet de faciliter la gestion de vos flux de travail. Au lieu d’examiner de nombreux flux de travail qui peuvent appliquer la même logique, vous pouvez simplement mettre à jour un flux de travail.  
  
## <a name="automatically-delete-completed-workflow-jobs"></a>Supprimer automatiquement les tâches de workflow terminées
Pour les flux de travail d’arrière-plan (asynchrones), nous vous recommandons de sélectionner l’option **supprimer automatiquement les tâches de workflow terminées (pour économiser l’espace disque)** dans la définition de Workflow. L’activation de cette case à cocher permet au système de supprimer les journaux de workflow en vue d’une exécution réussie afin d’économiser de l’espace. Notez que les journaux des exécutions de flux de travail ayant échoué seront toujours enregistrés pour la résolution des problèmes.  

![Rétention des tâches de workflow](media/workflow-job-retention.png)

<a name="BKMK_AutoDeleteCompletedWorkflowJobs"></a>   
## <a name="keep-logs-for-workflow-jobs-that-encountered-errors"></a>Conserver les journaux des tâches de workflow qui ont rencontré des erreurs  
Pour les flux de travail qui ne s’exécutent pas en arrière-plan (synchrone), nous vous recommandons de sélectionner l’option **conserver les journaux pour les tâches de workflow qui ont rencontré des erreurs** dans la définition de Workflow. La sélection de cette option permet d’enregistrer les journaux des exécutions de workflow ayant échoué pour le dépannage. Les journaux des exécutions de workflow synchrones réussis seront toujours supprimés pour économiser de l’espace.   

![Option conserver les journaux des flux de travail ayant échoué](media/keep-logs-for-workflows.png)

## <a name="limit-the-number-of-workflows-that-update-the-same-entity"></a>Limiter le nombre de workflows qui mettent à jour la même entité
L’exécution de plusieurs flux de travail qui met à jour la même entité peut entraîner des problèmes de verrouillage des ressources. Imaginez plusieurs flux de travail en cours d’exécution où chaque mise à jour d’opportunité déclenche une mise à jour du compte associé. Plusieurs instances de ces flux de travail exécutant et tentant de mettre à jour le même enregistrement de compte en même temps peuvent entraîner des problèmes de verrouillage des ressources. Des échecs de flux de travail se produisent et un message d’erreur, tel que **délai d’expiration SQL : impossible d’obtenir un verrou sur le _nom de ressource_de ressource**, est enregistré. 

  
<a name="BKMK_DocumentChangesUsingNotes"></a>   
## <a name="use-notes-to-keep-track-of-changes"></a>Utiliser des notes pour effectuer le suivi des modifications  
 Lorsque vous modifiez des workflows, vous devez utiliser l’onglet remarques et taper ce que vous avez fait et pourquoi vous l’avez fait. Cela permet à un autre utilisateur de comprendre les modifications que vous avez apportées.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Vue d’ensemble des processus de flux de travail](workflow-processes.md)   
 [Configurer les processus de flux de travail](configure-workflow-steps.md)   
 [Surveiller et gérer les processus de flux de travail](monitor-manage-processes.md)
   
