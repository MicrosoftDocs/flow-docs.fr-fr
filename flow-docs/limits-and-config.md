---
title: Limites et configuration | Microsoft Docs
description: Limites et configuration
services: 
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/31/2018
ms.author: stepsic
ms.openlocfilehash: 60caaba88e825e97a49c3cf65d0ecceff586046c
ms.sourcegitcommit: b943fa83d7ca2d1a313c0c7b2cf0d7e4a9528b85
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2018
---
# <a name="limits-and-configuration-in-microsoft-flow"></a>Limites et configuration dans Microsoft Flow
Cette rubrique contient des informations sur les limites actuelles et les détails de configuration des flux.

## <a name="request-limits"></a>Limites de demande
Il s’agit des limites pour une seule demande sortante.

### <a name="timeout"></a>Délai d’attente
| Nom | Limite |
| --- | --- |
| Délai d’expiration de la demande |120 secondes |

### <a name="message-size"></a>Taille du message
| Nom | Limite | Notes |
| --- | --- | --- |
| Taille du message |100 Mo |Toutes les API ne prennent pas en charge la taille de 100 Mo. |
| Limite d’évaluation d’expression |131 072 caractères |`@concat()`, `@base64()` et `string` ne peuvent pas dépasser cette limite. |

### <a name="retry-policy"></a>Stratégie de nouvelle tentative
| Nom | Limite |
| --- | --- |
| Nouvelles tentatives |4 |

## <a name="run-duration-and-retention"></a>Durée et rétention des exécutions
Il s’agit des limites pour une seule exécution de flux.

| Nom | Limite | Notes |
| --- | --- | --- |
| Durée d’exécution |30 jours |Inclut des flux de travail avec des étapes en attente telles que des approbations. Après 30 jours, toutes les étapes en attente expirent. Les approbations expirées sont supprimées du centre d’approbations. Si une personne tente d’approuver une demande expirée, elle reçoit un message d’erreur. |
| Rétention du stockage |30 jours |À compter de l’heure de début de l’exécution. |
| Intervalle de périodicité minimal |1 minute | |
| Intervalle de périodicité maximal |500 jours | |

## <a name="looping-and-debatching-limits"></a>Limites de l’exécution de boucles et de la décomposition des lots
Il s’agit des limites pour une seule exécution de flux.

| Nom | Limite | Notes |
| --- | --- | --- |
| Éléments ForEach |5 000 |Vous pouvez utiliser l’action de filtrage pour filtrer des tableaux plus volumineux en fonction des besoins. |
| Itérations Until (Jusqu’à) |5 000 | |
| Éléments SplitOn |5 000 | |
| Parallélisme ForEach |1 | |

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

### <a name="logic-app-service"></a>Service d’application logique
Les appels effectués à partir d’un flux sont directement transmis au service Azure Logic Apps. Par exemple : HTTP, ou HTTP + OpenAPI. Ces appels proviennent des adresses IP suivantes :

| Région | Adresse IP de sortie |
| --- | --- |
| Asie |168.63.200.173, 13.75.89.159, 23.97.68.172, 13.75.94.173, 40.83.127.19, 52.175.33.254, 52.163.93.214, 52.187.65.81, 52.187.65.155, 13.76.133.155, 52.163.228.93, 52.163.230.166 |
| Australie |13.75.153.66, 104.210.89.222, 104.210.89.244, 13.75.149.4, 104.210.91.55, 104.210.90.241, 13.73.115.153, 40.115.78.70, 40.115.78.237, 13.73.114.207, 13.77.3.139, 13.70.159.205 |
| Canada |52.233.29.92, 52.228.39.241, 52.228.39.244, 52.232.128.155, 52.229.120.45, 52.229.126.25 |
| Europe |13.79.173.49, 52.169.218.253, 52.169.220.174, 40.113.12.95, 52.178.165.215, 52.178.166.21, 13.95.155.53, 52.174.54.218, 52.174.49.6, 40.68.222.65, 40.68.209.23, 13.95.147.65 |
| Inde |52.172.157.194, 52.172.184.192, 52.172.191.194, 52.172.154.168, 52.172.186.159, 52.172.185.79, 52.172.9.47, 52.172.49.43, 52.172.51.140, 52.172.50.24, 52.172.55.231, 52.172.52.0 |
| Japon |13.71.146.140, 13.78.84.187, 13.78.62.130, 13.71.158.3, 13.73.4.207, 13.71.158.120, 40.74.140.173, 40.74.81.13, 40.74.85.215, 40.74.140.4, 104.214.137.243, 138.91.26.45 |
| États-Unis |137.135.106.54, 40.117.99.79, 40.117.100.228, 13.92.98.111, 40.121.91.41, 40.114.82.191, 52.160.90.237, 138.91.188.137, 13.91.252.184, 52.160.92.112, 40.118.244.241, 40.118.241.243 |

