---
title: Améliorer les flux de processus métier avec le branchement avec PowerApps | Microsoft Docs
description: Découvrez comment utiliser le branchement dans un flux de processus métier
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: f8911c828b216d8f65210b4c54603fd8838e848b
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "65054113"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Tutoriel : Améliorer les flux de processus métier avec le branchement

Les flux de processus métier vous guident tout au long des différentes phases des processus de ventes, de marketing ou de service. Dans les cas simples, un flux de processus métier linéaire est une bonne option. Toutefois, dans les scénarios plus complexes, vous pouvez améliorer un flux de processus métier avec le branchement. Si vous disposez des autorisations de création sur les flux de processus métier, vous pouvez créer des flux de processus métier avec plusieurs branches à l’aide de la logique `If-Else`. La condition de branchement peut être formée de plusieurs expressions logiques qui utilisent une combinaison d’opérateurs `AND` ou `OR`. La sélection de branche s’effectue automatiquement, en temps réel, selon les règles définies pendant la définition de processus. Par exemple, dans la vente de voitures, vous pouvez configurer un flux de processus métier unique qui, après une phase de qualification commune, se fractionne en deux branches distinctes sur la base d’une règle (le client préfère-t-il une nouvelle voiture ou une voiture d’occasion, son budget est-il supérieur ou inférieur à 20 000 €, etc. ) : une branche pour la vente de nouvelles voitures et une autre pour la vente de voitures d’occasion. Pour plus d’informations sur les flux de processus métier, consultez [Vue d’ensemble des flux de processus métier](business-process-flows-overview.md).  
  
 Le diagramme suivant montre un flux de processus métier avec des branches.  
  
 ![Organigramme illustrant les étapes du processus de vente de voitures](media/example-car-sales-flow-chart.png "Organigramme illustrant les étapes du processus de vente de voitures")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Ce que vous devez savoir quand vous concevez des flux de processus métier avec des branches  
 Prenez en compte les informations suivantes quand vous concevez les flux de processus métier avec des branches :  
  
-   Un processus peut englober un maximum de 5 entités uniques.  
  
-   Vous pouvez utiliser un maximum de 30 phases par processus et un maximum de 30 étapes par phase.  
  
-   La profondeur de chaque branche est limitée à 5 niveaux.  
  
-   La règle de branchement doit être basée sur les étapes de la phase qui la précède immédiatement.  
  
-   Vous pouvez combiner plusieurs conditions dans une règle à l’aide de l’opérateur `AND` ou de l’opérateur `OR`, mais pas avec les deux opérateurs.  
  
-   Quand vous définissez un flux de processus, vous pouvez sélectionner une relation d’entité. Cette relation doit être une relation d’entité 1 à N (un-à-plusieurs).  
  
-   Plusieurs processus actifs peuvent s’exécuter simultanément sur le même enregistrement de données.  
  
-   Vous pouvez réorganiser les vignettes (Phases, Étapes, Conditions, etc.) sur le flux de processus à l’aide d’opérations glisser-déplacer.  
  
-   Quand vous fusionnez des branches, toutes les branches paires doivent être fusionnées en une phase unique. Soit toutes les branches paires sont fusionnées en une phase unique, soit chaque branche paire doit terminer le processus. Une branche paire ne peut pas simultanément être fusionnée avec d’autres branches et terminer le processus.  
  
> [!NOTE]
> - Une entité utilisée dans le processus peut être revisitée à plusieurs reprises (plusieurs boucles d’entité fermées).  
> - Un processus peut revenir à la phase précédente, quel que soit le type d’entité. Par exemple, si la phase active est **Fournir un devis** sur un enregistrement de devis, les utilisateurs du processus peuvent déplacer la phase active vers la phase **Proposer** sur un enregistrement d’opportunité.  
>   
>   Ou bien, supposons qu’un processus se trouve dans la phase **Présenter la proposition** dans votre flux de processus : **Inclure le prospect** > **Identifier les besoins** > **Créer une proposition** > **Présenter la proposition** > **Fermer**. Si la proposition présentée au client nécessite que des recherches supplémentaires soient effectuées pour identifier ses besoins, les utilisateurs peuvent simplement sélectionner la phase **Identifier les besoins** de votre processus et choisir **Définir comme actif**.  
  
<a name="CarSelling365"></a>   
## <a name="dynamics-365-customer-engagement-example-car-selling-process-flow-with-two-branches"></a>Exemple Dynamics 365 Customer Engagement : Flux de processus Vente de voiture avec deux branches
 
Examinons l’exemple du flux de processus métier avec deux branches pour la vente de voitures nouvelles et d’occasion.  
  
 Tout d’abord, nous allons créer un processus nommé **Processus de vente de voiture**.  
  
1.  [Ouvrez l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) puis, dans le volet de navigation gauche, sélectionnez **Processus**.  
  
2.  Sélectionnez **Nouveau** pour créer un processus.  
  
3.  Spécifiez **Catégorie** comme **Flux de processus métier** et choisissez **Prospect** comme **Entité** principale.  
  
4.  Ajoutez au processus la première phase appelée **Inclure** et ajoutez les étapes **Délai d’exécution de l’achat** et **Préférence de voiture**.  
  
