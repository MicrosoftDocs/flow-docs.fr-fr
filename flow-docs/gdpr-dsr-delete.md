---
title: Demandes de suppression de l’objet des données de Microsoft Flow RGPD | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux demandes de suppression de l’objet de données RGPD.
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
ms.date: 4/17/2018
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 53e33d1c202b05854401573ca16040f17eb138c9
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548069"
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Réponse aux demandes de suppression de l’objet de données RGPD pour Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Le « droit d’effacement » par la suppression des données personnelles des données client d’une organisation est une protection clé dans le RGPD. La suppression des données personnelles consiste à supprimer toutes les données personnelles et les journaux générés par le système, à l’exception des informations du journal d’audit.

Microsoft Flow permet aux utilisateurs de créer des flux de travail d’automatisation qui constituent un élément essentiel des opérations quotidiennes de votre organisation. Lorsqu’un utilisateur quitte votre organisation, un administrateur doit vérifier manuellement et déterminer s’il faut ou non supprimer certaines données et ressources que l’utilisateur a créées. D’autres données personnelles sont supprimées automatiquement chaque fois que le compte de l’utilisateur est supprimé de Azure Active Directory.

Le tableau suivant indique quelles données personnelles sont supprimées automatiquement et quelles données nécessitent un administrateur pour la révision et la suppression manuelles :

|Nécessite une révision et une suppression manuelles|Supprimé automatiquement lorsque l’utilisateur est supprimé de Azure Active Directory|
|------|------|
|Environnement|Journaux générés par le système|
|Autorisations d’environnement * *|historique des exécutions|
|Trouvent|Flux d’activités|
|Autorisations de Flow|Gateway |
|Détails de l’utilisateur|Autorisations de la passerelle|
|Connexions||
|Autorisations de connexion||
|Connecteur personnalisé *||
|Autorisations de connecteur personnalisées||

\* Chacune de ces ressources contient les enregistrements « créé par » et « modifié par » qui incluent des données personnelles. Pour des raisons de sécurité, ces enregistrements sont conservés jusqu’à ce que la ressource soit supprimée.

