---
title: Flux de travail de Common Data Service classiques | MicrosoftDocs
ms.custom: ''
ms.date: 08/27/2019
ms.reviewer: matp
ms.service: flow
ms.topic: article
ms.assetid: 1f3c9780-26ad-49ec-a3fb-fc226def19c5
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 42ac7bd75268010a8d7e2bf88a600621504dda39
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548337"
---
# <a name="classic-common-data-service-workflows"></a>Flux de travail de Common Data Service classiques 
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les flux de travail automatisent les processus d’entreprise sans interface utilisateur. Les gens utilisent généralement des processus de flux de travail pour lancer l’automatisation qui ne requiert aucune interaction de l’utilisateur.

> [!IMPORTANT]
> Utilisez des flux au lieu de flux de travail classiques pour automatiser vos processus d’entreprise. Pour plus d’informations, [Replacez les flux de travail Common Data Service classiques avec des flux](replace-workflows-with-flows.md) .  
  
 Chaque processus de workflow est associé à une seule entité. Lorsque vous configurez des flux de travail, vous devez tenir compte de quatre aspects majeurs :  
  
-   Quand les démarrer ?  
  
-   Doivent-ils s’exécuter en tant que flux de travail en temps réel ou en arrière-plan ?  
  
-   Quelles actions doivent-elles effectuer ?  
  
