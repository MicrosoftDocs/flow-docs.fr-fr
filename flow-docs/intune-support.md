---
title: Microsoft Flow application mobile prend maintenant en charge la gestion des applications mobiles Microsoft Intune. | Microsoft Docs
description: Microsoft Flow application mobile prend maintenant en charge la gestion des applications mobiles Microsoft Intune.
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
ms.openlocfilehash: d5709d7f98c3f4cc1dcf7d0da8fc5c9501adb84c
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547393"
---
# <a name="microsoft-flow-mobile-app-supports-microsoft-intune"></a>Microsoft Flow application mobile prend en charge Microsoft Intune
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

L’application mobile Microsoft Flow pour iOS et Android prend en charge la gestion des applications mobiles (GAM) d’Intune sans inscription d’appareil. L’utilisation de GAM permet aux administrateurs informatiques de créer et d’appliquer des stratégies de données mobiles pour protéger les données organisationnelles.

## <a name="why-intune-support-is-important"></a>Pourquoi la prise en charge d’Intune est importante

Les organisations cherchent à mieux contrôler les données qui résident sur les appareils mobiles des employés. Les organisations peuvent souhaiter limiter la manière dont ces données se déplacent vers l’appareil et s’assurer que les données sont supprimées, si l’employé quitte l’organisation.

## <a name="what-is-microsoft-application-management-mam"></a>Qu’est-ce que la gestion des applications Microsoft (GAM)

GAM permet aux organisations de créer des stratégies qui régissent la façon dont les applications sont utilisées dans un locataire. Cela comprend l’application du chiffrement des données d’application, ce qui limite la possibilité de copier ou d’extraire des données vers des applications approuvées uniquement ou d’appliquer un code confidentiel sur un appareil.

### <a name="prerequisites"></a>Conditions préalables

- Une [stratégie de protection des applications](https://docs.microsoft.com/intune/app-protection-policies)Intune.
- Groupe de Azure Active Directory (Azure AD).
- Portail d'entreprise. L’un des principaux avantages de l’utilisation de GAM est que les appareils n’ont pas besoin d’être inscrits dans Intune GAM. Tout ce qui est nécessaire est le Portail d’entreprise, qui est disponible à partir de l’App Store et du magasin de Google Play.
- Version 2.31.0 de l’application mobile Microsoft Flow pour iOS, Android ou Windows Phone.

## <a name="create-an-app-protection-policy-assign-apps-to-the-policy-define-settings-and-add-users-to-an-azure-ad-group"></a>Créer une stratégie de protection des applications, affecter des applications à la stratégie, définir des paramètres et ajouter des utilisateurs à un groupe de Azure AD

Pour que l’application mobile Microsoft Flow soit gérée, vous devez effectuer les opérations suivantes :

1. Créer une stratégie de protection des applications.
1. Affectez l’Microsoft Flow application mobile à la stratégie de protection des applications.
1. Affectez les paramètres de stratégie. Par exemple, vous pouvez affecter la stratégie pour exiger un code confidentiel pour accéder au périphérique mobile qui exécute l’application mobile Microsoft Flow.
1. Appliquez la stratégie de protection des applications à un groupe de Azure AD spécifique.
1. Ajoutez tous les utilisateurs auxquels s’applique la stratégie de protection des applications au groupe Azure AD.

Suivez ces étapes pour créer une [stratégie de protection des applications](https://docs.microsoft.com/intune/app-protection-policies) qui exige que Microsoft Flow utilisateurs de l’application mobile entrent un code confidentiel avant de pouvoir accéder à l’application. 


## <a name="test-the-app-protection-policy"></a>Tester la stratégie de protection des applications

Une fois que vous avez créé la stratégie de protection des applications et affecté les utilisateurs au groupe Azure AD, il est temps d’utiliser l’application mobile Microsoft Flow et de confirmer le fonctionnement de la stratégie.

Pour confirmer le fonctionnement de la stratégie, procédez comme suit :

1. Installez le Microsoft Flow application mobile sur un appareil dont la plateforme correspond à l’une des plateformes que vous avez définies dans la stratégie de protection des applications.
1. Connectez-vous à l’application mobile avec un compte qui se trouve dans le groupe Azure AD qui limite l’utilisation de l’application mobile aux utilisateurs disposant d’un code confidentiel.

Vous serez ensuite invité à :
1. Installez le Portail d’entreprise.
1. Définissez votre code confidentiel si vous n’avez pas encore de code confidentiel qui répond aux critères de la stratégie de protection des applications.


## <a name="learn-more"></a>Pour en savoir plus

Apprenez à créer une [stratégie de protection des applications](https://docs.microsoft.com/intune/app-protection-policies).

