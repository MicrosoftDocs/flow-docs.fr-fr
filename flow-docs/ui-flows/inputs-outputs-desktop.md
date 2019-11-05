---
title: Utiliser les entrées et les sorties dans les flux d’interface utilisateur du Bureau | Microsoft Docs
description: Utilisez les entrées et les sorties dans les flux d’interface utilisateur de bureau.
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
ms.openlocfilehash: 88bea3b8a038c01360fc5f3e61dbf30599b5deba
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589785"
---
# <a name="use-inputs-and-outputs-in-desktop-ui-flows"></a>Utiliser les entrées et les sorties dans les flux d’interface utilisateur de bureau

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

## <a name="define-inputs"></a>Définir les entrées

Les entrées vous permettent de transmettre des informations à partir d’une source externe, telle qu’une base de données ou tout connecteur pris en charge vers le logiciel hérité que le flux de l’interface utilisateur automatise.

Par exemple, vous pouvez utiliser les informations sur le client à partir d’une liste SharePoint en tant que source d’entrée dans votre logiciel de comptabilité hérité.

### <a name="define-inputs-in-the-ui-flows-wizard"></a>Définir des entrées dans l’Assistant flux d’interface utilisateur

1. Sélectionnez « nouvelle entrée »

   ![](../media/inputs-outputs-desktop/2eb6313a0e966f1fbfc352445b89ee39.png)

1. Ajoutez un nom, un exemple de données et une description à votre entrée.

    - Les exemples de données sont utilisés lors de l’enregistrement ou du test.

    - La description est utile pour différencier les entrées que vous avez créées.

   ![](../media/inputs-outputs-desktop/e33d206bf2158228277a276261c49785.png)

1.  Une fois vos entrées créées, vous pouvez cliquer sur suivant pour les utiliser dans un enregistrement.

### <a name="use-inputs-to-pass-information-to-the-application"></a>Utiliser des entrées pour transmettre des informations à l’application

1. Lors de l’enregistrement, vous pouvez utiliser une entrée dans une application en sélectionnant **utiliser l’entrée**.

1. Dans la liste, vous pouvez choisir entre trois options :

    - Sélectionnez l’une des entrées que vous avez définies dans l’étape **configurer les champs d’entrée** de l’interface utilisateur flux.

    - Utilisez une sortie précédemment définie (consultez la section sorties). Cela est utile pour transmettre des informations entre différentes applications au sein du même Workflow d’interface utilisateur.

    - Créez une entrée lors de l’enregistrement. Vous le retrouverez dans l’étape **configurer les champs d’entrée** de l’interface utilisateur flux.

   ![](../media/inputs-outputs-desktop/de36baa0f85d5a19304e1606de25aa3e.png)

1. Sélectionnez l’emplacement où vous souhaitez utiliser l’entrée. L’exemple de valeur que vous avez défini est utilisé automatiquement. Dans l’exemple ci-dessous, « Hello World » est l’exemple de valeur pour le nom d’entrée « My Input » et est ajouté à la page dans Microsoft Word.  
    
    ![](../media/inputs-outputs-desktop/d6b74dc86f38c51cf1daa0582ff0cc33.png)

1. Dans Power automate **enregistrer et modifier des étapes**, développez actions qui utilisent des entrées pour afficher celle qui est sélectionnée.

   ![](../media/inputs-outputs-desktop/340aa71942b618431b0455b632f76f52.png)

1. Lors du déclenchement de votre workflow d’interface utilisateur, vous pouvez modifier la valeur d’entrée à la place. Pour plus d’informations, consultez utiliser des entrées & des sorties.

## <a name="use-outputs-to-extract-information-from-the-app"></a>Utiliser des sorties pour extraire des informations de l’application

Les sorties vous permettent de transmettre des informations à partir des logiciels hérités que le flux de l’interface utilisateur automatise vers une destination externe, telle qu’une base de données ou tout [connecteur pris en charge](https://flow.microsoft.com/connectors/).

Par exemple, vous pouvez extraire les informations sur le client de votre logiciel de comptabilité hérité et l’ajouter à une liste SharePoint.

Les sorties peuvent être créées uniquement lorsque vous enregistrez votre workflow d’interface utilisateur.

1. Pendant un enregistrement, sélectionnez dans le bouton « obtenir la sortie » de l’enregistreur

   ![](../media/inputs-outputs-desktop/13f8dfca19c0ed04ca2a0f87bf7055ea.png)

1. Sélectionnez le bouton « Sélectionner le texte » (il s’agit du seul type de sortie disponible pour l’instant)

   ![](../media/inputs-outputs-desktop/2845b73ee807a5be747c1dc494570ab7.png)

1. Cliquez sur un élément d’interface utilisateur pour sélectionner son texte pour la sortie. La valeur sera capturée automatiquement.

   ![](../media/inputs-outputs-desktop/7df19b56aadcd0aef207c7372a04b3c6.png)

   ![](../media/inputs-outputs-desktop/af55a0bf39d805b154a783eff3de131b.png)

1. Définissez le nom et la description de la sortie.

   ![](../media/inputs-outputs-desktop/a083579ee011dfb76aa21fac116796a3.png)

1. Sélectionnez **Enregistrer.** 

Votre sortie est désormais disponible dans la zone dédiée de l’Assistant

   ![](../media/inputs-outputs-desktop/b9f396de0b5893c5a3152b592911f67a.png)

Chaque sortie a :

-  Nom de sortie tel que défini lors de l’enregistrement
-  Description : ce champ peut être très utile lorsque vous définissez de nombreuses sorties pendant un enregistrement et que vous souhaitez les identifier facilement.
-  Nom de l’action : action dans laquelle la sortie a été définie dans votre workflow d’interface utilisateur

## <a name="delete-an-output-from-a-ui-flow"></a>Supprimer une sortie d’un workflow d’interface utilisateur

Si vous n’avez plus besoin d’une sortie, vous pouvez la supprimer en revenons à l’action associée et en supprimant le nom de sortie dans la valeur dynamique.

## <a name="test-your-ui-flow"></a>Tester votre workflow d’interface utilisateur

Le test des flux de l’interface utilisateur vous permet de valider vos modifications et le comportement de lecture approprié.

1. Facultatif Entrez une nouvelle valeur dans le champ d’entrée. 
    
    ![](../media/inputs-outputs-desktop/0b4aef639c4ab30b93413e1e7a5e662d.png)

1. Cliquez sur **tester maintenant** pour voir les logiciels hérités automatisés. Vous verrez l’automatisation du déroulement de l’interface utilisateur en lisant les étapes que vous avez enregistrées. **N’interagissez pas avec votre appareil pendant la durée de la lecture.**

1. Une fois la lecture terminée, vous verrez l’état d’exécution de votre workflow d’interface utilisateur :

    - Pour chaque action, état indiquant que le test a fonctionné correctement et les entrées associées.

    - Valeur des sorties obtenues pour ce test.

    - En cas de génération d’une erreur, vous serez en mesure de voir quelle étape était problématique avec une capture d’écran du moment où l’erreur s’est produite.

   ![](../media/inputs-outputs-desktop/85056d7942d12a5408005f5b683d432b.png)

## <a name="learn-more"></a>Pour en savoir plus

- Découvrez comment [déclencher le workflow de l’interface utilisateur](run-ui-flow.md) que vous venez de créer.

- Si vous souhaitez en faire plus avec les flux d’interface utilisateur, vous pouvez également essayer des flux d’interface utilisateur avec des paramètres [d’entrée et de sortie](inputs-outputs-web.md) .


