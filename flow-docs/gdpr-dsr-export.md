---
title: Microsoft Flow les demandes d’exportation de l’objet des données RGPD | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes d’exportation de l’objet de données RGPD.
services: ''
suite: flow
documentationcenter: na
author: MSFTMAN
manager: KVIVEK
ms.author: Deonhe
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/24/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 15eff70b8996e5ea130142a1c01699906e199642
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548199"
---
# <a name="responding-to-gdpr-data-subject-export-requests-for-microsoft-flow"></a>Réponse aux demandes d’exportation de l’objet de données RGPD pour Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Dans le cadre de notre engagement à nous faire part de votre engagement envers le Règlement général sur la protection des données (RGPD), nous avons développé la documentation qui vous aidera à vous préparer. La documentation décrit non seulement ce que nous faisons pour préparer le RGPD, mais également des exemples d’étapes que vous pouvez effectuer dès aujourd’hui avec Microsoft pour prendre en charge la conformité RGPD lors de l’utilisation de Microsoft Flow.

## <a name="manage-export-requests"></a>Gérer les demandes d’exportation

Le *droit de portabilité des données* permet à un sujet de données de demander une copie de ses données personnelles dans un format électronique (c’est-à-dire un format « structuré, couramment utilisé, lisible par machine et interopérable ») qui peut être transmis à un autre contrôleur de données.

Microsoft Flow offre les expériences suivantes pour rechercher ou exporter des données personnelles pour un utilisateur spécifique :

