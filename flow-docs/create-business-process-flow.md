---
title: Créer un flux de processus métier dans PowerApps | Microsoft Docs
description: Découvrez comment créer un flux de processus métier
ms.custom: ''
ms.date: 08/17/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 1e765d4c7c11354e382c3ff74ac66103345ff39f
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691031"
---
# <a name="tutorial-create-a-business-process-flow-to-standardize-processes"></a>Tutoriel : Créer un flux de processus métier pour standardiser les processus

Ce tutoriel vous montre comment créer un flux de processus métier dans PowerApps. Pour en savoir plus sur les raisons d’utiliser des flux de processus métier, consultez [Vue d’ensemble des flux de processus d’entreprise](business-process-flows-overview.md). Pour plus d’informations sur la création d’un flux de tâches mobile, consultez [Créer un flux de tâches mobile](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-mobile-task-flow).  
  
 Quand un utilisateur démarre le flux d’un processus métier, les différentes phases et étapes du processus s’affichent dans la barre du processus située en haut d’un formulaire :  
  
 ![Phases d’un processus métier](media/business-process-stages.png "Phases d’un processus métier")  
  
 > [!TIP]
 >  Après avoir créé une définition du flux de processus métier, vous pouvez contrôler qui est autorisé à créer, lire, mettre à jour ou supprimer l’instance du flux de processus métier. Par exemple, pour des processus de service, vous pouvez accorder un accès total aux conseillers du service clientèle pour leur permettre de changer l’instance du flux de processus métier, mais accorder un accès en lecture seule à l’instance destinée aux commerciaux pour leur permettre de superviser les activités après-vente de leurs clients. Pour configurer la sécurité d’une définition de flux de processus métier que vous créez, sélectionnez **Activer les rôles de sécurité** dans la barre d’action.  
  
<a name="BKMK_Createbusinessprocessflows"></a>   
## <a name="create-a-business-process-flow"></a>Créer un flux de processus métier  
  
1. Ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer).
  
2. Dans le volet de navigation de gauche, sélectionnez **Processus**. 
  
3.  Dans la barre d’outils **Actions**, sélectionnez **Nouveau**.  
  
4.  Dans la boîte de dialogue **Créer un processus**, renseignez les champs obligatoires :  
  
    -   Entrez un nom de processus. Le nom du processus ne doit pas nécessairement être unique, mais il doit être significatif pour aider les utilisateurs dans le choix d’un processus. Vous pourrez modifier ce nom ultérieurement.  
  
    -   Dans la liste **Catégorie**, sélectionnez **Flux des processus d’entreprise**.  
  
         Vous ne pourrez pas modifier la catégorie après avoir créé le processus.  
  
    -   Dans la liste **Entité**, sélectionnez l’entité sur laquelle vous voulez baser le processus.  
  
         L’entité sélectionnée s’applique aux champs disponibles pour les étapes qui peuvent être ajoutées à la première phase du flux du processus. Si vous ne trouvez pas l’entité souhaitée, vérifiez que le groupe d’options Flux des processus d’entreprise (des champs vont être créés) est spécifié dans la définition de l’entité. Vous ne pourrez pas modifier ce paramètre après avoir enregistré le processus.  
  
5. Sélectionnez **OK**.  
  
     Le nouveau processus est créé, et le concepteur de flux de processus métier s’ouvre, avec une phase déjà créée pour vous.  
  
 ![Fenêtre du flux du processus métier montrant les principaux éléments](media/business-process-flow-window-showing-main-elements.png "Fenêtre du flux du processus métier montrant les principaux éléments")  
  
6. **Ajoutez les phases nécessaires.** Si vous souhaitez que les utilisateurs progressent d’une phase métier à une autre dans le processus :  
  
    1.  Faites glisser un composant **Phase** de l’onglet **Composants** vers un signe + dans le concepteur.  
  
        ![Faire glisser une phase du processus métier](media/drag-business-process-stage.png "Faire glisser une phase du processus métier")  
  
    2.  Pour définir les propriétés d’une phase, sélectionnez la phase, puis définissez ses propriétés sous l’onglet **Propriétés** sur le côté droit de l’écran :  
  
        -   Entrez un nom complet.  
  
        -   Si vous le souhaitez, sélectionnez une catégorie pour la phase.  La catégorie (par exemple, **Qualifier** ou **Développer**) apparaît sous la forme d’un chevron dans la barre du processus.  
  
            ![Chevron de la barre du processus métier](media/business-process-bar-chevron.png "Chevron de la barre du processus métier")  
  
        -   Quand vous avez terminé de modifier les propriétés, sélectionnez le bouton **Appliquer**.  
  