5.  Après la phase **Inclure** commune, nous fractionnons le processus en deux branches séparées, à l’aide de la vignette **Condition**.  
  
    1.  Configurer la vignette de condition avec des règles qui répondent aux besoins de votre entreprise  
  
    2.  Pour ajouter la première branche pour une phase, ajoutez une vignette Phase sur le chemin « Oui » de la vignette de condition.  
  
    3.  Pour ajouter la deuxième branche qui est exécutée quand la condition n’est pas satisfaite, ajoutez une autre vignette Phase sur le chemin « Non » de la vignette de condition.  
  
> [!TIP]
>  Vous pouvez ajouter une autre condition sur le chemin « Non » d’une vignette de condition existante pour créer un branchement plus complexe.  
  
 ![Image montrant la phase Inclure créée](media/example-car-sales-qualify-stage.JPG "Image montrant la phase Inclure créée")  
  
 Si **Préférence de voiture** = **Nouveau**, le processus bifurque vers la phase **Ventes de nouvelles voitures**, sinon, il accède à la phase **Ventes de voitures d’occasion**, dans la deuxième branche, comme illustré ci-dessous.  
  
 ![Image montrant la phase de vente de nouvelles voitures](media/example-car-sales-new-stage-1.JPG "Image montrant la phase de vente de nouvelles voitures")  
  
 ![Phase de vente de voitures d’occasion](media/example-car-sales-pre-owned-stage.JPG "Phase de vente de voitures d’occasion")  
  
 Après avoir effectué toutes les étapes de la phase **Ventes de nouvelles voitures** ou **Ventes de voitures d’occasion**, le processus rejoint le flux principal, au niveau de la phase **Fournir un devis**.  
  
 ![Phase Fournir un devis](media/example-car-sales-deliver-quote-stage.JPG "Phase Fournir un devis")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Empêcher la divulgation d’informations  
 Envisagez un flux de processus métier avec des branches pour le traitement d’une demande de prêt à une banque, comme illustré ci-dessous. Les entités personnalisées utilisées dans les phases sont affichées entre parenthèses.  
  
 ![Organigramme montrant les étapes d’un exemple de processus pour empêcher la divulgation d’informations](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Organigramme montrant les étapes d’un exemple de processus pour empêcher la divulgation d’informations")  
  
 Dans ce scénario, la responsable des prêts bancaires a besoin d’accéder à l’enregistrement Demande, mais elle ne doit avoir aucune visibilité sur l’examen de la demande. À première vue, il semble que nous pouvons facilement mettre en œuvre cette configuration en affectant à la responsable des prêts un rôle de sécurité qui spécifie l’absence d’accès à l’entité Investigation. Mais, examinons l’exemple plus en détail pour voir si cela est effectivement vrai.  
  
 Supposons qu’un client dépose une demande de prêt pour plus de 60 000 € auprès de la banque. La responsable des prêts examine la demande dans la première phase. Si la règle de branchement qui vérifie si le montant dû à la banque ne dépasse pas 50 000 € est satisfaite, la phase suivante du processus consiste à examiner si la demande est frauduleuse. S’il est établi qu’il s’agit d’un cas de fraude, le processus passe à la phase consistant à intenter une action en justice à l’encontre du demandeur. La responsable des prêts ne doit pas avoir de visibilité sur les deux phases d’investigation, car elle n’a pas accès à l’entité Investigation.  
  
 Toutefois, si la responsable des prêts ouvrait un enregistrement Demande, elle serait en mesure de voir la totalité du processus. Non seulement elle serait en mesure de voir la phase d’investigation de la fraude, mais également d’identifier le résultat de l’investigation en ayant pu voir la phase Action en justice dans le processus. De plus, elle serait en mesure d’afficher un aperçu des étapes des phases d’investigation en choisissant une phase. Malgré l’impossibilité de voir les données ou l’état d’achèvement des étapes, elle serait en mesure d’identifier les actions potentielles effectuées par rapport à l’émetteur de la demande pendant les phases d’investigation et d’action en justice.  
  
 Dans ce flux de processus, la responsable des prêts serait en mesure de voir les phases Investigation de fraude et Action en justice, ce qui constituerait une divulgation d’informations inappropriée. Nous vous recommandons de prêter une attention particulière aux informations susceptibles d’être divulguées en raison de la création d’une branche. Dans notre exemple, fractionnez le processus en deux processus distincts, un pour le traitement de la demande, un autre pour l’investigation de la fraude, pour empêcher la divulgation d’informations. Le processus pour la responsable des prêts ressemble alors à ceci :  
  
 ![Organigramme montrant les étapes supplémentaires du processus pour empêcher la divulgation d’informations](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Organigramme montrant les étapes supplémentaires du processus pour empêcher la divulgation d’informations")  
  
 Le processus de l’investigation est autonome et comprend les phases suivantes :  
  
 ![Organigramme indiquant les étapes d’un processus d’investigation pour les cas de divulgation d’informations](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Organigramme indiquant les étapes d’un processus d’investigation pour les cas de divulgation d’informations")  
  
 Vous devez fournir un workflow pour synchroniser la décision Approuver/Refuser à partir de l’enregistrement Investigation et de l’enregistrement Demande.  
  
### <a name="next-steps"></a>Étapes suivantes  
 [Créer un flux de processus métier](create-business-process-flow.md)   
 [Créer une logique métier personnalisée avec des processus](guide-staff-through-common-tasks-processes.md)   
 
