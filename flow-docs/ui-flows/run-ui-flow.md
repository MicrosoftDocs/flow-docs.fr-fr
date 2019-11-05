---
title: Exécuter des flux d’interface utilisateur à partir d’autres flux | Microsoft Docs
description: Exécuter des flux d’interface utilisateur à partir d’autres flux
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 275ef331d37ff83d8890b4b6ddd750dc038dd099
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589748"
---
# <a name="run-ui-flows"></a>Exécuter des flux d’interface utilisateur

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Une fois que vous avez créé et testé un workflow d’interface utilisateur, vous pouvez l’exécuter à partir d’un événement, d’une planification ou d’un bouton. Pour ce faire, ajoutez votre workflow d’interface utilisateur à un [workflow automatisé](../get-started-logic-flow.md), à un workflow de [bouton](../introduction-to-button-flows.md), à un [Workflow planifié](../run-scheduled-tasks.md)ou à un [Workflow de processus d’entreprise](../business-process-flows-overview.md).

## <a name="prerequisites"></a>Conditions préalables

- Vous avez besoin de la [passerelle de données locale](https://go.microsoft.com/fwlink/?LinkID=820580&clcid=0x409) pour votre appareil pour que le workflow de l’interface utilisateur soit déclenché par Power automate.
   
   La passerelle est une connexion sécurisée à l’échelle de l’entreprise entre Power automate et votre appareil (où le workflow de votre interface utilisateur s’exécute). Power automate utilise la passerelle pour accéder à votre appareil local afin qu’il puisse déclencher vos flux d’interface utilisateur à partir d’un événement, d’une planification ou d’un bouton.
- Un compte professionnel ou scolaire. 

   >[!IMPORTANT]
   >Vous devez utiliser le même compte professionnel ou scolaire pour configurer la passerelle, pour vous connecter à Power automate et pour vous connecter à votre appareil Windows.
   

## <a name="run-your-ui-flow-from-an-event-button-schedule-or-business-process-flow"></a>Exécuter le workflow de votre interface utilisateur à partir d’un événement, d’un bouton, d’une planification ou d’un workflow de processus d’entreprise

Dans cet exemple, nous allons utiliser un Flow automatique pour déclencher un workflow d’interface utilisateur lors de l’arrivée d’un nouvel e-mail.

1. Accédez à [Power automate](https://flow.microsoft.com/).
1. Sélectionnez **mes flux** dans la barre de navigation de gauche.
1. Sélectionnez **nouveau**, puis sélectionnez **automatisé-à partir d’un espace vide**.

   >[!TIP]
   >Vous pouvez choisir n’importe quel autre type de Flow pour répondre à vos besoins.

1. Donnez un nom à votre Flow dans la zone **nom du flot** .
1. Recherchez « nouveau courrier », puis sélectionnez le **moment où un nouvel e-mail arrive (v3)** à partir de la liste des déclencheurs. 
    
   ![Sélectionner un déclencheur](../media/run-ui-flow/2d4ec17d239169a46905cef1829fa3a1.png "Sélectionner un déclencheur")

1. Sélectionnez **créer**, puis sélectionnez **nouvelle étape**.

1. Recherchez **flux d’interface utilisateur**, puis sélectionnez **exécuter un flux d’interface utilisateur pour le bureau** dans la liste des **actions**. 

   ![Action de recherche](../media/run-ui-flow/search-action.png "Action de recherche")

1. Fournissez les informations de passerelle et les informations d’identification de l’appareil. 

   Vous devrez effectuer cette opération une fois par appareil :

    - **Nom**de la connexion : choisissez un nom pour l’appareil pour le passage de la connexion. Il peut être différent du nom de la passerelle.
    - **Nom d’utilisateur**: indiquez le compte professionnel ou scolaire de votre appareil.
    - **Type d’authentification**: sélectionnez Windows.
    - **Mot**de passe : mot de passe de votre compte professionnel ou scolaire.
    - **Passerelle**: sélectionnez la passerelle que vous avez créée pendant l’installation.

      ![Paramètres de connexion](../media/run-ui-flow/connection-settings.png "Paramètres de connexion")

      >[!TIP]
      >Si vous ne voyez pas votre passerelle, vous devrez peut-être sélectionner une autre connexion. Pour ce faire, sélectionnez **...** dans le coin supérieur droit de la carte **exécuter un workflow d’interface utilisateur pour ordinateur de bureau (version préliminaire)** , puis sélectionnez la connexion que vous souhaitez utiliser à partir de **mes connexions**.

      ![Sélectionner une nouvelle connexion](../media/run-ui-flow/select-new-connection.png "Sélectionner une nouvelle connexion")

1. Sélectionnez le workflow de l’interface utilisateur que vous avez créé précédemment.

   ![Sélectionner le workflow de l’interface utilisateur](../media/run-ui-flow/select-ui-flow.png "Sélectionner le workflow de l’interface utilisateur")

1. Sélectionnez **Enregistrer** pour enregistrer votre workflow automatisé.

1. Testez votre Flow en envoyant un courrier électronique pour le déclencher. Vous verrez que le workflow de votre interface utilisateur lit les étapes que vous avez enregistrées. 

![Exécution réussie qui appelle un workflow d’interface utilisateur](../media/run-ui-flow/successful-run.png "Exécution réussie qui appelle un workflow d’interface utilisateur")

>[!TIP]
>N’interagissez pas avec votre appareil pendant l’exécution du Workflow.

## <a name="use-inputs-and-outputs"></a>Utiliser les entrées et les sorties

Quand vous définissez des entrées et des sorties dans un workflow d’interface utilisateur, vous pouvez passer des informations à partir de et à ces entrées.

1. Lorsque vous ajoutez un workflow d’interface utilisateur à un Flow, vous pouvez voir la liste des entrées qui ont été définies dans le workflow de l’interface utilisateur.

   ![Entrées du Flow de l’interface utilisateur](../media/run-ui-flow/inputs.png "Entrées du Flow de l’interface utilisateur")

1. Vous pouvez renseigner chaque champ d’entrée dans le workflow de l’interface utilisateur avec les valeurs des étapes précédentes du Workflow. Pour ce faire, sélectionnez le champ d’entrée, puis sélectionnez une entrée dans le sélecteur de jetons.


1. Vous pouvez également utiliser des sorties de votre workflow d’interface utilisateur en tant qu’entrées pour les actions qui apparaissent plus tard dans le Workflow. Pour ce faire, sélectionnez le champ d’entrée, puis sélectionnez une entrée dans le sélecteur de jetons.

## <a name="limitations-and-known-issues"></a>Limitations et problèmes connus

- Les clusters de passerelle ne sont pas pris en charge.
- Étant donné que les claviers non US (QWERTY) ne sont pas pris en charge dans ce realease, la lecture d’une étape d’entrée où la séquence de touches a été enregistrée à partir d’un clavier non US (QWERTY) entraînera des frappes de touche en US (QWERTY).

## <a name="learn-more"></a>Pour en savoir plus

 - Installez la [passerelle de données locale](https://docs.microsoft.com/data-integration/gateway/service-gateway-app).
 - [Utilisez la documentation de l’application de passerelle de données locale](https://docs.microsoft.com/flow/gateway-manage) .
 - [Résolvez les problèmes](https://docs.microsoft.com/data-integration/gateway/service-gateway-tshoot) de la passerelle de données locale.
