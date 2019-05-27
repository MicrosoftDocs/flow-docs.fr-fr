---
title: Découverte des requêtes RGPD des personnes concernées avec Microsoft Flow | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux requêtes de découverte RGPD des personnes concernées.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 9ec66eefdbf2f6b6a9047678e9c29cb66900eda2
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64454087"
---
# <a name="responding-to-gdpr-data-subject-discovery-requests-for-microsoft-flow"></a>Répondre aux requêtes de découverte RGPD des personnes concernées avec Microsoft Flow

La première étape pour répondre à une DSR consiste à identifier les données personnelles qui font l’objet de la requête. Cette première étape vous aide à déterminer si une DSR répond aux exigences de votre organisation, ce qui vous permet alors d’accepter ou de refuser une requête DSR. Par exemple, après avoir identifié et examiné les données personnelles en question, vous pouvez décider que la requête ne répond pas aux exigences de votre organisation car elle risque de porter atteinte aux droits et libertés d’autres personnes.

Voici un résumé des types de ressources Microsoft Flow contenant des données personnelles pour un utilisateur spécifique.

|**Ressources contenant des données personnelles**|**Objectif**|
|-----|-----|
|Journaux générés par le système|Données de télémétrie qui consignent les événements système et l’historique.|
|Historique des exécutions|Historique de chaque exécution de flux au cours des 28 derniers jours. Ces données incluent l’heure de début, l’heure de fin, l’état et toutes les informations d’entrée/sortie du flux. [En savoir plus](https://flow.microsoft.com/blog/download-history-recurrence/)|
|Flux d'activités| Fournit un récapitulatif des activités du flux, y compris l’état de l’exécution, les échecs et les notifications.|
|Tâches de l’utilisateur|Invisibles pour l’utilisateur, ces tâches système sont effectuées pour le compte d’un utilisateur afin d’exécuter les flux.|
|Flux|Logique du workflow appliquée à un flux. [En savoir plus](https://docs.microsoft.com/flow/get-started-logic-flow)|
|Autorisations de flux|Les flux peuvent être partagés et réassignés à d’autres utilisateurs. Il existe des listes d’autorisations pour tous les flux. [En savoir plus](https://docs.microsoft.com/flow/frequently-asked-questions#can-i-share-the-flows-i-create)|
|Détails de l’utilisateur|Informations invisibles par l’utilisateur et qui permettent l’exécution du flux.|
|Connexions|Informations utilisées par les connecteurs et assurant la connectivité avec les API, systèmes, bases de données, etc. [En savoir plus](https://docs.microsoft.com/flow/add-manage-connections)|
|Autorisations de connexion|Autorisations pour une connexion spécifique. [En savoir plus](https://docs.microsoft.com/flow/add-manage-connections)|
|Connecteurs personnalisés|Connecteurs personnalisés qu’un utilisateur a créés et publiés, assurant la connectivité avec des systèmes tiers ou personnalisés. [En savoir plus](https://docs.microsoft.com/connectors/custom-connectors/)|
|Autorisations des connecteurs personnalisés|Listes des autorisations pour les connecteurs personnalisés. [En savoir plus](https://docs.microsoft.com/connectors/custom-connectors/share)|
|Passerelle|Les passerelles représentent des services de données locaux qui peuvent être installés par un utilisateur pour transférer des données rapidement et en toute sécurité entre Microsoft Flow et une source de données qui ne figure pas dans le cloud. [En savoir plus](https://docs.microsoft.com/flow/gateway-manage)|
|Autorisations de passerelle|Les passerelles peuvent être partagées avec des utilisateurs au sein d’une organisation. [En savoir plus](https://go.microsoft.com/fwlink/?linkid=872249)|