-   Dans quelles conditions dois-je effectuer des actions ?  
  
 Cette rubrique explique comment rechercher des processus de flux de travail et décrit quand les démarrer et s’ils doivent s’exécuter en temps réel ou en arrière-plan. Pour plus d’informations sur les actions qu’ils doivent effectuer et les conditions, consultez [Configuration des processus de flux de travail](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Où personnaliser les processus de flux de travail ?  
 Vous pouvez voir les flux de travail de votre organisation en affichant le nœud **processus** dans la **solution par défaut** et en filtrant sur les processus qui ont la **catégorie** **Workflow**.  
  
 ![Processus filtrés par Workflow dans Dynamics 365](media/workflow-processes-filtered.PNG "Processus filtrés par Workflow dans Dynamics 365")  
  
 Selon la façon dont l’application est générée, les utilisateurs peuvent créer ou modifier leurs flux de travail dans l’application. 
 
Les développeurs peuvent créer des flux de travail à l’aide des informations contenues dans le [Guide du développeur Common Data Service](https://docs.microsoft.com/powerapps/developer/common-data-service/workflow/workflow-extensions) et les solutions que vous achetez peuvent inclure des flux de travail que vous pouvez modifier.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propriétés du flux de travail  
 Dans l’Explorateur de solutions, sélectionnez **processus** , puis cliquez sur **nouveau**.  
  
 Lorsque vous créez un flux de travail, la boîte de dialogue **créer un processus** vous demande de définir trois propriétés :  
  
 ![Création d’un workflow dans Dynamics 365](media/create-workflow.PNG "Création d’un workflow dans Dynamics 365")  
  
 **Nom du processus**  
 Le nom du processus de workflow n’a pas besoin d’être unique, mais si vous pensez que vous aurez un grand nombre de flux de travail, vous souhaiterez peut-être utiliser une convention d’affectation de noms pour distinguer clairement vos processus. Vous pouvez appliquer des préfixes standard au nom du flux de travail. Le préfixe peut décrire la fonction du flux de travail ou du service au sein de l’entreprise. Cela vous permet de regrouper des éléments similaires dans la liste des flux de travail.  
  
 **Catégorie**  
 Cette propriété établit qu’il s’agit d’un processus de flux de travail.  
  
 **EDM**  
 Chaque processus de Workflow doit être défini sur une entité unique. Vous ne pouvez pas modifier l’entité une fois le processus de flux de travail créé.  
  
 **Exécuter ce flux de travail en arrière-plan (recommandé)**  
 Cette option apparaît lorsque vous sélectionnez workflow comme catégorie. Ce paramètre détermine si le flux de travail est un flux de travail en temps réel ou en arrière-plan. Les workflows en temps réel s’exécutent immédiatement (de façon synchrone) et les flux de travail en arrière-plan s’exécutent de façon asynchrone. Les options de configuration disponibles dépendent de votre choix pour ce paramètre. Les flux de travail en arrière-plan autorisent les conditions d’attente qui ne sont pas disponibles pour les flux de travail en temps réel. Tant que vous n’utilisez pas ces conditions d’attente, vous pouvez ultérieurement convertir des workflows en arrière-plan en temps réel et des flux de travail en temps réel en flux de travail en arrière-plan. Pour plus d’informations sur les conditions d’attente, consultez [définition de conditions pour les actions de flux de travail](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 Vous disposez également de l’option **type** pour spécifier si vous souhaitez créer un nouveau flux de travail à partir de zéro ou choisir de démarrer à partir d’un modèle existant. Quand vous choisissez **nouveau processus à partir d’un modèle existant (sélectionner dans la liste),** vous pouvez choisir parmi les processus de flux de travail disponibles précédemment enregistrés en tant que modèle de processus.  
  
 Après avoir créé le flux de travail ou si vous en modifiez un existant, vous aurez les propriétés supplémentaires suivantes :  
  
 ![Onglet général dans un flux de travail](media/create-workflow-general-tab.PNG "Onglet général dans un flux de travail")  
  
 **Activer en tant que**  
 Vous pouvez choisir le **modèle de processus** pour créer un point de départ avancé pour d’autres modèles. Si vous choisissez cette option, après avoir activé le flux de travail, celui-ci ne sera pas appliqué. à la place, il sera disponible pour la sélection dans la boîte de dialogue **créer un processus** si vous sélectionnez **type**: **nouveau processus à partir d’un modèle existant (sélectionner dans la liste)** .  
  
 Les modèles de processus sont pratiques lorsque vous avez un certain nombre de processus de flux de travail similaires et que vous souhaitez les définir sans dupliquer la même logique.  
  
> [!NOTE]
>  La modification d’un modèle de processus ne modifie pas les comportements des autres processus de workflow créés précédemment à l’aide de celui-ci en tant que modèle. Un nouveau flux de travail créé à l’aide d’un modèle est une copie du contenu du modèle.  
  
 **Disponible pour l’exécution**  
 Cette section contient des options qui décrivent comment le flux de travail est disponible pour être exécuté.  
  
 **Exécuter ce flux de travail en arrière-plan (recommandé)**  
 Cette case à cocher reflète l’option que vous avez sélectionnée lors de la création du flux de travail. Cette option est désactivée, mais vous pouvez la modifier à partir du menu **actions** en choisissant **convertir en flux de travail en temps réel** ou **convertir en flux de travail en arrière-plan**.  
  
 **En tant que processus à la demande**  
 Choisissez cette option si vous souhaitez autoriser les utilisateurs à exécuter ce flux de travail à partir de la commande **exécuter le flux de travail** .  
  
 **En tant que processus enfant**  
 Choisissez cette option si vous souhaitez permettre au flux de travail d’être disponible pour être démarré à partir d’un autre flux de travail.  
  
 **Rétention des tâches de workflow**  
 Cette section contient une option permettant de supprimer un flux de travail une fois l’exécution du flux de travail terminée.  
  
 **Supprimer automatiquement les tâches de workflow terminées (pour économiser de l’espace disque)**  
 Choisissez cette option si vous souhaitez qu’une tâche de workflow terminée soit automatiquement supprimée.  
  
> [!NOTE]
>  Les tâches de workflow ne sont pas supprimées immédiatement à l’achèvement, mais juste après, par le biais d’un processus de traitement par lots.  
  
 **Étendue**  
 Pour les entités appartenant à l’utilisateur, les options sont **organisation**, **parent : divisions enfants**, **Division**ou **utilisateur**. Pour les entités appartenant à l’organisation, la seule option est **organisation**.  
  
 Si Scope est **Organization**, la logique de workflow peut être appliquée à n’importe quel enregistrement dans l’organisation. Dans le cas contraire, le flux de travail ne peut être appliqué qu’à un sous-ensemble d’enregistrements qui se trouvent dans l’étendue.  
  
> [!NOTE]
>  La valeur d’étendue par défaut est **User**. Veillez à vérifier que la valeur d’étendue est appropriée avant d’activer le flux de travail.  
  
 **Démarrer quand**  
 Utilisez les options de cette section pour spécifier le moment où un flux de travail doit démarrer automatiquement. Vous pouvez configurer un flux de travail en temps réel à exécuter avant certains événements. Il s’agit d’une fonctionnalité très puissante, car le flux de travail peut arrêter l’action avant qu’elle ne se produise. Informations supplémentaires : [utilisation des flux de travail en temps réel](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Les options sont les suivantes :  
  
- **Enregistrement créé**  
  
- **Enregistrer les modifications d’État**  
  
- **L’enregistrement est attribué**  
  
- **Modification des champs d’enregistrement**  
  
- **Enregistrement supprimé**  
  
> [!NOTE]
>  Gardez à l’esprit que les actions et les conditions que vous définissez pour le workflow ne sont pas conscientes du moment où le workflow est exécuté. Par exemple, si vous définissez un flux de travail pour mettre à jour l’enregistrement, cette action ne peut pas être effectuée par un flux de travail en temps réel avant la création de l’enregistrement. Impossible de mettre à jour un enregistrement qui n’existe pas. De même, un flux de travail en arrière-plan ne peut pas mettre à jour un enregistrement qui a été supprimé, même si vous pouvez définir cette action pour le Workflow. Si vous configurez un flux de travail pour effectuer une action qui ne peut pas être effectuée, il échouera et l’intégralité du flux de travail échouera.  
  
 **Exécuter en tant que**  
 Cette option est disponible uniquement si vous avez sélectionné l’option **exécuter ce flux de travail en arrière-plan (recommandé)** quand vous avez créé le flux de travail ou si vous avez ultérieurement converti un flux de travail en arrière-plan en flux de travail en temps réel.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexte de sécurité des processus de workflow  
 Lorsqu’un flux de travail en arrière-plan est configuré en tant que processus à la demande et qu’il est démarré par un utilisateur à l’aide de la commande **exécuter le workflow** , les actions que le flux de travail peut effectuer sont limitées à celles que l’utilisateur peut effectuer en fonction des privilèges et des niveaux d’accès définis par le ou les rôles de sécurité définis pour leur compte d’utilisateur.  
  
 Lorsqu’un flux de travail en arrière-plan commence en fonction d’un événement, le workflow opère dans le contexte de la personne qui le possède, généralement la personne qui a créé le flux de travail.  
  
 Pour les flux de travail en temps réel, vous disposez de l’option **exécuter en tant que** et vous pouvez choisir si le flux de travail doit appliquer le contexte de sécurité du propriétaire du flux de travail ou l’utilisateur qui a apporté des modifications à l’enregistrement. Si votre flux de travail comprend des actions que tous les utilisateurs ne seraient pas en mesure d’effectuer en fonction des contraintes de sécurité, vous devez choisir d’exécuter le flux de travail en tant que propriétaire du flux de travail.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Activer un flux de travail  
 Les workflows peuvent être modifiés uniquement lorsqu’ils sont désactivés. Pour qu’un flux de travail puisse être utilisé manuellement ou être appliqué en raison des événements, il doit être activé. Pour qu’un flux de travail puisse être activé, il doit contenir au moins une étape. Pour plus d’informations sur la configuration des étapes, consultez [Configuration des processus de flux de travail](configure-workflow-steps.md) .  
  
 Un flux de travail peut être activé ou désactivé uniquement par le propriétaire du flux de travail ou par une personne ayant le droit **d’agir pour le compte d’un autre utilisateur** , tel que l’administrateur système.  Cela est dû au fait qu’un utilisateur malveillant peut modifier le flux de travail d’une personne sans avoir conscience de la modification. Vous pouvez réaffecter un flux de travail que vous possédez en modifiant le propriétaire. Ce champ se trouve sous l’onglet **administration** . Si vous n’êtes pas l’administrateur système et que vous devez modifier un flux de travail détenu par un autre utilisateur, vous en avez besoin pour le désactiver et l’attribuer. Une fois que vous avez fini de modifier le flux de travail, vous pouvez l’affecter à ce dernier afin qu’il puisse l’activer.  
  
 Pour les flux de travail en temps réel, l’utilisateur doit disposer du privilège **activer les processus en temps réel** . Étant donné que les flux de travail en temps réel présentent un risque plus élevé d’impact sur les performances du système, seules les personnes qui peuvent évaluer le risque potentiel doivent avoir ce privilège.  
  
 Les workflows sont enregistrés lorsqu’ils sont activés. il n’est donc pas nécessaire de les enregistrer avant de les activer.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Configuration des processus de flux de travail](configure-workflow-steps.md)  <br/>
[Ajouter un flux de travail à la demande à un flux de processus d’entreprise](bpf-add-on-demand-workflow.md) 

