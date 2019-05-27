---
title: Demandes d’exportation RGPD des personnes concernées avec Microsoft Flow pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes d’exportation RGPD des personnes concernées pour les comptes Microsoft.
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
ms.date: 5/25/2018
ms.author: keweare
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 6f181a66453573c2f636cbe5130b7fc003a3b151
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035024"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Répondre aux requêtes d’exportation RGPD des personnes concernées pour Microsoft Flow

Dans le cadre du partenariat conclu avec vous pour vous accompagner dans l’adoption des directives du Règlement général sur la protection des données (RGPD), nous avons élaboré une documentation qui vous aidera à bien vous préparer. Non seulement cette documentation décrit ce que nous faisons pour préparer l’environnement RGPD, mais elle fournit également des exemples d’étapes que vous pouvez effectuer dès aujourd'hui avec Microsoft pour garantir la conformité RGPD lors de l’utilisation de Microsoft Flow.

## <a name="manage-export-requests"></a>Gérer les demandes d’exportation

Le *droit à la portabilité des données* permet aux personnes concernées de demander une copie de leurs données personnelles dans un format électronique (c’est-à-dire un format « structuré, couramment utilisé, lisible par machine et interopérable ») et qui peut être transmise à un autre contrôleur de données.

Utilisez le [Tableau de bord de confidentialité Microsoft](https://account.microsoft.com/privacy/) ou [Microsoft Flow](https://flow.microsoft.com/) pour rechercher ou exporter les données personnelles d’un utilisateur spécifique.

|Données personnelles|Emplacement|
|-----------------|-------------------|
|Activité de produits et de services|Tableau de bord de confidentialité Microsoft|
|Flux|Portail Microsoft Flow Maker|
|Historique des exécutions|Portail Microsoft Flow Maker|
|Flux d’activité|Portail Microsoft Flow Maker|
|Connexions|Portail Microsoft Flow Maker|

## <a name="export-product-and-service-activity"></a>Exporter l’activité des produits et des services

1. Connectez-vous au [Tableau de bord de confidentialité Microsoft](https://account.microsoft.com/privacy/) avec votre compte Microsoft (MSA).
1. Sélectionnez **Historique des activités**.

    ![Historique des activités](./media/gdpr-dsr-export-msa/activityhistory.png) : vous pouvez parcourir l’historique de vos activités pour les différents services et applications Microsoft que vous utilisez.
1. Pour exporter les données de **l’activité des produits et des services**, sélectionnez **Télécharger vos données**, puis **CRÉER UNE ARCHIVE**.

    ![Télécharger vos données](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Sélectionnez **Utilisation des applications et des services**, puis sélectionnez **Créer une archive**.

    ![Télécharger vos données](./media/gdpr-dsr-export-msa/create-archive.png)
1. Une nouvelle archive est créée. Sélectionnez **Télécharger** pour obtenir les données exportées de votre activité de produits et de services.

    ![Télécharger](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exporter un flux

Un utilisateur final qui a accès à un flux peut exporter le flux en suivant ces étapes :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/).

1. Sélectionnez **Mes flux**, puis sélectionnez le flux à exporter.

1. Sélectionnez **... Plus**, puis **Exporter**.

    ![Exporter le flux](./media/gdpr-dsr-export/export-flow.png)

1. Sélectionnez **Package (.zip)**.

Votre flux sera désormais disponible sous forme d’un package compressé. Pour plus d’informations, voir le billet de blog sur [l’exportation et l’importation d’un flux](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exporter l’historique des exécutions

L’historique d’exécution comprend une liste de toutes les exécutions d’un flux. Ces données incluent l’état du flux, l’heure de début, la durée et les données d’entrée/sortie pour les déclencheurs et les actions.

Un utilisateur final qui a accès au flux peut effectuer ces étapes pour exporter ces données :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/).
1. Sélectionnez le lien **Mes flux**, puis choisissez le flux pour lequel vous voulez exporter l’historique des exécutions.
1. Dans le volet **Historique des exécutions**, sélectionnez **Afficher tout**.

    ![Historique des exécutions](./media/gdpr-dsr-export/run-history.png)

1. Sélectionnez **Télécharger le fichier CSV**.

    ![Télécharger le fichier CSV](./media/gdpr-dsr-export/download-csv.png)

L’historique des exécutions est téléchargé sous la forme d’un fichier .csv que vous pouvez ouvrir dans Microsoft Excel ou dans un éditeur de texte pour analyser les résultats.

## <a name="export-a-users-activity-feed"></a>Exporter le flux d’activités d’un utilisateur

Dans [Microsoft Flow](https://flow.microsoft.com/), le flux d’activités affiche l’historique des activités, échecs et notifications d’un utilisateur. Les utilisateurs peuvent consulter leur flux d’activités en procédant comme suit :

1. Connectez-vous à [Microsoft Flow](http://flow.microsoft.com/), sélectionnez l’icône en forme de cloche dans l’angle supérieur droit, puis choisissez **Afficher toute l’activité**.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/show-activity-feed.png)

1. Dans l’écran **Activité**, copiez les résultats, puis collez-les dans un éditeur de texte, comme Microsoft Word.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exporter les connexions d’un utilisateur

Les connexions permettent de connecter les flux aux API, applications SaaS et autres systèmes tiers. Procédez comme suit pour afficher vos connexions :

1. Connectez-vous à [Microsoft Flow](http://flow.microsoft.com/), sélectionnez l’icône en forme d’engrenage dans l’angle supérieur droit, puis choisissez **Connexions**.

    ![Afficher les connexions](./media/gdpr-dsr-export/show-connections.png)
1. Copiez les résultats, puis collez-les dans un éditeur de texte, comme Microsoft Word.
