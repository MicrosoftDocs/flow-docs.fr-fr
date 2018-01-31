---
title: "Utiliser Azure Active Directory avec un connecteur personnalisé | Microsoft Docs"
description: "Découvrez comment créer un connecteur personnalisé pour Azure Resource Manager, avec l’authentification Azure Active Directory."
services: 
suite: flow
documentationcenter: 
author: msftman
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/03/2016
ms.author: deonhe
ms.openlocfilehash: 791a44a681ef70ead495bf46623657b2b75cfb65
ms.sourcegitcommit: f3236f9f1ec050cda0d9c3e2b9c356132b2a2594
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2018
---
# <a name="use-azure-active-directory-with-a-custom-connector-in-microsoft-flow"></a>Utiliser Azure Active Directory avec un connecteur personnalisé dans Microsoft Flow
Azure Resource Manager (ARM) vous permet de gérer les composants d’une solution sur Azure : bases de données, machines virtuelles et applications web. Ce tutoriel montre comment activer l’authentification dans Azure Active Directory, inscrire une des API ARM en tant que connecteur personnalisé, puis s’y connecter dans Microsoft Flow. Cela peut s’avérer utile si vous souhaitez gérer des ressources Azure dans le cadre d’un flux. Pour plus d’informations sur ARM, consultez [Présentation d’Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview).

