---
title: Découvrir comment ajouter d’autres propriétaires à un flux et créer des flux d’équipe | Microsoft Docs
description: Microsoft Flow permet d’automatiser facilement les tâches répétitives. Vous pouvez ajouter des utilisateurs ou des groupes en tant que propriétaires et collaborer avec eux pour concevoir et gérer les flux.
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
ms.openlocfilehash: 29d6532593719bef147cdacf1c0e2576ec734837
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64457930"
---
# <a name="create-team-flows"></a>Créer des flux d’équipe
Créez un flux d’équipe en ajoutant d’autres personnes de votre organisation en tant que propriétaires. Tous les propriétaires d’un flux d’équipe peuvent exécuter les actions suivantes :

* Afficher l’historique du flux (autrement dit, chaque exécution).
* Gérez les propriétés du flux : par exemple, démarrez ou arrêtez le flux, ajoutez des propriétaires ou mettez à jour les informations d’identification pour une connexion.
* Modifiez la définition du flux : par exemple, ajoutez ou supprimez une condition ou action.
* Ajoutez et supprimez d’autres propriétaires (mais pas le créateur du flux).
* Supprimer le flux.

Si vous êtes le créateur ou le propriétaire d’un flux d’équipe, ce dernier est répertorié sous l’onglet **Flux d’équipes** de [Microsoft Flow](https://flow.microsoft.com).

![Onglet Flux d’équipes](./media/create-team-flows/addowner5.png)

> [!NOTE]
> Les connexions partagées peuvent être utilisées **uniquement** dans le flux dans lequel elles ont été créées.
> 
> 

Les propriétaires peuvent utiliser les services dans un flux mais ils ne peuvent pas modifier les informations d’identification d’une connexion créée par un autre propriétaire.

## <a name="prerequisites"></a>Prérequis
Vous devez avoir un [abonnement Microsoft Flow payant](https://flow.microsoft.com/pricing/) pour créer un flux d’équipe. En outre, vous devez être le créateur ou le propriétaire pour ajouter/supprimer des propriétaires d’un flux d’équipe.

## <a name="create-a-team-flow"></a>Créer un flux d’équipe
Pour créer un flux d’équipe ou pour ajouter des propriétaires à un flux d’équipe, procédez comme suit.

1. Connectez-vous à [Microsoft Flow](https://flow.microsoft.com), puis sélectionnez **Mes flux**.
2. Sélectionnez l’icône représentant des personnes en regard du flux que vous souhaitez modifier :
   
    ![Icône d’équipe](./media/create-team-flows/addowner1.png)
3. Entrez le nom, l’adresse e-mail ou le nom du groupe ou de la personne que vous souhaitez ajouter en tant que propriétaire :
   
    ![rechercher l’utilisateur](./media/create-team-flows/addowner2.png)
4. Dans la liste qui apparaît, sélectionnez l’utilisateur que vous souhaitez définir comme propriétaire :
   
    ![sélectionner l’utilisateur](./media/create-team-flows/addowner3.png)
   
     L’utilisateur ou le groupe sélectionné devient un des propriétaires du flux :
   
    ![nouveau propriétaire](./media/create-team-flows/addowner4.png)
   
     Félicitations, le flux d’équipe a été créé !

## <a name="add-a-list-as-a-co-owner"></a>Ajouter une liste en tant que copropriétaire

Vous pouvez ajouter des listes SharePoint en tant que copropriétaire dans un flux afin que toutes les personnes disposant d’un accès en modification obtiennent automatiquement un accès en modification sur le flux. Une fois que le flux est partagé, il vous suffit juste de distribuer un lien vers celui-ci.

> [!TIP]
> Utilisez une liste lorsque le flux est connecté à SharePoint et un groupe dans d’autres cas.
>

## <a name="remove-an-owner"></a>Supprimer un propriétaire

> [!IMPORTANT]
> Quand vous supprimez un propriétaire dont les informations d’identification sont utilisées pour accéder aux services Microsoft Flow, vous devez mettre à jour les informations d’identification de ces connexions afin que le flux continue à s’exécuter correctement.
> 
> 

1. Sélectionnez l’icône représentant des personnes en regard du flux que vous souhaitez modifier :
   
    ![icône de sélection de personnes](./media/create-team-flows/removeowner1.png)
2. Sélectionnez l’icône **Supprimer** correspondant au propriétaire que vous souhaitez supprimer :
   
    ![sélectionner l’option Supprimer](./media/create-team-flows/removeowner2.png)
3. Dans la boîte de dialogue de confirmation, sélectionnez **Supprimer ce propriétaire** :
   
    ![confirmer la suppression](./media/create-team-flows/removeowner3.png)
4. Félicitations, l’utilisateur ou le groupe que vous avez supprimé n’est plus répertorié en tant que propriétaire du flux :
   
    ![utilisateur supprimé](./media/create-team-flows/removeowner4.png)


## <a name="update-connection-owner"></a>Mettre à jour le propriétaire de connexion

Vous devrez peut-être changer le propriétaire d’une connexion dans un flux si vous supprimez le propriétaire existant. Suivez ces étapes pour changer le propriétaire d’un flux :

1. Sélectionnez le flux qui contient la connexion que vous souhaitez mettre à jour dans la liste **Flux d’équipes**.
1. Sélectionnez **Tout afficher** dans la liste **PROPRIÉTAIRES**.
1. Sélectionnez **Gérer les connexions** dans la liste **Connexions en cours d’utilisation**.
1. Recherchez la connexion que vous voulez mettre à jour, puis sélectionnez-la.
1. Sélectionnez **...** (plus de commandes), puis **Changer de compte**.
1. Suivez les étapes afin d’utiliser un autre compte pour la connexion.

## <a name="embedded-and-other-connections"></a>Connexions incorporées et autres

Les connexions utilisées dans un flux se répartissent en deux catégories :

* **Incorporées** &mdash; Ces connexions sont utilisées dans le flux.
* **Autres** &mdash; Ces connexions ont été définies pour un flux mais ne sont pas utilisées dans celui-ci.

Si vous arrêtez une connexion dans un flux, celle-ci s’affiche dans la liste de connexions **Autres** et y reste jusqu’à ce qu’un propriétaire l’inclue à nouveau dans le flux.

Suivez les étapes visant à [mettre à jour un propriétaire de connexion](./create-team-flows.md#update-connection-owner) pour apporter des modifications aux connexions incorporées.

La liste des connexions apparaît sous la liste des propriétaires dans les propriétés d’un flux :

![connexions incorporées](./media/create-team-flows/embeddedconnections.png)

