---
title: Découvrez comment ajouter d’autres propriétaires à un flux et créer des flux d’équipe | Microsoft Docs
description: Microsoft Flow permet d’automatiser facilement les tâches répétitives. Vous pouvez ajouter des utilisateurs ou des groupes en tant que propriétaires et collaborer avec eux pour concevoir et gérer des flux.
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
ms.date: 04/21/2017
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f2a986568a44f8329e55fc62aef4705207cdfc49
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547621"
---
# <a name="create-team-flows"></a>Créer des flux d’équipe
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]
Créez un workflow d’équipe en ajoutant d’autres membres de votre organisation en tant que propriétaires. Tous les propriétaires d’un Flow Team peuvent effectuer les actions suivantes :

* Affichez l’historique du Flow (c’est-à-dire, chaque exécution).
* Gérer les propriétés du Flow (par exemple, démarrer ou arrêter le Flow, ajouter des propriétaires ou mettre à jour les informations d’identification pour une connexion).
* Modifier la définition du Flow (par exemple, ajouter ou supprimer une action ou une condition).
* Ajoutez et supprimez d’autres propriétaires (mais pas le créateur du Flow).
* Supprimer le Flow.

Si vous êtes le créateur ou le propriétaire d’un flux d’équipe, vous le trouverez dans l’onglet **flux d’équipe** de [Microsoft Flow](https://flow.microsoft.com).

![onglet flux d’équipe](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Les connexions partagées ne peuvent être utilisées **que** dans le Flow dans lequel elles ont été créées.
> 
> 

Les propriétaires peuvent utiliser des services dans un Flow, mais ils ne peuvent pas modifier les informations d’identification d’une connexion créée par un autre propriétaire.

## <a name="prerequisites"></a>Conditions préalables
Vous devez disposer d’un [plan de Microsoft Flow payant](https://flow.microsoft.com/pricing/) pour créer un workflow d’équipe. En outre, vous devez être le créateur ou le propriétaire pour ajouter/supprimer des propriétaires d’un workflow d’équipe.

## <a name="create-a-team-flow"></a>Créer un workflow d’équipe
Procédez comme suit pour créer un workflow d’équipe ou pour ajouter d’autres propriétaires à un workflow d’équipe.

1. Connectez-vous au [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **mes flux**.
2. Sélectionnez l’icône personnes pour le Flow que vous souhaitez modifier :
   
    ![icône d’équipe](./media/create-team-flows/addowner1.png)
3. Entrez le nom, l’adresse de messagerie ou le nom de groupe de la personne ou du groupe que vous souhaitez ajouter en tant que propriétaire :
   
    ![Rechercher l’utilisateur](./media/create-team-flows/addowner2.png)
4. Dans la liste qui s’affiche, sélectionnez l’utilisateur que vous souhaitez définir comme propriétaire :
   
    ![sélectionner l’utilisateur](./media/create-team-flows/addowner3.png)
   
     L’utilisateur ou le groupe que vous avez sélectionné devient le propriétaire du Flow :
   
    ![nouveau propriétaire](./media/create-team-flows/addowner4.png)
   
     Félicitations &mdash; votre flow d’équipe a été créé !

## <a name="add-a-list-as-a-co-owner"></a>Ajouter une liste en tant que copropriétaire

Vous pouvez ajouter des listes SharePoint en tant que copropriétaires à un Flow afin que toutes les personnes qui ont un accès en modification à la liste récupèrent automatiquement l’accès au workflow. Une fois le Flow partagé, vous pouvez simplement distribuer un lien vers celui-ci.

> [!TIP]
> Utilisez une liste lorsque le Flow est connecté à SharePoint et utilisez un groupe dans d’autres cas.
>

## <a name="remove-an-owner"></a>Supprimer un propriétaire

> [!IMPORTANT]
> Lorsque vous supprimez un propriétaire dont les informations d’identification sont utilisées pour accéder à Microsoft Flow services, vous devez mettre à jour les informations d’identification pour ces connexions afin que le workflow continue à s’exécuter correctement.
> 
> 

1. Sélectionnez l’icône personnes pour le Flow que vous souhaitez modifier :
   
    ![icône sélectionner des personnes](./media/create-team-flows/removeowner1.png)
2. Sélectionnez l’icône de **suppression** pour le propriétaire que vous souhaitez supprimer :
   
    ![sélectionner supprimer](./media/create-team-flows/removeowner2.png)
3. Dans la boîte de dialogue de confirmation, sélectionnez **supprimer ce propriétaire**:
   
    ![confirmer la suppression](./media/create-team-flows/removeowner3.png)
4. Félicitations &mdash; l’utilisateur ou le groupe que vous avez supprimé n’est plus listé comme propriétaire du Flow :
   
    ![utilisateur supprimé](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Mettre à jour le propriétaire de la connexion

Vous devrez peut-être modifier le propriétaire d’une connexion dans un Flow si vous supprimez le propriétaire existant. Pour changer le propriétaire d’un Flow, procédez comme suit :

1. Dans le volet gauche, sélectionnez **données** .
1. Sélectionnez **connexions**.
1. Recherchez la connexion que vous souhaitez mettre à jour, puis sélectionnez-la.
1. Sélectionnez **...** (plus de commandes) sur la connexion que vous avez sélectionnée, puis sélectionnez **basculer le compte**.
1. Suivez les étapes pour utiliser un autre compte pour la connexion.

## <a name="embedded-and-other-connections"></a>Connexions incorporées et autres

Les connexions utilisées dans un workflow se répartissent en deux catégories :

* **Incorporé** &mdash; ces connexions sont utilisées dans le Flow.
* D' **autres** &mdash; ces connexions ont été définies pour un Flow, mais ne sont pas utilisées dans celui-ci.

Si vous arrêtez d’utiliser une connexion dans un Flow, cette connexion apparaît dans la liste **autres** connexions, où elle reste jusqu’à ce qu’un propriétaire l’inclue à nouveau dans le Workflow.

Suivez les étapes pour [mettre à jour un propriétaire de connexion](./create-team-flows.md#update-connection-owner) afin d’apporter des modifications aux connexions incorporées.

La liste des connexions apparaît sous la liste des propriétaires dans les propriétés d’un flow :

![connexions incorporées](./media/create-team-flows/embeddedconnections.png)