## <a name="prerequisites"></a>Prérequis
* Un [abonnement Azure](https://azure.microsoft.com/free/).
* Un [compte Microsoft Flow](https://flow.microsoft.com).
* L’[exemple de fichier OpenAPI](https://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json) utilisé dans ce didacticiel.

## <a name="enable-authentication-in-azure-active-directory"></a>Activer l’authentification dans Azure Active Directory
Tout d’abord, nous devons créer une application Azure Active Directory (AAD) qui effectue l’authentification lors de l’appel du point de terminaison d’API ARM.

1. Connectez-vous au [portail Azure](https://portal.azure.com).  Si vous avez plusieurs locataires Azure Active Directory, vérifiez que vous êtes connecté au répertoire approprié en examinant votre nom d’utilisateur dans le coin supérieur droit.
   
    ![Nom d’utilisateur](./media/customapi-azure-resource-manager-tutorial/current-user.png)
2. Dans le menu de gauche, cliquez sur **Autres services**.  Dans la zone de texte **Filtre**, tapez **Azure Active Directory**, puis cliquez sur **Azure Active Directory**.
   
    ![Azure Active Directory](./media/customapi-azure-resource-manager-tutorial/azureaad.png)
   
    Le panneau Azure Active Directory s’ouvre.   
3. Dans le menu du panneau Azure Active Directory, cliquez sur **Inscriptions des applications**.
   
    ![Inscriptions des applications](./media/customapi-azure-resource-manager-tutorial/azureapplication.png)
4. Dans la liste des applications inscrites, cliquez sur **Ajouter**.
   
    ![Bouton Ajouter](./media/customapi-azure-resource-manager-tutorial/add-app-btn.png)   
5. Tapez le nom de votre application, laissez le champ **Application/API web** sélectionné, puis pour **URL de connexion**, tapez `https://login.windows.net`.  Cliquez sur **Créer**.  
   
    ![Formulaire Nouvelle application](./media/customapi-azure-resource-manager-tutorial/newapplication.png)
6. Cliquez sur la nouvelle application dans la liste.
   
    ![Nouvelle application dans la liste](./media/customapi-azure-resource-manager-tutorial/newapplication2.png)
   
    Le panneau Application inscrite s’ouvre.  Notez l’**ID de l’application**.  Vous en aurez besoin ultérieurement.
7. Le panneau Paramètres doit également être ouvert.  Dans le cas contraire, cliquez sur le bouton **Paramètres**.
   
    ![Bouton Paramètres](./media/customapi-azure-resource-manager-tutorial/settings-btn.png)
8. Dans le panneau Paramètres, cliquez sur **URL de réponse**. Dans la liste des URL, ajoutez `https://msmanaged-na.consent.azure-apim.net/redirect` et cliquez sur **Enregistrer**.
   
    ![URL de réponse](./media/customapi-azure-resource-manager-tutorial/reply-urls.png)
9. Dans le panneau Paramètres, cliquez sur **Autorisations requises**.  Dans le panneau Autorisations requises, cliquez sur **Ajouter**.
   
    ![Autorisations requises](./media/customapi-azure-resource-manager-tutorial/permissions.png)
   
    Le panneau Ajouter un accès d’API s’ouvre.
10. Cliquez sur **Sélectionner une API**. Dans le panneau qui s’ouvre, cliquez sur l’option pour l’API de gestion des services Azure, puis cliquez sur **Sélectionner**.
    
    ![Sélectionner une API](./media/customapi-azure-resource-manager-tutorial/permissions2.png)
11. Sélectionnez **Sélectionner des autorisations**.  Sous *Autorisations déléguées*, cliquez sur **Accès à la gestion des services Azure en tant qu’utilisateurs d’organisation**, puis cliquez sur **Sélectionner**.
    
    ![Autorisations déléguées](./media/customapi-azure-resource-manager-tutorial/permissions3.png)
12. Dans le panneau Ajouter un accès d’API, cliquez sur **Terminé**.
13. Dans le panneau Paramètres, cliquez sur **Clés**.  Dans le panneau Clés, tapez une description pour votre clé, sélectionnez une période d’expiration, puis cliquez sur **Enregistrer**.  Votre nouvelle clé s’affiche.  Prenez note de la valeur de clé dont vous aurez besoin plus tard.  Vous pouvez maintenant fermer le portail Azure.
    
    ![Créer une clé](./media/customapi-azure-resource-manager-tutorial/configurekeys.png)

## <a name="add-the-connection-in-microsoft-flow"></a>Ajouter la connexion dans Microsoft Flow
Maintenant que l’application AAD est configurée, ajoutez le connecteur personnalisé.

1. Dans l’[application web Microsoft Flow](https://flow.microsoft.com/), cliquez sur le bouton **Paramètres** dans l’angle supérieur droit de la page (il ressemble à un engrenage).  Cliquez ensuite sur **Connecteurs personnalisés**.
   
    ![Rechercher des connecteurs personnalisés](./media/customapi-azure-resource-manager-tutorial/finding-custom-apis.png)  
2. Cliquez sur **Créer un connecteur personnalisé**.  
   
    Vous êtes invité à indiquer les propriétés de votre API.  
   
   | Propriété | Description |
   | --- | --- |
   | Nom |En haut de la page, cliquez sur **Sans titre** et donnez un nom à votre flux. |
   | Fichier OpenAPI |Accédez à l’[exemple de fichier OpenAPI ARM](https://pwrappssamples.blob.core.windows.net/samples/AzureResourceManager.json). |
   | Charger l’icône de l’API |Cliquez sur **Charger l’icône** afin de sélectionner un fichier image pour l’icône. Toutes les images PNG ou JPG d’une taille inférieure à 1 Mo sont prises en charge. |
   | Description |Saisissez une description de votre connecteur personnalisé (facultatif). |
   
    ![Créer un connecteur personnalisé](./media/customapi-azure-resource-manager-tutorial/create-custom-api.png)  
   
    Sélectionnez **Continuer**.
3. Sur l’écran suivant, étant donné que le fichier OpenAPI utilise votre application AAD pour l’authentification, vous devez donner à Flow des informations sur l’application.  Sous **ID client**, tapez l’**ID de l’application AAD** que vous avez noté précédemment.  Pour la clé secrète client, utilisez la **clé**.  Enfin, pour **URL de la ressource**, tapez `https://management.core.windows.net/`.
   
   > [!IMPORTANT]
   > Veillez à inclure l’URL de ressource exactement comme ci-dessus, y compris la barre oblique de fin.
   > 
   > 
   
    ![Paramètres OAuth](./media/customapi-azure-resource-manager-tutorial/oauth-settings.png)
   
    Une fois que vous avez entré les informations de sécurité, cliquez sur la coche (**&#x2713;**) en regard du nom du flux, en haut de la page, pour créer le connecteur personnalisé.
4. Votre connecteur personnalisé est à présent affiché sous **Connecteurs personnalisés**.
   
    ![API disponibles](./media/customapi-azure-resource-manager-tutorial/list-custom-apis.png)  
5. Maintenant que le connecteur personnalisé est inscrit, vous devez créer une connexion vers celui-ci afin qu’elle puisse être utilisée dans vos applications et vos flux.  Cliquez sur **+** à droite du nom du connecteur personnalisé, puis suivez les étapes de l’écran de connexion.

> [!NOTE]
> L’exemple OpenAPI ne définit pas l’ensemble complet d’opérations ARM et contient actuellement uniquement l’opération [List all subscriptions (Répertorier tous les abonnements)](https://msdn.microsoft.com/library/azure/dn790531.aspx).  Vous pouvez modifier ce fichier OpenAPI ou en créer un à l’aide de l’[éditeur OpenAPI en ligne](http://editor.swagger.io/).
> 
> Ce processus peut être utilisé pour accéder à des API RESTful authentifiées à l’aide d’AAD.
> 
> 

## <a name="next-steps"></a>Étapes suivantes
Pour plus d’informations sur la création d’un flux, consultez [Commencer à développer avec Microsoft Flow](get-started-logic-flow.md).

Pour poser des questions ou ajouter des commentaires sur les connecteurs personnalisés, [rejoignez notre communauté](https://aka.ms/flow-community).

