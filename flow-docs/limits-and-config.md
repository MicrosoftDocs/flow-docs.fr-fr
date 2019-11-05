---
title: Limites et configuration | Microsoft Docs
description: Limites et configuration
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/30/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c6a9b3c344ac25afe90c607b4a665aeaab49321f
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547377"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limites et configuration dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Cette rubrique contient des informations sur les limites actuelles et les détails de configuration des flux.

## <a name="request-limits"></a>Limites des demandes
Il s’agit de limites pour une seule demande sortante.

### <a name="timeout"></a>Expiré

| Nomme | Sépar |
| --- | --- |
| Délai d’expiration de la demande pour les appels synchrones |120 secondes |
| Délai d’expiration de la demande pour les appels asynchrones|Configurable. Le nombre maximal est de 30 jours. |

### <a name="message-size"></a>Taille du message

| Nomme | Sépar | Notes |
| --- | --- | --- |
| Taille du message |100 MO |Toutes les API ne prennent pas en charge la totalité des 100 Mo. |
| Limite d’évaluation d’expression |131 072 caractères |`@concat()`, `@base64()``string` ne peut pas dépasser cette limite. |

### <a name="retry-policy"></a>Stratégie de nouvelle tentative

| Nomme | Sépar |
| --- | --- |
| Nouvelles tentatives |90 | La valeur par défaut est 4. Pour modifier les paramètres d’action d’utilisation par défaut | 
| Délai maximal entre deux tentatives |1 jour | |
| Délai min. des nouvelles tentatives |5 secondes | |

## <a name="run-duration-and-retention"></a>Durée d’exécution et rétention
Il s’agit des limites pour une seule exécution de Workflow.

| Nomme | Sépar | Notes |
| --- | --- | --- |
| Durée d’exécution |30 jours |Comprend des flux de travail avec des étapes en attente telles que des approbations. Au bout de 30 jours, le délai d’attente des étapes en attente est dépassé. Les approbations ayant expiré sont supprimées du centre d’approbations. Si quelqu’un tente d’approuver une demande ayant expiré, il reçoit un message d’erreur. |
| Rétention du stockage |30 jours |Il s’agit de l’heure de début de l’exécution. |
| Intervalle de récurrence min. |1 minute | |
| Intervalle de récurrence max. |500 jours | |
| Rétention maximale de l’historique d’exécution |28 jours, par règles RGPD. | |
|Intervalle de report minimal-licence gratuite et plan 1|5 secondes||
|Intervalle de report minimal-licence plan 2|1 seconde||

## <a name="looping-and-debatching-limits"></a>Limites de bouclage et de dégroupage
Il s’agit de limites pour une seule exécution de Workflow.

| Nomme | Sépar | Notes |
| --- | --- | --- |
| Appliquer à chaque article-licence gratuite|5 000 |Vous pouvez utiliser l’action de filtrage pour filtrer des tableaux plus volumineux en fonction des besoins. |
| Appliquer à chaque élément-plan 1 et licence plan 2|100 000 |Vous pouvez utiliser l’action de filtrage pour filtrer des tableaux plus volumineux en fonction des besoins. |
| Jusqu’à itérations |5 000 | |
| Éléments SplitOn-licence gratuite |5 000 ||
| Éléments SplitOn-licence plan 1 et plan 2 |100 000 ||
| Appliquer à chaque parallélisme |50 |Par défaut, les boucles s’exécutent en séquence (fondamentalement, le parallélisme est 1). Vous pouvez configurer jusqu’à 50 en parallèle. |
| Exécutions d’actions par 5 minutes – gratuit, Office 365, licences plan 1 et plans d’essai | 2 000 | En outre, vous pouvez distribuer une charge de travail sur plusieurs flows si nécessaire. |
|Exécutions d’actions par 5 minutes – licences du plan 2 payantes|100 000|En outre, vous pouvez distribuer une charge de travail sur plusieurs flows si nécessaire.|
|Exécutions d’actions par 5 minutes – licences du plan 2 payantes|150 000|En outre, vous pouvez distribuer une charge de travail sur plusieurs flows si nécessaire.|
| Actions appels sortants simultanés-licence gratuite et plan 1 | ~ 500 | Réduisez le nombre de demandes simultanées ou réduisez la durée en fonction des besoins. |
| Exécutions d’actions par 24 heures – gratuit, Office 365, licences plan 1 et plans d’essai | ~ 2 500 | Réduisez le nombre de demandes simultanées ou réduisez la durée en fonction des besoins. | 

