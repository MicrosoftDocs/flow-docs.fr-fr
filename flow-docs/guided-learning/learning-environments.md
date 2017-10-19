---
title: "Utiliser des environnements pour gérer des flux | Microsoft Docs"
description: "Apprenez-en davantage sur l’utilisation d’environnements pour séparer et gérer des flux."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: wnScBLz7css
courseduration: 8m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/16/2017
ms.author: deonhe
ms.openlocfilehash: 8ded06b5ffb08cf3cced1bf95e7e81415cdfe21b
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="use-environments-to-manage-flows"></a>Utiliser des environnements pour gérer des flux
## <a name="what-is-an-environment"></a>Qu’est-ce qu’un environnement ?
Un environnement est un espace virtuel utilisé pour stocker, gérer et partager des applications, des flux et des données d’entreprise dans Common Data Service. Les environnements sont géolocalisés afin que toutes les applications et données stockées dans la base de données d’un environnement le soient également.  

## <a name="terms-you-should-get-familiar-with"></a>Termes que vous devez connaître
| **Terme** | **Description** |
| --- | --- |
| **Centre d’administration** |Le centre d’administration est un [portail web](https://admin.flow.microsoft.com) pour la gestion de l’ensemble de vos environnements et stratégies de protection contre la perte de données. |
| **Common Data Service** |Common Data Service vous permet d’ajouter à vos applications des fonctionnalités de stockage et de modélisation des données. |
| **Rôles d’environnement** |Les deux rôles de l’environnement sont Administrateur d’environnement et Créateur d’environnement. |
| **Rôles d’utilisateur** |Les rôles d’utilisateur par défaut sont ceux d’utilisateur de l’organisation et de propriétaire de base de données. Vous pouvez ajouter des rôles et y associer des autorisations. |

## <a name="purposes-for-an-environment"></a>Objectifs d’un environnement
Vous pouvez utiliser des environnements aux fins suivantes :  

* Séparer les applications, les flux et les données en fonction des rôles, des exigences de sécurité ou des utilisateurs.  
* Séparer les applications, flux et données d’entreprise en fonction de l’emplacement de vos équipes ou services.
* Gérer les environnements de test et de production.  

## <a name="how-to-use-environments"></a>Utilisation des environnements
Les environnements peuvent servir à différentes fins selon les besoins de votre organisation. En voici quelques exemples :  

* Vous pouvez choisir de générer l’ensemble de vos applications et flux au sein d’un environnement unique. 
* Vous pouvez choisir de créer un environnement pour différents types d’applications et de flux. Par exemple, vous pouvez créer un environnement de test et environnement de production distincts.  
* Vous pouvez également choisir de créer des environnements en fonction de la structure de votre organisation ou même de l’emplacement géographique de vos équipes ou services. Par exemple, si vous avez des équipes en Australie, au Mexique et en Europe, vous pouvez créer un environnement pour chacun de ces emplacements et les gérer de manière indépendante.  

**Remarque** : les utilisateurs ne voient pas les environnements. Ils n’ont pas besoin de savoir dans quel environnement ils se trouvent. Les environnements sont des outils permettant aux administrateurs de catégoriser, gérer et partager des applications et des flux d’organisation.  

## <a name="what-are-roles"></a>Que sont les rôles ?
Une personne ayant accès à un environnement doit exercer l’un des rôles **Administrateur d’environnement** ou **Créateur d’environnement**. Les administrateurs d’environnement peuvent effectuer toutes les tâches d’administration sur un environnement. Un créateur d’environnement peut créer des ressources dans un environnement existant. Une personne peut avoir les deux rôles simultanément.  

**Remarque** : tous les utilisateurs ont accès à un environnement par défaut quand chaque utilisateur a accès à Microsoft Flow. Les utilisateurs peuvent avoir accès à plusieurs environnements.  

## <a name="create-an-environment"></a>Créer un environnement
Pour créer des environnements à partir du [Centre d’administration de Microsoft Flow](https://admin.flow.microsoft.com) procédez comme suit :  

1. Nommez votre environnement.
2. Sélectionnez une région d’hébergement de votre environnement.
3. Si vous le souhaitez, vous pouvez décider de créer une base de données pour votre environnement. Vous pouvez créer une base de données une fois que vous avez créé un environnement, si vous le souhaitez.
4. Vous pouvez également sélectionner les personnes autorisées à accéder à la base de données. Vous pouvez restreindre l’accès à la base de données ou l’accorder à tout le monde. 

## <a name="add-users-to-an-environment"></a>Ajouter des utilisateurs à un environnement
Une fois que vous avez créé un environnement, vous pouvez ajouter des utilisateurs au rôle Administrateur d’environnement ou Créateur d’environnement. Pour cela, comme avec toutes les autres tâches d’administration, utilisez le centre d’administration.  

Une fois que vous avez créé l’environnement et ajouté des utilisateurs, vous pouvez également créer une stratégie de protection contre la perte de données pour gérer l’utilisation de vos données d’entreprise. Nous abordons ce sujet dans la rubrique suivante. 

