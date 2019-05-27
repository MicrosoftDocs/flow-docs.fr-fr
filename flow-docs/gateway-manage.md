---
title: Gérer les passerelles de données locales | Microsoft Docs
description: Afficher et installer une passerelle de données locale dans Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/05/2018
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b8b14f720736a60b04cbd9ae23dec5c0524ff03c
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65054059"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gérer une passerelle de données locale dans Microsoft Flow

Installez et gérez une passerelle de données locale pour intégrer en toute sécurité plusieurs applications cloud avec vos données et applications locales par le biais de Microsoft Flow.

Une passerelle vous permet de vous connecter à des données locales sur ces connexions :

* Apache Impala
* Connecteurs personnalisés créés par vos soins
* DB2
* Système de fichiers
* HTTP avec Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (préversion)

> [!IMPORTANT]
> Les passerelles de données Microsoft SharePoint prennent maintenant en charge le trafic HTTP et HTTPS.

## <a name="prerequisites"></a>Prérequis

* Nom d’utilisateur et mot de passe que vous avez utilisés pour vous [inscrire](sign-up-sign-in.md) à Microsoft Flow.
* Autorisations d’administration sur une passerelle.

  Ces autorisations sont octroyées par défaut au moment de l’installation d’une passerelle. L’administrateur d’une passerelle peut aussi les accorder à quelqu’un d’autre pour la passerelle en question.
* Licence qui prend en charge les passerelles. Pour plus d’informations, consultez la section « Connectivité » de la [page sur la tarification](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Vous pouvez créer une passerelle et une connexion locale uniquement dans votre [environnement par défaut](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Installer une passerelle

1. Téléchargez l’[Assistant d’installation de la passerelle](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).

1. Exécutez l’Assistant et entrez les informations d’identification avec lesquelles vous avez établi la connexion à Microsoft Flow.

    Après l’inscription et la configuration, la passerelle s’affiche dans la liste **Mes passerelles** de Microsoft Flow.

## <a name="view-your-gateways"></a>Afficher vos passerelles

Dans l’angle supérieur droit du [site web Microsoft Flow](https://flow.microsoft.com), sélectionnez l’icône d’engrenage, puis **Passerelles**.

![Passerelle sous gestion][1]

> [!NOTE]
> Les passerelles que vous avez créées ou auxquelles vous avez obtenu l’accès dans PowerApps apparaissent dans la liste **Mes passerelles** de Microsoft Flow.


## <a name="cluster-your-gateways"></a>Vos passerelles du cluster

Vous pouvez créer *clusters à haute disponibilité des installations de passerelle de données locales* afin d’éviter les points uniques de défaillance dans l’accès aux ressources de données en local. 

Par défaut, Microsoft Flow utilise la passerelle principale du cluster. Si la passerelle principale n’est pas disponible, le service bascule vers la passerelle suivante dans le cluster et ainsi de suite.

Une fois que vous avez configuré un cluster de passerelle, vous pouvez autoriser le trafic doit être réparti entre toutes les passerelles dans le cluster. 

Suivez ces étapes pour répartir le trafic sur vos passerelles :

1. Sélectionnez **données** sur la barre de navigation sur le côté gauche.
1. Sélectionnez **passerelles**.
1. Sélectionnez un de vos passerelles.
1. Sélectionnez **répartir les demandes entre toutes les passerelles actives dans ce cluster**.
1. Sélectionnez **appliquer** pour enregistrer vos modifications.


Pour plus d’informations, consultez [Comprendre les passerelles](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
