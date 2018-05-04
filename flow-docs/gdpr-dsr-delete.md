---
title: Requêtes de suppression RGPD d’une personne concernée avec Microsoft Flow | Microsoft Docs
description: Découvrez comment utiliser Microsoft Flow pour répondre aux requêtes de suppression RGPD d’une personne concernée.
services: ''
suite: flow
documentationcenter: na
author: KentWeareMSFT
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 4/17/2018
ms.author: keweare
ms.openlocfilehash: d750ee2bc672d08bff940341349663b4721f9a57
ms.sourcegitcommit: 12fbfe22fedd780d42ef1d2febfd7a0769b4902e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="responding-to-gdpr-data-subject-delete-requests-for-microsoft-flow"></a>Répondre aux requêtes de suppression RGPD d’une personne concernée pour Microsoft Flow

Le « droit à l’effacement » par suppression des données personnelles des données client d’une organisation est une protection clé de la directive RGPD. La suppression des données personnelles inclut la suppression de la totalité des données personnelles et des journaux générés par le système, à l’exception des informations du journal d’audit.

Microsoft Flow permet aux utilisateurs de créer des flux de travail d’automatisation essentiels aux opérations quotidiennes de votre organisation. Lorsqu’un utilisateur quitte votre organisation, un administrateur doit manuellement examiner et décider ou non de supprimer certaines données et ressources créées par l’utilisateur. D’autres données personnelles sont supprimées automatiquement chaque fois que le compte de l’utilisateur est supprimé d’Azure Active Directory.

Le tableau suivant présente les données personnelles automatiquement supprimées et celles qu’un administrateur doit vérifier et supprimer manuellement :

|Nécessite une vérification et une suppression manuelles|Automatiquement supprimées lorsque l’utilisateur est supprimé d’Azure Active Directory|
|------|------|
|Environnement*|Journaux générés par le système|
|Autorisations d’environnement**|Historique des exécutions|
|Flux|Tâches de l’utilisateur|
|Autorisations de flux|Passerelle |
|Détails de l’utilisateur|Autorisations de passerelle |
|Connexions*||
|Autorisations de connexion||
|Connecteur personnalisé*||
|Autorisations des connecteurs personnalisés||

* Chacune de ces ressources contient les enregistrements « Créé par » et « Modifié par » incluant des données personnelles. Pour des raisons de sécurité, ces enregistrements sont conservés jusqu'à ce que la ressource soit supprimée.

* Pour les environnements qui incluent une base de données Common Data Service For Apps, les autorisations d’environnement (par exemple, les utilisateurs affectés à des rôles Environment Maker et Admin) sont stockées sous forme d’enregistrements dans la base de données Common Data Service. Consultez la section [Exécution de demandes DSR avec des données client Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251) pour obtenir des conseils sur la façon de répondre aux demandes DSR pour les utilisateurs de Common Data Service.

Pour les données et ressources nécessitant une vérification manuelle, Microsoft Flow offre les expériences suivantes, qui permettent de rechercher ou de modifier les données personnelles d’un utilisateur spécifique :

