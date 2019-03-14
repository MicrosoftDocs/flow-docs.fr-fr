---
title: Workflows Common Data Service (CDS) for Apps classiques | Microsoft Docs
ms.custom: ''
ms.date: 08/06/2018
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
ms.openlocfilehash: 5f3e2145741c96d20f73ff74f5fd6cc6c1cbb52e
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462899"
---
# <a name="classic-common-data-service-cds-for-apps-workflows"></a>Workflows Common Data Service (CDS) for Apps classiques 

Les workflows automatisent les processus métier sans interface utilisateur. En règle générale, les processus de workflow servent à lancer des automatisations qui ne nécessitent pas d’interaction utilisateur.  
  
 Chaque processus de workflow est associé à une seule entité. Quand vous configurez des workflows, vous devez prendre en compte quatre aspects principaux :  
  
-   Quand les démarrer ?  
  
-   Doivent-ils s’exécuter en tant que workflow en temps réel ou workflow d’arrière-plan ?  
  
-   Quelles actions doivent-ils effectuer ?  
  
-   Dans quelles conditions les actions doivent-elles être effectuées ?  
  
 Cette rubrique explique comment rechercher les processus de workflow, quand les démarrer et s’ils doivent s’exécuter en tant que workflow en temps réel ou d’arrière-plan. Pour plus d’informations sur les actions qu’ils doivent effectuer et sur les conditions, consultez [Configuration de processus de workflow](configure-workflow-steps.md).  
  
<a name="BKMK_WhereToCustomizeWorkflows"></a>   
## <a name="where-do-you-customize-workflow-processes"></a>Où personnalisez-vous les processus de workflow ?  
 Vous pouvez voir les workflows dans votre organisation en consultant le nœud **Processus** dans la **Solution par défaut** et en filtrant sur les processus qui ont la **Catégorie** **Workflow**.  
  
 ![Processus filtrés par workflow dans Dynamics 365](media/workflow-processes-filtered.PNG "Processus filtrés par workflow dans Dynamics 365")  
  
 Selon la façon dont l’application est générée, les utilisateurs peuvent y créer ou modifier leurs workflows. 
 
Les développeurs peuvent créer des workflows à l’aide des informations contenues dans le [Guide du développeur pour Dynamics 365 Customer Engagement](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-guide), et les solutions que vous achetez peuvent inclure des workflows que vous pouvez modifier.  
  