7. **Ajoutez des étapes à une phase.** Pour afficher les étapes d’une phase, sélectionnez **Détails** en bas à droite de la phase. Pour ajouter des étapes :  
  
    1.  Faites glisser un composant **Étape** de l’onglet **Composants** vers la phase.  
  
        ![Ajouter une étape à une phase d’un processus métier](media/add-step-stage-business-process.png "Ajouter une étape à une phase d’un processus métier")  
  
    2.  Sélectionnez l’étape, puis définissez ses propriétés sous l’onglet **Propriétés** :  
  
        1.  Entrez un nom complet pour l’étape.  
  
        2.  Si vous voulez que les utilisateurs entrent des données pour terminer une étape, sélectionnez le champ approprié dans la liste déroulante.  
  
        3.  Sélectionnez **Obligatoire** si les utilisateurs doivent renseigner le champ pour terminer l’étape avant de passer à la phase suivante du processus.  
  
        4.  Sélectionnez **Appliquer** quand vous avez terminé.  
  
8. **Ajoutez une branche (condition) au processus.** Pour ajouter une condition de branche :  
  
    1.  Faites glisser le composant **Condition** de l’onglet **Composants** vers un signe + entre deux phases.  
  
        ![Ajouter une condition à un flux de processus métier](media/add-condition-business-process-flow.png "Ajouter une condition à un flux de processus métier")  
  
    2.  Sélectionnez la condition, puis définissez ses propriétés sous l’onglet **Propriétés**. Pour plus d’informations sur les propriétés de création de branche, consultez [Améliorer les flux de processus d’entreprise avec le branchement](enhance-business-process-flows-branching.md). Quand vous avez terminé de définir les propriétés de la condition, sélectionnez **Appliquer**.  
  
9. **Ajoutez un workflow.** Pour appeler un workflow :  
  
    1.  Faites glisser un composant **Workflow** de l’onglet **Composants** vers une phase ou vers l’élément **Workflow global** dans le concepteur.   L’endroit où vous ajoutez le composant dépend de ce qui suit :  
  
       - **Faites-le glisser vers une phase** si vous souhaitez déclencher le workflow à l’entrée ou à la sortie de la phase. Le composant Workflow doit être basé sur la même entité principale que la phase.  
  
       - **Faites-le glisser vers l’élément Workflow global** si vous souhaitez déclencher le workflow au moment de l’activation ou de l’archivage du processus (quand l’état passe à **Terminé** ou à **Abandonné**). Le composant Workflow doit être basé sur la même entité principale que le processus.  
  
    2.  Sélectionnez le workflow, puis définissez ses propriétés sous l’onglet **Propriétés** :  
  
       1.  Entrez un nom complet.  
  
       2.  Choisissez à quel moment le workflow doit être déclenché.  
  
       3.  Recherchez un workflow actif à la demande existant qui correspond à l’entité de la phase, ou créez un workflow en sélectionnant **Nouveau**.  
  
       4.  Sélectionnez **Appliquer** quand vous avez terminé.  
  
       Pour plus d’informations sur les workflows, consultez [Processus de workflow](../common-data-service/workflow-processes.md).  
  
10. Pour valider le flux du processus métier, sélectionnez **Valider** dans la barre d’action.  
  
11. Pour enregistrer le processus comme brouillon afin de continuer à travailler dessus, sélectionnez **Enregistrer** dans la barre d’action.  
  
    > [!IMPORTANT]
    >  Tant qu’un processus est un brouillon, personne d’autre que vous ne peut l’utiliser.  
  
12. Pour activer le processus et le mettre à la disposition de votre équipe, sélectionnez **Activer** dans la barre d’action.  

