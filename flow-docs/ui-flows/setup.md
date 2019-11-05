---
title: Configurer des flux d’interface utilisateur sur votre appareil | Microsoft Docs
description: Configurer des flux d’interface utilisateur sur votre appareil
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
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 9e5029189df9807ba727efbe377392f87ef20884
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589679"
---
# <a name="set-up-ui-flows"></a>Configurer des flux d’interface utilisateur

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Avant de pouvoir utiliser votre appareil pour créer des flux d’interface utilisateur, vous devez vous assurer qu’il répond à la configuration requise décrite ici.

> [!TIP]
> Avant de créer un workflow d’interface utilisateur, vérifiez la [liste des connecteurs](https://flow.microsoft.com/connectors/) pour voir si l’application que vous souhaitez automatiser possède déjà un connecteur. Si c’est le cas, envisagez de créer un fluide au lieu d’un workflow d’interface utilisateur. Vous pouvez également créer votre [propre connecteur](https://docs.microsoft.com/connectors/custom-connectors/).

## <a name="prerequisites"></a>Conditions préalables

- Un plan d’autogestion de l’alimentation [payante](https://flow.microsoft.com/pricing/) ou [d’essai](https://flow.microsoft.com/manage/) .

- Un compte professionnel ou scolaire pour se connecter à Power automate et à votre appareil Windows.

- Un appareil qui exécute Windows 10, Windows Server 2016 ou Windows Server 2019.
- Clavier US (QWERTY) attaché.

- La [prochaine version de Microsoft Edge](https://www.microsoftedgeinsider.com) ou Google Chrome.

- [Environnement](https://docs.microsoft.com/power-platform/admin/environments-overview) avec une [base de données Common Data Service](https://docs.microsoft.com/power-platform/admin/create-database).

> [!IMPORTANT]
> Le flux de l’interface utilisateur est en cours de déploiement entre les régions. Si vous ne voyez pas la fonctionnalité en version préliminaire ou si vous ne pouvez pas créer de nouveaux flux d’interface utilisateur, Veuillez réessayer ultérieurement.


## <a name="limitations"></a>Limitations

L’interface flux de l’interface utilisateur (préversion) est disponible en anglais.

Les éléments suivants ne sont pas pris en charge :

-   Flux de l’interface utilisateur du Bureau

    -   Moniteurs multiples
    -   Machines virtuelles
    -   Double-clic, pointage de la souris, entrée tactile/du stylet
    -   Interactions sur Windows (Explorateur de fichiers, menu Démarrer, barre des tâches, etc.)

-   Flux d’interface utilisateur Web

    -   Clic droit
    -   Les informations de session utilisateur (par exemple, les cookies) ne seront pas réutilisées lors de la lecture. Vous devrez modifier le script pour incorporer les informations de connexion lorsque cela est requis par les sites Web.

Vous trouverez des limitations spécifiques aux fonctionnalités incluses dans la documentation de chaque fonctionnalité.

## <a name="get-your-device-ready"></a>Préparer votre appareil

Installez les composants suivants pour créer et exécuter des flux d’interface utilisateur :

|  | **Nomme**                             | **Syntaxe**  |                                                        
|---|--------------------------------------|----------------------------------------------------------------------|
|   | [Application flux de l’interface utilisateur](https://go.microsoft.com/fwlink/?linkid=2102613)                         | Enregistrer des applications Windows bureautiques                                  |          |
|   | Extension du navigateur de flux d’interface utilisateur           | Enregistrez et testez les applications Windows bureautiques. Enregistrez les applications Web. |                                                                                              |
|   | Disque dur                            | Tester et exécuter des applications Windows bureautiques                            |                                                                                              |
|   | [IDE sélénium](https://go.microsoft.com/fwlink/?linkid=2107665) | Enregistrer et lire des applications Web                                 |  |
|   | [Gateway](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409)                              | Utilisé pour activer des événements, des flux planifiés ou des flux de bouton pour se connecter à, déclencher vos flux d’interface utilisateur (s’exécutant au sein de votre organisation) et les exécuter.              |  | 

## <a name="install-the-ui-flows-app"></a>Installer l’application flux de l’interface utilisateur

Le programme d’installation de flux d’interface utilisateur contient tous les composants nécessaires pour enregistrer, modifier et tester les flux d’interface utilisateur pour le bureau. 

>[!IMPORTANT]
>Le programme d’installation du flux de l’interface utilisateur installe le composant WebDriver et l’extension de navigateur flux de l’interface utilisateur. Ces deux éléments sont nécessaires pour enregistrer, tester et exécuter des flux d’interface utilisateur pour le bureau.

Procédez comme suit pour installer l’application flux de l’interface utilisateur :

1. [Téléchargez le programme d’installation de l’application flux d’interface utilisateur](https://go.microsoft.com/fwlink/?linkid=2102613).
1. Ouvrez le fichier **Setup. Microsoft. Flow. UIflow. exe** . Ce fichier se trouve probablement dans votre dossier **téléchargements** une fois que vous l’avez téléchargé à l’étape précédente.
1. Suivez les instructions du programme d’installation du flux de l' **interface utilisateur (version préliminaire)** pour terminer l’installation.

## <a name="activate-the-ui-flows-browser-extension"></a>Activer l’extension de navigateur de flux d’interface utilisateur 

Une fois le programme d’installation de flux de l’interface utilisateur terminé, votre navigateur vous invite à activer l’extension.

- Sur Microsoft Edge (chrome), sélectionnez chaque icône d’avertissement en haut à droite du navigateur, puis sélectionnez **activer l’extension**.
-   Dans Google Chrome, sélectionnez **activer l’extension** lorsque vous y êtes invité.  


## <a name="install-selenium-ide"></a>Installer l’IDE de sélénium

L’IDE de sélénium est un outil open source qui vous permet d’enregistrer et de lire des interactions humaines sur des sites Web.

Avec les flux d’interface utilisateur, vous pouvez exécuter des scripts IDE de sélénium à partir de Power automate et les conserver en mode de stockage sécurisé (avec la gouvernance informatique appropriée) dans Common Data Service.

Pour installer l’IDE de sélénium, procédez comme suit :

1. [Téléchargez et installez](https://go.microsoft.com/fwlink/?linkid=2107665) l’IDE de sélénium pour la prochaine version de Microsoft Edge ou Google Chrome.

1. Sur Microsoft Edge (chrome), sélectionnez **autoriser les extensions dans d’autres magasins**, puis sélectionnez **Ajouter au chrome**.

## <a name="install-the-on-premises-data-gateway"></a>Installer la passerelle de données locale

Vous aurez besoin de la passerelle pour déclencher le workflow de votre interface utilisateur à partir d’un [Workflow d’événement, de planification ou de bouton.](../getting-started.md/#types-of-flows)

>[!TIP]
>La passerelle n’est pas requise si vous souhaitez uniquement créer, modifier et tester les flux d’interface utilisateur sur votre appareil.

[Installez la passerelle de données locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-install)si vous en avez besoin.

## <a name="uninstall-ui-flows"></a>Désinstaller les flux d’interface utilisateur

1. Ouvrez le menu **démarrer** > **paramètres** > **applications**.
1. Recherchez **flux d’interface utilisateur (version préliminaire)** , puis sélectionnez-le.
1. Sélectionnez **désinstaller**.

## <a name="next-steps"></a>Étapes suivantes

- Apprenez à [créer des flux d’interface utilisateur de bureau](create-desktop.md).
- Apprenez à [créer des flux d’interface utilisateur Web](create-web.md).
- Découvrez comment exécuter des [flux d’interface utilisateur](run-ui-flow.md).
- Apprenez à [gérer les flux d’interface utilisateur](manage.md).
- En savoir plus sur la [passerelle locale](../gateway-reference.md/#use-a-gateway)

