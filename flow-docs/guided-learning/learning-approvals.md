---
title: "Demandes d’approbation avec Microsoft Flow | Microsoft Docs"
description: "Apprenez à utiliser Microsoft Flow pour gérer un flux de travail d’approbation."
services: 
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: 
tags: 
featuredvideoid: o-pgEBW3fOI
courseduration: 14m
ms.service: flow
ms.devlang: na
ms.topic: get-started-article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2016
ms.author: deonhe
ms.openlocfilehash: 049b713ed653ab5555e5f48f63e46cce7f3207ee
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="approval-requests"></a>Demandes d’approbation
En plus de vous aider à **recevoir des notifications**, **copier des fichiers** et **collecter des données**, Microsoft Flow peut vous aider à **simplifier votre processus d’approbation**.

## <a name="vacation-scenario"></a>Scénario lié aux congés
Supposons que vous êtes **responsable** d’une équipe et que vous demandez à vos employés de créer des **demandes de congés** dans une **liste SharePoint**. Vous souhaitez maintenant générer un **processus d’approbation** autour de ces éléments de liste afin que les nouvelles demandes de congés soient **rapidement traitées** et que le demandeur soit **automatiquement notifié**.  

## <a name="sharepoint-and-microsoft-flow"></a>SharePoint et Microsoft Flow
**SharePoint** **intègre** Microsoft Flow.  À partir de votre **liste SharePoint**, cliquez sur la liste déroulante **Flux** , puis sur **Créer un flux**.

![Créer un flux](./media/learning-approvals/new-flow.png)   

Dans le **menu à droite**, recherchez un **modèle** comme celui-ci.

![Modèle d’approbation](./media/learning-approvals/approval-template.png)

## <a name="using-the-template"></a>Utilisation du modèle
Le déclencheur **SharePoint** dans le modèle est **prérempli** avec les informations de votre liste.  Il vous suffit d’ajouter une **adresse de messagerie** pour l’**approbateur**.  Notez que l’**élément SharePoint d’origine n’est pas modifié**.  Pour cela, vous devez ajouter l’action **SharePoint - Mettre à jour l’élément**.

![Mettre à jour l’élément](./media/learning-approvals/update-item.png)

Qu’en est-il de la branche **Si Non** dans *Envoyer emailScope*?  Par défaut, elle ne fait rien.  Vous pouvez ajouter une action pour envoyer à l’auteur de la demande un message lui indiquant que sa demande a été rejetée. 

![Si Non](./media/learning-approvals/if-no.png)

## <a name="next-lesson"></a>Leçon suivante
Vous allez maintenant passer en revue ce que vous avez appris dans cette section.

