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
ms.date: 12/04/2018
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 615d13adaee8b5db302065b3c21a488504f39398
ms.sourcegitcommit: f1f1b8e24f30fcf6c2e3bb01a0223e382a10bed7
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/29/2019
ms.locfileid: "64906392"
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limites et configuration dans Microsoft Flow
Cette rubrique contient des informations sur les limites actuelles et les détails de configuration des flux.

## <a name="request-limits"></a>Limites de demande
Il s’agit des limites pour une seule demande sortante.

### <a name="timeout"></a>Délai d’attente

| Nom | Limite |
| --- | --- |
| Délai d’expiration de la demande pour les appels synchrones |120 secondes |
| Délai d’expiration de la demande pour les appels asynchrones|Configurable. La valeur maximale est 30 jours. |

### <a name="message-size"></a>Taille du message

| Nom | Limite | Notes |
| --- | --- | --- |
| Taille du message |100 Mo |Toutes les API ne prennent pas en charge la taille de 100 Mo. |
| Limite d’évaluation d’expression |131 072 caractères |`@concat()`, `@base64()` et `string` ne peuvent pas dépasser cette limite. |

### <a name="retry-policy"></a>Stratégie de nouvelle tentative

| Nom | Limite |
| --- | --- |
| Nouvelles tentatives |90 | La valeur par défaut est 4. Pour modifier la valeur par défaut, utilisez les paramètres d’action | 
| Délai maximal de nouvelle tentative |1 jour | |
| Délai minimal de nouvelle tentative |5 secondes | |

## <a name="run-duration-and-retention"></a>Durée et rétention des exécutions
Il s’agit des limites pour une seule exécution de flux.

| Nom | Limite | Notes |
| --- | --- | --- |
| Durée d’exécution |30 jours |Inclut des flux de travail avec des étapes en attente telles que des approbations. Après 30 jours, toutes les étapes en attente expirent. Les approbations expirées sont supprimées du centre d’approbations. Si une personne tente d’approuver une demande expirée, elle reçoit un message d’erreur. |
| Rétention du stockage |30 jours |À compter de l’heure de début de l’exécution. |
| Intervalle de périodicité minimal |1 minute | |
| Intervalle de périodicité maximal |500 jours | |
| Conservation maximale de l’historique des exécutions |28 jours, selon les règles RGPD. | |
|Intervalle minimum de report - Licence Gratuite et Plan 1|5 secondes||
|Intervalle minimum de report - Licence Plan 2|1 seconde||

## <a name="looping-and-debatching-limits"></a>Limites de l’exécution de boucles et de la décomposition des lots
Il s’agit des limites pour une seule exécution de flux.

| Nom | Limite | Notes |
| --- | --- | --- |
| Appliquer à chacun des éléments - Licence Gratuite|5 000 |Vous pouvez utiliser l’action de filtrage pour filtrer des tableaux plus volumineux en fonction des besoins. |
| Appliquer à chacun des éléments - Licences Plan 1 et Plan 2|100 000 |Vous pouvez utiliser l’action de filtrage pour filtrer des tableaux plus volumineux en fonction des besoins. |
| Itérations Until (Jusqu’à) |5 000 | |
| Éléments SplitOn - Licence Gratuite |5 000 ||
| Éléments SplitOn - Licences Plan 1 et Plan 2 |100 000 ||
| Parallélisme Apply to each (Appliquer à chacun) |50 |Par défaut, les boucles s’exécutent en séquence (essentiellement, le parallélisme est égal à 1). Vous pouvez en configurer jusqu’à 50 en parallèle. |
| Exécutions d’actions toutes les 5 minutes - Licence Gratuite et Plan 1 | 2 000 | En outre, vous pouvez distribuer une charge de travail sur plusieurs flux en fonction des besoins. |
|Exécutions d’actions toutes les 5 minutes - Licence Plan 2|100 000|En outre, vous pouvez distribuer une charge de travail sur plusieurs flux en fonction des besoins.|
| Actions simultanées aux appels sortants - Licence Gratuite et Plan 1 | ~500 | Réduisez le nombre de requêtes simultanées ou réduisez la durée en fonction des besoins. |
| Actions simultanées aux appels sortants - Licence Gratuite et Plan 1 | ~2 500 | Réduisez le nombre de requêtes simultanées ou réduisez la durée en fonction des besoins. | 

