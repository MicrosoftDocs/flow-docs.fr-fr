---
title: Microsoft Flow pour les développeurs d’entreprise, les éditeurs de logiciels indépendants et les partenaires | Microsoft Docs
description: Introduction au développement de solutions pour Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: MSFTMan
manager: KVivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: Deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: f26143533e84bc3ea8bc0784fef3c56eeb0551e1
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547824"
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow pour les développeurs d’entreprise, les éditeurs de logiciels indépendants et les partenaires
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

En tant que développeur, vous pouvez étendre Microsoft Flow, en activant des solutions encore plus puissantes pour les organisations et les clients.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow pour les développeurs d’entreprise

En tant que développeur d’entreprise, donnez à votre organisation la capacité de créer des solutions personnalisées robustes sur Microsoft Flow :

- **Créer des connecteurs personnalisés**: développez des connecteurs personnalisés pour vous connecter aux données et services Web de votre organisation par le biais de Microsoft Flow. [Pour en savoir plus](https://docs.microsoft.com/connectors/custom-connectors/)

- **Azure Functions de build : créez**des Azure Functions pour étendre les applications avec une logique personnalisée côté serveur. [Pour en savoir plus](/azure/azure-functions/app-service-export-api-to-powerapps-and-flow)

- **Incorporez Microsoft Flow**: incorporez Microsoft Flow directement dans vos expériences de site Web pour créer des solutions intégrées, en représentant des flux de travail ou des processus où les personnes de votre organisation effectuent déjà leur travail. [Pour en savoir plus](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow pour les éditeurs de logiciels indépendants et les partenaires Microsoft

En tant que partenaire Microsoft ou éditeur de logiciels indépendant (ISV), Accélérez l’adoption par les clients en étendant vos produits pour une intégration avec les données et les processus métier de vos clients, et ajoutez et personnalisez des flux de travail pour automatiser les processus d’entreprise dans le cadre de votre oeuvre. Une fois que vous avez effectué les sept étapes ci-dessous, votre application aura la possibilité de tirer parti d’un moteur de flux de travail robuste à l’échelle du Cloud, capable de se connecter à plus de 200 services différents.

| Phase | Première | Quand cela est nécessaire ? |
| --- | --- | --- |
| Développement | 1. créer un connecteur personnalisé pour vos données | Si vous souhaitez exposer vos propres données ISV à PowerApps ou Microsoft Flow |
| Développement | 2. Ajoutez la prise en charge de votre application pour authentifier les utilisateurs avec Azure Active Directory (Azure AD) | Si vous souhaitez incorporer l’interface utilisateur ou la liste Microsoft Flow dans Microsoft AppSource | 
| Développement | 3. incorporer l’interface utilisateur Microsoft Flow dans votre application à l’aide de notre iframe Web | Si vous souhaitez inclure la création ou la gestion de Flow dans votre application | 
| Développement | 4. créer et publier des modèles de Flow | Si vous souhaitez pré-créer des flux pour vos clients | 
| Développement | 5. Ajouter une logique d’application pour déployer des flux par programme | Si vous souhaitez déployer automatiquement vos flux prédéfinis pour vos clients | 
| Distributeurs | 6. accordez à vos clients des licences pour Microsoft Flow par le biais du programme fournisseur de solutions Microsoft Cloud | Si vos clients n’ont pas de licence Office 365 ou Dynamics 365 |
| Distributeurs | 7. répertoriez votre solution sur Microsoft AppSource | Recommandé pour augmenter la visibilité de votre solution ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. connexion à vos API ou activation des clients pour la connexion à vos API

En tant qu’ISV, vous avez souvent des données propriétaires auxquelles vous souhaitez que les clients accèdent via vos flux. Vous pouvez exposer l’accès à toutes vos données par le biais d’un connecteur personnalisé. [Pour en savoir plus](https://docs.microsoft.com/connectors/custom-connectors/)

Une fois créé, il existe deux façons de mettre le connecteur à la disposition de vos clients :
- Le connecteur peut être déployé dans le locataire du client via des API REST ou PowerShell.
- Pour rendre le connecteur personnalisé disponible publiquement pour tous les utilisateurs, vous pouvez soumettre votre connecteur à la certification. [Pour en savoir plus](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. authentification 

Pour appeler les API REST et incorporer l’interface utilisateur authentifiée, votre application doit utiliser Azure AD l’authentification unique fédérée pour authentifier les utilisateurs finaux et les clients. Pour plus d’informations sur l’activation de l’authentification unique fédérée AAD, [cliquez ici](https://identity.microsoft.com/) . Nous ne prenons pas en charge l’accès non authentifié ou l’accès avec des fournisseurs d’identité autres que Azure AD. 

### <a name="3-embedding-ui-components"></a>3. intégration des composants de l’interface utilisateur

Incorporez Microsoft Flow dans votre application pour permettre une intégration profonde et en contexte entre votre application et tous les autres services pris en charge par Microsoft Flow. [Pour en savoir plus](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. créer et publier des modèles de Flow

Une fois que vous disposez d’un connecteur, vous devez publier des modèles qui montrent comment utiliser votre service. Ces modèles serviront d’exemples que les utilisateurs peuvent utiliser pour apprendre et s’étendre à leurs propres flux de travail uniques. [Pour en savoir plus](../publish-a-template.md)

### <a name="5-deployment"></a>5. déploiement

Pour permettre aux utilisateurs finaux d’accéder aux flux qu’ils peuvent utiliser automatiquement, déployez les flux dans le Azure AD locataire de l’utilisateur. Utilisez un package de déploiement que vous déployez à l’aide de nos API REST ou de PowerShell. [Pour en savoir plus](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. gestion des licences

Si vos clients disposent déjà de Office 365 ou Dynamics 365, et que ces licences sont associées aux identités que les utilisateurs se connectent avec Azure AD, il n’existe aucune exigence de licence supplémentaire pour vous. Toutefois, si vos clients n’utilisent pas Office 365 ou Dynamics 365, vous devez acquérir des droits d’utilisation pour leur compte pour Microsoft Flow, afin qu’ils soient concédés sous licence pour tirer parti de ces composants incorporés dans votre application.

Nous proposons au programme [fournisseur de solutions Microsoft Cloud](https://partner.microsoft.com/cloud-solution-provider) pour acquérir des licences pour le compte de vos clients. Deux [plans de tarification](https://flow.microsoft.com/pricing/) différents sont disponibles pour Microsoft Flow, qui vous permettent de vérifier les détails des plans et des fonctionnalités.

### <a name="7-list-on-appsource"></a>7. liste sur AppSource

Une fois que vous avez intégré Microsoft Flow à votre application, vous pouvez la répertorier sur AppSource. Avec AppSource, vous pouvez générer de nouveaux prospects pour votre entreprise en créant une application et en la publiant sur AppSource pour que les nouveaux clients puissent la tester. [Pour en savoir plus](dev-appsource-test-drive.md)
