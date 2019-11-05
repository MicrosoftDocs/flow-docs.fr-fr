---
title: Créer un flux de travail d’approbation moderne avec plusieurs approbateurs | Microsoft Docs
description: 'Créer un flux de travail d’approbation moderne avec plusieurs approbateurs '
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
ms.date: 06/08/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 269239bd3fbb07c78bf316f9e58003690c63d878
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548976"
---
# <a name="manage-sequential-approvals-with-microsoft-flow"></a>Gérer les approbations séquentielles avec Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Certains flux de travail nécessitent une approbation préalable pour que l’approbateur final soit obligé de se déconnecter. Par exemple, une entreprise peut avoir une stratégie d’approbation séquentielle qui exige une approbation préalable des factures supérieures à $1000,00 avant d’être approuvées par le service financier.

Dans cette procédure pas à pas, nous créons un workflow d’approbation séquentiel qui gère les demandes de congé des employés.

> [!NOTE]
> SharePoint est utilisé ici uniquement à titre d’exemple ; Il n’est pas nécessaire de créer des flux d’approbation. Vous pouvez utiliser l’un des plus de 200 services avec lesquels Microsoft Flow s’intègre pour piloter vos flux.


## <a name="detailed-steps-in-the-flow"></a>Étapes détaillées du processus
Le flow :

