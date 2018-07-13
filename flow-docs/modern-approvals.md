---
title: Automatisez facilement les flux de travail d’approbation. | Microsoft Docs
description: Automatisez les flux de travail d’approbation qui s’intègrent à SharePoint, Dynamics CRM, Salesforce, OneDrive Entreprise, Zendesk ou WordPress.
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
ms.openlocfilehash: bd89bca994a77072815a73ba1cbc7ba1db6955d3
ms.sourcegitcommit: 4a8d11e1768cd0ca96a60b6f5548a68c0c8999e5
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38949720"
---
# <a name="create-and-test-an-approval-workflow-with-microsoft-flow"></a>Créer et tester un flux de travail d’approbation avec Microsoft Flow

Avec Microsoft Flow, vous pouvez gérer l’approbation de documents ou processus au sein de plusieurs services, y compris SharePoint, Dynamics CRM, Salesforce, OneDrive Entreprise, Zendesk ou WordPress.

Pour créer un flux de travail d’approbation, vous devez ajouter l’action **Approvals - Start an approval (Approbations - Démarrer une approbation)** à un flux. Une fois que vous avez ajouté cette action, votre flux peut gérer l’approbation des documents ou processus. Par exemple, vous pouvez créer un flux d’approbation de document qui approuve les factures, les ordres de travail ou les devis. Vous pouvez également créer un flux d’approbation de processus qui approuve les demandes de congés, les heures supplémentaires ou les programmes de voyage.

Les approbateurs peuvent répondre aux demandes à partir de leur boîte de réception, [du centre d’approbations](https://flow.microsoft.com/manage/approvals/received/) sur le site web Microsoft Flow ou de l’application Microsoft Flow.

## <a name="create-an-approval-flow"></a>Créer un flux d’approbation
Voici une vue d’ensemble du flux que vous allez créer et tester :

   ![vue d’ensemble du flux](./media/modern-approvals/create-flow-overview.png)

Le flux effectue les étapes suivantes :

1. Il démarre lorsqu’un employé crée une demande de congés dans une liste SharePoint Online.
2. Il ajoute la demande de congés dans le centre d’approbation, puis envoie la demande par e-mail à l’approbateur.
3. Il envoie un e-mail avec la décision prise par l’approbateur à la personne qui a demandé le congé.
4. Il met à jour la liste SharePoint Online avec les commentaires sur la décision de l’approbateur.

## <a name="prerequisites"></a>Prérequis
Pour effectuer cette procédure pas à pas, vous devez :

[!INCLUDE [prerequisites-for-modern-approvals](includes/prerequisites-for-modern-approvals.md)]

Créer ces colonnes dans votre liste SharePoint Online :

   ![colonnes de liste SharePoint Online](./media/modern-approvals/sharepoint-list-fields.png)

Notez le nom et l’URL de la liste SharePoint Online. Vous aurez besoin de ces éléments plus tard pour configurer le déclencheur **SharePoint - Création d’un élément**.

## <a name="create-your-flow-from-the-blank-template"></a>Créer votre flux à partir du modèle vide
[!INCLUDE [sign-in-and-create-flow-from-blank-template](includes/sign-in-and-create-flow-from-blank-template.md)]

## <a name="add-a-trigger"></a>Ajouter un déclencheur

[!INCLUDE [add-trigger-when-sharepoint-item-created](includes/add-trigger-when-sharepoint-item-created.md)]

L’**Adresse du site** et le **Nom de la liste** sont les éléments que vous avez notés précédemment dans cette procédure pas à pas.

![informations SharePoint](./media/modern-approvals/select-sharepoint-site-info.png)

## <a name="add-a-profile-action"></a>Ajouter une action de profil

1. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**.
   
    ![nouvelle étape](./media/modern-approvals/select-sharepoint-add-action.png)
2. Entrez **Profil** dans la zone de recherche **Choisir une action**.
   
    ![rechercher un profil](./media/modern-approvals/search-for-profile.png)
3. Recherchez et sélectionnez l’action **Utilisateurs Office 365 - Obtenir mon profil**.
   
    ![sélectionner les utilisateurs office](./media/modern-approvals/select-my-profile.png)
4. Fournissez un nom pour votre flux, puis sélectionnez **Créer un flux** pour enregistrer le travail réalisé jusqu'à présent.
   
    ![enregistrer le flux](./media/modern-approvals/save.png)

## <a name="add-an-approval-action"></a>Ajouter une action d’approbation

[!INCLUDE [add-an-approval-action](includes/add-an-approval-action.md)]

> [!NOTE]
> Cette action envoie la demande d’approbation à l’adresse e-mail indiquée dans la zone **Assigned To** (Assigné à).
>
>

## <a name="add-a-condition"></a>Ajouter une condition

[!INCLUDE [add-approval-condition-response](includes/add-approval-condition-response.md)]

## <a name="add-an-email-action-for-approvals"></a>Ajouter une action de messagerie pour les approbations

Suivez ces étapes pour envoyer un e-mail si la demande de congé est approuvée :

[!INCLUDE [add-action-to-send-email-when-vacation-approved](includes/add-action-to-send-email-when-vacation-approved.md)]

   ![configurer un modèle d’e-mail approuvé](./media/sequential-modern-approvals/yes-email-config.png)

## <a name="add-an-update-action-for-approved-requests"></a>Ajouter une action de mise à jour pour les demandes approuvées

[!INCLUDE [add-action-to-update-sharepoint-with-approval](includes/add-action-to-update-sharepoint-with-approval.md)]

> [!NOTE]
> Les champs **Adresse du site**, **Nom de la liste**, **ID** et **Titre** sont obligatoires.
>
>

![mettre à jour la configuration de l’élément](./media/modern-approvals/configure-update-item.png)

## <a name="add-an-email-action-for-rejections"></a>Ajouter une action de messagerie pour les refus

[!INCLUDE [add-action-to-send-email-when-vacation-rejected](includes/add-action-to-send-email-when-vacation-rejected.md)]

![configuration des demandes refusées](./media/modern-approvals/configure-rejected-email.png)

## <a name="add-update-action-for-rejected-requests"></a>Ajouter une action de mise à jour pour les demandes refusées

[!INCLUDE [add-action-to-update-sharepoint-with-rejection](includes/add-action-to-update-sharepoint-with-rejection.md)]

   > [!NOTE]
   > Les champs **Adresse du site**, **Nom de la liste**, **ID** et **Titre** sont obligatoires.
   >
   >

![carte Mettre à jour l’élément](./media/modern-approvals/configure-update-item-no.png)

1. Sélectionnez **Mettre à jour le flux** pour enregistrer le travail réalisé.
   
    ![sélectionner l’action Mettre à jour](./media/modern-approvals/update.png)

Si vous avez respecté cette procédure, votre flux doit ressembler à la capture d’écran suivante :

![vue d’ensemble du flux](./media/modern-approvals/completed-flow.png)

Maintenant que vous avez créé le flux, il est temps de le tester !

## <a name="request-an-approval"></a>Demander une approbation

[!INCLUDE [request-vacation-approval](includes/request-vacation-approval.md)]

Maintenant que vous avez créé et testé votre flux, indiquez aux autres comment l’utiliser.

## <a name="learn-more"></a>En savoir plus

* Voir et gérer les [demandes d’approbation en attente](approve-reject-requests.md)
* Créez des [flux d’approbations séquentielles.](sequential-modern-approvals.md)
* Créez des [flux d’approbations parallèles.](parallel-modern-approvals.md)
* Installez l’application mobile Microsoft Flow pour [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios) ou [Windows Phone](https://aka.ms/flowmobilewindows).
