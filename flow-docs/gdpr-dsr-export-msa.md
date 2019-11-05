---
title: Microsoft Flow les demandes d’exportation de l’objet des données RGPD pour les comptes Microsoft (MSA) | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes d’exportation de l’objet de données RGPD pour les comptes Microsoft.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 5/25/2018
ms.author: Deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 253d6785228fb28b5c78d0cae629a237a2e176da
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548153"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Réponse aux demandes d’exportation de l’objet de données RGPD pour Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Dans le cadre de notre engagement à nous faire part de votre engagement envers le Règlement général sur la protection des données (RGPD), nous avons développé la documentation qui vous aidera à vous préparer. La documentation décrit non seulement ce que nous faisons pour préparer le RGPD, mais également des exemples d’étapes que vous pouvez effectuer dès aujourd’hui avec Microsoft pour prendre en charge la conformité RGPD lors de l’utilisation de Microsoft Flow.

## <a name="manage-export-requests"></a>Gérer les demandes d’exportation

Le *droit de portabilité des données* permet aux personnes concernées de demander une copie de leurs données personnelles dans un format électronique (c’est-à-dire un format « structuré, couramment utilisé, lisible par machine et interopérable ») qui peut être transmis à un autre contrôleur de données.

Utilisez le [tableau de bord de confidentialité de Microsoft](https://account.microsoft.com/privacy/)ou [Microsoft Flow](https://flow.microsoft.com/) pour rechercher ou exporter des données personnelles pour un utilisateur spécifique.

|Données personnelles|Emplacement|
|-----------------|-------------------|
|Activité du produit et du service|Tableau de bord de confidentialité Microsoft|
|Trouvent|Portail Microsoft Flow Maker|
|historique des exécutions|Portail Microsoft Flow Maker|
|Flux d’activités|Portail Microsoft Flow Maker|
|Connexions|Portail Microsoft Flow Maker|

## <a name="export-product-and-service-activity"></a>Exporter l’activité du produit et du service

1. Connectez-vous au [tableau de bord de confidentialité Microsoft](https://account.microsoft.com/privacy/) à l’aide de votre compte Microsoft (MSA).
1. Sélectionnez **historique de l’activité**.

    ![historique de l’activité](./media/gdpr-dsr-export-msa/activityhistory.png) vous pouvez parcourir l’historique de vos activités en fonction des applications et services Microsoft que vous utilisez.
1. Pour exporter les données de l' **activité du produit et du service** , sélectionnez **télécharger vos données**, puis sélectionnez **créer une nouvelle archive**.

    ![Télécharger vos données](./media/gdpr-dsr-export-msa/downloaddata.png)

1. Sélectionnez **App & service usage**, puis **Create Archive**.

    ![Télécharger vos données](./media/gdpr-dsr-export-msa/create-archive.png)
1. Une nouvelle archive est créée. Sélectionnez **Télécharger** pour obtenir les données exportées du produit et de l’activité du service.

    ![Downloader](./media/gdpr-dsr-export-msa/download.png)

## <a name="export-a-flow"></a>Exporter un Flow

Un utilisateur final qui a accès à un Flow peut exporter le Flow en procédant comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/).

1. Sélectionnez **mes flux**, puis sélectionnez le flux à exporter.

1. Sélectionner **... Plus**, puis sélectionnez **Exporter**.

    ![Exporter le workflow](./media/gdpr-dsr-export/export-flow.png)

1. Sélectionnez **package (. zip)** .

Votre Flow sera maintenant disponible en tant que package compressé. Pour plus d’informations, consultez le billet de blog sur l' [exportation et l’importation d’un fluide](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exporter l’historique des exécutions

L’historique des exécutions comprend une liste de toutes les exécutions d’un Workflow. Ces données incluent l’État, l’heure de début, la durée et les données d’entrée/sortie du fluide pour les déclencheurs et les actions.

Un utilisateur final qui a accès au Flow peut effectuer les étapes suivantes pour exporter ces données :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/).
1. Sélectionnez le lien **mes flux** , puis sélectionnez le flux pour lequel vous souhaitez exporter l’historique des exécutions.
1. Dans le volet **historique des exécutions** , sélectionnez **Afficher tout**.

    ![historique des exécutions](./media/gdpr-dsr-export/run-history.png)

1. Sélectionnez **Télécharger CSV**.

    ![Télécharger CSV](./media/gdpr-dsr-export/download-csv.png)

L’historique des exécutions est téléchargé sous forme de fichier. csv afin que vous puissiez l’ouvrir dans Microsoft Excel ou un éditeur de texte pour analyser les résultats.

## <a name="export-a-users-activity-feed"></a>Exporter le flux d’activités d’un utilisateur

Dans [Microsoft Flow](https://flow.microsoft.com/), le flux d’activités affiche l’historique des activités, des échecs et des notifications d’un utilisateur. Les utilisateurs peuvent afficher leur flux d’activités en procédant comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/), sélectionnez l’icône en forme de cloche près de l’angle supérieur droit, puis sélectionnez **afficher toutes les activités**.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/show-activity-feed.png)

1. Dans l’écran **activité** , copiez les résultats, puis collez-les dans un éditeur de texte tel que Microsoft Word.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exporter les connexions d’un utilisateur

Les connexions permettent aux flux de se connecter à des API, des applications SaaS et d’autres systèmes tiers. Pour afficher vos connexions, procédez comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/), sélectionnez l’icône d’engrenage près de l’angle supérieur droit, puis sélectionnez **connexions**.

    ![Afficher les connexions](./media/gdpr-dsr-export/show-connections.png)
1. Copiez les résultats, puis collez-les dans un éditeur de texte tel que Microsoft Word.
