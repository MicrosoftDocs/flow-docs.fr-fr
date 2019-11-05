---
title: Vue d’ensemble de l’environnement pour les administrateurs | Microsoft Docs
description: Utilisation, création et gestion d’environnements dans Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: sunaysv
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/22/2017
ms.author: sunayv
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: eb3e1050d22b8f672f47214952428b86186ba145
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547960"
---
# <a name="using-environments-within-microsoft-flow"></a>Utilisation d’environnements dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="benefits"></a>Avantageuse

Les environnements offrent les avantages suivants :

* **Localité des données**: les environnements peuvent être créés dans différentes régions et sont liés à cet emplacement géographique. Lorsque vous créez un workflow dans un environnement, ce Flow est acheminé vers tous les centres de donnés de cet emplacement géographique. Cela offre également un avantage en matière de performances.

    Si vos utilisateurs sont en Europe, créez et utilisez l’environnement dans la région Europe. Si vos utilisateurs se trouvent dans le États-Unis, créez et utilisez l’environnement dans la 

    > [!IMPORTANT]
    > Si vous supprimez l’environnement, tous les flux au sein de cet environnement sont également supprimés. Cela s’applique à tous les éléments que vous créez dans cet environnement, y compris les connexions, les passerelles, les PowerApp et bien plus encore.
* **Protection contre la perte de données**: en tant qu’administrateur, vous ne voulez pas que les flux obtenant des données à partir d’un emplacement interne (tel que *OneDrive entreprise* ou une liste SharePoint contenant des informations sur les salaires), puis publient ces données publiquement (par exemple *, Twitter*). Utilisez la protection contre la perte de données pour contrôler les services qui peuvent partager des données au sein de votre déploiement Microsoft Flow.

    Par exemple, vous pouvez ajouter les services *SharePoint* et *OneDrive entreprise* à une stratégie de données d’entreprise uniquement. Tous les flux créés dans cet environnement peuvent utiliser les services *SharePoint* et *OneDrive entreprise* . Toutefois, ils ne peuvent pas partager des données avec d’autres services qui ne sont pas inclus dans la stratégie de données d’entreprise uniquement.

  > [!NOTE]
  > La protection contre la perte de données est disponible avec certaines références SKU de licence, y compris la licence P2.

* **Limite d’isolation pour toutes les ressources**: tous les flux, passerelles, connexions, connecteurs personnalisés, etc. résident dans un environnement spécifique. Ils n’existent pas dans les autres environnements.
* **Common Data Service**: Voici vos options si vous souhaitez créer un Flow qui insère des données dans un service :

  * Insérez des données dans un fichier Excel et stockez le fichier Excel dans un compte de stockage cloud, tel que OneDrive.
  * Créez un SQL Database, puis stockez vos données dans celui-ci.
  * Utilisez la Common Data Service pour stocker vos données.

    Chaque environnement peut avoir au maximum une base de données pour vos flux dans le Common Data Service. L’accès à la Common Data Service dépend de la licence que vous avez achetée. le Common Data Service n’est pas inclus dans la licence gratuite.

## <a name="limitations"></a>Limitations

Bien que les environnements présentent de nombreux avantages, ils introduisent également de nouvelles limitations. Le fait que les environnements soient une limite d’isolation signifie que vous ne pouvez jamais avoir de ressources qui référencent des ressources *dans* des environnements. Par exemple, vous ne pouvez pas créer un connecteur personnalisé dans un environnement, puis créer un fluide qui utilise ce connecteur personnalisé dans un environnement différent.

## <a name="use-the-default-environment"></a>Utiliser l’environnement par défaut

L’environnement **par défaut** est partagé par tous les utilisateurs et tout utilisateur peut créer des flux dans l’environnement **par défaut** .

> [!TIP]
> Si vous êtes un utilisateur en version préliminaire, tous les flux existants résident dans l’environnement par défaut. Un *utilisateur* de la version préliminaire est une personne qui utilisait Microsoft Flow avant sa mise à la disposition générale.