13. Pour contrôler qui peut créer, lire, mettre à jour ou supprimer l’instance du flux de processus métier, sélectionnez **Modifier les rôles de sécurité** dans la barre de commandes du concepteur. Par exemple, pour des processus de service, vous pouvez accorder un accès total aux conseillers du service clientèle pour leur permettre de changer l’instance du flux de processus métier, mais accorder un accès en lecture seule à l’instance destinée aux commerciaux pour leur permettre de superviser les activités après-vente de leurs clients.

  Dans l’écran **Rôles de sécurité**, sélectionnez le nom d’un rôle pour ouvrir la page d’informations sur le rôle de sécurité. Sélectionnez l’onglet Flux des processus d’entreprise, puis assignez les privilèges d’accès appropriés au flux de processus métier pour un rôle de sécurité.

  > [!NOTE]
  > Les rôles de sécurité Administrateur système et Personnalisateur de système ont par défaut accès aux nouveaux flux de processus métier.

   ![Assigner des privilèges à un flux de processus métier](media/bpf-assign-privileges.png)

  Choisissez les privilèges à assigner en sélectionnant les cases d’option correspondantes, puis cliquez sur Enregistrer. Pour plus d’informations sur les privilèges, consultez [Privilèges des flux des processus d’entreprise](business-process-flows-overview.md#BKMK_MultipleBPF).

  N’oubliez pas ensuite d’assigner le rôle de sécurité aux utilisateurs souhaités dans votre organisation.

> [!TIP] 
>  Voici quelques conseils à prendre en compte quand vous créez votre flux de tâches dans la fenêtre du concepteur :  
>   
> - Pour effectuer une capture instantanée du contenu de la fenêtre du flux de processus métier, sélectionnez **Capture instantanée** dans la barre d’action. Cette fonction est utile, par exemple, pour partager ou voir les commentaires d’un membre de l’équipe sur le processus.  
> - Utilisez la mini-carte pour accéder rapidement aux différentes parties du processus. C’est utile si vous avez un processus complexe qui n’est pas entièrement visible à l’écran.  
> - Pour ajouter une description au processus métier, sélectionnez **Détails** sous le nom du processus affiché dans le coin gauche de la fenêtre du flux de processus métier. La description est limitée à 2 000 caractères.  
  
<a name="BKMK_Editbusinessprocessflows"></a>   
## <a name="edit-a-business-process-flow"></a>Modifier un flux de processus métier  
 Pour modifier un flux de processus métier, ouvrez l’Explorateur de solutions, sélectionnez **Processus**, puis sélectionnez le **flux de processus métier** à modifier dans la liste des processus.  
  
 Quand vous sélectionnez le nom du flux de processus métier à modifier dans la liste des processus, le flux s’ouvre dans le concepteur, où vous pouvez ensuite apporter les modifications souhaitées. Développez **Détails** sous le nom du processus pour le renommer ou ajouter une description, et afficher des informations supplémentaires.  
  
 ![Section Détails développée pour un flux de processus métier](media/business-process-flow-details.png "Section Détails développée pour un flux de processus métier")  
  
  
## <a name="other-things-to-know-about-business-process-flows"></a>Autres points à connaître sur les flux de processus métier
 **Modifier les phases**  
Les flux de processus métier peuvent avoir jusqu’à 30 phases.    
  
Vous pouvez ajouter ou modifier les propriétés suivantes d’une phase :  
  
- **Nom de la phase**  
  
- **Entité**. Vous pouvez modifier l’entité de n’importe quelle phase, à l’exception de la première.  
  
- **Catégorie de phase**. Une catégorie vous permet de regrouper les phases par type d’action. Cela est utile pour les rapports qui regroupent les enregistrements en fonction de la phase dans laquelle ils se trouvent. Les options de catégorie de phase proviennent du groupe d’options général Catégorie de phase. Vous pouvez éventuellement ajouter des options à ce groupe d’options général et changer les étiquettes des options existantes. Vous avez aussi la possibilité de supprimer ces options, mais nous vous recommandons de conserver les options existantes. Si vous supprimez des options, vous ne pourrez pas ajouter exactement les mêmes ultérieurement. Si vous ne souhaitez pas que ces options soient utilisées, changez l’étiquette en « Ne pas utiliser ».  
  
- **Relation**. Entrez une relation quand la phase précédente dans le processus est basée sur une autre entité. Pour la phase que vous êtes en train de définir, choisissez **Sélectionner les relations** et sélectionnez une relation à utiliser lors du passage d’une phase à une autre. Nous vous recommandons de sélectionner une relation pour les motifs suivants :  
  
    -   Les relations ont souvent des mappages d’attributs qui reportent automatiquement les données entre les enregistrements, afin de réduire la saisie de données.  
  
    -   Quand vous sélectionnez **Phase suivante** dans la barre du processus pour un enregistrement, tous les enregistrements qui utilisent la relation seront également répertoriés dans le flux du processus, encourageant de ce fait la réutilisation des enregistrements dans le processus. En outre, dans un souci de simplifier le processus, vous pouvez utiliser des workflows pour automatiser la création d’enregistrements afin que l’utilisateur n’ait plus qu’à les sélectionner au lieu d’avoir à les créer.  
  
**Modifier les étapes**  
 Chaque phase peut comporter jusqu’à 30 étapes.    
  
**Ajouter une branche**  
Pour en savoir plus sur l’ajout d’une branche à une phase, consultez [Améliorer les flux de processus d’entreprise avec le branchement](enhance-business-process-flows-branching.md).  
  
Pour mettre un flux de processus métier à la disposition des utilisateurs, vous devez définir l’ordre du flux de processus, modifier les rôles de sécurité et activer le flux de processus.  
  
**Définir l’ordre du flux de processus**  
 Si plusieurs flux de processus métier ont été créés pour une entité (type d’enregistrement), vous devez définir lequel des processus est automatiquement assigné aux nouveaux enregistrements. Dans la barre de commandes, sélectionnez **Ordre des flux des processus**. Pour les nouveaux enregistrements ou ceux qui n’ont pas encore de flux de processus associé, le premier flux de processus métier auquel un utilisateur peut accéder est celui qui sera automatiquement utilisé.  
  
**Modifier les rôles de sécurité**  
Un utilisateur a accès à un flux de processus métier en fonction du privilège ayant été défini pour ce flux dans le rôle de sécurité assigné à l’utilisateur. 

Par défaut, seuls les rôles de sécurité **Administrateur système** et **Personnalisateur de système** ont accès aux nouveaux flux de processus métier. 

Pour assigner les privilèges d’accès à un flux de processus métier, ouvrez le flux de processus métier à modifier, puis sélectionnez **Modifier les rôles de sécurité** dans la barre de commandes du concepteur de flux de processus métier. Reportez-vous à l’étape 13 sous [Créer un flux de processus métier](#create-a-business-process-flow), plus haut dans cette rubrique.
  
**Activer**  
Pour mettre un flux de processus métier à la disposition des utilisateurs, vous devez d’abord l’activer. Dans la barre de commandes, sélectionnez **Activer**. Une fois que vous avez confirmé l’activation, le flux de processus métier est disponible pour les utilisateurs. Si un flux de processus métier contient des erreurs, vous ne pouvez pas l’activer tant que vous n’avez pas corrigé les erreurs.  

## <a name="add-an-on-demand-action-to-a-business-process-flow"></a>Ajouter une action à la demande à un flux de processus métier
La mise à jour Dynamics 365 (Online) version 9.0 intègre une nouvelle fonctionnalité : l’automatisation des flux de processus métier à l’aide d’étapes d’action. Vous pouvez ajouter un bouton à un flux de processus métier qui déclenchera une action ou un workflow.

### <a name="add-on-demand-workflows-or-actions-using-an-action-step"></a>Ajouter des workflows ou des actions à la demande à l’aide d’une étape d’action
Supposons que, dans le cadre du processus de qualification des opportunités, l’organisation Contoso exige que toutes les opportunités soient examinées par un approbateur désigné. En conséquence, l’organisation Contoso a créé une action qui : 

- crée un enregistrement de tâche assigné à l’approbateur de l’opportunité ; 
- ajoute l’étiquette « Prête pour la révision » à la rubrique de l’opportunité. 

De plus, Contoso doit permettre l’exécution de ces actions à la demande. Pour intégrer ces tâches au processus de qualification des opportunités, les actions doivent figurer dans le flux de processus métier des opportunités. Pour activer cette fonctionnalité, sélectionnez **En tant qu’étape d’action du flux de processus métier**.
![Exécution possible en tant que flux de processus métier.](media/action-available-to-run.png)

Ensuite, l’étape d’action est ajoutée au flux de processus métier des opportunités de Contoso. Enfin, le flux de processus est validé et mis à jour.

![Action ajoutée au flux de processus métier des opportunités.](media/add-action-to-bpf.png)

À présent, les commerciaux de Contoso peuvent lancer l’action de l’étape du processus métier **Qualifier l’opportunité**, à la demande, en sélectionnant **Exécuter**.

![Exécuter l’action.](media/action-execute.png)

> [!IMPORTANT]
> - Pour permettre l’exécution d’une action ou d’un workflow à la demande, le flux de processus métier doit contenir une étape d’action. Si l’étape d’action exécute un workflow, celui-ci doit être configuré pour être exécuté à la demande.
> - L’entité associée à l’action ou au workflow doit être identique à celle qui est associée au flux de processus métier.

### <a name="limitation-of-using-action-steps-in-a-business-process-flow"></a>Limitations relatives à l’utilisation des étapes d’action dans un flux de processus métier

- Les actions ne sont pas disponibles en tant qu’étapes d’action si les paramètres d’entrée ou de sortie ont les types Entity, EntityCollection ou OptionSet (Picklist). Les actions ayant plusieurs paramètres de sortie EntityReference et celles ayant un ou plusieurs paramètres d’entrée EntityReference ne sont pas disponibles en tant qu’étapes d’action. Les actions qui ne sont pas associées à une entité principale (action globale) ne sont pas disponibles en tant qu’étapes d’action.

  
## <a name="next-steps"></a>Étapes suivantes  
 [Vue d’ensemble des flux de processus d’entreprise](business-process-flows-overview.md) </br>   
 [Améliorer les flux de processus d’entreprise avec le branchement](enhance-business-process-flows-branching.md)

