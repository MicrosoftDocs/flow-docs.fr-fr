---
title: Application mobile Microsoft Flow prend désormais en charge la gestion des applications mobiles de Microsoft Intune. | Microsoft Docs
description: Application mobile Microsoft Flow prend désormais en charge la gestion des applications mobiles de Microsoft Intune.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/29/2019
ms.author: deonhe
ms.openlocfilehash: 7cc2b37eb27ed0e2107eeaada02afb072d9a0098
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65060488"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Application mobile Microsoft Flow prend en charge Microsoft Intune

L’application mobile Microsoft Flow pour iOS et Android prend en charge Mobile Application Management (MAM d’Intune) sans inscription d’appareils. À l’aide de la gestion des applications mobiles permet aux administrateurs de créer et appliquer des stratégies de données des appareils mobiles pour protéger les données de l’organisation.

## <a name="why-intune-support-is-important"></a>Pourquoi le support technique Intune est important

Les organisations recherchent pour mieux contrôler les données qui résident sur les appareils mobiles des employés. Les organisations souhaiterez peut-être limiter la façon dont ces données se déplacent vers l’appareil et vous assurer que les données sont supprimées, doit les employés quittent l’organisation.

## <a name="what-is-microsoft-application-management-mam"></a>Qu’est Microsoft Application Management (MAM)

Gestion des applications mobiles permet aux organisations de créer des stratégies qui régissent la façon dont les applications sont utilisées au sein d’un locataire. Cela inclut l’aide du chiffrement de données d’application, limitant la capacité à copier ou extraire des données à des applications approuvées ou en appliquant un code confidentiel sur un appareil.

### <a name="prerequisites"></a>Prérequis

- Un Intune [stratégie de protection des applications](https://docs.microsoft.com/intune/app-protection-policies).
- Un groupe Azure Active Directory (Azure AD).
- Portail d’entreprise. Présente l’avantage majeur d’à l’aide de la gestion des applications mobiles est que les appareils n’avez pas besoin d’être inscrits dans Intune MAM. Tout ce qui est nécessaire est le portail d’entreprise, qui est disponible à partir de l’App Store et Google Play store.
- Version 2.31.0 de l’application mobile Microsoft Flow pour iOS, Android ou Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Créer une stratégie de protection des applications, affecter des applications à la stratégie, définir des paramètres et ajouter des utilisateurs à un groupe Azure AD

Pour l’application mobile Microsoft Flow à gérer, vous devez :

1. Créer une stratégie de protection d’application.
1. Affecter l’application mobile Microsoft Flow à la stratégie de protection d’application.
1. Affecter les paramètres de stratégie. Par exemple, vous pouvez affecter la stratégie pour exiger un code confidentiel pour accéder à l’appareil mobile qui s’exécute l’application mobile Microsoft Flow.
1. Appliquer la stratégie de protection d’application à spécifique à un groupe Azure AD.
1. Ajouter tous les utilisateurs auxquels la stratégie de protection d’application s’applique au groupe Azure AD.

Suivez ces étapes pour créer un [stratégie de protection des applications](https://docs.microsoft.com/intune/app-protection-policies) qui requiert des utilisateurs de l’application mobile Microsoft Flow à entrer un code confidentiel pour accéder à l’application. 


## <a name="test-the-app-protection-policy"></a>Tester la stratégie de protection d’application

Une fois que vous avez créé la stratégie de protection des applications et utilisateurs affectés au groupe Azure AD, il est temps à utiliser l’application mobile Microsoft Flow et à confirmer cette stratégie s’applique.

Pour vérifier que cette stratégie s’applique, procédez comme suit :

1. Installer l’application mobile Microsoft Flow sur un appareil dont la plateforme correspond à l’une des plateformes que vous avez défini dans la stratégie de protection d’application.
1. Connectez-vous à l’application mobile avec un compte qui se trouve dans le groupe Azure AD qui restreint l’utilisation de l’application mobile pour les utilisateurs qui ont un code confidentiel.

Vous allez ensuite invité à :
1. Installer le portail d’entreprise.
1. Configurer votre code confidentiel si vous ne disposez pas d’un code confidentiel qui répond aux critères de la stratégie de protection.


## <a name="learn-more"></a>En savoir plus

Apprenez à créer un [stratégie de protection des applications](https://docs.microsoft.com/intune/app-protection-policies).

