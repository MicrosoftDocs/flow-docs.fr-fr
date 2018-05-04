---
title: Requêtes d’exportation RGPD des personnes concernées avec Microsoft Flow | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux requêtes d’exportation RGPD des personnes concernées.
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
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: 1e1fe346ba6ffb264985da0115714246a621ef5a
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Répondre aux requêtes d’exportation RGPD des personnes concernées pour Microsoft Flow

Dans le cadre du partenariat conclu avec vous pour vous accompagner dans l’adoption des directives du Règlement général sur la protection des données (RGPD), nous avons élaboré une documentation qui vous aidera à bien vous préparer. Non seulement cette documentation décrit ce que nous faisons pour préparer l’environnement RGPD, mais elle fournit également des exemples d’étapes que vous pouvez effectuer dès aujourd'hui avec Microsoft pour garantir la conformité RGPD lors de l’utilisation de Microsoft Flow.

## <a name="manage-export-requests"></a>Gérer les requêtes d’exportation

Le *droit à la portabilité des données* permet à une personne concernée de demander une copie de ses données personnelles dans un format électronique (c’est-à-dire un format « structuré, couramment utilisé, lisible par machine et interopérable ») et qui peut être transmise à un autre contrôleur de données.

Microsoft Flow offre les options suivantes pour rechercher ou exporter les données personnelles d’un utilisateur spécifique :

