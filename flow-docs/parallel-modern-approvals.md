---
title: Créer un flux de travail d’approbation moderne parallèle | Microsoft Docs
description: Créer un flux de travail d’approbation moderne en parallèle
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/09/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 6cbaaecf70e4f6549a790861130dcde0b5a888e6
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548948"
---
# <a name="create-parallel-approval-workflows-with-microsoft-flow"></a>Créer des flux de travail d’approbation parallèles avec Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Dans un flux de travail d’approbation parallèle, plusieurs personnes doivent approuver des éléments tels que des factures, des bons de commande, des demandes de congés, etc. L’approbation de chaque personne est indépendante de tous les autres approbateurs.

Dans cette procédure pas à pas, nous utilisons Microsoft Flow pour créer un flux qui automatise un flux de travail d’approbation parallèle. Ce workflow automatise un processus de demande de congé des employés qui nécessite l’approbation de toutes les personnes (ou équipes) que l’employé prend régulièrement en charge. Les employés utilisent une [liste SharePoint](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7) pour demander des congés. Les congés de vacances sont exigés du responsable direct de l’employé, de l’équipe de vente et de l’équipe des ressources humaines. Chaque demande de congé est acheminée vers chaque approbateur pour une décision. Le Flow envoie un e-mail avec des modifications d’État, puis met à jour SharePoint avec les décisions.

## <a name="prerequisites"></a>Conditions préalables

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

La liste SharePoint Online que vous créez doit inclure les colonnes suivantes :

   ![Colonnes de liste SharePoint](./media/parallel-modern-approvals/sharepoint-columns.png)

Notez le nom et l’URL de la liste SharePoint Online. Nous utilisons ces éléments ultérieurement pour configurer le déclencheur **SharePoint-quand un élément est créé** .

## <a name="create-your-flow-from-the-blank-template"></a>Créer votre Flow à partir du modèle vide

