---
title: "Vue d’ensemble de l’environnement pour les administrateurs | Microsoft Docs"
description: "Utilisation, création et gestion d’environnements dans Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/27/2016
ms.author: sunayv
ms.openlocfilehash: f1c50e5d16d5b9fbbd3e6db3128947b0554e9a85
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="using-environments-within-microsoft-flow"></a>Utilisation d’environnements dans Microsoft Flow
## <a name="benefits"></a>Avantages
Les environnements sont la nouvelle fonctionnalité de Microsoft Flow et incluent les avantages suivants : 

* **Localité des données** : les environnements peuvent être créés dans différentes régions et sont liés à cet emplacement géographique. Lorsque vous créez un flux dans un environnement, ce flux est acheminé vers tous les centres de données situés à cet emplacement géographique. Cela vous permet également de bénéficier de meilleures performances. 
  
    Si vos utilisateurs sont en Europe, créez et utilisez l’environnement dans la région Europe. Si vos utilisateurs sont aux États-Unis, créez et utilisez l’environnement aux États-Unis 
  
    Si vous supprimez l’environnement, tous les flux associés sont également supprimés. Cela s’applique à tous les éléments que vous créez dans l’environnement, y compris les connexions, les passerelles, PowerApps et bien plus encore.
* **Protection contre la perte de données** : en tant qu’administrateur, vous ne voulez pas que les flux qui récupèrent des données à partir d’un emplacement interne (tel que *OneDrive Entreprise*), publient ces données publiquement (p. ex. sur *Twitter*). Grâce à la protection contre la perte de données, vous contrôlez les services qui peuvent être utilisés dans une stratégie pour les données métier uniquement. 
  
    Par exemple, vous pouvez ajouter les services *SharePoint* et *OneDrive Entreprise* à une stratégie pour les données métier uniquement. Tous les flux créés dans cet environnement peuvent utiliser ces services *SharePoint* et *OneDrive Entreprise*. Seuls les services que vous ajoutez sont disponibles. 
  
  > [!NOTE]
  > La protection contre la perte de données est disponible avec certaines références de licence, y compris la licence P2. 
  > 
  > 
* **Limite d’isolation pour toutes les ressources** : l’ensemble des flux, passerelles, connexions, connecteurs personnalisés, etc. résident dans cet environnement spécifique. Ils n’existent pas dans les autres environnements. 
* **Service Common Data Service** : vous voulez créer un flux qui insère des données quelque part. Voici les options disponibles :
  
  * Insérez des données dans un fichier Excel que vous stockez dans un compte de stockage cloud tel que OneDrive.
  * Créez votre propre base de données SQL Database et stockez-y vos données.
  * Utilisez le service Common Data Service pour stocker vos données.
    
    Chaque environnement peut avoir zéro ou un stockage de base de données pour vos flux dans le service Common Data Service. L’accès au service Common Data Service dépend de la licence que vous achetez ; il n’est pas inclus dans la licence gratuite.

## <a name="limitations"></a>Limitations
Bien que les environnements présentent de nombreux avantages, ils introduisent également de nouvelles limitations. Le fait que les environnements soient une limite d’isolement signifie que vous ne pouvez jamais avoir de ressources qui référencent d’autres ressources *entre* les environnements. Par exemple, il est impossible de créer un connecteur personnalisé dans un environnement spécifique et de créer un flux qui utilise ce connecteur personnalisé et une passerelle dans un environnement différent.

Par conséquent, il est important que les environnements soient uniquement créés lorsque cela est nécessaire. La création d’un trop grand nombre d’environnements complique le partage des ressources des utilisateurs au sein de votre organisation.

## <a name="use-the-default-environment"></a>Utiliser l’environnement par défaut
L’environnement **par défaut** est disponible pour chaque utilisateur et il est partagé par tous les utilisateurs. Tous les utilisateurs peuvent créer des flux dans cet environnement.

> [!TIP]
> Si vous êtes un utilisateur de la version préliminaire, tous les flux existants se trouvent dans l’environnement par défaut. Un *utilisateur de la version préliminaire* est une personne qui utilisait Microsoft Flow avant sa mise à disposition générale. 
> 
> 

## <a name="use-the-administrator-center"></a>Utiliser le centre d’administration
Les administrateurs utilisent le centre d’administration pour créer des environnements, ajouter des utilisateurs à ces environnements et effectuer d’autres tâches similaires. Il existe deux manières d’ouvrir le centre d’administration :

