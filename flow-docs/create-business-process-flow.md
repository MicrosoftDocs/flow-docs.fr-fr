---
title: Créer un workflow de processus d’entreprise dans PowerApps | MicrosoftDocs
description: Découvrez comment créer un workflow de processus d’entreprise
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: efe86ab3-430f-485a-b924-6ed82cfbb449
caps.latest.revision: 39
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3bd154935e06031b031432e10fa977f23e1a2c54
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546533"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Didacticiel : créer un workflow de processus d’entreprise pour normaliser les processus
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Ce didacticiel vous montre comment créer un workflow de processus d’entreprise avec PowerApps. Pour en savoir plus sur les raisons pour lesquelles vous utilisez des flux de processus d’entreprise, consultez [vue d’ensemble des flux de processus d’entreprise](business-process-flows-overview.md). Pour plus d’informations sur la création d’un workflow de tâche mobile, consultez [créer un workflow mobile](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quand un utilisateur démarre un workflow de processus d’entreprise, les étapes et étapes du processus s’affichent dans la barre de processus en haut d’un formulaire :  
  
 ![Processus d’entreprise avec étapes](media/business-process-stages.png "Processus d’entreprise avec étapes")  
  
 > [!TIP]
 >  Après avoir créé une définition de workflow de processus d’entreprise, vous pouvez contrôler qui peut créer, lire, mettre à jour ou supprimer l’instance de workflow de processus d’entreprise. Par exemple, pour les processus liés au service, vous pouvez fournir un accès complet aux représentants du service clientèle pour modifier l’instance de workflow du processus d’entreprise, mais fournir un accès en lecture seule à l’instance pour les représentants commerciaux, afin qu’ils puissent surveiller les activités postérieures à la vente pour leur acheteurs. Pour définir la sécurité d’une définition de workflow de processus d’entreprise que vous créez, sélectionnez **activer les rôles de sécurité** dans la barre d’action.  
  
<a name="BKMK_Createbusinessprocessflows"></a>

## <a name="prerequisites"></a>Conditions préalables

Vous avez besoin d’un [plan de flux 2](https://preview.flow.microsoft.com/pricing/) afin de créer des flux de processus d’entreprise. Certains plans de licence Dynamics 365 incluent Flow plan 2.

## <a name="create-a-business-process-flow"></a>Créer un workflow de processus d’entreprise  
  
1. Ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Dans le volet de navigation gauche, sélectionnez **processus**. 
  
3.  Dans la barre d’outils **actions** , sélectionnez **nouveau**.  
  
4.  Dans la boîte de dialogue **créer un processus** , renseignez les champs obligatoires :  
  
    -   Entrez un nom de processus. Le nom du processus n’a pas besoin d’être unique, mais il doit être significatif pour les personnes qui doivent choisir un processus. Vous pouvez le modifier ultérieurement.  
  
    -   Dans la liste **catégorie** , sélectionnez **Workflow du processus d’entreprise**.  
  
         Vous ne pouvez pas modifier la catégorie après avoir créé le processus.  
  
    -   Dans la liste **entité** , sélectionnez l’entité sur laquelle vous souhaitez baser le processus.  
  
         L’entité que vous sélectionnez affecte les champs disponibles pour les étapes qui peuvent être ajoutées à la première étape du processus. Si vous ne trouvez pas l’entité souhaitée, vérifiez que l’option flux des processus d’entreprise (champs créés) est définie dans la définition de l’entité. Vous ne pouvez pas le modifier une fois que vous avez enregistré le processus.  
  
5. Sélectionnez **OK**.  
  
     Le nouveau processus est créé et le concepteur de workflow de processus d’entreprise s’ouvre avec un seul étage déjà créé pour vous.  
  
 ![Fenêtre de workflow de processus d’entreprise présentant les principaux éléments](media/business-process-flow-window-showing-main-elements.png "Fenêtre de workflow de processus d’entreprise présentant les principaux éléments")  
  
6. **Ajoutez des étapes.** Si vos utilisateurs progressent d’une étape à l’autre dans le processus :  
  
    1.  Faites glisser un composant **stage** de l’onglet **composants** et déposez-le sur un signe + dans le concepteur.  
  
        ![Faire glisser une étape du processus d’entreprise](media/drag-business-process-stage.png "Faire glisser une étape du processus d’entreprise")  
  
    2.  Pour définir les propriétés d’une phase, sélectionnez l’étape, puis définissez les propriétés sous l’onglet **Propriétés** sur le côté droit de l’écran :  
  
        -   Entrez un nom d’affichage.  
  
        -   Si vous le souhaitez, sélectionnez une catégorie pour la phase.  La catégorie (par exemple, **qualifier** ou **développer**) apparaît sous la forme d’un chevron dans la barre des processus.  
  
            ![Chevron de la barre des processus d’entreprise](media/business-process-bar-chevron.png "Chevron de la barre des processus d’entreprise")  
  
        -   Lorsque vous avez terminé de modifier les propriétés, cliquez sur le bouton **appliquer** .  
  
7. **Ajoutez des étapes à une étape.** Pour afficher les étapes d’une étape, sélectionnez **Détails** dans le coin inférieur droit de la phase. Pour ajouter des étapes supplémentaires :  
  
    1.  Faites glisser le composant **Step** vers l’étape à partir de l’onglet **composants** .  
  
        ![Ajouter une étape à une étape dans un processus d’entreprise](media/add-step-stage-business-process.png "Ajouter une étape à une étape dans un processus d’entreprise")  
  
    2.  Sélectionnez l’étape, puis définissez les propriétés sous l’onglet **Propriétés** :  
  
        1.  Entrez un nom d’affichage pour l’étape.  
  
        2.  Si vous souhaitez que les utilisateurs entrent des données pour effectuer une étape, sélectionnez le champ approprié dans la liste déroulante.  
  
        3.  Sélectionnez **obligatoire** si les utilisateurs doivent renseigner le champ pour terminer l’étape avant de passer à l’étape suivante du processus.  
  
        4.  Sélectionnez **appliquer** lorsque vous avez terminé.  
  
8. **Ajoutez une branche (condition) au processus.** Pour ajouter une condition de branchement :  
  
    1.  Faites glisser le composant **condition** de l’onglet **composants** vers un signe + entre deux étapes.  
  
        ![Ajouter une condition à un workflow de processus d’entreprise](media/add-condition-business-process-flow.png "Ajouter une condition à un workflow de processus d’entreprise")  
  
    2.  Sélectionnez la condition, puis définissez les propriétés sous l’onglet **Propriétés** . Pour plus d’informations sur les propriétés de branchement, consultez [améliorer les flux de processus d’entreprise avec la branche](enhance-business-process-flows-branching.md). Lorsque vous avez terminé de définir les propriétés de la condition, sélectionnez **appliquer**.  
  
9. **Ajoutez un flux de travail.** Pour appeler un flux de travail :  
  
    1.  Faites glisser un composant de **Workflow** de l’onglet **composants** vers une étape ou vers l’élément de **flux de travail global** dans le concepteur.   Celui auquel vous l’ajoutez dépend des éléments suivants :  
  
       - **Faites-le glisser jusqu’à une étape** lorsque vous souhaitez déclencher le flux de travail à l’entrée ou à la sortie de l’étape. Le composant de Workflow doit être basé sur la même entité principale que l’étape.  
  
       - **Faites-le glisser vers l’élément de flux de travail global** lorsque vous souhaitez déclencher le flux de travail lorsque le processus est activé ou lorsque le processus est archivé (lorsque l’état passe à **terminé** ou **abandonné**). Le composant de Workflow doit être basé sur la même entité principale que le processus.  
  
    2.  Sélectionnez le flux de travail, puis définissez les propriétés sous l’onglet **Propriétés** :  
  
       1.  Entrez un nom d’affichage.  
  
       2.  Sélectionnez le moment auquel le flux de travail doit être déclenché.  
  
       3.  Recherchez un flux de travail actif à la demande existant qui correspond à l’entité stage ou créez un nouveau flux de travail en sélectionnant **nouveau**.  
  
       4.  Sélectionnez **appliquer** lorsque vous avez terminé.  
  
       Pour plus d’informations sur les flux de travail, consultez [processus de workflow](../common-data-service/workflow-processes.md).  
  
10. Pour valider le processus d’entreprise, sélectionnez **valider** dans la barre d’action.  
  
11. Pour enregistrer le processus en tant que brouillon pendant que vous continuez à l’utiliser, sélectionnez **Enregistrer** dans la barre d’action.  
  
    > [!IMPORTANT]
    >  Tant qu’un processus est un brouillon, les utilisateurs ne seront pas en mesure de l’utiliser.  
  
12. Pour activer le processus et le mettre à la disposition de votre équipe, sélectionnez **activer** dans la barre d’action.  

13. Pour contrôler qui peut créer, lire, mettre à jour ou supprimer l’instance de workflow de processus d’entreprise, sélectionnez **modifier des rôles de sécurité** dans la barre de commandes du concepteur. Par exemple, pour les processus liés au service, vous pouvez fournir un accès complet aux représentants du service clientèle pour modifier l’instance de workflow du processus d’entreprise, mais fournir un accès en lecture seule à l’instance pour les représentants commerciaux, afin qu’ils puissent surveiller les activités postérieures à la vente pour leur acheteurs.

  Dans l’écran **rôles de sécurité** , sélectionnez le nom d’un rôle pour ouvrir la page informations sur le rôle de sécurité. Sélectionnez l’onglet flux de processus d’entreprise, puis attribuez les privilèges appropriés sur le flux de processus d’entreprise pour un rôle de sécurité.

  > [!NOTE]
  > Les rôles de sécurité administrateur système et Personnalisateur de système ont accès aux nouveaux flux de processus d’entreprise par défaut.

   ![Affecter des privilèges à un workflow de processus d’entreprise](media/bpf-assign-privileges.png)

  Spécifiez les privilèges en sélectionnant les cases d’option appropriées, puis cliquez sur Enregistrer. Pour plus d’informations sur les privilèges, consultez [privilèges de workflow de processus d’entreprise](business-process-flows-overview.md#BKMK_MultipleBPF).

  Ensuite, n’oubliez pas d’attribuer le rôle de sécurité aux utilisateurs appropriés de votre organisation.

> [!TIP] 
>  Voici quelques conseils à garder à l’esprit quand vous travaillez sur votre workflow dans la fenêtre du concepteur :  
>   
> - Pour prendre un instantané de tous les éléments de la fenêtre de workflow de processus d’entreprise, sélectionnez **instantané** dans la barre d’action. Cela est utile, par exemple, si vous souhaitez partager et obtenir des commentaires sur le processus à partir d’un membre de l’équipe.  
> - Utilisez la mini-carte pour accéder rapidement à différentes parties du processus. Cela est utile lorsque vous avez un processus complexe qui fait défiler l’écran.  
> - Pour ajouter une description du processus d’entreprise, sélectionnez **Détails** sous le nom du processus dans le coin gauche de la fenêtre de processus d’entreprise. Vous pouvez utiliser jusqu’à 2000 caractères.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Modifier un workflow de processus d’entreprise  
 Pour modifier les flux de processus d’entreprise, ouvrez l’Explorateur de solutions, sélectionnez **processus**, puis sélectionnez le **flux de processus d’entreprise** dans la liste des processus que vous souhaitez modifier.  
  
 Lorsque vous sélectionnez le nom du workflow de processus d’entreprise que vous souhaitez modifier dans la liste des processus, celui-ci s’ouvre dans le concepteur, où vous pouvez effectuer les mises à jour de votre choix. Développez **Détails** sous le nom du processus pour le renommer ou ajoutez une description, puis affichez des informations supplémentaires.  
  
 ![Section détaillée développée d’un workflow de processus d’entreprise](media/business-process-flow-details.png "Section détaillée développée d’un workflow de processus d’entreprise")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Autres choses à savoir sur les flux de processus d’entreprise
 **Modifier les étapes**  
Les flux de processus d’entreprise peuvent avoir jusqu’à 30 étapes.    
  
Vous pouvez ajouter ou modifier les propriétés suivantes d’une phase :  
  
- **Nom de la phase**  
  
- **Entité**. Vous pouvez modifier l’entité pour n’importe quelle étape, à l’exception de la première.  
  
- **Catégorie**de la phase. Une catégorie vous permet de regrouper des étapes selon un type d’action. Elle est utile pour les rapports qui regroupent les enregistrements en cours d’étape. Les options de la catégorie stage proviennent du groupe d’options global de la catégorie phase. Vous pouvez ajouter des options supplémentaires à ce groupe d’options global et modifier les étiquettes des options existantes si vous le souhaitez. Vous pouvez également supprimer ces options si vous le souhaitez, mais nous vous recommandons de conserver les options existantes. Si vous la supprimez, vous ne pourrez pas rajouter exactement la même option. Si vous ne souhaitez pas qu’ils soient utilisés, remplacez l’étiquette par « ne pas utiliser ».  
  
- **Relation**. Entrez une relation lorsque l’étape précédente du processus est basée sur une autre entité. Pour l’étape actuellement définie, choisissez **Sélectionner des relations** pour identifier une relation à utiliser lors du déplacement entre les deux étapes. Il est recommandé de sélectionner une relation pour les avantages suivants :  
  
    -   Les relations ont souvent des mappages d’attributs définis qui transportent automatiquement les données entre les enregistrements, ce qui réduit l’entrée des données.  
  
    -   Lorsque vous sélectionnez **étape suivante** sur la barre de processus d’un enregistrement, tous les enregistrements qui utilisent la relation sont listés dans le processus, ce qui permet de promouvoir la réutilisation des enregistrements dans le processus. En outre, vous pouvez utiliser des flux de travail pour automatiser la création d’enregistrements afin que l’utilisateur le sélectionne simplement au lieu d’en créer un pour simplifier le processus.  
  
**Modifier les étapes**  
 Chaque étape peut avoir jusqu’à 30 étapes.    
  
**Ajouter une branche**  
Pour en savoir plus sur l’ajout d’une branche à une phase, consultez [améliorer les flux de processus d’entreprise avec la branche](enhance-business-process-flows-branching.md).  
  
Pour mettre un workflow de processus d’entreprise à la disposition des personnes à utiliser, vous devez ordonner le processus, activer les rôles de sécurité et l’activer.  
  
**Définir l’ordre du déroulement des processus**  
 Lorsque vous avez plusieurs workflows de processus d’entreprise pour une entité (type d’enregistrement), vous devez définir le processus qui est automatiquement attribué aux nouveaux enregistrements. Dans la barre de commandes, sélectionnez **Flow Process process**. Pour les nouveaux enregistrements ou enregistrements qui n’ont pas encore de workflow de processus associé, le premier workflow de processus d’entreprise auquel un utilisateur a accès est celui qui sera utilisé.  
  
**Activer les rôles de sécurité**  
Les utilisateurs ont accès à un workflow de processus d’entreprise en fonction du privilège défini sur le processus d’entreprise dans le rôle de sécurité attribué à l’utilisateur. 

Par défaut, seuls les rôles de sécurité **administrateur système** et **Personnalisateur de système** peuvent afficher un nouveau workflow de processus d’entreprise. 

Pour spécifier des privilèges sur un workflow de processus d’entreprise, ouvrez le processus d’entreprise pour le modifier, puis sélectionnez **modifier les rôles de sécurité** dans la barre de commandes du concepteur de workflow de processus d’entreprise. Consultez l’étape 13 sous [créer un workflow de processus d’entreprise](#create-a-business-process-flow) répertorié précédemment dans cette rubrique.
  
**Déclencher**  
Avant de pouvoir utiliser le workflow de processus d’entreprise, vous devez l’activer. Dans la barre de commandes, sélectionnez **activer**. Une fois que vous avez confirmé l’activation, le workflow du processus d’entreprise est prêt à être utilisé. Si un workflow de processus d’entreprise contient des erreurs, vous ne pouvez pas l’activer tant que les erreurs ne sont pas corrigées.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Ajouter une action à la demande à un workflow de processus d’entreprise
La mise à jour de la version 9,0 de Dynamics 365 (Online) introduit une fonctionnalité de workflow de processus d’entreprise : automatisation du déroulement des processus d’entreprise avec des étapes d’action. Vous pouvez ajouter un bouton à un flux de processus d’entreprise qui déclenchera une action ou un flux de travail.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Ajouter des flux de travail ou des actions à la demande à l’aide d’une étape d’action
Supposons que, dans le cadre du processus de qualification des opportunités, l’organisation contoso exige que toutes les opportunités soient révisées par un réviseur désigné. Par la suite, l’organisation contoso a créé une action qui : 

- Crée un enregistrement de tâche affecté au réviseur de l’opportunité. 
- Ajoute « prêt pour révision » à la rubrique opportunité. 

En outre, contoso doit être en mesure d’exécuter ces actions à la demande. Pour intégrer ces tâches dans le processus de qualification des opportunités, les actions doivent apparaître dans le processus d’entreprise opportunité. Pour activer cette fonctionnalité, sélectionnez **en tant qu’étape d’action de workflow de processus d’entreprise**.
![disponible pour une exécution en tant que workflow de processus d’entreprise.](media/action-available-to-run.png)

Ensuite, l’étape de l’action est ajoutée au workflow de processus d’entreprise de l’opportunité de contoso. Le processus est ensuite validé et mis à jour.

![Action ajoutée au workflow de processus d’entreprise opportunité.](media/add-action-to-bpf.png)

Désormais, les membres de la Salesforce de contoso peuvent lancer l’action à partir de l’étape **qualifier l’opportunité** du processus d’entreprise, à la demande, en sélectionnant **exécuter**.

![Action d’exécution.](media/action-execute.png)

> [!IMPORTANT]
> - Pour pouvoir exécuter une action ou un flux de travail à la demande, le flux de processus d’entreprise doit inclure une étape d’action. Si l’étape de l’action exécute un flux de travail, le flux de travail doit être configuré pour s’exécuter à la demande.
> - L’entité associée à l’action ou au flux de travail doit être la même que l’entité associée au flux du processus d’entreprise.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitation de l’utilisation des étapes d’action dans un workflow de processus d’entreprise

- Les actions ne sont pas disponibles en tant qu’étapes d’action si les paramètres d’entrée ou de sortie sont des types Entity, EntityCollection ou d’utilisateur (liste déroulante). Les actions avec plusieurs paramètres de sortie EntityReference ou un nombre quelconque de paramètres d’entrée EntityReference ne sont pas disponibles en tant qu’étapes d’action. Les actions qui ne sont pas associées à une entité principale (action globale) ne sont pas disponibles en tant qu’étapes d’action.

## <a name="instant-flows-in-business-process-flows"></a>Flux instantanés dans les flux de processus d’entreprise

Vous pouvez exécuter un **Workflow instantané** pour automatiser des tâches répétitives, générer des documents, effectuer le suivi des approbations, et bien plus encore, à partir d’une étape dans un processus d’entreprise.

### <a name="add-an-instant-flow-as-a-step-in-a-business-process"></a>Ajouter un workflow instantané en tant qu’étape dans un processus d’entreprise

Supposons que vous vendez des imprimantes et que vous utilisiez le **processus de vente Lead-opportunité** pour fermer les contrats. Dans le cadre de ce processus, vous aimeriez que le responsable de l’équipe révise et approuve les propositions que l’équipe de vente rassemble au cours d’une étape antérieure du processus d’entreprise avant de la partager avec le client.

Pour ce faire, vous devez effectuer deux opérations :
1. Créez un workflow instantané qui demande la révision et l’approbation de la proposition de la part de l’équipe.
1. Ajoutez le workflow instantané comme étape dans le **processus de vente opportunité**.

> [!TIP]
> Seuls les [flux sensibles](https://docs.microsoft.com/flow/overview-solution-flows) à la solution peuvent être ajoutés en tant qu’étape dans un processus d’entreprise. 

### <a name="build-an-instant-flow"></a>Créer un workflow instantané

1. Dans Microsoft Flow, sélectionnez **solutions** dans le menu de navigation.
1. Sélectionnez **solution par défaut** dans la liste des solutions qui s’affiche. 
1. Sélectionnez le menu **+ nouveau** , puis sélectionnez **Flow** dans la liste qui s’affiche.
1. Recherchez, puis sélectionnez le connecteur **Common Data Service** .
1. Recherchez, puis sélectionnez le déclencheur **lorsqu’un enregistrement est sélectionné** dans la liste des déclencheurs de **Common Data Service** .
1. Définissez **environnement** sur **par défaut**, puis affectez à nom de l' **entité** la valeur **prospect au processus de vente des opportunités**.
1. Ajoutez un champ d’entrée de texte pour que l’utilisateur entre le lien vers la proposition.

   ![Déclencheur de workflow instantané](media/instant-flow-trigger.png "Déclencheur de workflow instantané")

   Nous aurons besoin d’informations de l’instance de workflow de processus d’entreprise pour fournir un contexte à la demande d’approbation. par conséquent, procédez comme suit.

1. Ajoutez l’action **analyser JSON** . 
1. Définissez le **contenu** sur **entité** en le sélectionnant dans la liste des valeurs dynamiques du déclencheur lors de la **sélection d’un enregistrement** .
1. Collez le contenu suivant dans le champ **schéma** .

    ```json
    {
        "type": "object",
        "properties": {
        "entity": {
            "type": "object",
            "properties": {
                "FlowsWorkflowLogId": {
                    "type": "string"
                },
                "BPFInstanceId": {
                    "type": "string"
                },
                "BPFInstanceEntityName": {
                    "type": "string"
                },
                "BPFDefinitionId": {
                    "type": "string"
                },
                "BPFDefinitionEntityName": {
                    "type": "string"
                },
                "StepId": {
                    "type": "string"
                },
                "BPFDefinitionName": {
                    "type": "string"
                },
                "BPFInstanceName": {
                    "type": "string"
                },
                "BPFFlowStageLocalizedName": {
                    "type": "string"
                },
                "BPFFlowStageEntityName": {
                    "type": "string"
                },
                "BPFFlowStageEntityCollectionName": {
                    "type": "string"
                },
                "BPFFlowStageEntityRecordId": {
                    "type": "string"
                },
                "BPFActiveStageId": {
                    "type": "string"
                },
                "BPFActiveStageEntityName": {
                    "type": "string"
                },
                "BPFActiveStageLocalizedName": {
                    "type": "string"
                }
            }
          }
        }
   }
   ```

   Voici à quoi ressemblent les choses :

   ![Analyser JSON](media/instant-flow-json-date.png "Analyser JSON")

  1. Ajoutez l’action d' **extraction d’enregistrement** à partir du connecteur **Common Data Service** .
  1. Affectez à **environnement** la valeur **(actuel)** , **nom** de l’entité pour **diriger le processus de vente des opportunités**et identificateur d' **élément** en **BPFFlowStageEntityRecordID**.

     ![Ajouter un enregistrement](media/instant-flow-add-record.png)

     Maintenant que nous disposons des données, définissez le processus d’approbation en ajoutant l’action **Démarrer et attendre une approbation (v2)** , puis en renseignant les informations pertinentes. En savoir plus sur les [approbations]( sequential-modern-approvals.md) si vous n’êtes pas familiarisé.

     > [!TIP]
     > - Utilisez le sélecteur de contenu dynamique pour ajouter des champs à partir de l’action **obtenir un enregistrement** afin d’ajouter des informations pertinentes à la demande d’approbation afin que les approbateurs puissent facilement savoir ce que fait la demande. 
     > - Pour fournir un contexte supplémentaire concernant l’étape active dans laquelle se trouve le processus d’entreprise, ajoutez le champ **BPFActiveStageLocalizedName** dans la liste des valeurs dynamiques.

     Votre carte d' **approbation (v2)** peut ressembler à celle-ci :

      ![Carte d’approbation](media/instant-flow-add-approval-action.png)

1. Enfin, enregistrez le workflow, puis activez-le.

### <a name="add-this-flow-as-a-step-in-the-lead-to-opportunity-sales-process"></a>Ajoutez ce workflow comme étape dans le processus de vente de l’opportunité.

Maintenant que vous avez créé le workflow instantané, il vous suffit de l’ajouter à votre processus d’entreprise. 

1. Ouvrez le **processus de vente Lead-opportunité** dans le concepteur de workflow pour les processus d’entreprise. 
1. Glissez-déposez l' **étape de Flow (** préversion) à partir de la liste des **composants** jusqu’à la phase **proposer** .
1. Ensuite, sélectionnez l’icône de recherche dans le champ **Sélectionner un flux** pour répertorier tous les flux que vous pouvez ajouter à un flux de processus d’entreprise.
1. Sélectionnez un Flow dans la liste, puis enregistrez vos modifications en sélectionnant le bouton **appliquer** en bas du volet Propriétés.
1. Enfin, sélectionnez le bouton **mettre à jour** pour que ce processus d’entreprise s’effectue avec la nouvelle étape de transmission instantanée disponible pour vos utilisateurs.
  
## <a name="next-steps"></a>Étapes suivantes

 - [Vue d’ensemble des flux de processus d’entreprise](business-process-flows-overview.md)  
 - [Améliorer les flux de processus d’entreprise avec branchement](enhance-business-process-flows-branching.md)
 - [Vue d’ensemble des approbations](sequential-modern-approvals.md)
 - [Procédure détaillée pour ajouter un workflow instantané à un workflow de processus d’entreprise](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/instant-steps-business-process-flows)


