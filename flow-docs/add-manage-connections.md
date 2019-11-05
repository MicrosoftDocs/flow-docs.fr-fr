---
title: Apprenez à vous connecter à vos données à l’aide de connexions et de passerelles de données locales | Microsoft Docs
description: Ajoutez ou gérez des connexions à SharePoint, SQL Server, OneDrive entreprise, Salesforce, Office 365, OneDrive, Dropbox, Twitter, Google Drive, etc.
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
ms.openlocfilehash: 1de8602cc573e800d721b6b70222df49cf1577e3
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544752"
---
# <a name="manage-connections-in-microsoft-flow"></a>Gérer les connexions dans Microsoft Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Si vous créez une connexion dans Microsoft Flow, vous pouvez facilement accéder à vos données lors de la création d’un fluide. Microsoft Flow inclut des connexions couramment utilisées, notamment SharePoint, SQL Server, Office 365, OneDrive entreprise, Salesforce, Excel, Dropbox, Twitter et bien plus encore. Les connexions sont partagées avec PowerApps. par conséquent, lorsque vous créez une connexion dans un produit, la connexion s’affiche dans l’autre.

Par exemple, vous pouvez utiliser une connexion pour effectuer les tâches suivantes :

* Mettre à jour une liste SharePoint.
* Obtenir des données à partir d’un fichier Excel dans votre compte OneDrive entreprise ou Dropbox.
* Envoyer un courrier électronique dans Office 365.
* Envoyer un tweet.

Vous pouvez créer une connexion dans plusieurs scénarios, tels que ceux-ci :

* Création [d’un workflow à partir d’un modèle](get-started-logic-template.md)
* Création [d’un workflow à partir d’un espace vide](get-started-logic-flow.md) ou mise à jour d’un workflow existant
* Création directe d’une connexion dans le [site web Microsoft Flow][1]

Cette rubrique vous montre comment gérer les connexions dans le [site web Microsoft Flow][1].

## <a name="add-a-connection"></a>Ajouter une connexion
1. Dans le [site web Microsoft Flow][1], connectez-vous avec votre compte professionnel ou d’organisation.
2. Près de l’angle supérieur droit, sélectionnez l’icône d’engrenage, puis sélectionnez **connexions**.
   
    ![Sélectionner les connexions](./media/add-manage-connections/connections-menu.png)
3. Sélectionnez **créer une connexion**.
4. Dans la liste des **connexions disponibles**, sélectionnez la connexion que vous souhaitez configurer, telle que SharePoint.
5. Sélectionnez le bouton **créer une connexion** , puis entrez vos informations d’identification pour configurer la connexion.

Une fois la connexion configurée, elle est indiquée dans **mes connexions**.

## <a name="connect-to-your-data-through-an-on-premises-data-gateway"></a>Connectez-vous à vos données via une passerelle de données locale
À la rédaction de cet article, SQL Server et SharePoint Server prennent en charge la passerelle de données locale. Pour créer une connexion qui utilise une passerelle :

1. Suivez les étapes décrites précédemment dans cette rubrique pour ajouter une connexion.
2. Dans la liste des **connexions disponibles**, sélectionnez **SQL Server**, puis activez la case à cocher **se connecter via une passerelle de données locale** .
   
    ![Sélectionner une passerelle](./media/add-manage-connections/select-gateway.png)
   
   > [!IMPORTANT]
   > Les passerelles de données Microsoft SharePoint prennent en charge le trafic HTTP, mais pas HTTPs.
   > 
   > 
3. Fournissez les informations d’identification de la connexion, puis sélectionnez la passerelle que vous souhaitez utiliser.
   
    Pour plus d’informations, consultez [gérer les passerelles](gateway-manage.md) et [comprendre les passerelles](gateway-reference.md).
   
    Une fois la connexion configurée, elle est indiquée dans **mes connexions**.

## <a name="delete-a-connection"></a>Supprimer une connexion
1. Accédez à la page **mes connexions** , puis sélectionnez l’icône Corbeille pour la connexion que vous souhaitez supprimer.
   
    ![Supprimer la connexion](./media/add-manage-connections/delete-connection.png)
2. Sélectionnez **OK** pour confirmer que vous souhaitez supprimer la connexion.
   
    ![Confirmer la suppression](./media/add-manage-connections/delete-confirmation.png)

Lorsque vous supprimez une connexion, elle est supprimée de PowerApps et Microsoft Flow.

## <a name="update-a-connection"></a>Mettre à jour une connexion
Vous pouvez mettre à jour une connexion qui ne fonctionne pas, car les détails de votre compte ou votre mot de passe ont été modifiés.

1. Sur la page **mes connexions** , sélectionnez le lien **vérifier le mot de passe** pour la connexion que vous souhaitez mettre à jour.
   
    ![Vérifier le mot de passe](./media/add-manage-connections/verify-password.png)
2. Lorsque vous y êtes invité, mettez à jour votre connexion avec les nouvelles informations d’identification.

Lorsque vous mettez à jour une connexion, celle-ci est mise à jour pour PowerApps et Microsoft Flow.

## <a name="troubleshoot-a-connection"></a>Résoudre les problèmes de connexion
Selon les stratégies de votre organisation, vous devrez peut-être utiliser le même compte pour vous connecter à Microsoft Flow et créer une connexion à SharePoint, Office 365 ou OneDrive entreprise.

Par exemple, vous pouvez vous connecter à Microsoft Flow avec *yourname@outlook.com* , mais vous devez être bloqué lorsque vous essayez de vous connecter à SharePoint avec *yourname@contoso.com* . Au lieu de cela, vous pouvez vous connecter à Microsoft Flow avec *yourname@contoso.com* et vous serez en mesure de vous connecter à SharePoint.

<!--Reference links in article-->
[1]: https://flow.microsoft.com
