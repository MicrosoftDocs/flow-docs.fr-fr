---
title: En savoir plus sur la gestion des passerelles de données locales | Microsoft Docs
description: Affichez et installez une passerelle de données locale dans Microsoft Flow.
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
ms.date: 10/16/2019
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 3991e739178f86bbea3ae1b68b9d3337c42b4727
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547665"
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gérer une passerelle de données locale dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Installez et gérez une passerelle de données locale pour intégrer en toute sécurité une variété d’applications basées sur le Cloud à vos données et applications locales par le biais de Microsoft Flow.

Avec une passerelle, vous pouvez vous connecter à des données locales via ces connexions :

* Apache Impala
* Connecteurs personnalisés que vous créez
* DB2
* Système de fichiers
* Http avec Azure AD
* Informix
* MySQL
* Oracle Database
* PostgreSQL
* SharePoint
* SQL Server
* Teradata (version préliminaire)

> [!IMPORTANT]
> Les passerelles de données Microsoft SharePoint prennent désormais en charge le trafic HTTP et HTTPs.

## <a name="prerequisites"></a>Conditions préalables

* Nom d’utilisateur et mot de passe que vous avez utilisés pour vous [inscrire](sign-up-sign-in.md) à Microsoft Flow.
* Autorisations d’administration sur une passerelle.

  Vous disposez de ces autorisations par défaut pour chaque passerelle que vous installez. En outre, un administrateur d’une autre passerelle peut vous accorder ces autorisations pour cette passerelle.
* Licence qui prend en charge les passerelles. Pour plus d’informations, consultez la section « connectivité » de la [page de tarification](https://flow.microsoft.com/pricing/).

> [!NOTE]
> Vous pouvez créer une passerelle et une connexion locale uniquement dans votre [environnement par défaut](environments-overview-maker.md).

## <a name="install-a-gateway"></a>Installer une passerelle

Pour installer une passerelle, suivez les étapes de la section [installer une passerelle de données locale](/data-integration/gateway/service-gateway-install). Installez la passerelle en mode standard, car la _passerelle de données locale (mode personnel)_ est disponible uniquement pour les Power bi.

## <a name="view-your-gateways"></a>Afficher vos passerelles

Dans l’angle supérieur droit du [site web Microsoft Flow](https://flow.microsoft.com), sélectionnez l’icône d’engrenage, puis sélectionnez **passerelles**.

![Passerelle sous gérer][1]

> [!NOTE]
> Si vous avez créé ou reçu l’accès à une passerelle dans PowerApps, cette passerelle s’affiche dans la liste **mes passerelles** dans Microsoft Flow.

## <a name="cluster-your-gateways"></a>Mise en cluster de vos passerelles

Vous pouvez créer [des clusters à haute disponibilité d’installations de passerelle de données locale](/data-integration/gateway/service-gateway-high-availability-clusters) afin d’éviter des points de défaillance uniques pour accéder aux ressources de données locales.

Par défaut, Microsoft Flow utilise la passerelle principale du cluster. Si la passerelle principale n’est pas disponible, le service bascule vers la passerelle suivante dans le cluster, et ainsi de suite.

Une fois que vous avez configuré un cluster de passerelle, vous pouvez autoriser la distribution du trafic sur toutes les passerelles du cluster.

Procédez comme suit pour répartir votre trafic entre vos passerelles :

1. Sélectionnez **données** dans la barre de navigation sur le côté gauche.
1. Sélectionnez **passerelles**.
1. Sélectionnez l’une de vos passerelles.
1. Sélectionnez **distribuer les demandes sur toutes les passerelles actives de ce cluster**.
1. Sélectionnez **appliquer** pour enregistrer vos modifications.

Pour plus d’informations, consultez [comprendre les passerelles](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
