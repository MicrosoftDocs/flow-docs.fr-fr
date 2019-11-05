---
title: Automatisez facilement les flux de travail d’approbation. | Microsoft Docs
description: Automatisez les flux de travail d’approbation qui s’intègrent à SharePoint, Dynamics CRM, Salesforce, OneDrive entreprise, Zendesk ou WordPress.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/20/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c46ac3dc65b6e1a3970bd0b9b4ef17df5bef16f8
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548690"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Créer et tester un flux de travail d’approbation avec Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Avec Microsoft Flow, vous pouvez gérer l’approbation des documents ou des processus sur plusieurs services, notamment SharePoint, Dynamics 365, Salesforce, OneDrive entreprise, Zendesk ou WordPress.

Pour créer un flux de travail d’approbation, ajoutez l’action **approbations-démarrer une approbation** à un flux. Une fois que vous avez ajouté cette action, votre Flow peut gérer l’approbation des documents ou des processus. Par exemple, vous pouvez créer des flux d’approbation de document qui approuvent les factures, les ordres de travail ou les devis de vente. Vous pouvez également créer des flux d’approbation de processus qui approuvent les demandes de congés, les heures supplémentaires ou les plans de voyage.

Les approbateurs peuvent répondre aux demandes à partir de leur boîte de réception, [du centre d’approbations](https://flow.microsoft.com/manage/approvals/received/) sur le site Web Microsoft Flow ou de l’application Microsoft Flow.

## <a name="create-an-approval-flow"></a>Créer un workflow d’approbation
Voici une vue d’ensemble du Flow que nous allons créer et tester :

   ![vue d’ensemble du Flow](./media/modern-approvals/create-flow-overview.png)

Le Flow effectue les étapes suivantes :

1. Démarre lorsque quelqu’un crée une demande de congés dans une liste SharePoint Online.
2. Ajoute la demande de congé au centre d’approbation, puis l’envoie à l’approbateur.
3. Envoie un e-mail avec la décision de l’approbateur à la personne qui a demandé les congés.
4. Met à jour la liste SharePoint Online avec les commentaires de décision de l’approbateur.

## <a name="prerequisites"></a>Conditions préalables
Pour effectuer cette procédure pas à pas, vous devez avoir accès à :

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Créez ces colonnes dans votre liste SharePoint Online :

   ![Colonnes de liste SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Notez le nom et l’URL de la liste SharePoint Online. Vous aurez besoin de ces éléments plus tard lorsque vous configurerez le déclencheur **SharePoint-quand un élément est créé** .

## <a name="create-your-flow-from-the-blank-template"></a>Créer votre Flow à partir du modèle vide
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Ajouter un déclencheur

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

L' **adresse du site** et le nom de la **liste** sont les éléments que vous avez notés précédemment dans cette procédure pas à pas.

![Informations SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Ajouter une action de profil

1. Sélectionnez **nouvelle étape**, puis **Ajouter une action**.
   
    ![Nouvelle étape](./media/modern-approvals/select-sharepoint-add-action.png)
2. Entrez **Profil** dans la zone de recherche **choisir une action** .
   
    ![Rechercher un profil](./media/modern-approvals/search-for-profile.png)
3. Recherchez, puis sélectionnez l’action **utilisateurs Office 365-obtenir mon profil** .
   
    ![sélectionner des utilisateurs Office](./media/modern-approvals/select-my-profile.png)
4. Donnez un nom à votre Flow, puis sélectionnez **créer un Flow** pour enregistrer le travail que nous avons effectué jusqu’à présent.
   
    ![enregistrer le Flow](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Ajouter une action d’approbation

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Cette action envoie la demande d’approbation à l’adresse de messagerie dans la boîte de **affecté à** .
>
>

## <a name="add-a-condition"></a>Ajouter une condition

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Ajouter une action de messagerie pour les approbations

Procédez comme suit pour envoyer un e-mail si la demande de congés est approuvée :

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurer un modèle de message électronique approuvé](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Ajouter une action de mise à jour pour les demandes approuvées

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> L' **adresse du site**, le nom de la **liste**, l' **ID**et le **titre** sont requis.
>
>

![mettre à jour la configuration de l’élément](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Ajouter une action de messagerie pour les rejets

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuration pour les demandes rejetées](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Ajouter une action de mise à jour pour les demandes rejetées

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > L' **adresse du site**, le nom de la **liste**, l' **ID**et le **titre** sont requis.
   >
   >

![mettre à jour une carte d’élément](./media/modern-approvals/configure-update-item-no.png)

1. Sélectionnez **mettre à jour le workflow** pour enregistrer le travail que nous avons effectué.
   
    ![sélectionner l’action de mise à jour](./media/modern-approvals/update.png)

Si vous avez suivi le, votre Flow devrait ressembler à la capture d’écran suivante :

![vue d’ensemble du Flow](./media/modern-approvals/completed-flow.png)

Maintenant que nous avons créé le Flow, il est temps de le tester !

## <a name="request-an-approval"></a>Demander une approbation

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]


## <a name="create-long-running-approvals"></a>Créer des approbations de longue durée

S’il est probable que votre flow s’exécutera pendant plus de 30 jours, envisagez de stocker vos approbations dans Common Data Service. Cela vous permet de créer des flux qui agissent sur les réponses aux demandes d’approbation, même après l’expiration de l’exécution du flux d’origine. Pour ce faire, utilisez deux flux, un pour envoyer une demande d’approbation, et l’autre pour exécuter la logique métier sur les réponses à la demande d’approbation, en fonction de l’action **créer une approbation (v2)** . En savoir plus sur les [approbations de longue durée](https://docs.microsoft.com/business-applications-release-notes/april19/microsoft-flow/long-lived-approvals-other-approval-improvements).

>[!TIP]
> Si vous utilisez des clients de messagerie modernes, vous n’êtes pas obligé de vous demander si une demande est toujours requise, car Microsoft Flow met automatiquement à jour l’e-mail pour indiquer que l’approbation est terminée.

## <a name="cancel-an-approval-requests"></a>Annuler une demande d’approbation

Parfois, vous souhaiterez peut-être annuler une demande d’approbation que vous avez envoyée. Vous avez peut-être fait une erreur dans la demande ou n’est plus pertinente. Dans les deux cas, la personne qui a envoyé la demande peut l’annuler en procédant comme suit :

1. Sélectionner l’approbation
1. Sélectionnez **Annuler l’approbation** dans le volet latéral.

>[!TIP]
>Vous pouvez toujours sélectionner l’onglet **historique** pour afficher les demandes d’approbation que vous avez annulées.

>[!NOTE]
> La fonctionnalité d’annulation est prise en charge sur l’action **créer une approbation (v2)** .

## <a name="request-approvals-from-guest-users"></a>Demander les approbations des utilisateurs invités

Vous pouvez envoyer des demandes d’approbations à des personnes extérieures à votre organisation. Pour ce faire, utilisez les utilisateurs invités Azure Active Directory (Azure AD) en [invitant les utilisateurs d’autres locataires en tant qu’invités](https://docs.microsoft.com/azure/active-directory/b2b/add-user-without-invite).

Lorsque vous attribuez un rôle à un invité, cela donne à l’invité l’autorisation requise pour participer au processus d’approbation.

Maintenant que vous avez créé et testé votre Flow, assurez-vous que les autres utilisateurs savent comment l’utiliser.

## <a name="learn-more"></a>Pour en savoir plus

* Afficher et gérer les [demandes d’approbation en attente](approve-reject-requests.md)
* Créer des [flux d’approbations séquentiels.](sequential-modern-approvals.md)
* Créer des [flux d’approbation parallèles.](parallel-modern-approvals.md)
* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios)ou [Windows Phone](https://aka.ms/flowmobilewindows).
