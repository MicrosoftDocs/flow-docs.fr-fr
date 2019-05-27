---
title: Se connecter aux données à l’aide de connexions et de passerelles de données locales | Microsoft Docs
description: Ajoutez ou gérez des connexions à SharePoint, SQL Server, OneDrive Entreprise, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive, etc.
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 02/15/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: bdfa1072bca2afc7c608a4dbf68b8f598dff89f1
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64456841"
---
# <a name="manage-connections-in-microsoft-flow"></a>Gérer les connexions dans Microsoft Flow
Si vous créez une connexion dans Microsoft Flow, vous pouvez facilement accéder à vos données lors de la création d’un flux. Microsoft Flow inclut des connexions populaires, telles que SharePoint, SQL Server, Office 365, OneDrive Entreprise, Salesforce, Excel, Dropbox, Twitter, etc. Les connexions sont partagées avec PowerApps. Par conséquent, lorsque vous créez une connexion dans un produit, celle-ci s’affiche dans l’autre produit.

Par exemple, vous pouvez utiliser une connexion pour effectuer les tâches suivantes :

* mettre à jour une liste SharePoint ;
* obtenir des données d’un fichier Excel dans votre compte OneDrive Entreprise ou Dropbox ;
* envoyer un e-mail dans Office 365 ;
* envoyer un tweet.

Vous pouvez créer une connexion dans plusieurs scénarios. En voici quelques exemples :

* création d’un [flux à partir d’un modèle](get-started-logic-template.md) ;
* création d’un [de flux de zéro](get-started-logic-flow.md) ou mise à jour d’un flux existant ;
* création d’une connexion dans le [site web Microsoft Flow][1] directement.

Cette rubrique vous montre comment gérer des connexions dans le [site web Microsoft Flow][1].

## <a name="add-a-connection"></a>Ajouter une connexion
1. Dans le [site web Microsoft Flow][1], connectez-vous avec votre compte professionnel.
2. Dans l’angle supérieur droit, sélectionnez l’icône d’engrenage, puis **Connexions**.
   
    ![Sélectionner les connexions](./media/add-manage-connections/connections-menu.png)
3. Sélectionnez **Créer une connexion**.
4. Dans la liste des **connexions disponibles**, sélectionnez la connexion que vous souhaitez configurer, telle que SharePoint.
5. Sélectionnez le bouton **Créer une connexion**, puis entrez vos informations d’identification pour établir la connexion.

Lorsque la connexion est configurée, elle est répertoriée dans **Mes connexions**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Se connecter à vos données via une passerelle de données locale
À la date où nous rédigeons cet article, SQL Server et SharePoint prennent en charge la passerelle de données locale. Pour créer une connexion qui utilise une passerelle :

1. Suivez les étapes plus haut dans cette rubrique pour ajouter une connexion.
2. Dans la liste des **connexions disponibles**, sélectionnez **SQL Server**, puis la case à cocher **Se connecter via une passerelle de données locale**.
   
    ![Sélectionner la passerelle](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Les passerelles de données Microsoft SharePoint prennent en charge le trafic HTTP (pas le trafic HTTPS).
   > 
   > 
3. Fournissez les informations d’identification de connexion, puis sélectionnez la passerelle que vous souhaitez utiliser.
   
    Pour plus d’informations, consultez [Gérer les passerelles](gateway-manage.md) et [Comprendre les passerelles](gateway-reference.md).
   
    Lorsque la connexion est configurée, elle est répertoriée dans **Mes connexions**.

## <a name="delete-a-connection"></a>Supprimer une connexion
1. Accédez à la page **Mes connexions**, puis sélectionnez l’icône de corbeille en regard de la connexion que vous souhaitez supprimer.
   
    ![Supprimer la connexion](./media/add-manage-connections/delete-connection.png)
2. Sélectionnez **OK** pour confirmer que vous souhaitez supprimer la connexion.
   
    ![Confirmer la suppression](./media/add-manage-connections/delete-confirmation.png)

Lorsque vous supprimez une connexion, celle-ci est supprimée de PowerApps et de Microsoft Flow.

## <a name="update-a-connection"></a>Mettre à jour une connexion
Vous pouvez mettre à jour une connexion qui ne fonctionne pas en raison de modifications apportées à vos informations de compte ou à votre mot de passe.

1. Dans la page **Mes connexions**, sélectionnez le lien **Vérifier le mot de passe** de la connexion que vous souhaitez mettre à jour.
   
    ![Vérifier le mot de passe](./media/add-manage-connections/verify-password.png)
2. Lorsque vous y êtes invité, mettez à jour votre connexion avec les nouvelles informations d’identification.

Lorsque vous mettez à jour une connexion, celle-ci est mise à jour dans PowerApps et Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Dépanner une connexion
Selon les stratégies de votre organisation, vous devrez peut-être utiliser le même compte pour la connexion à Microsoft Flow et la création d’une connexion à SharePoint, Office 365 ou OneDrive Entreprise.

Par exemple, vous pouvez vous connecter à Microsoft Flow avec *yourname@outlook.com*, mais être bloqué lorsque vous essayez de vous connecter à SharePoint avec *yourname@contoso.com*. À la place, vous pouvez vous connecter à Microsoft Flow avec *yourname@contoso.com* pour pouvoir ensuite vous connecter à SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
