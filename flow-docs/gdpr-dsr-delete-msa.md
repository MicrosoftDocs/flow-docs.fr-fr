---
title: Demandes de suppression RGPD des personnes concernées avec Microsoft Flow pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de suppression RGPD des personnes concernées pour les comptes Microsoft.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: KFile
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: e42da775d5c004bfbe0d6bb8923e6d05aaa5e976
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688970"
---
# <a name="respond-to-gdpr-data-subject-delete-requests"></a>Répondre aux demandes de suppression RGPD des personnes concernées

Le **droit d’effacer** par suppression des données personnelles est une protection fondamentale dans le RGPD. La suppression des données personnelles inclut la suppression de toutes les données personnelles, à l’exception des informations du journal d’audit.

Microsoft Flow permet aux utilisateurs de créer des flux de travail automatisés. Quand un utilisateur décide de supprimer ses données personnelles de Microsoft Flow, il peut examiner ses données personnelles et déterminer s’il faut ou non supprimer tout ou partie de celles-ci.

Le tableau suivant indique quelles données personnelles sont automatiquement supprimées, et celles qu’un utilisateur avec un compte Microsoft (MSA) doit examiner et supprimer manuellement.

|Nécessite l’examen et la suppression par l’utilisateur MSA|Supprimé automatiquement|
|------|------|
|Activité de produits et de services|Historique des exécutions|
|Flux|Flux d’activité|
|Connexions||

Microsoft Flow offre les expériences suivantes, qui permettent aux utilisateurs de rechercher, d’examiner ou de modifier des données et des ressources personnelles qui ne sont pas supprimées automatiquement :

## <a name="manage-delete-requests"></a>Gérer les requêtes de suppression

Les étapes ci-dessous décrivent comment effectuer soi-même des demandes de suppression pour RGPD.

### <a name="delete-product-and-service-activity"></a>Supprimer l’activité des produits et des services

1. Connectez-vous au [Tableau de bord de confidentialité Microsoft](https://account.microsoft.com/privacy/) avec votre compte de service administré.
1. Sélectionnez le lien **Historique des activités**.

    ![Historique des activités](./media/gdpr-dsr-export-msa/activityhistory.png)

1. Vous pouvez parcourir ou faire des recherches dans l’historique de vos activités pour les différents services et applications Microsoft que vous utilisez, notamment Microsoft Flow. Sélectionnez **Supprimer** pour supprimer les événements des activités de produits ou de services spécifiques.

    ![Supprimer un événement](./media/gdpr-dsr-delete-msa/deleteevent.png)

1. Après quelques instants, l’élément est supprimé et disparaît du tableau de bord de confidentialité.

### <a name="list-and-delete-flows"></a>Lister et supprimer des flux

Un utilisateur peut lister et supprimer ses flux de [Microsoft Flow](https://flow.microsoft.com) en suivant ces étapes :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **Mes flux**.

1. Sélectionnez **...** à côté du flux que vous voulez supprimer, puis sélectionnez **Supprimer**.

    ![Supprimer un événement](./media/gdpr-dsr-delete-msa/deleteflow.png)

### <a name="delete-connections"></a>Supprimer des connexions

Les connecteurs utilisent des connexions pour communiquer avec des API et des systèmes SaaS. Les connexions incluent des références à l’utilisateur qui les crée. L’utilisateur peut supprimer ces références à tout moment en suivant ces étapes :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), sélectionnez l’icône d’engrenage, puis sélectionnez **Connexions**.

    ![Supprimer un événement](./media/gdpr-dsr-delete-msa/deleteconnections.png)

1. Sélectionnez la connexion que vous voulez supprimer, sélectionnez **...**, puis sélectionnez **Supprimer**.

    ![Supprimer un événement](./media/gdpr-dsr-delete-msa/delete-connection.png)

1. Sélectionnez l’icône **Supprimer** à l’invite de confirmation.

    ![Supprimer un événement](./media/gdpr-dsr-delete-msa/confirmdelete.png)

> [!NOTE]
> Si d’autres flux utilisent la connexion que vous supprimez, vous êtes averti qu’une nouvelle connexion est nécessaire. Sinon, sélectionnez **Supprimer** pour continuer.
>
>

## <a name="learn-more"></a>En savoir plus

* Prise en main de [Microsoft Flow](getting-started.md)
* Découvrez [les nouveautés](release-notes.md) de Microsoft Flow
