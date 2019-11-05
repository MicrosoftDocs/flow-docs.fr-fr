---
title: Présentation des stratégies de protection contre la perte de données (DLP). | Microsoft Docs
description: Présentation des stratégies de protection contre la perte de données pour Microsoft Flow.
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
ms.date: 04/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 46f646fb81fcf7043ff612a240528fed72638048
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548550"
---
# <a name="data-loss-prevention-dlp-policies"></a>Stratégies de protection contre la perte de données (DLP)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Ce document présente les stratégies de protection contre la perte de données, qui permettent de protéger les données de votre organisation du partage avec une liste de connecteurs que vous définissez.

## <a name="whats-a-data-loss-prevention-policy"></a>Qu’est-ce qu’une stratégie de protection contre la perte de données ?

Les données d’une entreprise sont essentielles à sa réussite. Ses données doivent être immédiatement disponibles pour la prise de décision, mais elles doivent être protégées afin qu’elles ne soient pas partagées avec des publics qui ne devraient pas y avoir accès. Pour protéger ces données, Microsoft Flow vous offre la possibilité de créer et d’appliquer des stratégies qui définissent les connecteurs consommateurs qui peuvent accéder aux données d’entreprise et les partager. Ces stratégies qui définissent la façon dont les données peuvent être partagées sont appelées stratégies de protection contre la perte de données (DLP).

## <a name="why-create-a-dlp-policy"></a>Pourquoi créer une stratégie DLP ?

Vous créez une stratégie DLP pour définir clairement les connecteurs grand public qui peuvent accéder à vos données d’entreprise et les partager. Par exemple, une organisation qui utilise Microsoft Flow peut ne pas vouloir que ses données d’entreprise dans SharePoint soient publiées automatiquement sur son flux Twitter. Pour éviter cela, vous créez une stratégie DLP qui empêche l’utilisation des données SharePoint comme source pour les tweets.

## <a name="benefits-of-a-dlp-policy"></a>Avantages d’une stratégie DLP

* Garantit que les données sont gérées de manière uniforme dans toute l’organisation.
* Empêche la publication accidentelle de données métier importantes sur des connecteurs tels que des sites de réseaux sociaux.

## <a name="managing-dlp-policies"></a>Gestion des stratégies DLP

### <a name="prerequisites-for-managing-dlp-policies"></a>Conditions préalables à la gestion des stratégies DLP

* Les autorisations d’administrateur d’environnement ou d’administrateur client.

    Pour plus d’informations sur les autorisations, consultez l' [article environnements](environments-overview-admin.md).
* Une [licence Microsoft Flow P2](billing-questions.md).

## <a name="create-a-dlp-policy"></a>Créer une stratégie DLP

### <a name="prerequisites-for-creating-dlp-policies"></a>Conditions préalables à la création de stratégies DLP

Pour créer une stratégie DLP, vous devez disposer d’autorisations pour au moins un environnement.

Suivez ces étapes pour créer une stratégie DLP qui empêche la publication des données du site SharePoint de votre entreprise sur Twitter :