[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Ajouter un déclencheur

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![Informations SharePoint](includes/media/parallel-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obtenir le responsable de la personne qui a créé la demande de congé

[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

## <a name="name-and-save-your-flow"></a>Nommer et enregistrer votre Flow

1. Donnez un nom à votre Flow, puis sélectionnez l’icône **Enregistrer** pour enregistrer le travail que nous avons effectué jusqu’à présent.

   ![enregistrer le Flow](./media/parallel-modern-approvals/save.png)

> [!NOTE]
> Sélectionnez régulièrement l’icône **Enregistrer** pour enregistrer les modifications apportées à votre Flow.
> 
> 


## <a name="add-an-approval-action-for-immediate-manager"></a>Ajouter une action d’approbation pour le responsable immédiat

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!IMPORTANT]
> Cette action envoie la demande de congé à l’adresse de messagerie dans la boîte de **affecté à** . par conséquent, insérez le jeton de **courrier électronique** dans la liste **obtenir le gestionnaire (v2)** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-sales-team"></a>Insérer une action d’approbation de branche parallèle pour l’équipe des ventes

1. Sélectionnez la flèche vers le bas située entre le **Gestionnaire d’extraction (v2)** et les cartes **Démarrer une approbation** .
2. Sélectionnez le signe plus qui s’affiche sur la flèche orientée vers le bas après l’avoir sélectionné.
3. Sélectionnez **Ajouter une branche parallèle**.
4. Sélectionnez **Ajouter une action**.

    ![accéder à la configuration du gestionnaire](./media/parallel-modern-approvals/add-parallel-branch.png)
5. Recherchez, sélectionnez, puis configurez une action **Démarrer une approbation** qui envoie la demande de congé à l’équipe des ventes. Consultez les [étapes permettant d’ajouter une action d’approbation pour le responsable immédiat](parallel-modern-approvals.md#add-an-approval-action-for-immediate-manager) si vous n’êtes pas sûr de savoir comment ajouter l’action **Démarrer une approbation** .

> [!IMPORTANT]
> Utilisez l’adresse de messagerie de l’équipe des ventes dans la boîte de **affecté à** de l’action **Démarrer une approbation 2** .
> 
> 

## <a name="insert-a-parallel-branch-approval-action-for-the-human-resources-team"></a>Insérer une action d’approbation de branche parallèle pour l’équipe des ressources humaines

1. Répétez les étapes pour [Insérer une branche parallèle pour l’équipe des ventes](parallel-modern-approvals.md#insert-a-parallel-branch-approval-action-for-the-sales-team) à ajouter, puis configurez une action **Démarrer une approbation** pour envoyer des demandes de congés aux ressources humaines.

> [!IMPORTANT]
> Utilisez l’adresse de messagerie de l’équipe des ressources humaines dans la zone **affecté à** de l’action **Démarrer une approbation 3** .
> 
> 

Si vous avez suivi le, votre Flow devrait ressembler à cet exemple :

   ![Flow avec branches parallèles](./media/parallel-modern-approvals/flow-with-parallel-branches.png)

## <a name="options-after-adding-parallel-branches"></a>Options après l’ajout de branches parallèles

Une fois que vous avez ajouté des actions à des branches parallèles, vous avez le choix entre deux options pour ajouter des étapes à votre Flow :

1. Utilisez le petit bouton **Insérer une nouvelle étape** (le bouton plus circulaire qui apparaît lorsque vous sélectionnez un espace blanc sur une branche ou la zone située juste au-dessous d’une branche). Ce bouton ajoute une étape à cette **branche spécifique**. Les étapes que vous ajoutez avec ce bouton s’exécutent après la fin de cette branche spécifique.
1. Utilisez le plus grand bouton **nouvelle étape** situé en bas de l’ensemble du flux de travail. Les étapes que vous ajoutez avec ce bouton s’exécutent après la fin de toutes les branches.

Dans les sections suivantes, nous utilisons le petit bouton **Insérer une nouvelle étape** pour effectuer ces étapes sur chaque branche :

* Ajoutez une condition qui vérifie si la demande de congé a été approuvée ou rejetée.
* Envoyer un e-mail qui informe l’employé de la décision.
* Mettez à jour la demande de congés dans SharePoint avec la décision d’approbation.

Ensuite, nous utilisons le plus grand nouveau bouton d' **étape** pour envoyer un e-mail qui résume toutes les décisions prises sur la demande de congé.

Poursuivons :

## <a name="add-a-condition-to-each-branch"></a>Ajouter une condition à chaque branche

1. Sélectionnez un espace blanc dans la branche **Démarrer une approbation** .
2. Sélectionnez le petit bouton **Insérer une nouvelle étape** (le bouton plus circulaire qui apparaît une fois que vous avez sélectionné l’espace blanc à l’étape précédente).
3. Sélectionnez **Ajouter une condition** dans le menu qui s’affiche.
4. Sélectionnez la première zone sur la carte **condition** , puis sélectionnez le jeton de **réponse** dans la catégorie **Démarrer une approbation** dans la liste de contenu dynamique.

    ![condition Flow avec branches parallèles](./media/parallel-modern-approvals/configure-approval-condition.png)
5. Confirmez que la liste (au milieu de la **carte condition**) est définie sur **est égale à**.
6. Entrez **approuver** (ce texte respecte la casse) dans la dernière zone.
7. Votre carte de condition doit maintenant ressembler à cet exemple :

    ![condition Flow avec branches parallèles](includes/media/parallel-modern-approvals/condition-card.png)

   > [!NOTE]
   > Cette condition vérifie la réponse de l’action **Démarrer une approbation** qui accède au responsable de l’employé.
   > 
   > 
8. Répétez les étapes précédentes sur les branches **Démarrer une approbation 2** (demande d’approbation aux ventes) et **Démarrer une approbation 3** (demande d’approbation aux ressources humaines).

## <a name="add-email-actions-to-each-branch"></a>Ajouter des actions de messagerie à chaque branche

Procédez comme suit sur le côté **si oui** de la branche **condition** .

   Remarque : votre Flow utilise ces étapes pour envoyer un message électronique lorsque la demande est approuvée :

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurer un modèle d’e-mail pré-approuvé](includes/media/parallel-modern-approvals/yes-email-config.png)

Pour envoyer un e-mail lorsqu’une demande est rejetée, utilisez la branche **si non** de la branche **condition** , puis répétez les étapes précédentes pour ajouter un modèle pour l’e-mail de rejet.

Répétez les étapes précédentes sur les branches **Démarrer une approbation 2** (demande d’approbation aux ventes) et **Démarrer une approbation 3** (demande d’approbation aux ressources humaines).

## <a name="update-the-vacation-request-with-the-decision"></a>Mettre à jour la demande de congé avec la décision

Procédez comme suit pour mettre à jour SharePoint lorsque des décisions sont prises.

   Remarque : Veillez à effectuer ces étapes sur les deux côtés **si oui** et **si non** de la branche.

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![mettre à jour la configuration de l’élément](./media/parallel-modern-approvals/configure-update-item.png)

Répétez les étapes précédentes sur les branches **Démarrer une approbation 2** et **Démarrer une approbation 3** .

## <a name="complete-the-flow"></a>Terminer le Flow

1. Sélectionner une **nouvelle étape** > **Ajouter une action**

    ![mettre à jour la configuration de l’élément](includes/media/parallel-modern-approvals/add-an-action-2-step.png)
1. Utilisez les étapes fournies précédemment pour envoyer un e-mail qui résume les résultats de chaque approbation. Envoyez cet e-mail à l’employé qui a demandé des congés. Votre carte peut ressembler à l’exemple suivant :

   ![mettre à jour la configuration de l’élément](./media/parallel-modern-approvals/final-email-card.png)

## <a name="learn-more-about-modern-approvals"></a>En savoir plus sur les approbations modernes

[Présentation des approbations modernes](modern-approvals.md)