#### <a name="option-1-select-settings"></a>Option 1 : sélectionner des paramètres
1. Connectez-vous à [flow.microsoft.com](https://flow.microsoft.com).
2. Sélectionnez l’icône des paramètres, puis choisissez **Centre d’administration** dans la liste :  
   ![Paramètres et portail d’administration](./media/environments-overview-admin/settings.png)
3. Le centre d’administration s’ouvre.

#### <a name="option-2-open-adminflowmicrosoftcom"></a>Option 2 : ouvrir admin.flow.microsoft.com
Accédez à [admin.flow.microsoft.com](https://admin.flow.microsoft.com) et connectez-vous avec votre compte professionnel. Le centre d’administration s’ouvre.

## <a name="create-an-environment"></a>Créer un environnement
1. Dans le [centre d’administration Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **Environnements**. Les environnements existants s’affichent :  
   ![](./media/environments-overview-admin/environments-list.png)
2. Sélectionnez **Nouvel environnement**. Entrez les informations suivantes :
   
   | Propriété | Description |
   | --- | --- |
   | Nom de l’environnement |Entrez le nom de votre environnement, tel que `Human Resources` ou `Europe flows`. |
   | Région |Choisissez l’emplacement dans lequel héberger votre environnement. Pour bénéficier de performances optimales, utilisez la région la plus proche de vos utilisateurs. Par exemple, si vos utilisateurs de flux sont basés à Paris, choisissez la région Europe. Si vos utilisateurs de flux sont basés à New York, choisissez la région États-Unis. |
3. Sélectionnez **Créer un environnement**. Votre nouvel environnement est répertorié. 

Ensuite, ajoutez des utilisateurs à l’environnement.

## <a name="manage-your-existing-environments"></a>Gérer vos environnements existants
1. Dans le [centre d’administration Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **Environnements** :  
   ![](./media/environments-overview-admin/select-environments.png)  
2. Sélectionnez un environnement pour ouvrir ses propriétés. 
3. La section **Détails** affiche des informations supplémentaires sur l’environnement, y compris le créateur de l’environnement, son emplacement géographique et d’autres propriétés :  
   ![](./media/environments-overview-admin/open-environment.png)
4. Sélectionnez **Sécurité**. Dans **Rôles d’environnement**, il existe deux options : **Administrateur** et **Créateur** :  
   
    ![](./media/environments-overview-admin/environment-roles.png)
   
    Un **créateur** peut créer des ressources dans un environnement, telles que les flux, les connexions aux données et les passerelles. 
   
   > [!NOTE]
   > Un utilisateur n’a pas besoin d’être **créateur** pour *modifier* des ressources dans un environnement, mais uniquement pour créer des ressources *net*. Chaque créateur de ressource peut déterminer qui peut modifier cette ressource et accorder des autorisations de modification aux utilisateurs qui ne sont pas des créateurs de l’environnement.
   > 
   > 
   
    Un **administrateur** peut créer des stratégies de protection contre la perte de données. Il peut également effectuer des tâches administratives, telles que la création d’environnements, l’ajout d’utilisateurs à un environnement et l’assignation des privilèges d’administrateur/de créateur.  
   
   1. Sélectionnez le rôle **Créateur de l’environnement**, puis **Utilisateurs** :  
      ![](./media/environments-overview-admin/add-environment-maker.png)
   2. Entrez un nom, une adresse de messagerie ou un groupe d’utilisateurs auquel vous souhaitez affecter le rôle Créateur. À mesure que vous tapez, intellisense commence à indiquer les utilisateurs/groupes qui correspondent au texte que vous entrez. 
   3. Sélectionnez **Enregistrer** pour terminer l’ajout d’utilisateurs. 
5. Dans **Sécurité**, sélectionnez **Rôles d’utilisateur** :  
    ![](./media/environments-overview-admin/security-user-roles.png)
   
    Tous les rôles existants sont répertoriés, y compris les options pour modifier ou supprimer le rôle. 
   
    Sélectionnez **Nouveau rôle** pour créer un rôle. 
6. Dans **Sécurité**, sélectionnez **Jeux d’autorisations** :  
    ![](./media/environments-overview-admin/security-permission-set.png)
   
    Tous les jeux d’autorisations existants sont répertoriés, y compris les options pour modifier ou supprimer le rôle. 
   
    Sélectionnez **Nouvel ensemble d’autorisations** pour en créer un. 
7. Dans **Base de données**, vous pouvez choisir de créer une base de données pour stocker vos données. Cette base de données fait partie du service Common Data Service.

## <a name="commonly-asked-questions"></a>Forum aux questions
##### <a name="can-i-migrate-a-microsoft-flow-in-my-us-environment-to-a-europe-environment"></a>Puis-je migrer un flux Microsoft de mon environnement situé aux États-Unis dans un environnement en Europe ?
Non, vous ne pouvez pas déplacer les flux entre différents environnements. Vous devez recréer le flux dans un environnement différent.

##### <a name="which-license-includes-the-common-data-service"></a>Quelle licence inclut le service Common Data Service ?
Seul Microsoft PowerApps plan 2 inclut les droits nécessaires à la création des bases de données avec le service Common Data Service. Toutefois, tous les plans payants (Microsoft Flow plans 1 et 2 et Microsoft PowerApps plans 1 et 2) ont les droits nécessaires à l’utilisation du service Common Data Service.

La page sur la [tarification de Flow](https://flow.microsoft.com/pricing/) peut vous aider à choisir une offre adaptée à vos besoins.  

La page de [questions sur la facturation](billing-questions.md) vous permet également de consulter certaines des questions fréquentes que nous avons reçues. 

##### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Le service Common Data Service peut-il être utilisé en dehors d’un environnement ?
Non. Le service Common Data Service nécessite un environnement. [En savoir plus](common-data-model-intro.md) à ce sujet.

##### <a name="what-regions-include-microsoft-flow"></a>Quelles régions incluent Microsoft Flow ?
Microsoft Flow prend en charge la plupart des régions que Office 365 prend en charge, consultez [la vue d’ensemble des régions](regions-overview.md) pour plus de détails.

##### <a name="what-is-needed-to-create-my-own-custom-environment"></a>Quels sont les éléments nécessaires pour créer mon environnement personnalisé ?
Tous les utilisateurs possédant la licence Microsoft Flow plan 2 peuvent créer leurs environnements, en plus de l’environnement par défaut. Tous les utilisateurs de Microsoft Flow, y compris d’Office 365 et de la version gratuite, peuvent utiliser les environnements créés par les administrateurs plan 2, mais ils ne peuvent pas créer leurs environnements. 