<a name="BKMK_WorkflowProperties"></a>   
## <a name="workflow-properties"></a>Propriétés de workflow  
 Dans l’Explorateur de solutions, sélectionnez **Processus** et cliquez sur **Nouveau**.  
  
 Quand vous créez un workflow, la boîte de dialogue **Créer un processus** vous demande de définir trois propriétés communes à tous les processus :  
  
 ![Création d’un workflow dans Dynamics 365](media/create-workflow.PNG "Création d’un workflow dans Dynamics 365")  
  
 **Nom du processus**  
 Le nom du processus de workflow ne doit pas être unique, mais si vous prévoyez un grand nombre de workflows, vous pouvez utiliser une convention de nommage pour différencier clairement vos processus. Vous pouvez appliquer des préfixes standard au nom du workflow. Le préfixe peut décrire la fonction du workflow ou le département de l’entreprise. Vous pouvez ainsi regrouper les éléments similaires dans la liste de workflows.  
  
 **Catégorie**  
 Cette propriété établit qu’il s’agit d’un processus de workflow.  
  
 **Entité**  
 Chaque processus de workflow doit être défini sur une seule entité. Vous ne pouvez pas changer l’entité une fois le processus de workflow créé.  
  
 **Exécuter ce workflow en arrière-plan (recommandé)**  
 Cette option apparaît quand vous sélectionnez un workflow en guise de catégorie. Ce paramètre détermine si le workflow est un workflow en temps réel ou d’arrière-plan. Les workflows en temps réel s’exécutent immédiatement (de façon synchrone), tandis que les workflows d’arrière-plan s’exécutent de façon asynchrone. Les options de configuration disponibles dépendent de votre choix pour ce paramètre. Les workflows d’arrière-plan autorisent des conditions d’attente qui ne sont pas disponibles pour les workflows en temps réel. Tant que vous n’utilisez pas ces conditions d’attente, vous pouvez par la suite convertir des workflows d’arrière-plan en workflows en temps réel et vice versa. Pour plus d’informations sur les conditions d’attente, consultez [Définition des conditions pour les actions de workflow](configure-workflow-steps.md#BKMK_SettingConditionsForWorkflowActions).  
  
 De plus, l’option **Type** vous permet de spécifier s’il faut générer un nouveau workflow à partir de zéro ou démarrer à partir d’un modèle existant. Quand vous choisissez **Nouveau processus à partir d’un modèle existant (sélection à partir d’une liste)**, vous pouvez choisir parmi les processus de workflow disponibles qui ont été enregistrés en tant que modèle de processus.  
  
 Après avoir créé le workflow ou si vous modifiez un workflow existant, vous disposez des propriétés supplémentaires suivantes :  
  
 ![Onglet Général dans un workflow](media/create-workflow-general-tab.PNG "Onglet Général dans un workflow")  
  
 **Activer en tant que**  
 Vous pouvez choisir **Modèle de processus** afin de créer un point de départ avancé pour d’autres modèles. Si vous choisissez cette option après avoir activé le workflow, celui-ci n’est pas appliqué, mais peut être sélectionné dans la boîte de dialogue **Créer un processus** si vous sélectionnez **Type** : **Nouveau processus à partir d’un modèle existant (sélection à partir d’une liste)**.  
  
 Les modèles de processus sont pratiques si vous avez de nombreux processus de workflow similaires et que vous souhaitez les définir sans dupliquer la même logique.  
  
> [!NOTE]
>  La modification d’un modèle de processus ne change pas le comportement des processus de workflow qui ont été créés à l’aide de ce modèle. Un workflow créé à l’aide d’un modèle est une copie du contenu du modèle.  
  
 **Disponible pour exécution**  
 Les options de cette section décrivent les modes d’exécution du workflow.  
  
 **Exécuter ce workflow en arrière-plan (recommandé)**  
 Cette case à cocher reflète l’option que vous avez sélectionnée quand vous avez créé le workflow. Cette option est désactivée, mais vous pouvez la changer à partir du menu **Actions** en sélectionnant **Convertir en workflow temps réel** ou **Convertir en workflow d’arrière-plan**.  
  
 **En tant que processus à la demande**  
 Choisissez cette option si vous souhaitez autoriser les utilisateurs à exécuter ce workflow à partir de la commande **Exécuter le workflow**.  
  
 **En tant que processus enfant**  
 Choisissez cette option si vous souhaitez que le workflow puisse être démarré à partir d’un autre workflow.  
  
 **Rétention des tâches de workflow**  
 Cette section contient une option permettant de supprimer un workflow une fois son exécution terminée.  
  
 **Supprimer automatiquement les tâches de workflow terminées (pour libérer de l’espace disque)**  
 Choisissez cette option si vous souhaitez qu’une tâche de workflow terminée soit automatiquement supprimée.  
  
> [!NOTE]
>  Les tâches de workflow ne sont pas supprimées immédiatement quand elles s’achèvent, mais peu après, via un traitement par lots.  
  
 **Étendue**  
 Pour les entités appartenant à l’utilisateur, les options sont **Organisation**, **Divis. mère : sous-divisions**, **Division** ou **Utilisateur**. Pour les entités appartenant à l’organisation, la seule option est **Organisation**.  
  
 Si l’étendue est **Organisation**, la logique de workflow peut être appliquée à n’importe quel enregistrement dans l’organisation. Sinon, le workflow est uniquement applicable à un sous-ensemble d’enregistrements appartenant à l’étendue.  
  
> [!NOTE]
>  La valeur d’étendue par défaut est **Utilisateur**. Vérifiez que la valeur d’étendue est appropriée avant d’activer le workflow.  
  
 **Démarrer quand**  
 Utilisez les options de cette section pour spécifier quand un workflow doit démarrer automatiquement. Vous pouvez configurer un workflow en temps réel afin qu’il s’exécute avant certains événements. Cette fonctionnalité est très puissante, car le workflow peut arrêter l’action avant qu’il ne se produise. Plus d’informations : [Utilisation de workflows en temps réel](configure-workflow-steps.md#BKMK_SynchronousWorkflows). Voici les options disponibles :  
  
- **L’enregistrement est créé**  
  
- **Statut de l’enregistrement modifié**  
  
- **L’enregistrement est attribué**  
  
- **Champs d’enregistrement modifiés**  
  
- **L’enregistrement est supprimé**  
  
> [!NOTE]
>  N’oubliez pas que les actions et les conditions que vous définissez pour le workflow ignorent à quel moment il est exécuté. Par exemple, si vous définissez un workflow pour mettre à jour l’enregistrement, cette action ne peut pas être effectuée par un workflow en temps réel tant que l’enregistrement n’a pas été créé. Il est impossible de mettre à jour un enregistrement qui n’existe pas. De même, un workflow en arrière-plan ne peut pas mettre à jour un enregistrement qui a été supprimé, même si vous pouvez définir cette action pour le workflow. Si vous configurez un workflow pour effectuer une action qui ne peut pas être exécutée, celle-ci échoue, de même que l’intégralité du workflow.  
  
 **Exécuter en tant que**  
 Cette option est disponible uniquement si vous avez désélectionné l’option **Exécuter ce workflow en arrière-plan (recommandé)** quand vous avez créé le workflow ou si vous avez par la suite converti un workflow d’arrière-plan en workflow en temps réel.  
  
<a name="BKMK_SecurityContextOfWorkflowProcesses"></a>   
## <a name="security-context-of-workflow-processes"></a>Contexte de sécurité des processus de workflow  
 Quand un workflow en arrière-plan est configuré en tant que processus à la demande et qu’un utilisateur le démarre à l’aide de la commande **Exécuter le workflow**, les actions que le workflow peut effectuer sont limitées à celles que l’utilisateur peut exécuter selon les privilèges et les niveaux d’accès définis par le(s) rôle(s) de sécurité associé(s) à son compte d’utilisateur.  
  
 Quand un workflow d’arrière-plan démarre en fonction d’un événement, le workflow agit dans le contexte de la personne qui en est le propriétaire, généralement la personne qui l’a créé.  
  
 Pour les workflows en temps réel, vous avez l’option **Exécuter en tant que** et pouvez choisir si le workflow doit appliquer le contexte de sécurité du propriétaire du workflow ou de l’utilisateur qui a apporté des modifications à l’enregistrement. Si votre workflow inclut des actions qu’aucun utilisateur ne pourrait effectuer en raison de contraintes de sécurité, vous devez choisir de le rendre exécutable dans le contexte de son propriétaire.  
  
<a name="BKMK_ActivatingWorkflows"></a>   
## <a name="activate-a-workflow"></a>Activer un workflow  
 Les workflows peuvent uniquement être modifiés quand ils sont désactivés. Un workflow doit être activé pour être utilisable manuellement ou applicable en fonction d’événements. Pour être activé, un workflow doit contenir au moins une étape. Pour plus d’informations sur la configuration des étapes, consultez [Configuration des processus de workflow](configure-workflow-steps.md)  
  
 Un workflow ne peut être activé ou désactivé que par son propriétaire ou par une personne détenant le privilège **Agir au nom d’un autre utilisateur** telle que l’administrateur système.  En effet, un utilisateur malveillant pourrait modifier le workflow d’une personne sans que cette dernière en ait conscience. Vous pouvez réattribuer un workflow que vous possédez en changeant le propriétaire. Ce champ se trouve sous l’onglet **Administration**. Si vous n’êtes pas l’administrateur système et que vous devez modifier un workflow qui est détenu par un autre utilisateur, ce dernier doit le désactiver et vous l’attribuer. Une fois que vous avez terminé de modifier le workflow, vous pouvez le réattribuer à cet utilisateur afin qu’il puisse l’activer.  
  
 Avec les workflows en temps réel, l’utilisateur doit avoir le privilège **Activer les processus en temps réel**. Comme les workflows en temps réel ont un plus grand risque d’affecter les performances système, seuls les utilisateurs qui peuvent évaluer le risque potentiel doivent disposer de ce privilège.  
  
 Les workflows étant enregistrés quand ils sont activés, il n’est pas nécessaire de les enregistrer avant de les activer.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Configuration de processus de workflow](configure-workflow-steps.md)  <br/>
[Ajouter un workflow à la demande à un flux de processus métier](bpf-add-on-demand-workflow.md) 

