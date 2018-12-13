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
ms.openlocfilehash: 8a8a6561840f91ab61b8d7440f1620c2e7cd0076
ms.sourcegitcommit: a505b0aac796960d57fccee92eb18c6566ac9c35
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/06/2018
ms.locfileid: "53006952"
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

## <a name="looping-and-debatching-limits"></a>Limites de l’exécution de boucles et de la décomposition des lots
Il s’agit des limites pour une seule exécution de flux.

| Nom | Limite | Notes |
| --- | --- | --- |
| Éléments Apply to each (Appliquer à chacun) |100 000 |100 000 est uniquement disponible pour les plans Premium. Sinon, vous êtes limité à 5 000. Vous pouvez utiliser l’action de filtrage pour filtrer des tableaux plus volumineux en fonction des besoins. |
| Itérations Until (Jusqu’à) |5 000 | |
| Éléments SplitOn |100 000 |Comme pour les éléments Apply to each (Appliquer à chacun), la limite est de 5 000, sauf si vous avez un plan Premium. |
| Parallélisme Apply to each (Appliquer à chacun) |50 |Par défaut, les boucles s’exécutent en séquence (essentiellement, le parallélisme est égal à 1). Vous pouvez en configurer jusqu’à 50 en parallèle. |
| Exécutions d’actions toutes les 5 minutes | 100 000 | En outre, vous pouvez distribuer une charge de travail sur plusieurs flux en fonction des besoins. |
| Actions simultanées aux appels sortants | ~2 500 | Réduisez le nombre de requêtes simultanées ou réduisez la durée en fonction des besoins. | 

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

### <a name="logic-apps"></a>Logic Apps
Les appels effectués à partir d’un flux sont directement transmis au service Azure Logic Apps. Par exemple : HTTP, ou HTTP + OpenAPI. Veuillez vous reporter à [la documentation Logic Apps](https://docs.microsoft.com/azure/logic-apps/logic-apps-limits-and-config#configuration-ip-addresses) pour connaître les adresses IP utilisées par ce service.

### <a name="connectors"></a>Connecteurs
Les appels effectués à partir d’un connecteur dans un flux (par exemple l’API SQL ou SharePoint) proviennent des adresses IP listées ici :

| Région | Adresse IP de sortie |
| --- | --- |
| Asie-Pacifique | 13.75.36.64 - 13.75.36.79, 13.67.8.240 - 13.67.8.255, 52.175.23.169, 52.187.68.19, 52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 52.187.53.78, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124, 23.97.72.250  |
| Australie  | 13.70.72.192 - 13.70.72.207, 13.72.243.10, 13.77.50.240 - 13.77.50.255, 13.70.136.174, 13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.188.38, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35, 13.70.88.23 |
| Canada | 13.71.170.208 - 13.71.170.223, 13.71.170.224 - 13.71.170.239, 52.237.24.126, 40.69.106.240 - 40.69.106.255, 52.242.35.152, 52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56, 52.229.123.161, 52.233.27.68 |
| Europe | 13.69.227.208 - 13.69.227.223, 52.178.150.68, 13.69.64.208 - 13.69.64.223, 52.174.88.118, 52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 52.178.37.42, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254, 52.164.249.26, 137.117.161.181 |
| Inde  | 104.211.81.192 - 104.211.81.207, 52.172.211.12, 40.78.194.240 - 40.78.194.255, 13.71.125.22, 104.211.146.224 - 104.211.146.239, 104.211.189.218, 52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.49.180, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245, 52.172.153.107 |
| Japon | 13.78.108.0 - 13.78.108.15, 13.71.153.19, 40.74.100.224 - 40.74.100.239, 104.215.61.248, 104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 104.214.151.229, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229, 13.78.121.151 |
| Amérique du Sud | 191.233.203.192 - 191.233.203.207, 104.214.19.48 - 104.214.19.63, 13.65.86.57, 104.41.59.51 |
| Royaume-Uni | 51.140.148.0 - 51.140.148.15, 51.140.80.51, 51.140.211.0 - 51.140.211.15, 51.141.47.105 |
| États-Unis | 13.89.171.80 - 13.89.171.95, 52.173.245.164, 40.71.11.80 - 40.71.11.95, 40.71.249.205, 40.70.146.208 - 40.70.146.223, 52.232.188.154, 52.162.107.160 - 52.162.107.175, 52.162.242.161, 40.112.243.160 - 40.112.243.175, 104.42.122.49, 104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| Préversion (États-Unis)  | 13.71.195.32 - 13.71.195.47, 52.161.102.22, 13.66.140.128 - 13.66.140.143, 52.183.78.157, 52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 52.161.31.35, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29, 13.66.208.24 |

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