## <a name="the-admin-center"></a>Centre d’administration

Les administrateurs utilisent le centre d’administration pour créer et gérer des environnements. Voici les deux façons d’ouvrir le centre d’administration :

### <a name="option-1-select-settings"></a>Option 1 : sélectionner les paramètres

1. Connectez-vous à [Flow.Microsoft.com](https://flow.microsoft.com).
1. Sélectionnez l’engrenage paramètres, puis choisissez **Centre d’administration** dans la liste :

   ![Paramètres et portail d’administration](./media/environments-overview-admin/settings.png)
1. Le centre d’administration s’ouvre.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Option 2 : ouvrir admin.flow.microsoft.com

Accédez à [admin.Flow.Microsoft.com](https://admin.flow.microsoft.com), puis connectez-vous à l’aide de votre compte professionnel.

## <a name="create-an-environment"></a>Créer un environnement

1. Dans le [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **environnements**. Vous verrez tous les environnements existants : environnements ![](./media/environments-overview-admin/environments-list.png)
2. Sélectionnez **nouvel environnement** , puis fournissez les informations requises :


   |     Propriété     |                                                 Descriptive                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nom de l’environnement |              Entrez le nom de votre environnement, par exemple `Human Resources`ou `Europe flows`.              |
   |      Sous      | Choisissez l’emplacement où héberger votre environnement. Pour des performances optimales, utilisez une région la plus proche de vos utilisateurs. |
   | Type d’environnement |                  Choisissez un type d’environnement en fonction de votre licence : production ou essai.                   |

     ![paramètres d’environnement](./media/environments-overview-admin/new-environment-dialog.png)
3. Cliquez sur **créer un environnement**.
4. Vous avez maintenant la possibilité de **créer une base de données ou de** l' **Ignorer**.
5. Si vous choisissez de **créer une base de données**, vous serez invité à entrer une **devise** et une **langue** pour la base de données. En outre, vous pouvez également choisir de déployer des exemples d’applications et de données.

   ![paramètres de configuration de base de données](./media/environments-overview-admin/create-database-dialog2.png)


Vous pouvez maintenant ajouter des utilisateurs à l’environnement.

## <a name="manage-your-existing-environments"></a>Gérer vos environnements existants

1. Dans le [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **environnements**:

   ![élément de menu environnements](./media/environments-overview-admin/select-environments.png)
1. Sélectionnez un environnement pour ouvrir ses propriétés.
1. Utilisez l’onglet **Détails** pour afficher des informations supplémentaires sur un environnement, notamment la personne qui a créé l’environnement, son emplacement géographique et bien plus encore :

   ![onglet Détails](./media/environments-overview-admin/open-environment.png)
1. Sélectionnez **sécurité**.

    Si vous n’avez pas sélectionné **créer une base de données** dans les étapes précédentes, dans rôles d' **environnement**, il existe deux options : **administrateur d’environnement** et créateur d' **environnement**:

    ![rôles d’administrateur](./media/environments-overview-admin/environment-roles.png)

    Un **créateur** peut créer des ressources telles que les flux, les connexions de données et les passerelles dans un environnement.

   > [!NOTE]
   > Un utilisateur n’a pas besoin d’être un **créateur** pour *modifier* les ressources dans un environnement. Chaque fabricant détermine qui peut modifier ses ressources en accordant des autorisations aux utilisateurs qui ne sont pas des fabricants d’environnement.
   > 
   > 

    Un **administrateur** peut créer des stratégies de protection contre la perte de données et effectuer d’autres tâches administratives, telles que la création d’environnements, l’ajout d’utilisateurs à des environnements et l’attribution de privilèges administrateur/créateur.

   1. Sélectionnez le rôle **créateur d’environnement** , puis sélectionnez **utilisateurs**: rôle ![Maker](./media/environments-overview-admin/add-environment-maker.png)
   1. Entrez un nom, une adresse de messagerie ou un groupe d’utilisateurs que vous souhaitez attribuer au rôle de **créateur** .
   1. Sélectionnez **Enregistrer**.

1. Dans **sécurité**, sélectionnez **rôles d’utilisateur**:

    ![rôles d’utilisateur](./media/environments-overview-admin/security-user-roles.png)

    Tous les rôles existants sont répertoriés, y compris les options permettant de modifier ou de supprimer le rôle.

    Sélectionnez **nouveau rôle** pour créer un nouveau rôle.
1. Dans **sécurité**, sélectionnez **jeux d’autorisations**:

    ![paramètre d’autorisation](./media/environments-overview-admin/security-permission-set.png)

    Vous verrez tous les jeux d’autorisations existants et les options permettant de modifier ou de supprimer des rôles.

    Sélectionnez **nouveau jeu d’autorisations** pour créer un nouveau jeu d’autorisations.
1. Si vous avez choisi de **créer une base de**données, pour stocker vos données, cette base de données fait partie du Common Data Service. Lorsque vous cliquez sur l’onglet **sécurité** , vous êtes invité à accéder au centre de **gestion des instances Dynamics 365** , où la sécurité basée sur les rôles peut être appliquée.
![les paramètres de sécurité Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Sélectionnez l’utilisateur dans la liste des utilisateurs dans l’environnement/l’instance.
  ![les paramètres de sécurité Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Attribuez le rôle à l’utilisateur.

   ![attribuer un rôle à un utilisateur](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Les utilisateurs ou les groupes affectés à ces rôles d’environnement n’ont pas automatiquement accès à la base de données de l’environnement (s’il existe) et doivent être accessibles séparément par un propriétaire de la base de données. 
>
>

### <a name="database-security"></a>Sécurité de la base de données
La possibilité de créer et de modifier un schéma de base de données et de se connecter aux données stockées dans une base de données configurée dans votre environnement est contrôlée par les rôles d’utilisateur et les jeux d’autorisations de la base de données. Vous pouvez gérer les rôles d’utilisateur et les jeux d’autorisations pour la base de données de votre environnement à partir de la section **rôles d’utilisateur** et **jeux d’autorisations** de l’onglet **sécurité** . 

   ![attribuer un rôle à un utilisateur](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="can-i-move-a-flow-between-environments"></a>Puis-je déplacer un flow entre des environnements ?

Oui, les flux peuvent être exportés à partir d’un environnement et importés dans un autre environnement.

### <a name="which-license-includes-the-common-data-service"></a>Quelle licence comprend la Common Data Service ?

Seul Microsoft PowerApps plan 2 comprend des droits de création de bases de données avec le Common Data Service. Toutefois, tous les plans payants (Microsoft Flow plans 1 et 2 et Microsoft PowerApps plans 1 et 2) ont les droits d’utiliser le Common Data Service.

Choisissez un plan qui vous convient en visitant la page de [tarification Microsoft Flow](https://flow.microsoft.com/pricing/) .

Pour obtenir des réponses aux questions fréquemment posées sur la facturation, consultez le document sur les questions sur la [facturation](billing-questions.md) .

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Le Common Data Service peut-il être utilisé en dehors d’un environnement ?

º. L’Common Data Service nécessite un environnement. [En savoir plus](common-data-model-intro.md) à ce sujet.

### <a name="what-regions-include-microsoft-flow"></a>Quelles sont les régions Microsoft Flow ?

Microsoft Flow prend en charge la plupart des régions prises en charge par Office 365, consultez [la vue d’ensemble des régions](regions-overview.md) pour plus de détails.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Qu’est-ce qui est nécessaire pour créer mon environnement personnalisé ?

Tous les utilisateurs ayant la licence Microsoft Flow plan 2 peuvent créer leurs propres environnements. Tous les utilisateurs de Microsoft Flow peuvent utiliser les environnements créés par les administrateurs de plan 2, mais ils ne peuvent pas créer leurs propres environnements.
