---
title: Microsoft Flow les demandes de fermeture de compte d’objet des données RGPD pour les comptes Microsoft (MSA) | Microsoft Docs
description: Apprenez à utiliser Microsoft Flow pour répondre aux demandes de fermeture de compte d’objet de données RGPD pour les comptes Microsoft.
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
ms.openlocfilehash: 8665148baf4d752f1f384670b296a66bbfca6163
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548021"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Réponse aux demandes de fermeture de compte d’objet de données RGPD pour Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le **droit d’effacer** des données personnelles est la protection des clés dans le RGPD. Ce droit comprend la suppression de toutes les données personnelles, à l’exception des informations du journal d’audit. Lorsque les utilisateurs décident de fermer leur compte Microsoft (MSA), les données sous-jacentes de l’utilisateur sont également supprimées.

Ces ressources contiennent des données personnelles qui sont automatiquement supprimées lorsqu’un utilisateur ferme un MSA :

|Ressources contenant des données personnelles|
|------|
|Activité du produit et du service|
|historique des exécutions|
|Trouvent|
|Flux d’activités|
|Détails de l’utilisateur|
|Connexions|

## <a name="account-close-requests"></a>Demandes de fermeture de compte

Ces étapes décrivent comment fournir des demandes de fermeture de compte libre-service pour RGPD.

1. Connectez-vous au [compte Microsoft fermez le portail](https://go.microsoft.com/fwlink/?LinkId=523898) à l’aide de votre compte Microsoft, puis sélectionnez **suivant**.

    > [!NOTE]
    > Vous êtes rappelé d’annuler les abonnements existants ou d’exporter les données des services existants auxquels vous vous êtes abonné.
    >
    >

    ![Annuler les abonnements](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirmez que vous comprenez l’impact de la fermeture de votre MSA, puis sélectionnez **marquer le compte pour la clôture**.

    Une notification s’affiche, indiquant que votre compte sera fermé dans 30 jours. Vous pouvez rouvrir ce compte à tout moment pendant cette période de 30 jours.

    ![Compte fermé](./media/gdpr-dsr-delete-msa/accountclosed.png)

    À la fin de cette période de 30 jours, le processus de suppression de toutes les ressources de Microsoft Flow pour ce MSA démarre.

## <a name="learn-more"></a>Pour en savoir plus

* Prise en main de [Microsoft Flow](getting-started.md)
* Découvrez [les](release-notes.md) nouveautés de Microsoft Flow
