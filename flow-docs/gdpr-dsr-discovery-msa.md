---
title: Demandes de découverte RGPD des personnes concernées avec Microsoft Flow pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de découverte RGPD des personnes concernées pour les comptes Microsoft.
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
ms.date: 5/16/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9a7031780ed6582d9f881571c3d07ce8aece074d
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44690724"
---
# <a name="respond-to-gdpr-data-subject-discovery-requests"></a>Répondre aux demandes de découverte RGPD des personnes concernées 

La première étape pour répondre à une demande DSR consiste à trouver les données personnelles qui font l’objet de la demande.
Voici un résumé des ressources Microsoft Flow qui contiennent des données personnelles pour un utilisateur qui s’authentifie avec son compte Microsoft (MSA).

|Ressource|Objectif|
|-----|-----|
|Historique des exécutions|Fournit l’historique de chaque exécution de flux au cours des 28 derniers jours. Ces données incluent l’heure de début, l’heure de fin, l’état et toutes les informations d’entrée/sortie pour chaque exécution de flux. Découvrez plus d’informations sur [l’historique d’exécution des flux](https://flow.microsoft.com/blog/download-history-recurrence/).|
|Flux d'activités| Fournit un récapitulatif des activités de chaque flux, notamment l’état de l’exécution, les échecs et les notifications.|
|Flux|Logique du flux de travail pour un [flux](https://docs.microsoft.com/flow/get-started-logic-flow).|
|Connexions|Utilisées par les connecteurs et assurant la connectivité avec les API, les systèmes, les bases de données, etc. Découvrez plus d’informations sur les [connexions](add-manage-connections.md).|

