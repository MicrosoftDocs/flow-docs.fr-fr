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
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 030e0563ce9adaa7c1c5c44f1446859e3152a398
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547441"
---
# <a name="learn-all-about-data-groups"></a>En savoir plus sur les groupes de données
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
## <a name="what-is-a-data-group"></a>Qu’est-ce qu’un groupe de données ?
Les groupes de données constituent un moyen simple de classer les services au sein d’une [stratégie de protection contre la perte de données (DLP)](prevent-data-loss.md). Les deux groupes de données disponibles sont le groupe **données d’entreprise uniquement** et le groupe **aucune donnée commerciale autorisée** . Les organisations sont libres de déterminer quels services sont placés dans un groupe de données particulier. Un bon moyen de classer des services consiste à les placer dans des groupes, en fonction de l’impact sur l’organisation. Par défaut, tous les services sont placés dans le groupe de données **aucune donnée commerciale autorisée** . Vous gérez les services dans un groupe de données lorsque vous créez ou modifiez les propriétés d’une stratégie DLP à partir du centre d’administration.

## <a name="how-data-is-shared-between-data-groups"></a>Mode de partage des données entre les groupes de données
Les données ne peuvent pas être partagées entre des services situés dans différents groupes. Par exemple, si vous placez SharePoint et Salesforce dans le groupe **données d’entreprise uniquement** et que vous placez Facebook et Twitter dans le groupe **aucune donnée métier autorisée** , vous ne pouvez pas créer de Flow qui déplace les données entre SharePoint et Facebook. Alors que les données ne peuvent pas être partagées entre des services dans différents groupes, vous pouvez partager des données entre les services d’un groupe spécifique. Par conséquent, revenons à l’exemple précédent, puisque SharePoint et Salesforce ont été placés dans le même groupe de données, les flux que vos utilisateurs finaux créent peuvent partager des données entre SharePoint et Salesforce. De même, les utilisateurs finaux peuvent créer des flux et des PowerApp qui partagent des données entre Facebook et Twitter. Le point essentiel est que les services d’un groupe spécifique peuvent partager des données, tandis que les services de différents groupes ne peuvent pas partager de données.  

En outre, un groupe de données doit être désigné comme groupe *par défaut* . Initialement, le groupe **aucune donnée métier autorisée** est le groupe *par défaut* et tous les services se trouvent dans le groupe de données. Un administrateur peut remplacer le groupe de données par défaut par le groupe de données **données d’entreprise uniquement** . **Notez** que les nouveaux services ajoutés au Flow seront placés dans le groupe *par défaut* désigné. Pour cette raison, nous vous recommandons de conserver les **données d’entreprise non autorisées** en tant que groupe par défaut et d’ajouter manuellement des services dans le groupe **données d’entreprise uniquement** une fois que votre organisation a évalué l’impact de la possibilité de partager les données d’entreprise avec le nouveau services.

## <a name="add-services-to-a-data-group"></a>Ajouter des services à un groupe de données
Dans cette procédure pas à pas, nous allons ajouter SharePoint et Salesforce au groupe de données **données d’entreprise uniquement** d’une stratégie de protection contre la perte de données (DLP). 

1. Sélectionnez le lien **+ Ajouter** situé dans la zone de groupe **données d’entreprise uniquement** d’une stratégie DLP :    
   ![ajouter une image](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Sélectionnez SharePoint et Salesforce, puis sélectionnez **Ajouter des services** pour ajouter les deux au groupe données d’entreprise uniquement :    
   ![ajouter une image de services](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Sélectionnez **enregistrer la stratégie** dans le menu en haut :  
   ![enregistrer la stratégie](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Notez que SharePoint et Salesforce se trouvent désormais dans le groupe données d’entreprise uniquement :  
   ![Groupe de données d’entreprise mis à jour](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Dans cette procédure pas à pas, vous avez ajouté SharePoint et Salesforce au groupe de données **données d’entreprise uniquement** d’une stratégie DLP. Si une personne qui fait partie de l’environnement de la stratégie DLP crée une application qui partage des données entre SharePoint ou Salesforce et n’importe quel service dans le groupe de données **aucune donnée commerciale autorisée** , l’application ne sera pas autorisée à s’exécuter.

## <a name="remove-services-from-a-data-group"></a>Supprimer des services d’un groupe de données
Étant donné que tous les services doivent être dans l’un des groupes de données disponibles, pour supprimer un service d’un groupe spécifique, ajoutez simplement le service à un autre groupe, puis enregistrez la stratégie.  

## <a name="change-the-default-data-group"></a>Modifier le groupe de données par défaut
Dans cette procédure pas à pas, nous allons modifier le groupe de données par défaut à partir du groupe de données **aucune donnée métier autorisée** vers le groupe de données **données d’entreprise uniquement** .  

**Important** les nouveaux services ajoutés au Flow seront placés dans le groupe *par défaut* désigné. Pour cette raison, nous vous recommandons de conserver les **données d’entreprise non autorisées** en tant que groupe par défaut et d’ajouter manuellement des services dans le groupe **données d’entreprise uniquement** .

1. Sélectionnez le **...** situé dans le coin supérieur droit du groupe de données que vous souhaitez désigner comme groupe de données par défaut :    
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Sélectionnez **définir comme groupe par défaut**:  
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Sélectionnez **enregistrer la stratégie** dans le menu en haut :  
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/add-to-data-group-4.png) 
4. Notez que le groupe de données est maintenant désigné comme groupe de données par défaut :  
   ![modifier le groupe par défaut](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Étapes suivantes
* [En savoir plus sur les stratégies de protection contre la perte de données (DLP)](prevent-data-loss.md)
* [En savoir plus sur les environnements](environments-overview-admin.md)   

