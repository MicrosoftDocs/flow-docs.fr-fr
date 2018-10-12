---
title: Configurer des phases et des étapes de workflow dans PowerApps | Microsoft Docs
description: Découvrez comment configurer des étapes de workflow
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 8e34f8ef8847ab08e14c91ee6d7871697b0275ce
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690442"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurer des phases et des étapes de workflow

Quand vous concevez des workflows, vous pouvez placer la logique à exécuter dans des phases et des étapes.  
  
 **Phases**  
 Les phases facilitent la lecture de la logique des workflows et expliquent cette logique. Toutefois, les phases n’affectent pas la logique ou le comportement des workflows. Si un processus comprend des phases, toutes les étapes du processus doivent être accompagnées d’une phase.  
  
 **Étapes**  
 Les étapes sont des unités de logique métier dans un workflow. Les étapes peuvent inclure des conditions, des actions, d’autres étapes ou une combinaison de ces éléments.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Actions réalisables par les processus de workflow  

 Les processus de workflow peuvent effectuer les actions répertoriées dans le tableau suivant.  
  
|Action|Description|  
|------------|-----------------|  
|**Créer l’enregistrement**|Crée un enregistrement pour une entité et assigne aux attributs les valeurs de votre choix.|  
|**Mettre à jour l’enregistrement**|Vous pouvez mettre à jour l’enregistrement sur lequel le workflow s’exécute, tous les enregistrements liés à cet enregistrement par une relation N à 1 ou tous les enregistrements créés par des étapes précédentes.|  
|**Attribuer l’enregistrement**|Vous attribuer l’enregistrement sur lequel le workflow s’exécute, tous les enregistrements liés à cet enregistrement par une relation N à 1 ou tous les enregistrements créés par des étapes précédentes.|  
|**Envoyer un courrier électronique**|Envoie un e-mail. Vous pouvez choisir de créer un e-mail ou d’utiliser un modèle d’e-mail configuré pour l’entité de l’enregistrement sur lequel le workflow est en cours d’exécution, pour toutes les entités qui ont une relation N à 1 avec l’entité ou pour l’entité de tous les enregistrements créés par des étapes précédentes.|  
|**Lancer un workflow enfant**|Démarre un processus de workflow qui a été configuré en tant que workflow enfant.|  
|**Modifier le statut**|Change le statut de l’enregistrement sur lequel le processus s’exécute, de tous les enregistrements liés à cet enregistrement par une relation N à 1 ou de tous les enregistrements créés par des étapes précédentes.|  
|**Arrêter le workflow**|Arrête le workflow actuel. Vous pouvez définir un statut **Terminé** ou **Annulé** et spécifier un message de statut.<br /><br /> Quand des workflows en temps réel sont configurés pour un événement, l’arrêt d’un workflow ayant le statut « Annulé » empêche l’exécution de l’action d’événement. Pour plus d’informations, consultez [Utilisation de workflows en temps réel](configure-workflow-steps.md#BKMK_SynchronousWorkflows).|  
|**Étape personnalisée**|Les développeurs peuvent créer des étapes de workflow personnalisées qui définissent des actions. Aucune étape personnalisée n’est disponible par défaut.|  
  
### <a name="setting-record-values"></a>Définition des valeurs d’un enregistrement  

 Quand vous créez un enregistrement, vous pouvez définir des valeurs pour celui-ci. Quand vous mettez à jour un enregistrement, vous pouvez définir, ajouter, incrémenter, décrémenter, multiplier ou effacer des valeurs.  
  
 Quand vous sélectionnez **Définir les propriétés**, une boîte de dialogue s’ouvre et affiche le formulaire par défaut pour l’entité.  
  
 En bas de la boîte de dialogue, vous pouvez voir une liste de champs supplémentaires non présents dans le formulaire.  
  
 Pour n’importe quel champ, vous pouvez définir une valeur statique qui sera définie par le workflow.  
  
 Sur le côté droit de la boîte de dialogue, **l’Assistant Formulaire** vous permet de définir ou d’ajouter des valeurs dynamiques à partir du contexte de l’enregistrement actuel. Ces valeurs comprennent les valeurs des enregistrements associés qui sont accessibles à partir des relations N à 1 (plusieurs-à-un) pour l’entité.  
  
 Les options disponibles dans **l’Assistant Formulaire** dépendent du champ que vous avez sélectionné dans le formulaire. Quand vous définissez une valeur dynamique, vous voyez un espace réservé jaune appelé « champ de données dynamiques » qui indique où les données dynamiques seront incluses. Pour enlever la valeur, il vous suffit de sélectionner le champ de données dynamiques et de le supprimer. Pour les champs de texte, vous pouvez utiliser une combinaison de données statiques et de données dynamiques.  
  
 Avec des valeurs dynamiques, vous n’avez pas la certitude qu’un champ ou une entité associée a la valeur que vous souhaitez définir. Vous pouvez en fait définir une série de champs pour essayer de définir la valeur et les trier à l’aide des flèches vertes. Si le premier champ ne contient pas de données, le deuxième champ est essayé, et ainsi de suite. Si aucun des champs ne contient de données, vous pouvez spécifier une valeur à utiliser par défaut.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Définition des conditions pour les actions de workflow  

 Les actions que vous souhaitez appliquer dépendent souvent de conditions. Les processus de workflow offrent plusieurs moyens de définir des conditions et de créer une logique de branchement pour obtenir les résultats souhaités. Vous pouvez vérifier les valeurs de l’enregistrement sur lequel le processus de workflow s’exécute, de tous les enregistrements liés à cet enregistrement par une relation N à 1 ou les valeurs au sein du processus lui-même.  
  
|Type de condition|Description|  
|--------------------|-----------------|  
|**Condition de vérification**|Instruction « si-\<condition>-alors » logique.<br /><br /> Vous pouvez vérifier les valeurs actuelles de l’enregistrement sur lequel le workflow s’exécute, de tous les enregistrements liés à cet enregistrement par une relation N à 1 ou de tous les enregistrements créés par des étapes précédentes. En fonction de ces valeurs, vous pouvez définir des étapes supplémentaires quand la condition est vérifiée.<br /><br /> Dans l’instruction « si-\<condition>-alors », vous pouvez utiliser les opérateurs suivants : **Est égal à**, **Est différent de**, **Contient des données**, **Ne contient pas de données**, **Sous** et **Pas sous**. **Remarque :** Les opérateurs **Sous** et **Pas sous** sont des opérateurs hiérarchiques. Ils peuvent uniquement servir sur les entités pour lesquelles une relation hiérarchique est définie. Si vous essayez d’utiliser ces opérateurs sur les entités pour lesquelles aucune relation hiérarchique n’est définie, le message d’erreur suivant apparaît : « Vous utilisez un opérateur hiérarchique sur une entité pour laquelle aucune relation hiérarchique n’est définie. Rendez l’entité hiérarchique (en marquant une relation comme hiérarchique) ou utilisez un autre opérateur. » Pour plus d’informations sur les relations hiérarchiques, consultez [Définir et interroger des données liées hiérarchiquement](/powerapps/maker/common-data-service/define-query-hierarchical-data). Une capture d’écran qui suit le tableau illustre la définition du processus de workflow qui utilise les opérateurs hiérarchiques **Sous** et **Pas sous**.|  
|**Branche conditionnelle**|Instruction « sinon-si-alors » logique. L’éditeur utilise le texte « Sinon, si \<condition>, alors : ».<br /><br /> Sélectionnez une condition de vérification que vous avez définie ; vous pouvez alors ajouter une branche conditionnelle pour définir des étapes supplémentaires qui sont exécutées si la condition n’est pas vérifiée.|  
|**Action par défaut**|Instruction « sinon » logique. L’éditeur utilise le texte « Sinon : ».<br /><br /> Sélectionnez une condition de vérification, une branche conditionnelle, une condition d’attente ou une branche d’attente parallèle que vous avez définie ; vous pouvez alors utiliser une action par défaut afin de définir des étapes pour tous les cas qui ne satisfont pas aux critères définis dans les éléments de condition ou de branche.|  
|**Condition d’attente**|Permet à un workflow d’arrière-plan de s’interrompre jusqu’à ce que les critères définis par la condition soient remplis. Le workflow redémarre automatiquement une fois que les critères de la condition d’attente sont remplis.<br /><br /> Les workflows en temps réel ne peuvent pas utiliser de conditions d’attente.|  
|**Branche d’attente parallèle**|Définit une condition d’attente alternative pour un workflow d’arrière-plan avec un ensemble correspondant d’étapes supplémentaires qui ne sont effectuées que si le critère initial est rempli. Vous pouvez utiliser des branches d’attente parallèles pour créer des limites de temps dans votre logique de workflow. Elles permettent d’éviter que le workflow attende indéfiniment que les critères définis dans une condition d’attente soient remplis.|  
|**Étape personnalisée**|Les développeurs peuvent créer des étapes de workflow personnalisées qui définissent des conditions. Aucune étape personnalisée n’est disponible par défaut.|  
  
 La capture d’écran suivante illustre la définition d’un processus de workflow avec les opérateurs hiérarchiques **Sous** et **Pas sous**. Dans notre exemple, nous appliquons deux remises différentes à deux groupes de comptes. Dans **Ajouter une étape**, nous avons sélectionné **Vérifier la condition** pour spécifier la condition **si-alors** contenant les opérateurs **Sous** ou **Pas sous**. La première condition **si-alors** s’applique à tous les comptes qui sont **Sous** le compte Alpine Ski House. Ces comptes bénéficient d’une remise de 10 % sur les produits et services achetés. La seconde condition **si-alors** s’applique à tous les comptes qui ne sont **Pas sous** le compte Alpine Ski House ; ces comptes bénéficie d’une remise de 5 %. Ensuite, nous avons sélectionné **Mettre à jour l’enregistrement** pour définir l’action à exécuter selon la condition.  
  
 ![Processus de workflow avec les opérateurs Sous&#47;Pas sous](media/wfp-under-not-under.PNG "Processus de workflow avec les opérateurs Sous/Pas sous")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Utilisation de workflows en temps réel  

 Vous pouvez configurer des workflows en temps réel, mais vous devez les utiliser avec précaution. Les workflows d’arrière-plan sont généralement recommandés, car le système peut les appliquer quand des ressources sur le serveur sont disponibles. Le travail que doit effectuer le serveur s’en trouve fluidifié et tout utilisateur peut bénéficier de performances système optimales. L’inconvénient est que les actions définies par les workflows d’arrière-plan ne sont pas immédiates. Vous ne pouvez pas prédire quand elles seront appliquées, mais en règle générale, cette opération prend quelques minutes. Pour la plupart des tâches d’automatisation de processus métier, cela est acceptable car les utilisateurs du système n’ont pas besoin d’avoir conscience que le processus est en cours d’exécution.  
  
 Utilisez des workflows en temps réel quand un processus métier requiert l’affichage immédiat des résultats du processus ou si vous souhaitez la possibilité d’annuler une opération. Par exemple, vous pouvez souhaiter définir certaines valeurs par défaut pour un enregistrement quand il est enregistré pour la première fois ou vous assurer que certains enregistrements ne sont pas supprimés.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversion entre workflows en temps réel et workflows d’arrière-plan  

 Vous pouvez convertir un workflow en temps réel en workflow d’arrière-plan en choisissant **Convertir en workflow d’arrière-plan** dans la barre d’outils.  
  
 Vous pouvez convertir un workflow d’arrière-plan en workflow en temps réel en choisissant **Convertir en workflow temps réel** dans la barre d’outils. Si le workflow d’arrière-plan utilise une condition d’attente, il devient non valide et vous ne pouvez pas l’activer tant que vous n’avez pas supprimé la condition d’attente.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Lancement de workflows en temps réel avant ou après la modification du statut  

 Quand vous configurez **Options des processus automatiques** pour des workflows en temps réel, les options **Démarrer quand** dont vous disposez pour l’événement de modification du statut sont **Après** ou **Avant**. L’option par défaut est **Après**.  
  
 Quand vous sélectionnez **Avant**, vous dites que vous voulez que la logique dans le workflow soit appliquée avant que les données modifiant le statut ne soient enregistrées. Vous pouvez ainsi vérifier les valeurs avant que toute autre logique ne soit appliquée après l’opération et empêcher l’exécution d’une logique supplémentaire. Par exemple, vous pouvez avoir une logique supplémentaire dans une action de workflow personnalisée ou de plug-in qui peut lancer des actions sur un autre système. En arrêtant un traitement supplémentaire, vous pouvez éviter les cas où des systèmes externes sont affectés. L’application de workflows en temps réel avant cet événement signifie également que les autres actions de plug-in ou de workflow qui peuvent avoir enregistré des données n’ont pas besoin d’être « restaurées » quand l’opération est annulée.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Utilisation de l’action Arrêter le workflow avec des workflow en temps réel  

 Quand vous appliquez une action **Arrêter le workflow** dans un workflow, vous pouvez spécifier une condition de statut qui peut être **Terminé** ou **Annulé**. Quand vous définissez le statut sur Annulé, vous empêchez l’opération. L’utilisateur reçoit un message dont l’en-tête est **Erreur du processus métier** et qui contient le texte du message de statut lié à l’action d’arrêt.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Créer une logique métier personnalisée avec des processus](guide-staff-through-common-tasks-processes.md)   
 [Vue d’ensemble des processus de workflow](workflow-processes.md)   
 [Superviser et gérer les processus de workflow](monitor-manage-processes.md)   
 [Bonnes pratiques pour les processus de workflow](best-practices-workflow-processes.md)
