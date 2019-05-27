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
ms.openlocfilehash: 43f6f36cc32ec40088bd9b4c61e2895a7de78589
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "65035034"
---
# <a name="using-environments-within-microsoft-flow"></a>Utilisation d’environnements dans Microsoft Flow

## <a name="benefits"></a>Avantages

Les environnements présentent les avantages suivants :

* **Localité des données**: Les environnements peuvent être créés dans différentes régions et sont liés à cet emplacement géographique. Lorsque vous créez un flux dans un environnement, ce flux est acheminé vers tous les centres de données situés à cet emplacement géographique. Cela vous permet également de bénéficier de meilleures performances.

    Si vos utilisateurs sont en Europe, créez et utilisez l’environnement dans la région Europe. Si vos utilisateurs sont aux États-Unis, créez et utilisez l’environnement aux États-Unis. 

    > [!IMPORTANT]
    > Si vous supprimez l’environnement, tous les flux associés sont également supprimés. Cela s’applique à tous les éléments que vous créez dans l’environnement, y compris les connexions, les passerelles, PowerApps et bien plus encore.
* **Protection contre la perte de données**: En tant qu’administrateur, vous ne souhaitez pas flux qui récupèrent des données à partir d’un emplacement interne (tel que *OneDrive entreprise* ou une liste SharePoint qui contient des informations sur les salaires), publient ces données publiquement (p. ex. sur * Twitter*). Utilisez la protection contre la perte de données pour contrôler les services qui peuvent partager des données dans votre déploiement Microsoft Flow.

    Par exemple, vous pouvez ajouter les services *SharePoint* et *OneDrive Entreprise* à une stratégie pour les données métier uniquement. Tous les flux créés dans cet environnement peuvent utiliser les services *SharePoint* et *OneDrive Entreprise*. Toutefois, ils ne pourront pas partager des données avec d’autres services qui ne sont pas inclus dans la stratégie pour les données métier uniquement.

  > [!NOTE]
  > La protection contre la perte de données est disponible avec certaines références de licence, y compris la licence P2.

* **Limite d’isolation pour toutes les ressources**: N’importe quel flux, passerelles, connexions, connecteurs personnalisés, etc. résident dans un environnement spécifique. Ils n’existent pas dans les autres environnements.
* **Common Data Service**: Voici les différentes options si vous souhaitez créer un flux qui insère des données dans un service :

  * Insérez des données dans un fichier Excel que vous stockez dans un compte de stockage cloud tel que OneDrive.
  * Créez une base de données SQL Database et stockez-y vos données.
  * Utilisez le service Common Data Service pour stocker vos données.

    Chaque environnement peut avoir au maximum une base de données pour vos flux dans le service Common Data Service. L’accès au service Common Data Service dépend de la licence que vous achetez ; il n’est pas inclus dans la licence gratuite.

## <a name="limitations"></a>Limitations

Bien que les environnements présentent de nombreux avantages, ils introduisent également de nouvelles limitations. Le fait que les environnements soient une limite d’isolement signifie que vous ne pouvez jamais avoir de ressources qui référencent des ressources *entre* les environnements. Par exemple, vous ne pouvez pas créer un connecteur personnalisé dans un environnement spécifique et créer un flux qui utilise ce connecteur personnalisé dans un environnement différent.

## <a name="use-the-default-environment"></a>Utiliser l’environnement par défaut

L’environnement **Par défaut** est partagé par tous les utilisateurs et n’importe quel utilisateur peut créer des flux dans l’environnement **Par défaut**.

> [!TIP]
> Si vous êtes un utilisateur de la version préliminaire, tous les flux existants se trouvent dans l’environnement par défaut. Un *utilisateur de la version préliminaire* est une personne qui utilisait Microsoft Flow avant sa mise à disposition générale.

## <a name="the-admin-center"></a>Centre d’administration

Les administrateurs utilisent le centre d’administration pour créer et gérer des environnements. Il existe deux manières d’ouvrir le centre d’administration :

### <a name="option-1-select-settings"></a>Option 1 : Sélectionnez les paramètres