* **Accès au site Web :** connectez-vous au [Centre d’administration de PowerApps](https://admin.powerapps.com/) ou au [Centre d'administration de Microsoft Flow](https://admin.flow.microsoft.com/).

* **Accès à PowerShell :**  [applets de commandes Admin PowerShell PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

|**Données client**|**Accès au site Web**|**Accès à PowerShell**|
|-----------------|------------------|-------------------|
|Journaux générés par le système|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|
|Historique des exécutions|Microsoft Flow Maker Portal||
|Tâches de l’utilisateur|| |
|Flux|Microsoft Flow Maker Portal||
|Autorisations de flux| Microsoft Flow Maker Portal et Centre d'administration de Microsoft Flow||
|Détails de l’utilisateur|| |
|Connexions|Microsoft Flow Maker Portal| |
|Autorisations de connexion|Microsoft Flow Maker Portal| |
|Connecteurs personnalisés|Microsoft Flow Maker Portal| |
|Autorisations des connecteurs personnalisés|Microsoft Flow Maker Portal| |
|Passerelle|Microsoft Flow Maker Portal|Applets de commande PowerShell de la passerelle locale|
|Autorisations de passerelle|Microsoft Flow Maker Portal|

## <a name="export-a-flow"></a>Exporter un flux

Tout utilisateur ou administrateur disposant d’un accès au flux peut exporter le flux en procédant comme suit :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/).

1. Sélectionnez le lien **Mes flux**, puis sélectionnez le flux à exporter.

1. Sélectionnez **... Plus**, puis **Exporter**.

    ![Exporter le flux](./media/gdpr-dsr-export/export-flow.png)

1. Sélectionnez **Package (.zip)**.

Votre flux sera désormais disponible sous forme d’un package compressé. Pour plus d’informations, voir le billet de blog sur [l’exportation et l’importation d’un flux](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exporter l’historique des exécutions

L’historique des exécutions inclut la liste de toutes les exécutions qui se sont produites pour un flux. Ces données incluent l’état du flux, l’heure de début, la durée et les données d’entrée/sortie pour les déclencheurs et les actions.

Tout utilisateur ou administrateur disposant d’un accès au flux via le Centre d'administration de Microsoft Flow peut exporter ces données en procédant comme suit :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/).
1. Sélectionnez le lien **Mes flux**, puis choisissez le flux pour lequel vous voulez exporter l’historique des exécutions.
1. Dans le volet **Historique des exécutions**, sélectionnez **Afficher tout**.

    ![Historique des exécutions](./media/gdpr-dsr-export/run-history.png)

1. Sélectionnez **Télécharger le fichier CSV**.

    ![Télécharger le fichier CSV](./media/gdpr-dsr-export/download-csv.png)

L’historique des exécutions est téléchargé sous forme d’un fichier .csv que vous pouvez ouvrir dans Microsoft Excel ou dans un éditeur de texte afin de poursuivre l’analyse des résultats.

## <a name="export-a-users-activity-feed"></a>Exporter le flux d’activités d’un utilisateur

Dans [Microsoft Flow](https://flow.microsoft.com/), le flux d’activités affiche l’historique des activités, échecs et notifications d’un utilisateur. Tout utilisateur peut consulter son flux d’activités en procédant comme suit :

1. Connectez-vous à [Microsoft Flow](http://flow.microsoft.com/), sélectionnez l’icône en forme de cloche dans l’angle supérieur droit, puis choisissez **Afficher toute l’activité**.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/show-activity-feed.png)

1. Dans l’écran **Activité**, copiez les résultats, puis collez-les dans un éditeur de document comme Microsoft Word.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exporter les connexions d’un utilisateur

Les connexions permettent de connecter les flux aux API, applications SaaS et autres systèmes tiers. Procédez comme suit pour afficher vos connexions :

1. Connectez-vous à [Microsoft Flow](http://flow.microsoft.com/), sélectionnez l’icône en forme d’engrenage dans l’angle supérieur droit, puis choisissez **Connexions**.

    ![Afficher les connexions](./media/gdpr-dsr-export/show-connections.png)
1. Copiez les résultats, puis collez-les dans un éditeur de document comme Microsoft Word.

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exporter une liste des autorisations de connexion d’un utilisateur

Un utilisateur peut exporter les attributions de rôle de connexion pour toutes les connexions auxquelles il a accès via la fonction Get-ConnectionRoleAssignment dans les [applets de commandes PowerShell PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).
![Exporter les autorisations de connexion](./media/gdpr-dsr-export/export-connection-permissions.png)

## <a name="export-a-users-custom-connectors"></a>Exporter les connecteurs personnalisés d’un utilisateur

Les connecteurs personnalisés complètent les connecteurs fournis par défaut et assurent la connectivité avec d’autres API, SaaS et systèmes personnalisés. Vous pouvez transférer la propriété d’un connecteur personnalisé ou supprimer ce connecteur.

Procédez comme suit pour exporter une liste des connecteurs d’un client :

1. Accédez à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez l’icône des paramètres (**engrenage**).
1. Sélectionnez **Connecteurs personnalisés**.
1. Copiez et collez la liste des connecteurs personnalisés dans un éditeur de texte comme Microsoft Word.

    ![Exporter des connecteurs personnalisés](./media/gdpr-dsr-export/export-custom-connectors.png)

Outre l’expérience fournie dans Microsoft Flow, vous pouvez utiliser la fonction Get-Connector des [applets de commande PowerShell PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) pour exporter tous les connecteurs personnalisés.

![Exporter des connecteurs personnalisés PowerShell](./media/gdpr-dsr-export/export-custom-connectors-powershell.png)

## <a name="export-a-users-custom-connector-permissions"></a>Exporter les autorisations du connecteur personnalisé d’un utilisateur

Un utilisateur peut exporter toutes les autorisations d’un connecteur personnalisé qu’il a créé via la fonction Get-ConnectorRoleAssignment des [applets de commande PowerShell PowerApps](https://go.microsoft.com/fwlink/?linkid=871804).

![Exporter les autorisations d’un connecteur personnalisé PowerShell](./media/gdpr-dsr-export/export-connector-permissions.png)

## <a name="export-approval-history"></a>Exporter l’historique des approbations

L’historique des approbations Microsoft Flow consigne les approbations qui ont été reçues ou envoyées pour un utilisateur. Tout utilisateur peut consulter son historique d’approbations en procédant comme suit :

1. Connectez-vous à [Microsoft Flow](http://flow.microsoft.com/), sélectionnez **Approbations**, puis choisissez **Historique**.

    ![Afficher l’historique des approbations](./media/gdpr-dsr-export/view-approval-history.png)

1. Une liste affiche les approbations reçues par l’utilisateur. Les utilisateurs peuvent afficher les approbations qu’ils ont envoyées en sélectionnant la flèche vers le bas en regard de l’option **Reçues**, puis en sélectionnant **Envoyées**.

    ![Afficher les approbations reçues](./media/gdpr-dsr-export/view-received-approvals.png)
