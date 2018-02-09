---
title: "Microsoft Flow pour les développeurs en entreprise, les ISV et les partenaires | Microsoft Docs"
description: "Introduction au développement de solutions pour Microsoft Flow."
services: 
suite: flow
documentationcenter: na
author: mgblythe
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: mblythe
ms.openlocfilehash: 3e6a6e0e369f8d89dcf834b4225dfd5aa4758dd7
ms.sourcegitcommit: b943fa83d7ca2d1a313c0c7b2cf0d7e4a9528b85
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2018
---
# <a name="microsoft-flow-for-enterprise-developers-isvs-and-partners"></a>Microsoft Flow pour les développeurs en entreprise, les ISV et les partenaires

En tant que développeur, vous pouvez étendre Microsoft Flow, de façon à obtenir des solutions encore plus puissantes pour les organisations et les clients.

## <a name="microsoft-flow-for-enterprise-developers"></a>Microsoft Flow pour les développeurs d’entreprise

En tant que développeur en entreprise, aidez votre organisation à générer des solutions personnalisées et robustes sur Microsoft Flow :

- **Développez des connecteurs personnalisés** pour vous connecter aux données et aux services web de votre organisation par le biais de Microsoft Flow. [En savoir plus](https://docs.microsoft.com/connectors/custom-connectors/)

- **Élaborez des fonctions Azure Functions** pour enrichir les applications d’une logique personnalisée côté serveur. [En savoir plus](https://docs.microsoft.com/azure/azure-functions/functions-flow-scenario)

- **Incorporez Microsoft Flow** directement dans vos expériences de site web pour créer des solutions intégrées, en exposant les workflows et les processus que les membres de votre organisation utilisent déjà dans le cadre de leur travail. [En savoir plus](embed-flow-dev.md)

## <a name="microsoft-flow-for-isvs-and-microsoft-partners"></a>Microsoft Flow pour les éditeurs de logiciels indépendants et les partenaires Microsoft

Si vous êtes partenaire Microsoft ou éditeur de logiciels indépendant (ISV), accélérez la phase d’adoption de vos clients en étendant vos produits pour intégrer leurs données et leurs processus métier, et ajouter et personnaliser les flux de travail pour automatiser les processus métier dans votre application. Après avoir suivi les sept étapes ci-dessous, votre application pourra tirer parti d’un solide moteur de flux de travail à l’échelle du cloud capable de se connecter à plus de 200 services différents.

| Phase | Étape | Quand la suivre ? |
| --- | --- | --- |
| Développement | 1. Créer un connecteur personnalisé à vos données | Si vous souhaitez exposer vos propres données ISV sur PowerApps ou Microsoft Flow |
| Développement | 2. Ajouter la prise en charge de votre application pour authentifier les utilisateurs avec Azure Active Directory (Azure AD) | Si vous souhaitez incorporer l’interface utilisateur de Microsoft Flow ou référencer votre application dans Microsoft AppSource | 
| Développement | 3. Incorporer l’interface utilisateur de Microsoft Flow dans votre application avec notre iframe web | Si vous souhaitez inclure la création ou la gestion de flux dans votre application | 
| Développement | 4. Créer et publier des modèles de flux | Si vous souhaitez précréer des flux pour vos clients | 
| Développement | 5. Ajouter une logique d’application pour déployer des flux par programmation | Si vous souhaitez déployer automatiquement vos flux précréés pour vos clients | 
| Distribution | 6. Accorder des licences clientes pour Microsoft Flow via le programme Fournisseur de solutions Microsoft Cloud | Si vos clients ne disposent pas de licences Office 365 ou Dynamics 365 |
| Distribution | 7. Référencer votre solution sur Microsoft AppSource | Recommandé pour augmenter la visibilité de votre solution ISV |

### <a name="1-connecting-to-your-apis-or-enabling-customers-to-connect-to-your-apis"></a>1. Connexion à vos API OU autorisation des clients à se connecter à vos API

En tant qu’éditeur ISV, vous avez généralement des données propriétaires auxquelles vous aimeriez que les clients accèdent via vos flux. Vous pouvez exposer l’accès à toutes vos données via un connecteur personnalisé. [En savoir plus](https://docs.microsoft.com/en-us/connectors/custom-connectors/)

Une fois créé, il existe deux façons de mettre le connecteur à la disposition de vos clients :
- Le connecteur peut être déployé dans le locataire des clients via les API REST ou PowerShell.
- Pour mettre le connecteur personnalisé à la disposition de tout le monde, vous pouvez soumettre votre connecteur à une certification. [En savoir plus](https://docs.microsoft.com/connectors/custom-connectors/submit-certification)

### <a name="2-authentication"></a>2. Authentification 

Pour appeler des API REST et incorporer une interface utilisateur authentifiée, votre application doit utiliser l’authentification unique fédérée Azure AD pour authentifier les utilisateurs finaux et les clients. [Rendez-vous ici](https://identity.microsoft.com/) pour plus d’informations sur l’activation de l’authentification unique fédérée AAD. Nous n’avons pas de prise en charge pour l’accès non authentifié ni pour l’accès avec des fournisseurs d’identité autres qu’Azure AD. 

### <a name="3-embedding-ui-components"></a>3. Incorporation des composants de l’interface utilisateur

Incorporez Microsoft Flow dans votre application pour une intégration profonde en contexte entre votre application et tous les autres services pris en charge par Microsoft Flow. [En savoir plus](embed-flow-dev.md)

### <a name="4-create-and-publish-flow-templates"></a>4. Créer et publier des modèles de flux

Une fois que vous avez un connecteur, vous devez publier les modèles qui illustrent l’utilisation de votre service. Ces modèles servent d’exemples qui permettent aux utilisateurs d’apprendre et d’étendre ce qu’ils auront appris à leurs propres flux de travail uniques. [En savoir plus](publish-a-template.md)

### <a name="5-deployment"></a>5. Déploiement

Pour donner aux utilisateurs finaux l’accès aux flux qu’ils peuvent utiliser automatiquement, déployez les flux dans le locataire Azure AD de l’utilisateur. Utilisez un package de déploiement que vous déployez avec nos API REST ou PowerShell. [En savoir plus](https://docs.microsoft.com/powerapps/export-import-packages)

### <a name="6-licensing"></a>6. Licences

Si vos clients disposent déjà d’Office 365 ou de Dynamics 365 et que ces licences sont associées avec les identités avec lesquelles les utilisateurs se connectent avec Azure AD, vous n’avez pas besoin d’avoir de licences supplémentaires. Par contre, si vos clients n’utilisent pas Office 365 ni Dynamics 365, vous devez obtenir des droits d’utilisation pour Microsoft Flow afin qu’ils disposent de licence et tirent parti de ces composants incorporés dans votre application.

Nous proposons le programme [Fournisseur de solutions Microsoft Cloud](https://partner.microsoft.com/en-US/cloud-solution-provider) qui permet d’acquérir des licences pour le compte de vos clients. Il existe deux [plans tarifaires](https://flow.microsoft.com/pricing/) disponibles pour Microsoft Flow, dont vous devriez consulter les détails et les fonctionnalités.

### <a name="7-list-on-appsource"></a>7. Référencer sur AppSource

Une fois que vous avez intégré Microsoft Flow dans votre application, vous pouvez référencer celle-ci sur AppSource. Avec AppSource, vous pouvez générer de nouveaux prospects pour votre entreprise en créant une application et en la publiant sur AppSource pour que les nouveaux clients puissent la tester. [En savoir plus](dev-appsource-test-drive.md)