1. Connectez-vous à [flow.microsoft.com](https://flow.microsoft.com).
1. Sélectionnez l’icône des paramètres, puis choisissez **Centre d’administration** dans la liste :

   ![Paramètres et portail d’administration](./media/environments-overview-admin/settings.png)
1. Le centre d’administration s’ouvre.

### <a name="option-2-open-adminflowmicrosoftcom"></a>Option 2 : Ouvrir admin.flow.microsoft.com

Accédez à [admin.flow.microsoft.com](https://admin.flow.microsoft.com) et connectez-vous avec votre compte professionnel.

## <a name="create-an-environment"></a>Créer un environnement

1. Dans le [centre d’administration Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **Environnements**. Vous verrez tous les environnements existants : ![Environnements](./media/environments-overview-admin/environments-list.png)
2. Sélectionnez **Nouvel environnement**, puis entrez les informations requises :


   |     Propriété     |                                                 Description                                                 |
   |------------------|-------------------------------------------------------------------------------------------------------------|
   | Nom de l’environnement |              Entrez le nom de votre environnement, tel que `Human Resources` ou `Europe flows`.              |
   |      Région      | Choisissez l’emplacement dans lequel héberger votre environnement. Pour bénéficier de performances optimales, utilisez la région la plus proche de vos utilisateurs. |
   | Type d’environnement |                  Sélectionnez un type d’environnement en fonction de votre licence : Version d’évaluation ou de production.                   |

     ![paramètres de l’environnement](./media/environments-overview-admin/new-environment-dialog.png)
3. Cliquez sur **Créer un environnement**.
4. Vous disposez maintenant de deux options : **Créer une base de données** ou **Ignorer**.
5. Si vous choisissez **Créer une base de données**, vous serez invité à entrer une **Devise** et une **Langue** pour la base de données. En outre, vous pouvez également choisir d’avoir des exemples d’applications et des données déployés.

   ![paramètres de configuration de la base de données](./media/environments-overview-admin/create-database-dialog2.png)


Vous pouvez maintenant ajouter des utilisateurs à l’environnement.

## <a name="manage-your-existing-environments"></a>Gérer vos environnements existants

1. Dans le [centre d’administration Microsoft Flow](https://admin.flow.microsoft.com), sélectionnez **Environnements** :

   ![élément de menu Environnements](./media/environments-overview-admin/select-environments.png)
1. Sélectionnez un environnement pour ouvrir ses propriétés.
1. Utilisez l’onglet **Détails** pour afficher des informations supplémentaires sur l’environnement, notamment le créateur de l’environnement, son emplacement géographique et d’autres propriétés :

   ![onglet Détails](./media/environments-overview-admin/open-environment.png)
1. Sélectionnez **Sécurité**.

    Si vous n’avez pas sélectionné **Create Database** dans les étapes précédentes, dans **rôles d’environnement**, deux options sont disponibles : **Administrateur d’environnement** et **créateur d’environnement**:

    ![rôles d’administrateur](./media/environments-overview-admin/environment-roles.png)

    Un **créateur** peut créer des ressources dans un environnement, telles que les flux, les connexions aux données et les passerelles.

   > [!NOTE]
   > Un utilisateur n’a pas besoin d’être un **créateur** pour *modifier* les ressources dans un environnement. Chaque créateur décide qui peut modifier leurs ressources en octroyant des autorisations aux utilisateurs qui ne sont pas des créateurs de l’environnement.
   > 
   > 

    Un **administrateur** peut créer des stratégies de protection contre la perte de données et effectuer d’autres tâches administratives, telles que la création d’environnements, l’ajout d’utilisateurs à des environnements et l’assignation des privilèges d’administrateur/de créateur.

   1. Sélectionnez le rôle **Créateur de l’environnement**, puis **Utilisateurs** : ![rôle de créateur](./media/environments-overview-admin/add-environment-maker.png)
   1. Entrez un nom, une adresse de messagerie ou un groupe d’utilisateurs auquel vous souhaitez affecter le rôle **Créateur**.
   1. Sélectionnez **Enregistrer**.

1. Dans **Sécurité**, sélectionnez **Rôles d’utilisateur** :

    ![rôles d’utilisateurs](./media/environments-overview-admin/security-user-roles.png)

    Tous les rôles existants sont répertoriés, y compris les options pour modifier ou supprimer le rôle.

    Sélectionnez **Nouveau rôle** pour créer un rôle.
1. Dans **Sécurité**, sélectionnez **Jeux d’autorisations** :

    ![définition des autorisations](./media/environments-overview-admin/security-permission-set.png)

    Vous verrez tous les jeux d’autorisations existants, ainsi que des options pour modifier ou supprimer des rôles.

    Sélectionnez **Nouveau jeu d’autorisations** pour créer une nouvelle autorisation.
1. Si vous avez choisi **Créer une base de données**, pour stocker vos données, cette base de données fait partie du service Common Data Service. Lorsque vous cliquez sur l’onglet **Sécurité**, vous serez invité à accéder au **centre de gestion des instance Dynamics 365** où la sécurité basée sur les rôles peut être appliquée.
![paramètres de sécurité Dynamics](./media/environments-overview-admin/Security-Link-D365.png)

1. Sélectionnez l’utilisateur dans la liste des utilisateurs dans l’environnement / l’instance.
  ![paramètres de sécurité Dynamics](./media/environments-overview-admin/D365-Select-User.png)

1. Attribuez le rôle à l’utilisateur.

   ![attribuer un rôle à l’utilisateur](./media/environments-overview-admin/D365-Assign-Role.png)

> [!NOTE]
> Les utilisateurs ou groupes affectés à ces rôles d’environnement n’ont pas automatiquement accès à la base de données de l’environnement (le cas échéant) et doivent se voir attribuer l’accès séparément par un propriétaire de la base de données. 
>
>

### <a name="database-security"></a>Sécurité de la base de données
La possibilité de créer et de modifier un schéma de base de données et de se connecter aux données stockées dans une base de données qui est provisionnée dans votre environnement est contrôlée par les rôles d’utilisateurs et les jeux d’autorisations pour la base de données. Vous pouvez gérer les rôles d’utilisateurs et les jeux d’autorisations pour la base de données de votre environnement à partir de la section **Rôles d’utilisateurs** et **Jeux d’autorisations** de l’onglet **Sécurité**. 

   ![attribuer un rôle à l’utilisateur](./media/environments-overview-admin/D365-Assign-Role.png)

## <a name="frequently-asked-questions"></a>Forum aux questions

### <a name="can-i-move-a-flow-between-environments"></a>Puis-je déplacer un flux entre des environnements ?

Oui, les flux peuvent être exportés à partir d’un environnement et importés dans un autre environnement.

### <a name="which-license-includes-the-common-data-service"></a>Quelle licence inclut le service Common Data Service ?

Seul Microsoft PowerApps plan 2 inclut les droits nécessaires à la création des bases de données avec le service Common Data Service. Toutefois, tous les plans payants (Microsoft Flow plans 1 et 2 et Microsoft PowerApps plans 1 et 2) ont les droits nécessaires à l’utilisation du service Common Data Service.

Choisissez un plan qui vous convient en consultant la page [Tarification Microsoft Flow](https://flow.microsoft.com/pricing/).

Consultez le document [Questions sur la facturation](billing-questions.md) pour obtenir des réponses aux questions fréquemment posées sur la facturation.

### <a name="can-the-common-data-service-be-used-outside-of-an-environment"></a>Le service Common Data Service peut-il être utilisé en dehors d’un environnement ?

Non. Le service Common Data Service nécessite un environnement. [En savoir plus](common-data-model-intro.md) à ce sujet.

### <a name="what-regions-include-microsoft-flow"></a>Quelles régions incluent Microsoft Flow ?

Microsoft Flow prend en charge la plupart des régions que Office 365 prend en charge, consultez [la vue d’ensemble des régions](regions-overview.md) pour plus de détails.

### <a name="whats-needed-to-create-my-own-custom-environment"></a>Quels sont les éléments nécessaires pour créer mon environnement personnalisé ?

Tous les utilisateurs possédant la licence Microsoft Flow plan 2 peuvent créer leurs environnements. Tous les utilisateurs de Microsoft Flow peuvent utiliser les environnements créés par les administrateurs plan 2, mais ils ne peuvent pas créer leurs environnements.