## <a name="throughput-limits"></a>Limites de débit

|Nomme|Sépar|Notes|
|---|---|---|
|Point de terminaison de Runtime-nombre d’appels de lecture autorisés par 5 minutes-licence gratuite et plan 1|6 000||
|Point de terminaison au moment de l’exécution-nombre d’appels de lecture autorisés par 5 minutes-licence plan 2|60 000||
|Point de terminaison du Runtime : appels Invoke par 5 minutes-licence gratuite et plan 1|4 500||
|Point de terminaison du Runtime : nombre d’appels Invoke par 5 minutes-licence plan 2|45 000||
|Débit autorisé par période de 5 minutes-licence gratuite et plan 1|600 MO||
|Quantité de débit autorisé par période de 5 minutes-licence de plan 2|6 GO||
|La quantité de flux de contenu est autorisée à produire (entrées/sorties actions) par heure-gratuit, plan 1 et licence plan 2|200 GO||


## <a name="definition-limits"></a>Limites de définition
Il s’agit de limites pour un seul Workflow.

| Nomme | Sépar | Notes |
| --- | --- | --- |
| Actions par Workflow |250 |Vous pouvez ajouter des workflows imbriqués pour étendre cette fonction si nécessaire. |
| Profondeur d’imbrication des actions autorisées |version8 |Vous pouvez ajouter des workflows imbriqués pour étendre cette fonction si nécessaire. |
| Nombre maximal de caractères par expression |8 192 | |
| `action`/`trigger` limite de nom |80 | |
| limite de longueur de `description` |256 | |

## <a name="sharepoint-limits"></a>Limites SharePoint
Il existe des [limitations](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) quant à la façon dont vous pouvez utiliser Microsoft SharePoint avec Microsoft Flow et powerapps.

## <a name="ip-address-configuration"></a>Configuration des adresses IP
L’adresse IP à partir de laquelle les demandes de Microsoft Flow sont envoyées dépend de la [région](regions-overview.md) où se trouve l' [environnement](environments-overview-admin.md) qui contient le Flow. Nous ne publions pas actuellement les noms de domaine complets disponibles pour les scénarios de Flow.

>[!IMPORTANT]
> Certains appels d’un fluide peuvent provenir d’adresses IP qui sont répertoriées dans la documentation [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) . Voici quelques exemples de ces appels : HTTP ou HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
Les appels effectués à partir d’un workflow passent directement par le service Azure Logic App. Voici quelques exemples de ces appels : HTTP ou HTTP + OpenAPI. Veuillez vous référer à [la documentation Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) pour savoir quelles adresses IP sont utilisées par ce service.

### <a name="connectors"></a>Reliés
Les appels effectués à partir d’un connecteur dans un workflow (par exemple, l’API SQL ou l’API SharePoint) proviennent des adresses IP répertoriées ici :

| Sous | Adresse IP sortante |
| --- | --- |
| Asie-Pacifique | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19 |
| Australie  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152|
| Europe | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 137.117.161.181 |
| Inde  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218 |
| Japon | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248 |
| Amérique du Sud | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Royaume-Uni | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| États-Unis | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49|
| Aperçu (États-Unis)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Par exemple, si vous devez autoriser des adresses IP pour votre base de données SQL Azure, vous devez utiliser ces adresses.

### <a name="required-services"></a>Services requis
Le tableau suivant répertorie les services auxquels Microsoft Flow se connecte. Assurez-vous qu’aucun de ces services n’est bloqué sur votre réseau.

Domaines | Relatifs | Se
--------|  ---------| -----
management.azure.com|https|Accès au Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Accès à Bibliothèque d’authentification Active Directory (ADAL).
graph.microsoft.com </br>graph.windows.net</br>|https|Accès à Azure AD API Graph-pour obtenir des informations utilisateur telles qu’une photo de profil.
*. azure-apim.net|https|Accès au runtime pour les connecteurs.
*. flow.microsoft.com|https|Accès au site de Microsoft Flow.
*. powerapps.com|https|Accès au site PowerApps.
*. azureedge.net|https|Accès au Microsoft Flow CDN.
nps.onyx.azure.net|https|Accès au serveur NPS (score de promotion net).