\* * Pour les environnements qui incluent une base de données Common Data Service, les autorisations d’environnement (par exemple, les utilisateurs affectés aux rôles concepteur d’environnement et administrateur) sont stockées sous forme d’enregistrements dans la base de données Common Data Service. Pour obtenir des conseils sur la façon de répondre à retours directs pour les utilisateurs qui utilisent le Common Data Service, voir [exécution de retours directs sur Common Data Service données client](https://go.microsoft.com/fwlink/?linkid=872251).

Pour les données et les ressources qui nécessitent une révision manuelle, Microsoft Flow offre les expériences suivantes pour rechercher ou modifier les données personnelles d’un utilisateur spécifique :

* **Accès au site Web :** Connectez-vous au [Centre d’administration PowerApp](https://admin.powerapps.com/), ou au [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com/)

* **Accès PowerShell :**  [cdmlets PowerShell admin de PowerApp](https://go.microsoft.com/fwlink/?linkid=871804) 

Voici la répartition des expériences disponibles pour un administrateur pour supprimer chaque type de données personnelles au sein de chaque type de ressource :

|Ressources contenant des données personnelles|Accès au site Web|Accès PowerShell|Suppression automatisée|
|-----|----|----|----|
|Journaux générés par le système|[Portail d’approbation des services Office 365](https://servicetrust.microsoft.com/)|||
|Environnement|Centre d’administration Microsoft Flow|Applets de commande PowerApps||
|Autorisations d’environnement *|Centre d’administration Microsoft Flow|Applets de commande PowerApps||
|historique des exécutions||| Supprimé jusqu’à la stratégie de rétention de 28 jours|
|Flux d’activités |||Supprimé jusqu’à la stratégie de rétention de 28 jours|
|Travaux utilisateur|| ||
|Trouvent|Portail Microsoft Flow Maker * *|||
|Autorisations de Flow|Portail Microsoft Flow Maker|||
|Détails de l’utilisateur||Applets de commande PowerApps||
|Connexions|Portail Microsoft Flow Maker| ||
|Autorisations de connexion|Portail Microsoft Flow Maker| ||
|Connecteur personnalisé|Portail Microsoft Flow Maker| ||
|Autorisations de connecteur personnalisées|Portail Microsoft Flow Maker| ||
|Historique des approbations|Portail Microsoft PowerApps Maker *|||

\* Avec l’introduction de la Common Data Service, si une base de données est créée dans l’environnement, les autorisations d’environnement et les autorisations d’applications basées sur des modèles sont stockées sous forme d’enregistrements dans l’instance de base de données Common Data Service. Pour obtenir des conseils sur la façon de répondre à retours directs pour les utilisateurs qui utilisent le Common Data Service, voir [exécution de retours directs sur Common Data Service données client](https://go.microsoft.com/fwlink/?linkid=872251).

\*\* un administrateur pourra accéder à ces ressources à partir du portail Microsoft Flow Maker uniquement si l’accès à partir du centre d’administration Microsoft Flow a été attribué à l’administrateur.

## <a name="manage-delete-requests"></a>Gérer les demandes de suppression

Les étapes ci-dessous décrivent comment des fonctions administratives existent pour traiter les requêtes de suppression pour RGPD. Ces étapes doivent être effectuées dans l’ordre indiqué ci-dessous.

> [!IMPORTANT]
> Pour éviter toute altération des données, procédez comme suit dans l’ordre.
>
>

## <a name="list-and-re-assign-flows"></a>Répertorier et réassigner des flux

Ces étapes copient les flux existants pour un utilisateur qui se départ. Si vous attribuez une nouvelle propriété aux copies, ces flux peuvent continuer à prendre en charge les processus d’entreprise existants. La copie de ces flux est importante pour supprimer les liens d’identificateur personnel à l’utilisateur qui se déplacent et de nouvelles connexions doivent être établies pour que le flux se connecte à d’autres API et applications SaaS.

1. Connectez-vous au [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com/), puis sélectionnez l’environnement qui contient les flux détenus par l’utilisateur supprimé.

    ![afficher les environnements](./media/gdpr-dsr-delete/view-environments.png)

1. Sélectionnez **ressources**, > **flux**, puis sélectionnez le titre du flux que vous souhaitez réaffecter.

    ![Afficher les flux](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Sélectionnez **gérer le partage**.

    ![Gérer le partage](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Dans le panneau de **partage** qui apparaît près du bord droit, ajoutez vous-même en tant que propriétaire, puis sélectionnez **Enregistrer**.

    ![Partager le workflow](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Connectez-vous [Microsoft Flow](https://flow.microsoft.com/), sélectionnez **mes flux**, puis sélectionnez **flux d’équipe**.

1. Sélectionnez les points de suspension **(...)** pour le Flow que vous souhaitez copier, puis sélectionnez **Enregistrer sous**.

    ![Enregistrer sous](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configurez les connexions en fonction des besoins, puis sélectionnez **Continuer**.

1. Indiquez un nouveau nom, puis sélectionnez **Enregistrer**.

    ![Créer une copie du Flow](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Cette nouvelle version du flux apparaît dans **mes flux**, où vous pouvez la partager avec d’autres utilisateurs si vous le souhaitez.

    ![Flux d’équipe](./media/gdpr-dsr-delete/team-flows.png)

1. Pour supprimer le workflow d’origine, sélectionnez les points de suspension **(...)** , sélectionnez **supprimer**, puis cliquez à nouveau sur **supprimer** lorsque vous y êtes invité. Cette étape supprime également les identificateurs personnels sous-jacents inclus dans les dépendances système entre l’utilisateur et Microsoft Flow.

    ![Confirmer la suppression du Workflow](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Activez la copie du flux, en ouvrant **mes flux** , puis en activant le contrôle de basculement **sur activé**.

    ![Activer le Flow](./media/gdpr-dsr-delete/toggle-on.png)

1. La copie effectue maintenant la même logique de workflow que la version d’origine.

## <a name="delete-approval-history-from-microsoft-flow"></a>Supprimer l’historique des approbations de Microsoft Flow

 Les données d’approbation pour Microsoft Flow sont stockées dans la version actuelle ou précédente de Common Data Service. Dans le cas d’une approbation, des informations personnelles existent sous la forme d’attributions d’approbation et de commentaires inclus dans une réponse d’approbation. Les administrateurs peuvent accéder à ces données en procédant comme suit :

1. Connectez-vous à [powerapps](https://web.powerapps.com/).

1. Sélectionnez **données**, puis sélectionnez **entités**.

1. Sélectionnez les points de suspension **(...)** pour l’entité **approbation du fluide** , puis ouvrez les données dans Microsoft Excel.

1. Dans Microsoft Excel, recherchez, filtrez, puis supprimez les données d’approbation selon vos besoins.

Pour obtenir des conseils supplémentaires sur la façon de répondre aux retours directs pour les utilisateurs qui utilisent le Common Data Service, voir [exécution de retours directs sur Common Data Service données client](https://go.microsoft.com/fwlink/?linkid=872251).


## <a name="delete-connections-created-by-a-user"></a>Supprimer les connexions créées par un utilisateur

Les connexions sont utilisées conjointement avec les connecteurs pour établir la connectivité avec d’autres API et systèmes SaaS.  Les connexions incluent des références à l’utilisateur qui les a créées et, par conséquent, peuvent être supprimées pour supprimer toutes les références à l’utilisateur.

Applets de commande PowerShell pour PowerApps Maker

Un utilisateur peut supprimer toutes ses connexions à l’aide de la fonction Remove-Connection des [applets de commande PowerShell de powerapps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-AdminPowerAppConnection | Remove-Connection
```

Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all connections for the DSR user and deletes them 
Get-AdminPowerAppConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection 

```

## <a name="delete-the-users-permissions-to-shared-connections"></a>Supprimer les autorisations de l’utilisateur pour les connexions partagées

Applets de commande PowerShell pour PowerApps Maker

Un utilisateur peut supprimer toutes ses attributions de rôles de connexion pour les connexions partagées, fonction Remove-ConnectionRoleAssignment dans les [applets de commande PowerShell de powerapps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

Applets de commande PowerShell pour admin PowerApp

```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all shared connections for the DSR user and deletes their permissions 
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment  

```
> [!NOTE]
> Impossible de supprimer les attributions de rôle de propriétaire sans supprimer la ressource de connexion.
>
>

## <a name="delete-custom-connectors-created-by-the-user"></a>Supprimer les connecteurs personnalisés créés par l’utilisateur

Les connecteurs personnalisés complètent les connecteurs prêts à l’emploi existants et permettent de se connecter à d’autres API, à des systèmes SaaS et à des systèmes développés personnalisés. Les connecteurs personnalisés incluent des références à l’utilisateur qui les a créées et, par conséquent, peuvent être supprimés pour supprimer toutes les références à l’utilisateur.

Applets de commande PowerShell pour PowerApps Maker

Un utilisateur peut supprimer tous ses connecteurs personnalisés la fonction Remove-Connector dans les [applets de commande PowerShell de powerapps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Applets de commande PowerShell pour admin PowerApp
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connectors created by the DSR user and deletes them 
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector  

```

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Supprimer les autorisations de l’utilisateur pour les connecteurs personnalisés partagés

Applets de commande PowerShell pour PowerApps Maker

Un utilisateur peut supprimer toutes ses attributions de rôle de connecteur pour le connecteur personnalisé partagé avec la fonction Remove-ConnectorRoleAssignment dans les [applets de commande PowerShell de powerapps Maker](https://go.microsoft.com/fwlink/?linkid=871448):

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

Applets de commande PowerShell pour admin PowerApp
```PowerShell
Add-PowerAppsAccount

$deleteDsrUserId = "7822bb68-7c24-49ce-90ce-1ec8deab99a7"
#Retrieves all custom connector role assignments for the DSR user and deletes them 
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment  

```

> [!NOTE]
> Impossible de supprimer les attributions de rôle de propriétaire sans supprimer la ressource de connexion.
>
>


## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Supprimer ou réassigner tous les environnements créés par l’utilisateur

En tant qu’administrateur, vous avez deux décisions à prendre lors du traitement d’une demande de suppression DSR pour un utilisateur pour chacun des environnements qui ont été créés par l’utilisateur :

1. Si vous déterminez que l’environnement n’est pas utilisé par une autre personne de votre organisation, vous pouvez choisir de supprimer l’environnement.
1. Si vous déterminez que l’environnement est toujours requis, vous pouvez choisir de ne pas supprimer l’environnement et de vous ajouter vous-même (ou un autre utilisateur de votre organisation) en tant qu’administrateur d’environnement.
> [!IMPORTANT]
> La suppression d’un environnement entraînera la suppression définitive de toutes les ressources au sein de l’environnement, y compris toutes les applications, les flux, les connexions, etc., vérifiez le contenu d’un environnement avant la suppression.
>
>

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Accorder l’accès aux environnements d’un utilisateur à partir du centre d’administration Microsoft Flow

Un administrateur peut accorder un accès administrateur à un environnement créé par un utilisateur spécifique à partir du [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com/). Pour plus d’informations sur les environnements d’administration, accédez à [utilisation d’environnements dans Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Supprimer les autorisations de l’utilisateur pour tous les autres environnements

Les utilisateurs peuvent se voir attribuer des autorisations (comme administrateur d’environnement, créateur d’environnement, etc.) dans un environnement, qui est stocké dans le service Microsoft Flow en tant qu' « attribution de rôle ».

Avec l’introduction de la Common Data Service, si une base de données est créée dans l’environnement, ces « attributions de rôle » sont stockées sous forme d’enregistrements dans l’instance de base de données Common Data Service.

Pour plus d’informations sur la suppression de l’autorisation d’un utilisateur dans un environnement, accédez à [utilisation d’environnements dans Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-gateway-settings"></a>Supprimer les paramètres de passerelle

Vous trouverez des réponses aux demandes de suppression de l’objet de données pour les passerelles de données locales [ici](https://docs.microsoft.com/power-bi/service-gateway-onprem#tenant-level-administration).

## <a name="delete-user-details"></a>Supprimer les détails de l’utilisateur

Les détails de l’utilisateur fournissent une liaison entre un utilisateur et un locataire spécifique. Avant d’exécuter cette commande, assurez-vous que tous les flux de cet utilisateur ont été réaffectés et/ou supprimés. Une fois cette opération terminée, un administrateur peut supprimer les détails de l’utilisateur en appelant l’applet de commande **Remove-AdminFlowUserDetails** et en transmettant l’ID d’objet de l’utilisateur.

Applets de commande PowerShell pour admin PowerApp
```PowerShell
Add-PowerAppsAccount
Remove-AdminFlowUserDetails -UserId 1b6759b9-bbea-43b6-9f3e-1af6206e0e80
```

> [!IMPORTANT]
> Si un utilisateur est toujours propriétaire d’un individu ou d’un flux d’équipe, cette commande renvoie une erreur. Pour résoudre ce cas, supprimez tous les flux de travail ou flux d’équipe restants pour cet utilisateur, puis exécutez à nouveau la commande.
>
>

## <a name="delete-the-user-from-azure-active-directory"></a>Supprimer l’utilisateur de Azure Active Directory

Une fois les étapes ci-dessus terminées, l’étape finale consiste à supprimer le compte de l’utilisateur pour Azure Active Directory en suivant les étapes décrites dans la documentation relative à la demande Azure Data subject RGPD qui se trouve sur le [portail Office 365 Service Trust](https://servicetrust.microsoft.com/ViewPage/GDPRDSR).

## <a name="delete-the-user-from-unmanaged-tenant"></a>Supprimer l’utilisateur du locataire non géré

Dans le cas où vous êtes membre d’un locataire non géré, vous devez effectuer une action de **clôture de compte** à partir du portail de [confidentialité professionnel et scolaire](https://go.microsoft.com/fwlink/?linkid=873123).

Pour déterminer si vous êtes un utilisateur d’un locataire géré ou non, effectuez les actions suivantes :

1. Ouvrez l’URL suivante dans un navigateur, en veillant à remplacer votre adresse de messagerie dans l’URL :[https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1](https://login.microsoftonline.com/common/userrealm/foobar@contoso.com?api-version=2.1).
1. Si vous êtes membre d’un **locataire non géré** , vous verrez une `"IsViral": true` dans la réponse.

    {

     « Connexion » : «foobar@unmanagedcontoso.com»,

    « Nom_domaine » : « unmanagedcontoso.com »,

    « IsViral » : **true**,
    
    }

1. Dans le cas contraire, vous appartenez à un locataire géré.