* **Accès au site Web :** connectez-vous au [Centre d’administration de PowerApps](https://admin.powerapps.com/) ou au [Centre d'administration de Microsoft Flow](https://admin.flow.microsoft.com/)

* **Accès à PowerShell :**  [applets de commandes Admin PowerShell PowerApps](https://go.microsoft.com/fwlink/?linkid=871804) 

Voici le détail des expériences disponibles permettant à un administrateur de supprimer chaque type de données personnelles au sein de chaque type de ressource :

|Ressources contenant des données personnelles|Accès au site Web|Accès à PowerShell|Suppression automatique|
|-----|----|----|----|
|Journaux générés par le système|[Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)|||
|Environnement|Centre d'administration de Microsoft Flow|Applets de commande PowerApps||
|Autorisations d’environnement*|Centre d'administration de Microsoft Flow|Applets de commande PowerApps||
|Historique des exécutions||| Supprimé via une stratégie de rétention de 28 jours|
|Flux d'activités ||Applets de commande PowerApps||
|Tâches de l’utilisateur|| ||
|Flux|Microsoft Flow Maker Portal**|||
|Autorisations de flux|Microsoft Flow Maker Portal|||
|Détails de l’utilisateur|| ||
|Connexions|Microsoft Flow Maker Portal| ||
|Autorisations de connexion|Microsoft Flow Maker Portal| ||
|Connecteur personnalisé|Microsoft Flow Maker Portal| ||
|Autorisations des connecteurs personnalisés|Microsoft Flow Maker Portal| ||
|Historique des approbations|Microsoft PowerApps Maker Portal*|||

*Avec l’introduction de Common Data Service for Apps, si une base de données est créée dans l’environnement, les autorisations de cet environnement et les autorisations d’apps basées sur un modèle sont stockées sous forme d’enregistrements dans Common Data Service pour l’instance de base de données d’applications. Consultez la section [Exécution de demandes DSR avec des données client Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251) pour obtenir des conseils sur la façon de répondre aux demandes DSR pour les utilisateurs de Common Data Service.

**Un administrateur pourra uniquement accéder à ces ressources depuis Microsoft Flow Maker Portal s’il en a reçu l’accès à partir du Centre d'administration de Microsoft Flow.

## <a name="manage-delete-requests"></a>Gérer les requêtes de suppression

Les étapes ci-dessous décrivent les fonctions administratives permettant d’exécuter les demandes de suppression RGPD.

> [!IMPORTANT]
> Pour éviter toute altération des données, effectuez ces étapes dans l’ordre.
>
>

## <a name="list-and-re-assign-flows"></a>Répertorier et réattribuer les flux

Ces étapes copient des flux existants pour un utilisateur qui quitte l’organisation. Si vous attribuez une nouvelle propriété aux copies, ces flux peuvent continuer à prendre en charge les processus d’entreprise existant. La copie de ces flux est importante pour supprimer les liaisons d’identification personnelle de l’utilisateur qui quitte l’organisation, et de nouvelles connexions doivent être établies pour le flux afin de se connecter à d’autres API et applications SaaS.

1. Connectez-vous au [Centre d’administration de Microsoft Flow](https://admin.flow.microsoft.com/), puis sélectionnez l’environnement contenant le flux qui appartient à l’utilisateur supprimé.

    ![Afficher les environnements](./media/gdpr-dsr-delete/view-environments.png)

1. Sélectionnez **Ressources** > **Flux**, puis choisissez le titre du flux que vous souhaitez réaffecter.

    ![Afficher les flux](./media/gdpr-dsr-delete/admin-view-flows.png)

1. Sélectionnez **Gérer le partage**.

    ![Gérer le partage](./media/gdpr-dsr-delete/admin-manage-sharing.png)

1. Dans le panneau **Partage** qui s’affiche près du bord droit, ajoutez-vous en tant que propriétaire, puis sélectionnez **Enregistrer**.

    ![Partager un flux](./media/gdpr-dsr-delete/flow-sharing-save.png)

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com/), sélectionnez **Mes flux**, puis **Flux d'équipes**.

1. Choisissez les points de suspension **(...)** pour le flux que vous souhaitez copier, puis sélectionnez **Enregistrer sous**.

    ![Enregistrer le flux sous](./media/gdpr-dsr-delete/flow-save-as.png)

1. Configurez les connexions selon vos besoins, puis sélectionnez **Continuer**.

1. Indiquez un nouveau nom, puis sélectionnez **Enregistrer**.

    ![Créer une copie du flux](./media/gdpr-dsr-delete/create-copy-flow.png)

1. Cette nouvelle version du flux apparaît dans **Mes flux**, où vous pouvez la partager avec d’autres utilisateurs si vous le souhaitez.

    ![Flux d'équipes](./media/gdpr-dsr-delete/team-flows.png)

1. Pour supprimer le flux d’origine, sélectionnez les points de suspension **(...)**  pour ce flux, choisissez **Supprimer**, puis **Supprimer** à nouveau lorsque vous y êtes invité. Cette étape supprimera également les identificateurs personnels sous-jacents inclus dans les dépendances système entre l’utilisateur et Microsoft Flow.

    ![Confirmation de suppression du flux](./media/gdpr-dsr-delete/delete-flow-confirmation.png)

1. Activez la copie du flux en ouvrant **Mes flux** puis en positionnant le contrôle de basculement sur **On** (Activé).
    ![Activer le flux](./media/gdpr-dsr-delete/toggle-on.png)

1. La copie exécute maintenant la même logique de workflow que la version d’origine.

## <a name="delete-approval-history-from-microsoft-flow"></a>Supprimer l’historique des approbations de Microsoft Flow

 Les données d’approbation de Microsoft Flow sont stockées dans la version actuelle ou une version précédente de Common Data Service for Apps. Dans une approbation, les informations personnelles existent sous la forme d’attributions d’approbation, et des commentaires sont inclus dans une réponse d’approbation. Les administrateurs peuvent accéder à ces données en procédant comme suit :

1. Connectez-vous à [PowerApps](https://web.powerapps.com/).

1. Sélectionnez **Données**, puis **Entités**.

1. Sélectionnez les points de suspension **(...)**  pour l’entité **Approbation de flux**, puis ouvrez les données dans Microsoft Excel.

1. Dans Microsoft Excel, recherchez, filtrez, puis supprimez les données d’approbation selon les besoins.

Consultez la section [Exécution de demandes DSR avec des données client Common Data Service](https://go.microsoft.com/fwlink/?linkid=872251) pour obtenir des conseils supplémentaires sur la façon de répondre aux demandes DSR pour les utilisateurs de Common Data Service.

## <a name="delete-connections-created-by-a-user"></a>Supprimer les connexions créées par un utilisateur

Les connexions sont utilisées conjointement avec les connecteurs pour établir la connectivité avec d’autres API et systèmes SaaS.  Les connexions incluent des références à l’utilisateur qui les a créés et, par conséquent, peuvent être supprimées pour effacer toutes les références à cet utilisateur.

Applets de commande PowerShell PowerApps Maker

Un utilisateur peut supprimer toutes ses connexions à l’aide de la fonction Remove-Connection des [applets de commande PowerShell PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448) :

```PowerShell
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

Applets de commandes PowerShell PowerApps Admin

Non disponible.

## <a name="delete-the-users-permissions-to-shared-connections"></a>Supprimer les autorisations de l’utilisateur pour les connexions partagées

Applets de commande PowerShell PowerApps Maker

Un utilisateur peut supprimer toutes ses attributions de rôles de connexion pour des connexions partagées à l’aide de la fonction ConnectionRoleAssignment des [applets de commande PowerShell PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448) :

```PowerShell
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```

> [!NOTE]
> Les attributions de rôle de propriétaire ne peuvent pas être supprimées sans supprimer également la ressource de connexion.
>
>

Applets de commandes PowerShell PowerApps Admin

Non disponible.

## <a name="delete-custom-connectors-created-by-the-user"></a>Supprimer les connecteurs personnalisés créés par l’utilisateur

Les connecteurs personnalisés complètent les connecteurs fournis par défaut et assurent la connectivité avec d’autres API, SaaS et systèmes personnalisés. Les connecteurs personnalisés incluent des références à l’utilisateur qui les a créés et, par conséquent, peuvent être supprimés pour effacer toutes les références à cet utilisateur.

Applets de commande PowerShell PowerApps Maker

Un utilisateur peut supprimer tous ses connecteurs personnalisés à l’aide de la fonction Remove-Connector des [applets de commande PowerShell PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448) :

```PowerShell
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

Applets de commandes PowerShell PowerApps Admin

Non disponible.

## <a name="delete-the-users-permissions-to-shared-custom-connectors"></a>Supprimer les autorisations de l’utilisateur pour les connecteurs personnalisés partagés

Applets de commande PowerShell PowerApps Maker

Un utilisateur peut supprimer toutes ses attributions de rôles de connexion pour un connecteur personnalisé partagé à l’aide de la fonction Remove-ConnectorRoleAssignment des [applets de commande PowerShell PowerApps Maker](https://go.microsoft.com/fwlink/?linkid=871448) :

```PowerShell
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

> [!NOTE]
> Les attributions de rôle de propriétaire ne peuvent pas être supprimées sans supprimer également la ressource de connexion.
>
>

Applets de commandes PowerShell PowerApps Admin

Non disponible.

## <a name="delete-or-reassign-all-environments-created-by-the-user"></a>Supprimer ou réassigner tous les environnements créés par l’utilisateur

En tant qu’administrateur, vous avez deux décisions à prendre lors du traitement d’une demande de suppression DSR d’un utilisateur pour chacun des environnements qu’il a créés :

1. Si vous déterminez que l’environnement n’est pas utilisé par quelqu'un d’autre dans votre organisation, vous pouvez choisir de le supprimer
1. Si vous déterminez que l’environnement est toujours nécessaire, vous pouvez choisir de ne pas le supprimer et de vous ajouter vous-même (ou un autre utilisateur de votre organisation) en tant qu’administrateur d’environnement.
    > [!IMPORTANT]
    > La suppression d’un environnement supprimera définitivement toutes ses ressources, y compris les applications, flux, connexions, etc., par conséquent, examinez attentivement le contenu d’un environnement avant la suppression.
    >
    >

## <a name="give-access-to-a-users-environments-from-the-microsoft-flow-admin-center"></a>Donner accès aux environnements d’un utilisateur depuis le Centre d’administration de Microsoft Flow

Un administrateur peut accorder un accès Administrateur à un environnement créé par un utilisateur spécifique à partir du [Centre d'administration de Microsoft Flow](https://admin.flow.microsoft.com/). Pour plus d’informations sur l’administration des environnements, consultez la rubrique [Utilisation d’environnements dans Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).

## <a name="delete-the-users-permissions-to-all-other-environments"></a>Supprimer les autorisations de l’utilisateur pour tous les autres environnements

Les utilisateurs peuvent recevoir des autorisations (par exemple, Administrateur d’environnement, Créateur d’environnement Maker, etc.) dans un environnement, stockées dans le service Microsoft Flow sous la forme d’une « attribution de rôle ».

Avec l’introduction de Common Data Service for Apps, si une base de données est créée dans l’environnement, ces « autorisations de rôle » sont stockées sous forme d’enregistrements dans Common Data Service pour l’instance de base de données d’applications.

Pour plus d’informations sur la suppression de l’autorisation d’un utilisateur dans un environnement, consultez la rubrique [Utilisation d’environnements dans Microsoft Flow](https://docs.microsoft.com/flow/environments-overview-admin).
