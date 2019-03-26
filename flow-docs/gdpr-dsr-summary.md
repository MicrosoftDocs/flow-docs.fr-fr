---
title: Résumé des requêtes RGPD de personnes concernées | Microsoft Docs
description: Découvrez comment répondre aux requêtes RGPD d’une personne concernée pour Microsoft Flow.
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
ms.date: 4/24/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 1eaa98b674e78f46988d253e2be76a5d92283a76
ms.sourcegitcommit: 24da014ea8db8e59f097c4622d1e2cca9a4d1709
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58353122"
---
# <a name="responding-to-gdpr-data-subject-requests-for-microsoft-flow"></a>Répondre aux requêtes RGPD d’une personne concernée pour Microsoft Flow

Cet article vous prépare, vous et votre organisation, aux directives du Règlement général sur la protection des données (RGPD) de l’Union européenne. Non seulement cet article décrit ce que Microsoft fait pour préparer l’environnement RGPD, mais il fournit également des exemples d’étapes que vous pouvez effectuer dès aujourd’hui pour garantir la conformité au RGPD lors de l’utilisation de PowerApps, de Microsoft Flow et de Common Data Service.

## <a name="prerequisites"></a>Prérequis

Les utilisateurs et les administrateurs peuvent effectuer les actions décrites dans cet article.

### <a name="users"></a>Utilisateurs

Un utilisateur doit avoir un compte Azure Active Directory actif ainsi qu’une [licence Microsoft Flow](https://preview.flow.microsoft.com/pricing/). Les utilisateurs qui ne remplissent pas cette condition doivent demander à un administrateur d’effectuer ces actions.

### <a name="administrators"></a>Administrateurs

Vous pouvez effectuer les opérations nécessitant des privilèges d’administrateur, présentées dans cet article, lorsque vous vous connectez au [Centre d’administration de Microsoft Flow](https://admin.flow.microsoft.com/) ou à [PowerApps Admin PowerShell](https://go.microsoft.com/fwlink/?linkid=871804) avec un compte disposant de ces deux autorisations :

- Une licence complète ou d’évaluation pour PowerApps Plan 2.

    [Une licence d’évaluation](http://web.powerapps.com/trial) expire dans 30 jours.

- [Administrateur général Office 365](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) ou [Administrateur général Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal).

### <a name="unmanaged-tenants"></a>Locataires non gérés
Si vous êtes membre d’un [locataire non géré](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover), ce qui signifie que votre locataire Azure AD n’a pas d’administrateur général, vous serez néanmoins en mesure de suivre les étapes décrites dans cet article pour exporter et supprimer vos propres données personnelles. 

## <a name="responding-to-dsrs-for-microsoft-flow-customer-data"></a>Répondre aux DSR pour les données client Microsoft Flow

Le système RGPD octroie à des personnes (également appelées « personnes concernées ») des droits pour gérer les données personnelles qui ont été collectées par un employeur ou autre type d’entité ou organisation (également appelé contrôleur de données ou tout simplement contrôleur). Les données personnelles sont définies de façon très large dans RGPD et désignent toutes les données relatives à une personne physique identifiée ou identifiable. Le système RGPD confère aux personnes concernées des droits spécifiques sur leurs données personnelles ; ces droits incluent l’obtention de copies de ces données personnelles, la possibilité de les corriger, de les traiter de manière restreinte, de les supprimer ou de les recevoir dans un format électronique afin de pouvoir les transférer vers un autre contrôleur. Une demande formelle transmise par une personne concernée à un contrôleur pour effectuer une action sur ses données personnelles est appelée demande DSR (Data Subject Rights).

Cet article explique comment utiliser les produits, services et outils d’administration Microsoft pour aider les contrôleurs à rechercher et à traiter les données personnelles en réponse à des demandes DSR. Tout particulièrement, il décrit comment rechercher, afficher et modifier les données personnelles qui résident dans le cloud Microsoft. Voici un aperçu des processus présentés dans ce guide :

1. Découvrir : utiliser les outils de recherche et de découverte pour trouver plus facilement les données client pouvant faire l’objet d’une demande DSR. Une fois les documents pouvant faire l’objet d’une réponse collectés, vous pouvez effectuer une ou plusieurs des actions DSR décrites dans les étapes suivantes pour répondre à la demande. Ou bien, vous pouvez décider que la demande ne répond pas aux directives de votre organisation en matière de réponse aux demandes DSR. [Documentation sur la découverte DSR Microsoft Flow](gdpr-dsr-discovery.md)

1. Accéder : récupérer les données personnelles qui résident dans le cloud Microsoft et, le cas échéant, effectuer une copie de celles-ci pouvant être mise à la disposition du titulaire des données.

1. Rectifier : apporter des modifications ou implémenter d’autres actions demandées sur les données personnelles, là où c’est applicable.

    Si une personne concernée vous demande de corriger ses données personnelles résidant dans votre organisation, vous et votre organisation devez déterminer s’il est judicieux de répondre favorablement à la demande.  La correction des données peut inclure des actions telles que la modification ou la suppression de données personnelles.

    Vous pouvez utiliser Azure Active Directory pour gérer les identités des utilisateurs Microsoft Flow. Les clients Entreprise peuvent gérer les demandes de rectification DSR, y compris avec des fonctionnalités d’édition limitées, selon la nature d’un service Microsoft donné.  En tant que processeur de données, Microsoft n’offre pas la possibilité de corriger les journaux générés par le système, car ces journaux reflètent des activités factuelles et constituent un enregistrement de l’historique des événements dans les services Microsoft.  [En savoir plus sur DSR](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure).

1. Restreindre : limiter le traitement des données personnelles, en supprimant les licences pour différents services en ligne ou en désactivant les services souhaités quand c’est possible. Vous pouvez également supprimer les données du cloud Microsoft et les conserver localement ou dans un autre emplacement.

    Les personnes concernées peuvent demander à limiter le traitement de leurs données personnelles.  Microsoft fournit des interfaces de programmation d’application (API) et des interfaces utilisateur (UI) à cet effet.  Ces interfaces permettent à l’administrateur d’un client Entreprise de gérer ces demandes DSR de façon anonyme en utilisant une combinaison d’exportation et de suppression des données. Un client peut exporter (1) une copie électronique des données personnelles de l’utilisateur, y compris les comptes, les journaux générés par le système et journaux associés, puis (2) supprimer le compte et les données associées résidant dans les systèmes Microsoft.

1. Supprimer supprimer définitivement des données personnelles qui se trouvent dans le cloud Microsoft. [En savoir plus sur la suppression des données personnelles](gdpr-dsr-delete.md).

1. Exporter : fournir une copie électronique (dans un format lisible par machine) des données personnelles au titulaire des données. Chaque section de cet article décrit les procédures techniques qu’une organisation de contrôle des données peut prendre pour répondre à une demande DSR affectant les données personnelles dans le cloud Microsoft. [En savoir plus sur l’exportation des données personnelles](gdpr-dsr-export.md).

## <a name="system-generated-logs"></a>Journaux générés par le système

Consultez ce [guide](https://docs.microsoft.com/powerapps/administrator/powerapps-gdpr-dsr-guide-systemlogs) pour plus d’informations sur les journaux générés par le système pour Microsoft Flow.
