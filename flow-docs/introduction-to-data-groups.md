---
title: Groupes de données pour Microsoft Flow | Microsoft Docs
description: Présentation des groupes de données pour Microsoft PowerApps et Microsoft Flow.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/26/2016
ms.author: deonhe
ms.openlocfilehash: fd76c12d1879c9b613ba833d9ef2211cd4aab702
ms.sourcegitcommit: 945614d737d5909c40029a61e050302d96e1619d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/04/2018
ms.locfileid: "23440242"
---
# <a name="learn-all-about-data-groups"></a>En savoir plus sur les groupes de données
## <a name="what-is-a-data-group"></a>Qu’est-ce qu’un groupe de données ?
Les groupes de données sont un moyen simple de classer les services au sein d’une [stratégie de protection contre la perte de données](prevent-data-loss.md). Les deux groupes de données disponibles sont le groupe **Données d’entreprise uniquement** et le groupe **Aucune donnée commerciale autorisée**. Les organisations sont libres de déterminer quels services sont placés dans un groupe de données particulier. Un bon moyen de classer des services consiste à les placer dans des groupes, en fonction de l’impact sur l’entreprise. Par défaut, tous les services sont placés dans le groupe de données **Aucune donnée commerciale autorisée**. Gérez les services dans un groupe de données lorsque vous créez ou modifiez les propriétés d’une stratégie de protection contre la perte de données à partir du centre d’administration.

## <a name="how-data-is-shared-between-data-groups"></a>Comment les données sont partagées entre les groupes de données
Les données ne peuvent pas être partagées entre des services situés dans différents groupes. Par exemple, si vous placez SharePoint et Salesforce dans le groupe **Données d’entreprise uniquement** et que vous placez Facebook et Twitter dans le groupe **Aucune donnée commerciale autorisée**, vous ne pouvez pas créer un flux qui déplace les données entre SharePoint et Facebook. Vous ne pouvez pas partager les données entre des services dans différents groupes, mais vous pouvez partager des données entre des services au sein d’un groupe spécifique. Par conséquent, pour revenir à l’exemple précédent, étant donné que SharePoint et Salesforce ont été placés dans le même groupe de données, les flux que créent vos utilisateurs finaux peuvent partager des données entre SharePoint et Salesforce. De même, les utilisateurs finaux peuvent créer des flux et des applications PowerApps qui partagent des données entre Facebook et Twitter. Le point important est que les services d’un groupe spécifique peuvent partager des données, ce qui n’est pas le cas des services dans différents groupes.  

En outre, un groupe de données unique doit être désigné comme groupe *par défaut*. Initialement, le groupe **Aucune donnée commerciale autorisée** est le groupe *par défaut* et tous les services se trouvent dans le groupe de données. Un administrateur peut définir le groupe de données par défaut sur **Données d’entreprise uniquement**. **Remarque** Les nouveaux services ajoutés au flux sont placés dans le groupe *par défaut*. Pour cette raison, nous vous recommandons de conserver le groupe **Aucune donnée commerciale autorisée** par défaut et d’ajouter manuellement les services dans le groupe **Données d’entreprise uniquement** une fois que votre organisation a évalué l’impact que peut avoir le fait d’autoriser le partage des données d’entreprise avec le nouveau service.

## <a name="add-services-to-a-data-group"></a>Ajouter des services à un groupe de données
Dans cette procédure pas à pas, nous allons ajouter SharePoint et Salesforce au groupe **Données d’entreprise uniquement** d’une stratégie de protection contre la perte de données. 

1. Sélectionnez le lien **+ Ajouter** situé dans la zone **Données d’entreprise uniquement** du groupe de la stratégie de protection contre la perte de données :    
   ![Ajouter une image](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Sélectionnez SharePoint et Salesforce, puis sélectionnez **Ajouter des services** pour ajouter les deux services au groupe Données d’entreprise uniquement :    
   ![Ajouter une image de services](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Sélectionnez **Enregistrer la stratégie** dans le menu en haut :  
   ![Enregistrer la stratégie](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Notez que SharePoint et Salesforce sont maintenant dans le groupe Données d’entreprise uniquement :  
   ![groupe de données d’entreprise mis à jour](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Dans cette procédure pas à pas, vous avez ajouté SharePoint et Salesforce au groupe **Données d’entreprise uniquement** d’une stratégie de protection contre la perte de données. Si une personne qui fait partie de l’environnement de la stratégie de protection contre la perte de données crée une application qui partage des données entre SharePoint ou Salesforce et des services dans le groupe **Aucune donnée commerciale autorisée**, l’application n’est pas autorisée à s’exécuter.

## <a name="remove-services-from-a-data-group"></a>Supprimer des services d’un groupe de données
Étant donné que tous les services doivent être dans un des groupes de données disponibles, pour supprimer un service d’un groupe spécifique, ajoutez simplement le service à un autre groupe, puis enregistrez la stratégie.  

## <a name="change-the-default-data-group"></a>Modifier le groupe de données par défaut
Dans cette procédure pas à pas, nous allons modifier le groupe de données par défaut de **Aucune donnée commerciale autorisée** à **Données d’entreprise uniquement**.  

**Important** Les nouveaux services ajoutés au flux sont placés dans le groupe *par défaut* désigné. Pour cette raison, nous vous recommandons de conserver le groupe **Aucune donnée commerciale autorisée** par défaut et d’ajouter manuellement les services dans le groupe **Données d’entreprise uniquement**.

1. Sélectionnez les points de suspension **...** situés dans le coin supérieur droit du groupe de données que vous souhaitez désigner en tant que groupe de données par défaut :    
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Sélectionnez **Définir comme groupe par défaut** :  
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Sélectionnez **Enregistrer la stratégie** dans le menu en haut :  
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Notez que le groupe de données est maintenant désigné comme groupe par défaut :  
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Étapes suivantes
* [En savoir plus sur les stratégies de protection contre la perte de données](prevent-data-loss.md)
* [En savoir plus sur les environnements](environments-overview-admin.md)   