1. Connectez-vous au [Centre d’administration Microsoft Flow](https://admin.flow.microsoft.com) (Centre d’administration).

1. Sélectionnez l’onglet stratégies de données, puis sélectionnez le lien **nouvelle stratégie** :

    ![Connexion](./media/prevent-data-loss/create-policy-1.png)
1. Sélectionnez l’onglet **groupes de données** .

1. Entrez le nom de la stratégie DLP comme *accès sécurisé aux données pour Contoso* dans l’étiquette nom de la **stratégie de données** en haut de la page :

    ![Connexion](./media/prevent-data-loss/create-policy-2.png)

1. Sélectionnez l' [environnement](environments-overview-admin.md) sous l’onglet **environnements** .

    > [!NOTE]
    > En tant qu’administrateur d’environnement, vous pouvez créer des stratégies qui s’appliquent à un seul environnement. En tant qu’administrateur client, vous pouvez créer des stratégies qui s’appliquent à n’importe quelle combinaison d’environnements :
    >
    >

    ![Sélectionner l’environnement](./media/prevent-data-loss/create-policy-3.png)

1. Sélectionnez l’onglet **groupes de données** :

    ![sélectionner des groupes de données](./media/prevent-data-loss/create-policy-4.png)

1. Sélectionnez le lien **Ajouter** situé dans la zone de groupe **données d’entreprise uniquement** :

    ![Sélectionnez Ajouter.](./media/prevent-data-loss/create-policy-5.png)

1. Sélectionnez les connecteurs **SharePoint** et **Salesforce** dans la page **Ajouter des connecteurs** :

   ![sélectionner les connecteurs](./media/prevent-data-loss/create-policy-6.png)

1. Sélectionnez le bouton **Ajouter des connecteurs** pour ajouter les connecteurs pouvant partager des données d’entreprise.

1. Sélectionnez **enregistrer la stratégie** dans le coin supérieur droit de l’écran.

1. Après quelques instants, votre nouvelle stratégie DLP s’affichera dans la liste des stratégies de protection contre la perte de données :

    ![Liste DLP](./media/prevent-data-loss/create-policy-9.png)

1. **Facultatif** Envoyez un courrier électronique ou toute autre communication à votre équipe, en les avertissant qu’une nouvelle stratégie DLP est désormais disponible.

Félicitations, vous avez maintenant créé une stratégie DLP qui permet à l’application de partager des données entre SharePoint et Salesforce et bloque le partage des données avec d’autres services.

> [!NOTE]
> L’ajout d’un service à un groupe de données le supprime automatiquement de l’autre groupe de données. Par exemple, si Twitter se trouve actuellement dans le groupe de données **données d’entreprise uniquement** et que vous ne souhaitez pas autoriser le partage des données d’entreprise avec Twitter, ajoutez simplement le service Twitter au groupe de données **aucune donnée commerciale autorisée** . Cette opération supprime Twitter du groupe de données données d’entreprise uniquement.
>
>

## <a name="data-sharing-violations"></a>Violations de partage de données

En supposant que vous ayez créé la stratégie DLP décrite ci-dessus, si un utilisateur crée un Flow qui partage des données entre Salesforce (qui se trouve dans le groupe de données **données d’entreprise uniquement** ) et Twitter (qui se trouve dans le groupe de données **aucune donnée métier autorisée** ), l’utilisateur sera informé que le workflow est **suspendu** en raison d’un conflit avec la stratégie de protection contre la perte de données que vous avez créée.

![créer un Flow](./media/prevent-data-loss/10.png)

Si vos utilisateurs vous contactent à propos des flux suspendus, voici quelques éléments à prendre en compte :

1. Dans cet exemple, s’il existe une raison commerciale valide pour partager des données d’entreprise entre SharePoint et Twitter, vous pouvez modifier la stratégie DLP.

1. Demandez à l’utilisateur de modifier le Flow pour se conformer à la stratégie DLP.

1. Demandez à l’utilisateur de conserver le workflow dans l’état suspendu jusqu’à ce qu’une décision concernant le partage des données entre ces deux entités soit prise.

## <a name="find-a-dlp-policy"></a>Rechercher une stratégie DLP

### <a name="admins"></a>Administrateurs

Les administrateurs peuvent utiliser la fonctionnalité de recherche à partir du centre d’administration pour rechercher des stratégies DLP spécifiques.

> [!NOTE]
> Les administrateurs doivent publier toutes les stratégies DLP afin que les utilisateurs de l’organisation connaissent les stratégies avant de créer des flux.
>
>

### <a name="makers"></a>Décideurs

Si vous ne disposez pas d’autorisations d’administrateur et que vous souhaitez en savoir plus sur les stratégies DLP dans votre organisation, contactez votre administrateur. Vous pouvez également en savoir plus à partir de l’article sur les [environnements de création](environments-overview-maker.md)

> [!NOTE]
> Seuls les administrateurs peuvent modifier ou supprimer des stratégies DLP.
>
>

## <a name="edit-a-dlp-policy"></a>Modifier une stratégie DLP

1. Lancez le [Centre d’administration](https://admin.flow.microsoft.com).

1. Dans le centre d’administration qui démarre, sélectionnez le lien **stratégies de données** sur le côté gauche.

    ![sélectionner des stratégies de données](./media/prevent-data-loss/2.png)

1. Recherchez dans la liste des stratégies DLP existantes, puis sélectionnez le bouton modifier en regard de la stratégie que vous souhaitez modifier.

1. Apportez les modifications nécessaires à la stratégie. Vous pouvez modifier l’environnement ou les services dans les groupes de données, par exemple.

1. Sélectionnez **enregistrer la stratégie** pour enregistrer vos modifications.

> [!NOTE]
> Les stratégies DLP créées par les administrateurs de locataire peuvent être consultées par les administrateurs de l’environnement, mais elles ne peuvent pas être modifiées par les administrateurs de l’environnement.
>
>

## <a name="delete-a-dlp-policy"></a>Supprimer une stratégie DLP

1. Lancez le [Centre d’administration](https://admin.flow.microsoft.com).

1. Sélectionnez l’onglet **stratégies de données** sur le côté gauche.

    ![sélectionner l’onglet stratégies de données](./media/prevent-data-loss/2.png)

1. Recherchez dans la liste des stratégies DLP existantes, puis sélectionnez le bouton supprimer en regard de la stratégie que vous souhaitez supprimer :

    ![Sélectionnez le bouton supprimer](./media/prevent-data-loss/3-delete.png)

1. Confirmez que vous voulez vraiment supprimer la stratégie en sélectionnant le bouton **supprimer** :

    ![confirmer que vous voulez vraiment supprimer la stratégie](./media/prevent-data-loss/4.png)

## <a name="dlp-policy-permissions"></a>Autorisations de stratégie DLP

Seuls les administrateurs de locataire et d’environnement peuvent créer et modifier des stratégies DLP. En savoir plus sur les autorisations dans l’article [environnements](environments-overview-admin.md) .


## <a name="custom-and-http-connectors"></a>Connecteurs HTTP et personnalisés

Les connecteurs HTTP et personnalisé doivent être ajoutés à DLPs à l’aide d’un modèle Microsoft Flow ou d’un PowerShell.

> [!TIP]
> Vous ne pouvez pas rétrograder de la version de schéma 2018-11-01. La prise en charge HTTP ne peut pas être supprimée d’une stratégie. Si vous tentez de supprimer la prise en charge HTTP, la stratégie DLP est peut-être endommagée. De plus, si une stratégie DLP est mise à jour pour prendre en charge les connecteurs HTTP, les flux actuels utilisant ces fonctionnalités HTTP peuvent être arrêtés.

Voici les connecteurs HTTP que vous pouvez ajouter à une stratégie :

- HTTP (et HTTP + Swagger)
- Webhook HTTP
- Requête HTTP

## <a name="add-connectors-custom-and-http-connectors-with-templates"></a>Ajouter des connecteurs HTTP et des connecteurs personnalisés avec des modèles

Pour ajouter un connecteur personnalisé à une stratégie à l’aide d’un [modèle](https://flow.microsoft.com/galleries/public/templates/ae9683086770420e902c043e5ed4b363/), entrez le nom de la stratégie, le groupe auquel ajouter le connecteur, ainsi que le nom, l’ID et le type du connecteur. Exécutez le Flow une seule fois pour ajouter le connecteur personnalisé à la stratégie et au groupe donnés.

Pour ajouter les connecteurs HTTP à une stratégie existante par le biais du [modèle](https://flow.microsoft.com/galleries/public/templates/834eb1366aa54335a5f979014a9e0477/), entrez le nom de la stratégie à laquelle vous souhaitez les ajouter, puis exécutez le Flow.

## <a name="add-custom-and-http-connectors-with-powershell"></a>Ajouter des connecteurs HTTP et personnalisés avec PowerShell

Pour ajouter la prise en charge des connecteurs personnalisés et/ou des connecteurs HTTP à une stratégie à l’aide de PowerShell, [Téléchargez](https://docs.microsoft.com/powerapps/administrator/powerapps-powershell) et importez les derniers scripts PowerShell powerapps, puis utilisez ces applets de commande : « New-AdminDlpPolicy », « Set-AdminDlpPolicy », « Add-CustomConnectorToPolicy» et « Remove-CustomConnectorFromPolicy » pour modifier la stratégie. Utilisez l’applet de commande « obtenir-Help-detailed » comme référence.


> [!IMPORTANT]
> Utilisez la version de schéma 2018-11-01 lors de la création ou de la mise à jour d’une stratégie DLP pour inclure les connecteurs HTTP. L’ajout de la prise en charge HTTP à l’aide du modèle ou de PowerShell n’affecte que la stratégie spécifiée. Les nouvelles stratégies créées via le centre d’administration ne contiennent pas les connecteurs HTTP.



## <a name="next-steps"></a>Étapes suivantes

* [En savoir plus sur les environnements](environments-overview-admin.md)
* [En savoir plus sur Microsoft Flow](getting-started.md)
* [En savoir plus sur le centre d’administration](admin-center-introduction.md)
* [En savoir plus sur l’intégration de données](https://docs.microsoft.com/common-data-service/entity-reference/dynamics-365-integration)