### <a name="services"></a>Services
Les appels effectués à partir d’une API connectée par le biais d’un flux (par exemple l’API SQL ou SharePoint) proviennent de l’adresse IP spécifiée ci-dessous :

| Région | Adresse IP de sortie |
| --- | --- |
| Asie |52.163.91.227, 52.163.89.40, 52.163.89.65, 52.163.95.29, 13.75.89.9, 13.75.91.198, 13.75.92.202, 13.75.92.124 |
| Australie |13.77.7.172, 13.70.191.49, 13.70.189.7, 13.70.187.251, 13.70.82.210, 13.73.203.158, 13.73.207.42, 13.73.205.35 |
| Canada |52.233.30.222, 52.233.30.148, 52.233.30.199, 52.233.29.254, 52.232.130.205, 52.229.126.118, 52.229.126.28, 52.229.123.56 |
| Europe |52.166.241.149, 52.166.244.232, 52.166.245.173, 52.166.243.169, 40.69.45.126, 40.69.45.11, 40.69.45.93, 40.69.42.254 |
| Inde |52.172.54.172, 52.172.55.107, 52.172.55.84, 52.172.51.70, 52.172.158.185, 52.172.159.100, 52.172.158.2, 52.172.155.245 |
| Japon |104.214.137.186, 104.214.139.29, 104.214.140.23, 104.214.138.174, 13.78.85.193, 13.78.84.73, 13.78.85.200, 13.78.86.229 |
| États-Unis |104.43.232.28, 104.43.232.242, 104.43.235.249, 104.43.234.211, 52.160.93.247, 52.160.91.66, 52.160.92.131, 52.160.95.100, 40.117.101.91, 40.117.98.246, 40.117.101.120, 40.117.100.191 |
| États-Unis (accès en avant-première) |52.161.26.191, 52.161.27.42, 52.161.29.40, 52.161.26.33, 13.66.213.240, 13.66.214.51, 13.66.210.166, 13.66.213.29 |

Par exemple, si vous recherchez des adresses IP autorisées pour votre base de données SQL Azure, vous devez utiliser ces adresses.

Le tableau suivant répertorie les services auxquels Microsoft Flow se connecte. Vérifiez qu’aucun de ces services n’est bloqué sur votre réseau.

Domaines | Protocoles | Utilisations
--------|  ---------| -----
management.azure.com|https|Accès à Azure Resource Manager.
login.microsoft.com</br>login.windows.net</br>login.microsoftonline.com</br>secure.aadcdn.microsoftonline-p.com|https|Accès à ADAL (Active Directory Authentication Library).
graph.microsoft.com </br>graph.windows.net</br>|https|Accès à l’API Graph Azure AD, pour obtenir des informations utilisateur telles qu’une photo de profil.
*.azure-apim.net|https|Accès au Runtime pour les connecteurs.
*.flow.microsoft.com|https|Accéder au site Microsoft Flow.
*.powerapps.com|https|Accéder au site PowerApps.
psux.azureedge.net|https|Accéder au CDN Microsoft Flow.

