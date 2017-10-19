---
title: "Gérer les passerelles de données locales | Microsoft Docs"
description: "Afficher et installer une passerelle de données locale dans Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: deonhe
ms.openlocfilehash: 41f5d40ca2ad5fcce3a7967beef7104dd532b1d8
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="manage-an-on-premises-data-gateway-in-microsoft-flow"></a>Gérer une passerelle de données locale dans Microsoft Flow
Installez et gérez une passerelle de données locale pour intégrer en toute sécurité plusieurs applications cloud avec vos données et applications locales par le biais de Microsoft Flow.

Une passerelle vous permet de vous connecter à des données locales sur ces connexions :

* SharePoint
* SQL Server
* Oracle
* Informix
* Système de fichiers
* DB2

> [!IMPORTANT]
> Les passerelles de données Microsoft SharePoint prennent en charge le trafic HTTP, mais pas le trafic HTTPS.
> 
> 

## <a name="prerequisites"></a>Conditions préalables
* Nom d’utilisateur et mot de passe que vous avez utilisés pour vous [inscrire](sign-up-sign-in.md) à Microsoft Flow.
* Autorisations d’administration sur une passerelle.
  
  Vous avez ces autorisations par défaut pour chaque passerelle que vous installez, et l’administrateur d’une autre passerelle peut vous accorder ces autorisations pour cette passerelle.
* Licence qui prend en charge les passerelles. Pour plus d’informations, consultez la section « Connectivité » de la [page sur la tarification](https://flow.microsoft.com/pricing/).
* Vous pouvez créer une passerelle et une connexion locale uniquement dans votre [environnement par défaut](environments-overview-maker.md).

## <a name="view-your-gateways"></a>Afficher vos passerelles
Dans l’angle supérieur droit du [site web Microsoft Flow](https://flow.microsoft.com), cliquez ou appuyez sur l’icône d’engrenage, puis sur **Passerelles**.

![Passerelle sous gestion][1]

**Remarque** : si vous avez créé une passerelle ou obtenu un accès à celle-ci dans PowerApps, la passerelle s’affiche dans la liste **Mes passerelles** dans Microsoft Flow.

## <a name="install-a-gateway"></a>Installer une passerelle
1. Téléchargez l’[Assistant d’installation de la passerelle](http://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409).
   
    Vous pouvez également télécharger cet Assistant en cliquant ou en appuyant sur l’icône d’engrenage dans le coin supérieur droit du [site web Microsoft Flow](https://flow.microsoft.com), en cliquant ou en appuyant sur **Passerelles**, puis sur **Créer une passerelle**.
   
    ![Installation de la passerelle][2]
2. Exécutez l’Assistant en fournissant les informations d’identification avec lesquelles vous vous êtes connecté à Microsoft Flow.
   
    Une fois que vous avez correctement inscrit et configuré votre passerelle, celle-ci s’affiche dans la liste **Mes passerelles** dans Microsoft Flow.

Pour plus d’informations, consultez [Comprendre les passerelles](gateway-reference.md).

<!-- Image references -->
[1]: ./media/manage-gateway/view-gateways.png
[2]: ./media/manage-gateway/list-gateways.png
