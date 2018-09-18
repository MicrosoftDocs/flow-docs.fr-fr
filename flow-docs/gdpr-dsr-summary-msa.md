---
title: Résumé des demandes RGPD des personnes concernées pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment répondre aux requêtes RGPD d’une personne concernée pour Microsoft Flow.
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
ms.openlocfilehash: 3742ac7afed24b0a1523a6038978589d293ba00b
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44688487"
---
# <a name="respond-to-gdpr-data-subject-rights-dsrs-requests"></a>Répondre aux demandes RGPD de droits des personnes concernées

Cet article décrit le Règlement général sur la protection des données (RGPD) de l’Union européenne et fournit les étapes que vous pouvez suivre pour prendre en charge la conformité au RGPD pour les utilisateurs Microsoft Flow qui s’authentifient avec les comptes Microsoft (MSA).

## <a name="prerequisites"></a>Prérequis

Vous avez besoin d’un compte de service administré avec une [licence Microsoft Flow gratuite](https://flow.microsoft.com/pricing/) pour effectuer les étapes de cet article.

>[!TIP]
> Des informations sur la conformité à RGPD sont également disponibles pour les utilisateurs qui s’authentifient avec des [comptes Azure Active Directory](gdpr-dsr-summary.md).
>
>

## <a name="respond-to-dsrs-for-microsoft-flow-customer-data"></a>Répondre aux demandes de droits des personnes concernées pour les données des clients Microsoft Flow

Une demande formelle d’une personne concernée à un contrôleur pour effectuer une action sur ses données personnelles est appelée demande de droits de la personne concernée (DSR, Data Subject Rights). Le RGPD définit les données personnelles comme étant **toute donnée relative à une personne physique identifiée ou identifiable**. Le RGPD octroie à des personnes (également appelées « personnes concernées ») des droits pour gérer les données personnelles qui ont été collectées par un employeur, une entité ou une organisation (également appelé « contrôleur de données » ou tout simplement « contrôleur »). Ces droits sont les suivants :

* Obtenir une copie des données personnelles.
* Demander des corrections des données personnelles.
* Limiter le traitement des données personnelles.
* Supprimer des données personnelles.
* Recevoir les données personnelles dans un format électronique, de façon à pouvoir les déplacer vers un autre contrôleur.

Microsoft fournit des produits, des services et des outils pour aider les contrôleurs à rechercher et à agir sur les données personnelles en réponse à des demandes DSR pour des données qui se trouvent dans le cloud.

Voici une vue d’ensemble des processus présentés dans ce guide :

1. **Découvrir** : utiliser des outils de recherche et de découverte pour trouver facilement les données des clients pouvant faire l’objet d’une demande DSR. Si vous déterminez que les documents que vous collectez répondent aux directives de votre contrôleur justifiant une action, vous pouvez effectuer une ou plusieurs des actions DSR décrites dans les étapes suivantes. Découvrez plus d’informations dans la [documentation sur la découverte DSR de Microsoft Flow pour les comptes Microsoft](gdpr-dsr-discovery-msa.md). Vous pouvez aussi déterminer que la demande ne satisfait pas aux directives de votre contrôleur en matière de réponse aux demandes DSR.

1. **Accéder** : récupérer les données personnelles qui se trouvent dans le cloud Microsoft et, si c’est demandé, effectuer une copie de celles-ci de façon à les mettre à disposition de la personne concernée.

1. **Rectifier** : apporter des modifications ou implémenter d’autres actions demandées sur les données personnelles, là où c’est applicable.

1. **Restreindre** : limiter le traitement des données personnelles, en supprimant les licences pour différents services en ligne ou en désactivant les services souhaités quand c’est possible. Vous pouvez également supprimer les données du cloud Microsoft et les conserver localement ou dans un autre emplacement.

1. **Supprimer** : supprimer définitivement des données personnelles qui se trouvent dans le cloud Microsoft. Découvrez plus d’informations sur la [suppression des données personnelles pour les comptes Microsoft](gdpr-dsr-delete-msa.md). Découvrez plus d’informations sur la [fermeture d’un compte Microsoft](gdpr-dsr-accountclose-msa.md).

1. **Exporter** : fournir une copie électronique des données personnelles (dans un format lisible par une machine). [Découvrez plus d’informations sur l’exportation des données personnelles pour les comptes Microsoft](gdpr-dsr-export-msa.md).
