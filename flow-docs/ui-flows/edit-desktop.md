---
title: Apprendre à modifier les flux d’interface utilisateur du Bureau | Microsoft Docs
description: Apprenez à modifier les flux d’interface utilisateur de bureau.
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
ms.openlocfilehash: d5b7e186ae5c644f00f57946fff5ef3e946ba2ba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589813"
---
# <a name="edit-desktop-ui-flows"></a>Modifier les flux de l’interface utilisateur du Bureau

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Les flux d’interface utilisateur de bureau automatisent les applications de bureau Windows. Reportez-vous aux [problèmes connus](create-desktop.md#known-issues-and-solutions) pour en savoir plus sur les problèmes que vous pouvez rencontrer, les solutions de contournement pour ces problèmes et les scénarios qui ne sont pas pris en charge dans cette version préliminaire.

## <a name="prerequisites"></a>Conditions préalables
Un workflow de l’interface utilisateur du bureau. [Créez un workflow d’interface utilisateur de bureau maintenant](create-desktop.md#create-and-test-desktop-ui-flows) si vous n’en avez pas à modifier.

## <a name="edit-actions"></a>Modifier les actions

![Modifier les actions](../media/edit-desktop/edit-actions.png "Modifier les actions")

Vous pouvez modifier votre enregistrement pour :

-   Modifiez la valeur des actions qui la prennent en charge.
-   Supprimer une étape.
-   Supprimer la totalité de l’enregistrement.
-   Modifiez l’ordre des actions par glisser-déplacer. Agissez avec prudence, car cela risque de perturber la cohérence de votre enregistrement.

Les paramètres avancés vous permettent de modifier :

-  Délai après l’exécution de l’action. Par exemple, vous pouvez ajouter un délai d’un seconde en remplaçant PT0S par PT1S. Cela peut être utile lorsque l’application cible a un temps de réponse lent qui ne se termine pas avant l’étape suivante du workflow de votre interface utilisateur.
-   [Sélecteur](edit-desktop.md#set-the-selector) de l’élément d’interface utilisateur cible.

## <a name="add-a-recording"></a>Ajouter un enregistrement

Vous souhaiterez peut-être enregistrer votre workflow d’interface utilisateur dans plusieurs sessions. Une fois que vous avez terminé votre premier enregistrement, vous pouvez procéder comme suit :

1. Connectez-vous à [Power automate](https://flow.microsoft.com).
1. Sélectionnez **mes flux** > **flux de l’interface utilisateur (version préliminaire)** .
1. Sélectionnez le Flow de l’interface utilisateur que vous souhaitez modifier.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Sélectionnez **modifier**. 
1. Sélectionnez **nouvelle étape**.

   ![Nouvelle étape](../media/edit-desktop/new-step.png "Nouvelle étape")

1. Sélectionnez **enregistrer l’application** dans la liste des actions.

   ![Enregistrer l’application](../media/edit-desktop/select-record-ui-actions.png "Enregistrer l’application")

1. Sélectionnez **lancer l’enregistreur**.

   ![Sélectionnez lancer l’enregistreur](../media/create-windows-ui-flow/select-launch-recorder.png "Sélectionnez lancer l’enregistreur")

   Le contrôle d’enregistreur s’affiche en haut de l’écran.

   ![Enregistreur-contrôle](../media/create-windows-ui-flow/recorder-control.png "Enregistreur-contrôle")

1. Démarrez l’application que vous souhaitez enregistrer.

     >[!TIP]
     >Lorsque la souris pointe sur les contrôles de l’application, vous remarquerez qu’un contour bleu met en évidence chaque contrôle. Attendez toujours la mise en surbrillance bleue avant de sélectionner un contrôle.
     >
     >Si la mise en surbrillance bleue ne s’affiche pas autour de l’élément, il est possible qu’il ne soit pas correctement enregistré.

1. Sélectionnez **enregistrement** dans le contrôle d’enregistreur.

1. Effectuez les étapes dans l’interface utilisateur de l’application que vous enregistrez, puis sélectionnez **terminé** sur le contrôle de l’enregistreur.
1. Sélectionnez **Enregistrer**, puis testez votre workflow d’interface utilisateur.

## <a name="add-a-manual-action"></a>Ajouter une action manuelle

Une fois que vous avez enregistré une application avec au moins une action, vous pouvez ajouter manuellement l’une des actions suivantes pour cette application.

| **Transactionnel**          | **Commentaire**                                                       |
|---------------------|-------------------------------------------------------------------|
| Fermer l’application   |                                                                   |
| Clic droit         |                                                                   |
| Envoyer les clés           | Envoyez des clés et des combinaisons de touches, telles que CTRL + C.                             |
| Clic gauche          |                                                                   |
| Récupérer du texte            | Lire le texte d’un élément d’interface utilisateur, puis l’utiliser comme sortie. |
| Entrer du texte          |                                                                   |
| Élément d’extraction activé | Vérifiez si un élément d’interface utilisateur est activé ou désactivé.         |
| Clear, élément       | Efface la valeur dans un élément d’interface utilisateur modifiable.             |
| Attendre quelques secondes    | Attendez avant de passer à l’étape suivante.                           |

Pour ajouter une action manuelle, procédez comme suit :

1. Connectez-vous à [Power automate](https://flow.microsoft.com).
1. Sélectionnez **mes flux** > **flux de l’interface utilisateur (version préliminaire)** .
1. Sélectionnez le Flow de l’interface utilisateur que vous souhaitez modifier.
   ![](../media/edit-desktop/select-ui-flow.png)
1. Sélectionnez **modifier**. 
1. Sélectionnez la carte d’enregistrement qui contient les étapes auxquelles vous souhaitez ajouter une nouvelle étape.
   La carte se développe et affiche les étapes enregistrées.

   ![Sélectionner la carte d’enregistrement](../media/edit-desktop/manual-select-recording-card.png)

1. Sélectionnez **Ajouter une action** sur la carte d’enregistrement, juste en dessous de la dernière étape enregistrée.
   Vous verrez la liste des actions manuelles répertoriées plus haut dans la procédure pas à pas. 

1. Sélectionnez l’action que vous souhaitez ajouter. Ici, j’ai sélectionné **obtenir l’élément activé**, mais vous pouvez sélectionner n’importe quelle action appropriée pour votre scénario.

   ![Sélectionnez l’action à ajouter. png](../media/edit-desktop/select-action-to-add.png)

Une fois l’action ajoutée, vous devez définir le **Sélecteur** dans les options avancées de l’action.

![Options avancées des actions](../media/edit-desktop/action-advanced-options.png "Options avancées des actions")

### <a name="set-the-selector"></a>Définir le sélecteur

Le sélecteur identifie l’élément d’interface utilisateur sur lequel l’action est effectuée lors de la lecture. Nous vous recommandons de copier/coller ces informations à partir d’une étape distincte ciblant le même élément d’interface utilisateur, si possible.

Le format du sélecteur est le suivant :

```json
{  
   "type":"WinUIA",
   "parameters":{  
      "elementStack":[  

      ],
      "elementXPath":""
   }
}
```

Vous devez fournir les données pour les champs **elemementStack** et **elementXPath** de l’élément Selector.

Voici un exemple de ce à quoi peut ressembler le **elemementStack** .

![Pile d’éléments](../media/edit-desktop/elementstack.png "Pile d’éléments")

Vous pouvez capturer le **elementXPath** à l’aide de l' [enregistreur d’interface utilisateur WinAppDriver](https://blogs.windows.com/windowsdeveloper/2018/06/20/introducing-winappdriver-ui-recorder/).

![Outil WAD](../media/edit-desktop/wad-tool.png "Outil WAD")

Supprimez le premier élément (tout ce qui précède/Window) avant d’utiliser le résultat dans **elementXPath** du sélecteur.

Testez votre workflow d’interface utilisateur pour vérifier que le sélecteur fonctionne correctement.

## <a name="next-steps"></a>Étapes suivantes

- Découvrez comment [exécuter le workflow de l’interface utilisateur](run-ui-flow.md) que vous venez de modifier.

- Si vous souhaitez en faire plus avec les flux d’interface utilisateur, vous pouvez également essayer des flux d’interface utilisateur avec des paramètres [d’entrée et de sortie](inputs-outputs-web.md) .

