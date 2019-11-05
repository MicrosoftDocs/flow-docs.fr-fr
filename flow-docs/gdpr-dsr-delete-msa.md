---
title: Microsoft Flow les demandes de suppression de l’objet des données RGPD pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de suppression de l’objet de données RGPD pour les comptes Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 379c88842b9724c7bdb6adfed79e2bb11497694d
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548053"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Répondre aux demandes de suppression de l’objet des données RGPD
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le **droit d’effacer** en supprimant les données personnelles est une protection clé dans le RGPD. La suppression des données personnelles comprend la suppression de toutes les données personnelles, à l’exception des informations du journal d’audit.

Microsoft Flow permet aux utilisateurs de créer des flux de travail automatisés. Lorsqu’un utilisateur décide de supprimer les données personnelles de Microsoft Flow, il peut passer en revue ses données personnelles et déterminer s’il faut en supprimer une partie ou la totalité.

Le tableau suivant indique quelles données personnelles sont supprimées automatiquement et quelles données nécessitent un utilisateur de compte Microsoft (MSA) pour les examiner et les supprimer.

|Nécessite que l’utilisateur MSA révise et supprime|Supprimé automatiquement|
|------|------|
|Activité du produit et du service|historique des exécutions|
|Trouvent|Flux d’activités|
|Connexions||

Microsoft Flow offre les expériences suivantes pour aider les utilisateurs à rechercher, examiner ou modifier les données et les ressources personnelles qui ne sont pas supprimées automatiquement :

## <a name="manage-delete-requests"></a>Gérer les demandes de suppression

Les étapes ci-dessous décrivent comment fournir des demandes de suppression en libre-service pour RGPD.

### <a name="delete-product-and-service-activity"></a>Supprimer l’activité du produit et du service

1. Connectez-vous au [tableau de bord de confidentialité Microsoft](https://account.microsoft.com/privacy/) avec votre MSA.
1. Sélectionnez le lien historique de l' **activité** .

    ![Historique de l’activité](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Vous pouvez rechercher ou parcourir l’historique de vos activités pour les différents services et applications Microsoft que vous utilisez, y compris Microsoft Flow. Sélectionnez **supprimer** pour supprimer des événements spécifiques d’un produit ou d’une activité de service.

    ![Supprimer l’événement](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Au bout de quelques instants, l’élément est supprimé et supprimé du tableau de bord de confidentialité.

### <a name="list-and-delete-flows"></a>Répertorier et supprimer des flux

Un utilisateur peut répertorier et supprimer ses flux de [Microsoft Flow](https://flow.microsoft.com) en suivantes les étapes suivantes :

1. Connectez-vous au [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez sur **mes flux**.

1. Sélectionnez **...** en regard du Flow que vous supprimez, puis sélectionnez **supprimer**.

    ![Supprimer l’événement](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Supprimer les connexions

Les connecteurs utilisent des connexions pour communiquer avec les API et les systèmes SaaS. Les connexions incluent des références à l’utilisateur qui les crée. L’utilisateur peut supprimer ces références à tout moment en suivantes les étapes suivantes :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com), sélectionnez l’icône d’engrenage, puis sélectionnez **connexions**.

    ![Supprimer l’événement](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Sélectionnez la connexion que vous souhaitez supprimer, sélectionnez **...** , puis sélectionnez **supprimer**.

    ![Supprimer l’événement](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Sélectionnez l’icône **supprimer** dans l’invite de confirmation.

    ![Supprimer l’événement](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Si d’autres flux utilisent la connexion, vous êtes en train de supprimer, vous êtes averti qu’une nouvelle connexion est requise. Dans le cas contraire, sélectionnez **supprimer** pour continuer.
>
>

## <a name="learn-more"></a>Pour en savoir plus

* Prise en main de [Microsoft Flow](getting-started.md)
* Découvrez [les](release-notes.md) nouveautés de Microsoft Flow