* **Accès au site Web :** Connectez-vous au [Centre d’administration PowerApp](https://admin.powerapps.com/), ou au [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com/).

* **Accès PowerShell :**  [cdmlets PowerShell admin de PowerApp](https://go.microsoft.com/fwlink/?linkid=871804).

|**Données client**|**Accès au site Web**|**Accès PowerShell**|
|-----------------|------------------|-------------------|
|Journaux générés par le système|[Portail d’approbation des services Office 365](https://servicetrust.microsoft.com/)|
|historique des exécutions|Portail Microsoft Flow Maker||
|Trouvent|Portail Microsoft Flow Maker||
|Autorisations de Flow| Portail Microsoft Flow Maker et centre d’administration des Microsoft Flow||
|Détails de l’utilisateur||Applets de commande PowerApps|
|Connexions|Portail Microsoft Flow Maker|Applets de commande PowerApps |
|Autorisations de connexion|Portail Microsoft Flow Maker|Applets de commande PowerApps |
|Connecteurs personnalisés|Portail Microsoft Flow Maker|Applets de commande PowerApps |
|Autorisations de connecteur personnalisées|Portail Microsoft Flow Maker|Applets de commande PowerApps |
|Gateway|Portail Microsoft Flow Maker|Applets de commande PowerShell de la passerelle de données locale|
|Autorisations de la passerelle|Portail Microsoft Flow Maker|Applets de commande PowerShell de la passerelle de données locale|

## <a name="export-a-flow"></a>Exporter un Flow

Un utilisateur final ou un administrateur, qui s’est vu accorder l’accès au Flow, peut exporter le Flow en procédant comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/).

1. Sélectionnez le lien **mes flux** , puis sélectionnez le flux à exporter.

1. Sélectionner **... Plus**, puis sélectionnez **Exporter**.

    ![Exporter le workflow](./media/gdpr-dsr-export/export-flow.png)

1. Sélectionnez **package (. zip)** .

Votre Flow sera maintenant disponible en tant que package compressé. Pour plus d’informations, consultez le billet de blog sur l' [exportation et l’importation d’un fluide](https://flow.microsoft.com/blog/import-export-bap-packages/).

## <a name="export-run-history"></a>Exporter l’historique des exécutions

L’historique des exécutions comprend une liste de toutes les exécutions qui se sont produites pour un Workflow. Ces données incluent l’État, l’heure de début, la durée et les données d’entrée/sortie du fluide pour les déclencheurs et les actions.

Un utilisateur final ou un administrateur, qui a reçu l’autorisation d’accéder au Flow via le centre d’administration Microsoft Flow, peut procéder comme suit pour exporter ces données :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/).
1. Sélectionnez le lien **mes flux** , puis sélectionnez le flux pour lequel vous souhaitez exporter l’historique des exécutions.
1. Dans le volet **historique des exécutions** , sélectionnez **Afficher tout**.

    ![historique des exécutions](./media/gdpr-dsr-export/run-history.png)

1. Sélectionnez **Télécharger CSV**.

    ![Télécharger CSV](./media/gdpr-dsr-export/download-csv.png)

L’historique des exécutions est téléchargé sous la forme d’un fichier. csv afin que vous puissiez l’ouvrir dans Microsoft Excel ou dans un éditeur de texte et analyser plus en détail les résultats.

## <a name="export-a-users-activity-feed"></a>Exporter le flux d’activités d’un utilisateur

Dans [Microsoft Flow](https://flow.microsoft.com/), le flux d’activités affiche l’historique des activités, des échecs et des notifications d’un utilisateur. Tout utilisateur peut consulter son flux d’activités en procédant comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/), sélectionnez l’icône en forme de cloche près de l’angle supérieur droit, puis sélectionnez **afficher toutes les activités**.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/show-activity-feed.png)

1. Dans l’écran **activité** , copiez les résultats, puis collez-les dans un éditeur de documents, tel que Microsoft Word.

    ![Afficher le flux d’activité](./media/gdpr-dsr-export/export-activity-feed.png)

## <a name="export-a-users-connections"></a>Exporter les connexions d’un utilisateur

Les connexions permettent aux flux de se connecter à des API, des applications SaaS et d’autres systèmes tiers. Pour afficher vos connexions, procédez comme suit :

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/), sélectionnez l’icône d’engrenage près de l’angle supérieur droit, puis sélectionnez **connexions**.

    ![Afficher les connexions](./media/gdpr-dsr-export/show-connections.png)
1. Copiez les résultats, puis collez-les dans un éditeur de documents, tel que Microsoft Word.

Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnection -CreateBy $userId | ConvertTo-Json |Out-File -FilePath "UserConnections.txt"
```

## <a name="export-a-list-of-a-users-connection-permissions"></a>Exporter une liste des autorisations de connexion d’un utilisateur

Un utilisateur peut exporter les attributions de rôle de connexion pour toutes les connexions auxquelles il a accès via la fonction ConnectionRoleAssignment dans le [cdmlets PowerShell powerapps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt"
```
Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "ConnectionPermissions.txt" 
```

## <a name="export-a-users-custom-connectors"></a>Exporter les connecteurs personnalisés d’un utilisateur

Les connecteurs personnalisés complètent les connecteurs prêts à l’emploi et permettent une connectivité à d’autres API, SaaS et systèmes développés personnalisés. Vous pouvez transférer la propriété d’un connecteur personnalisé ou le supprimer.

Pour exporter une liste de connecteurs clients, procédez comme suit :

1. Accédez à [Microsoft Flow](https://flow.microsoft.com).
1. Sélectionnez l’icône d' **engrenage** paramètres.
1. Sélectionnez **connecteurs personnalisés**.
1. Copiez et collez la liste des connecteurs personnalisés dans un éditeur de texte tel que Microsoft Word.

    ![Exporter des connecteurs personnalisés](./media/gdpr-dsr-export/export-custom-connectors.png)

En plus de l’expérience fournie dans Microsoft Flow, vous pouvez utiliser la fonction obtenir un connecteur des [applets de commande PowerShell de powerapps](https://go.microsoft.com/fwlink/?linkid=871804) pour exporter tous les connecteurs personnalisés.

~~~~
Add-PowerAppsAccount
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "CustomConnectors.txt"
~~~~

Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserCustomConnectors.txt"  
```

## <a name="export-a-users-custom-connector-permissions"></a>Exporter les autorisations de connecteur personnalisé d’un utilisateur

Un utilisateur peut exporter toutes les autorisations de connecteur personnalisées qu’il a créées via la fonction ConnectorRoleAssignment dans le [cdmlets PowerShell powerapps](https://go.microsoft.com/fwlink/?linkid=871804).

```PowerShell
Add-PowerAppsAccount
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"
```

Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection permissions for the specified user 
Add-PowerAppsAccount
$userId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "CustomConnectorPermissions.txt"   
```

## <a name="export-approval-history"></a>Exporter l’historique des approbations

Microsoft Flow historique des approbations capture un enregistrement historique des approbations qui ont été reçues ou envoyées pour un utilisateur. Tout utilisateur peut consulter son historique d’approbation en :

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/), en sélectionnant **approbations**, puis en sélectionnant **historique**.

    ![Afficher l’historique des approbations](./media/gdpr-dsr-export/view-approval-history.png)

1. Une liste affiche les approbations reçues par l’utilisateur. Les utilisateurs peuvent afficher les approbations qu’ils ont envoyés en sélectionnant la flèche vers le bas en regard de **reçu** , puis en sélectionnant **envoyé**.

    ![Afficher les approbations reçues](./media/gdpr-dsr-export/view-received-approvals.png)

## <a name="export-user-details"></a>Exporter les détails de l’utilisateur
Les détails de l’utilisateur fournissent une liaison entre un utilisateur et un locataire spécifique. Un administrateur peut exporter ces informations en appelant l’applet de commande **AdminFlowUserDetails** et en transmettant l’ID d’objet de l’utilisateur.

Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

Get-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

## <a name="export-gateway-settings"></a>Exporter les paramètres de la passerelle
Vous trouverez [ici](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration)des réponses aux demandes d’exportation de l’objet de données pour les passerelles de données locales.

