---
title: Demandes de fermeture de compte RGPD des personnes concernées avec Microsoft Flow pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de fermeture de compte RGPD des personnes concernées pour les comptes Microsoft.
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
ms.openlocfilehash: be12491490cac51a0b91906b1a663522c2a7658f
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688763"
---
# <a name="responding-to-gdpr-data-subject-account-close-requests-for-microsoft-flow"></a>Répondre aux demandes de fermeture de compte RGPD des personnes concernées pour Microsoft Flow

Le **droit d’effacer** des données personnelles est une protection fondamentale dans le RGPD. Ce droit inclut la suppression de toutes les données personnelles, à l’exception des informations du journal d’audit. Quand un utilisateur décide de fermer son compte Microsoft (MSA), ses données sous-jacentes sont également supprimées.

Ces ressources contiennent des données personnelles qui sont automatiquement supprimées quand un utilisateur ferme un compte de service administré :

|Ressources contenant des données personnelles|
|------|
|Activité de produits et de services|
|Historique des exécutions|
|Flux|
|Flux d’activité|
|Détails de l’utilisateur|
|Connexions|

## <a name="account-close-requests"></a>Demandes de fermeture de compte

Ces étapes décrivent comment effectuer soi-même des demandes de fermeture de compte pour RGPD.

1. Connectez-vous au [portail de fermeture de compte Microsoft](http://go.microsoft.com/fwlink/?LinkId=523898) avec votre compte Microsoft, puis sélectionnez **Suivant**.

    > [!NOTE]
    > Il vous est rappelé d’annuler les abonnements existants ou d’exporter les données des services existants auxquels vous vous êtes abonné.
    >
    >

    ![Annuler les abonnements](./media/gdpr-dsr-delete-msa/accountclose.png)

1. Confirmez que vous comprenez l’impact de la fermeture de votre compte de service administré, puis sélectionnez **Marquer le compte pour clôture**.

    Une notification apparaît, indiquant que votre compte sera fermé dans 30 jours. Vous pouvez rouvrir ce compte à tout moment au cours de cette période de 30 jours.

    ![Compte fermé](./media/gdpr-dsr-delete-msa/accountclosed.png)

    À la fin de cette fenêtre de 30 jours, le processus de suppression de toutes les ressources Microsoft Flow pour ce compte de service administré commence.

## <a name="learn-more"></a>En savoir plus

* Prise en main de [Microsoft Flow](getting-started.md)
* Découvrez [les nouveautés](release-notes.md) de Microsoft Flow