1. Démarre lorsqu’un employé crée une demande de congés dans une [liste SharePoint Online](https://support.office.com/article/Introduction-to-lists-0a1c3ace-def0-44af-b225-cfa8d92c52d7).
2. Ajoute la demande de congé au centre d’approbation, puis envoie la demande au pré-approbateur.
3. Envoie par courrier électronique la décision d’approbation préalable à l’employé.
4. Met à jour la liste SharePoint Online avec la décision et les commentaires de l’approbation préalable.
   
   Remarque : si la demande est pré-approuvée, le workflow se poursuit avec les étapes suivantes :
5. Envoie la demande à l’approbateur final.
6. Envoie par courrier électronique la décision finale à l’employé.
7. Met à jour la liste SharePoint avec la décision finale.

Cette image résume les étapes précédentes :

   ![diagramme Visio du Flow](./media/sequential-modern-approvals/visio-overview.png)

## <a name="prerequisites"></a>Conditions préalables
[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Dans le cadre de cette procédure pas à pas, la liste SharePoint Online que vous créez doit inclure les colonnes suivantes :

   ![Colonnes de liste SharePoint](./media/sequential-modern-approvals/sharepoint-columns.png)

Notez le nom et l’URL de la liste SharePoint Online. Nous utilisons ces éléments plus tard lorsque vous configurez le déclencheur **SharePoint-quand un nouvel élément est créé** .

## <a name="create-your-flow-from-the-blank-template"></a>Créer votre Flow à partir du modèle vide
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Ajouter un déclencheur
[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

   ![informations SharePoint](./media/sequential-modern-approvals/select-sharepoint-site-info.png)

## <a name="get-the-manager-for-the-person-who-created-the-vacation-request"></a>Obtenir le responsable de la personne qui a créé la demande de congé
[!INCLUDE [add-get-manager-action](includes/add-get-manager-action.md)]

1. Donnez un nom à votre Flow, puis sélectionnez **créer un Flow** pour enregistrer le travail que nous avons effectué jusqu’à présent.
   
    ![enregistrer le Flow](./media/sequential-modern-approvals/save.png)
   
   > [!NOTE]
   > Sélectionnez **mettre à jour le Flow** en haut de l’écran régulièrement pour enregistrer les modifications apportées à votre Flow.
   > 
   > 
   
    ![sélectionner l’action de mise à jour](./media/sequential-modern-approvals/update.png)

Après chaque opération d’enregistrement, sélectionnez **modifier le Flow** en haut de l’écran, puis continuez à apporter des modifications.

## <a name="add-an-approval-action-for-pre-approvals"></a>Ajouter une action d’approbation pour les approbations préalables
[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

Remarque : cette action envoie la demande d’approbation préalable à l’adresse de messagerie dans la boîte de **affecté à** .

## <a name="add-a-condition"></a>Ajouter une condition
[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

> [!NOTE]
> Cette condition vérifie la réponse de l’action **Démarrer une approbation** .
> 
> 

## <a name="add-an-email-action-for-pre-approvals"></a>Ajouter une action de messagerie pour les approbations préalables
[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurer un modèle d’e-mail pré-approuvé](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-pre-approved-requests"></a>Ajouter une action de mise à jour pour les demandes pré-approuvées
[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

   ![mettre à jour la configuration de l’élément](./media/sequential-modern-approvals/configure-update-item.png)

## <a name="get-the-pre-approvers-manager"></a>Procurez-vous le responsable de l’approbation préalable
1. Utilisez le [Gestionnaire pour la personne qui a créé les étapes de demande de congés](sequential-modern-approvals.md#get-the-manager-for-the-person-who-created-the-vacation-request) que nous avons précédemment ajoutées, puis configurez une autre action **obtenir le gestionnaire** . Cette fois, nous obtenons le responsable du pré-approbateur.
2. Lorsque vous avez terminé, la carte **recevoir le responsable 2** doit ressembler à cette image. Veillez à utiliser le jeton de **courrier électronique** à partir de la catégorie **accéder au responsable** sur la carte **Ajouter du contenu dynamique à partir des applications et services utilisés dans ce Flow** .
   
   ![Procurez-vous le responsable du pré-approbateur](includes/media/modern-approvals/get-pre-approver-manager.png)

## <a name="add-the-final-approval-action"></a>Ajouter l’action d’approbation finale
1. Utilisez les étapes [Ajouter une action d’approbation pour les approbations préalables](sequential-modern-approvals.md#add-an-approval-action-for-pre-approvals) que nous avons apportées précédemment pour ajouter, puis configurez une autre action **Démarrer une approbation** . Cette action envoie une demande de message électronique pour approbation finale.
2. Lorsque vous avez terminé, la carte doit ressembler à cette image :
   
    ![configurer l’approbation](./media/sequential-modern-approvals/provide-approval-config-info.png)

## <a name="add-the-final-approval-condition"></a>Ajouter la condition d’approbation finale
1. Répétez les étapes de la section [Ajouter une condition](sequential-modern-approvals.md#add-a-condition) à ajouter, puis configurez une **condition** qui vérifie la décision de l’approbateur final.

## <a name="send-email-with-final-approval"></a>Envoyer un e-mail avec l’approbation finale
1. Utilisez les étapes de la section [Ajouter une action de messagerie pour les approbations préalables](sequential-modern-approvals.md#add-an-email-action-for-pre-approvals) à ajouter, puis configurez une action qui envoie un e-mail lorsque les demandes de congés sont approuvées.
2. Lorsque vous avez terminé, votre carte doit ressembler à cette image :
   
   ![modèle d’e-mail d’approbation finale](./media/sequential-modern-approvals/vacatioin-request-approved-email-template.png)

## <a name="update-sharepoint-with-approval"></a>Mettre à jour SharePoint avec approbation
1. Utilisez les étapes de la section [Ajouter une action de mise à jour pour les demandes pré-approuvées](sequential-modern-approvals.md#add-an-update-action-for-pre-approved-requests) à ajouter, puis configurez une action qui met à jour SharePoint lorsque la demande de congés est approuvée.
2. Lorsque vous avez terminé, la carte doit ressembler à cette image :
   
    ![mettre à jour la configuration de l’élément](./media/sequential-modern-approvals/configure-update-item-approved.png)

## <a name="send-email-with-pre-approval-rejection"></a>Envoyer un e-mail avec un refus d’approbation préalable
[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

   ![configuration pour les demandes rejetées](./media/sequential-modern-approvals/configure-rejected-email.png)

Remarque : cette action doit être ajoutée à la branche **si non, ne rien faire** sous la carte **condition** .

## <a name="update-sharepoint-with-pre-approval-rejection"></a>Mettre à jour SharePoint avec le refus d’approbation préalable
[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   ![mettre à jour SharePoint pour les demandes rejetées](./media/sequential-modern-approvals/update-sharepoint-with-rejection.png)

## <a name="send-email-with-final-rejection"></a>Envoyer un e-mail avec le refus final
1. Suivez les étapes de la section [Envoyer un e-mail avec un refus d’approbation préalable](sequential-modern-approvals.md#send-email-with-pre-approval-rejection) à ajouter, puis configurez une action qui envoie un e-mail lorsque la demande de congés est rejetée par l’approbateur final.
   
    Remarque : cette action doit être ajoutée à la branche **si non, ne rien faire** sous la carte **condition 2** .
2. Lorsque vous avez terminé, la carte doit ressembler à cette image :
   
   ![configuration pour les demandes rejetées](./media/sequential-modern-approvals/final-rejection-email-card.png)

## <a name="update-sharepoint-with-final-rejection"></a>Mettre à jour SharePoint avec le refus final
1. Utilisez les étapes de [mise à jour de SharePoint avec refus d’approbation préalable](sequential-modern-approvals.md#update-sharepoint-with-pre-approval-rejection) à ajouter, puis configurez une action qui met à jour SharePoint si l’approbateur final rejette la demande de congés.
2. Lorsque vous avez terminé, la carte doit ressembler à cette image :
   
   ![mettre à jour une carte d’élément](./media/sequential-modern-approvals/final-rejection-update-sharepoint.png)
3. Sélectionnez **mettre à jour le workflow** pour enregistrer le travail que nous avons effectué.
   
   ![sélectionner l’action de mise à jour](./media/sequential-modern-approvals/update.png)

Si vous avez suivi le, votre Flow devrait ressembler à cette image :

![vue d’ensemble du Flow](./media/sequential-modern-approvals/completed-flow.png)

Maintenant que nous avons créé le Flow, voyons-le en action.

## <a name="request-an-approval"></a>Demander une approbation
[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Votre requête doit ressembler à cette image :

![demande de congé](./media/sequential-modern-approvals/vacation-request.png)

## <a name="view-pending-approval-requests"></a>Afficher les demandes d’approbation en attente
[!INCLUDE [view-pending-approvals](includes/view-pending-approvals.md)]

## <a name="pre-approve-a-request"></a>Pré-approuver une demande
[!INCLUDE [approve-request-from-different-locations](includes/approve-request-from-different-locations.md)]

## <a name="approve-the-request"></a>Approuver la demande
Les étapes d’approbation d’une demande sont identiques aux étapes de [pré-approbation d’une demande](sequential-modern-approvals.md#pre-approve-a-request) .

Remarque : l’approbateur final obtient la demande de congés uniquement après l’approbation préalable de la demande.

## <a name="reject-a-request"></a>Rejeter une demande
[!INCLUDE [reject-a-request](includes/reject-a-request.md)]

## <a name="more-information"></a>Plus d’informations
[Procédure pas à pas d’approbations modernes d’un seul approbateur](modern-approvals.md)