## <a name="throughput-limits"></a>Limites de débit

|Nom|Limite|Notes|
|---|---|---|
|Point de terminaison de runtime - Nombre d’appels de lecture autorisés toutes les 5 minutes - Licence Gratuite et Plan 1|6 000||
|Point de terminaison de runtime - Nombre d’appels de lecture autorisés toutes les 5 minutes - Licence Plan 2|60 000||
|Point de terminaison de runtime : Appels Invoke toutes les 5 minutes - Licence Gratuite et Plan 1|4 500||
|Point de terminaison de runtime : Nombre d’appels Invoke toutes les 5 minutes - Licence Plan 2|45 000||
|Quantité de débit autorisé toutes les 5 minutes - Licence Gratuite et Plan 1|600 Mo||
|Quantité de débit autorisé toutes les 5 minutes - Licence Plan 2|6 Go||
|Quantité de flux de contenu autorisés à produire (entrées/sorties d’actions) par heure - Licence Gratuite, Plan 1 et Plan 2|200 Go||


## <a name="definition-limits"></a>Limites de définition
Il s’agit des limites pour un seul flux.

| Nom | Limite | Notes |
| --- | --- | --- |
| Actions par workflow |250 |Vous pouvez ajouter des workflows imbriqués pour étendre cette fonction selon vos besoins. |
| Profondeur autorisée pour l’imbrication d’actions |5 |Vous pouvez ajouter des workflows imbriqués pour étendre cette fonction selon vos besoins. |
| Nombre maximal de caractères par expression |8 192 | |
| Limite de nom pour `action`/`trigger` |80 | |
| Limite de longueur pour `description` |256 | |

## <a name="sharepoint-limits"></a>Limites SharePoint
Il existe des [limitations](https://powerapps.microsoft.com/tutorials/connection-sharepoint-online/) sur la façon dont vous pouvez utiliser Microsoft SharePoint avec Microsoft Flow et PowerApps.

## <a name="ip-address-configuration"></a>Configuration des adresses IP
L’adresse IP à partir de laquelle les requêtes Microsoft Flow sont envoyées dépend de la [région](regions-overview.md) où se trouve l’[environnement](environments-overview-admin.md) qui contient le flux. Nous ne publions pas actuellement les noms de domaine complets disponibles pour les scénarios incluant des flux.

>[!IMPORTANT]
> Certains appels d’un flux peuvent provenir d’adresses IP qui sont répertoriées dans la documentation [Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses). Par exemple : HTTP, ou HTTP + OpenAPI.

### <a name="logic-apps"></a>Logic Apps
Les appels effectués à partir d’un flux sont directement transmis au service Azure Logic Apps. Par exemple : HTTP, ou HTTP + OpenAPI. Veuillez vous reporter à [la documentation Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) pour connaître les adresses IP utilisées par ce service.

### <a name="connectors"></a>Connecteurs
Les appels effectués à partir d’un connecteur dans un flux (par exemple l’API SQL ou SharePoint) proviennent des adresses IP listées ici :

| Région | Adresse IP de sortie |
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
| Préversion (États-Unis)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157 |

Par exemple, si vous recherchez des adresses IP autorisées pour votre base de données SQL Azure, vous devez utiliser ces adresses.

### <a name="required-services"></a>Services requis
Le tableau suivant répertorie les services auxquels Microsoft Flow se connecte. Vérifiez qu’aucun de ces services n’est bloqué sur votre réseau.

Domaines | Protocoles | Utilisations
--------|  ---------| -----
management.azure.com|https|Accès à Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Accès à ADAL (Active Directory Authentication Library).
graph.microsoft.com </br>graph.windows.net</br>|https|Accès à l’API Graph Azure AD, pour obtenir des informations utilisateur telles qu’une photo de profil.
*.azure-apim.net|https|Accès au Runtime pour les connecteurs.
*.flow.microsoft.com|https|Accéder au site Microsoft Flow.
*.powerapps.com|https|Accéder au site PowerApps.
*.azureedge.net|https|Accéder au CDN Microsoft Flow.
nps.onyx.azure.net|https|Accès à NPS (Net Promoter Score).
