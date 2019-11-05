---
title: Améliorez les flux de processus d’entreprise avec des branchements avec PowerApps | MicrosoftDocs
description: Découvrez comment utiliser la branche dans un workflow de processus d’entreprise
ms.custom: ''
ms.date: 06/27/2018
ms.tgt_pltfrm: ''
ms.topic: article
ms.service: flow
author: MSFTMAN
ms.assetid: 62cfac6b-0d78-48de-9364-0287454aa2a0
caps.latest.revision: 9
ms.author: Deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: c3a03cefcb3e808bb7900b79b05e6c2b3f8ef7f5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544780"
---
# <a name="tutorial-enhance-business-process-flows-with-branching"></a>Didacticiel : améliorer les flux de processus d’entreprise avec branchement
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les flux de processus d’entreprise vous guident à travers les différentes étapes des processus de vente, de marketing ou de service vers l’achèvement. Dans les cas simples, un processus d’entreprise linéaire est une bonne option. Toutefois, dans des scénarios plus complexes, vous pouvez améliorer un workflow de processus d’entreprise avec branchement. Si vous disposez des autorisations créer sur les flux de processus d’entreprise, vous pouvez créer un flux de processus d’entreprise avec plusieurs branches à l’aide de la logique de `If-Else`. La condition de branchement peut être formée de plusieurs expressions logiques qui utilisent une combinaison d’opérateurs `AND` ou `OR`. La sélection de branche est effectuée automatiquement, en temps réel, en fonction des règles définies pendant la définition du processus. Par exemple, dans la vente de voitures, vous pouvez configurer un seul processus d’entreprise, qui, après qu’une étape de qualification commune, se divise en deux branches distinctes sur la base d’une règle (le client préfère-t-il une nouvelle voiture ou un véhicule possédé, est-il budget au-dessus ou en dessous de $20 000 , et ainsi de suite. ), une branche pour vendre de nouvelles voitures et une autre branche pour vendre des voitures prédétenus. Pour plus d’informations sur les flux de processus d’entreprise, consultez [vue d’ensemble des flux de processus d’entreprise](business-process-flows-overview.md).  
  
 Le diagramme suivant illustre un workflow de processus d’entreprise avec des branches.  
  
 ![Organigramme présentant les étapes du processus de vente automobile](media/example-car-sales-flow-chart.png "Organigramme présentant les étapes du processus de vente automobile")  
  
<a name="Points"></a>   
## <a name="what-you-need-to-know-when-designing-business-process-flows-with-branches"></a>Ce que vous devez savoir lors de la conception de flux de processus d’entreprise avec des branches  
 Prenez note des informations suivantes lorsque vous concevez le workflow de processus d’entreprise avec les branches :  
  
-   Un processus peut s’étendre sur un maximum de 5 entités uniques.  
  
-   Vous pouvez utiliser un maximum de 30 étapes par processus et un maximum de 30 étapes par étape.  
  
-   Chaque branche ne peut pas avoir plus de 5 niveaux de profondeur.  
  
-   La règle de branchement doit reposer sur les étapes de l’étape qui la précède immédiatement.  
  
-   Vous pouvez combiner plusieurs conditions dans une règle en utilisant l’opérateur `AND` ou l’opérateur `OR`, mais pas les deux.  
  
-   Lorsque vous définissez un processus, vous pouvez éventuellement sélectionner une relation d’entité. Cette relation doit avoir une relation d’entité 1 : N (un-à-plusieurs).  
  
-   Plusieurs processus actifs peuvent s’exécuter simultanément sur le même enregistrement de données.  
  
-   Vous pouvez réorganiser les vignettes (étapes, étapes, conditions, etc.) sur le déroulement du processus à l’aide de la fonction glisser-déplacer.  
  
-   Lors de la fusion de branches, toutes les branches homologues doivent fusionner à une seule étape. Les branches homologues doivent toutes être fusionnées en une seule étape, ou chaque branche homologue doit mettre fin au processus. Une branche homologue ne peut pas fusionner avec d’autres branches et en même temps terminer le processus.  
  
> [!NOTE]
> - Une entité utilisée dans le processus peut être revisitée plusieurs fois (plusieurs boucles d’entité fermées).  
> - Un processus peut revenir à l’étape précédente, quel que soit le type d’entité. Par exemple, si l’étape active est **fournir un devis** sur un enregistrement de devis, les utilisateurs du processus peuvent déplacer le niveau actif vers la phase **proposer** sur un enregistrement opportunité.  
>   
>   Dans un autre exemple, supposons qu’un processus se trouve actuellement dans la phase de **proposition** de votre processus : **qualifier le prospect** > **identifier les besoins** > **créer une proposition** > **proposition présente** >  **Fermez**. Si la proposition présentée au client requiert davantage de recherches pour identifier les besoins des clients, les utilisateurs peuvent simplement sélectionner l’étape **identifier les besoins** de votre processus et choisir **définir comme actif**.  
  
<a name="CarSelling365"></a>   
## <a name="example-car-selling-process-flow-with-two-branches"></a>Exemple : processus de vente de voitures avec deux branches
 
Examinons l’exemple du workflow de processus d’entreprise avec deux branches, pour la vente de voitures nouvelles et prédétenues.  
  
 Tout d’abord, nous allons créer un processus nommé **automobile Sales process**.  
  
1.  [Ouvrez l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) , puis, dans le volet de navigation gauche, sélectionnez **processus**.  
  
2.  Sélectionnez **nouveau** pour créer un nouveau processus.  
  
3.  Spécifiez la **catégorie** comme **Workflow de processus d’entreprise** et pour l' **entité** principale choisissez **prospect**.  
  
4.  Ajoutez la première étape au processus appelé **Qualified** , puis ajoutez Steps **Time Purchases Frame** et **voiture preference**.  
  
5.  Après l’étape de **qualification** commune, nous avons divisé le processus en deux branches distinctes, à l’aide de la vignette **condition** .  
  
    1.  Configurer la vignette de condition avec des règles qui répondent aux besoins de votre entreprise  
  
    2.  Pour ajouter la première branche pour une phase, ajoutez une vignette d’étape sur le chemin « Oui » de la vignette de condition  
  
    3.  Pour ajouter la deuxième branche qui est exécutée lorsque la condition n’est pas satisfaite, ajoutez une autre vignette d’étape sur le chemin « non » de la vignette de condition  
  
> [!TIP]
>  Vous pouvez ajouter une autre condition sur le chemin « non » d’une vignette de condition existante pour créer une branche plus complexe.  
  
 ![Image représentant l’étape de qualification créée](media/example-car-sales-qualify-stage.JPG "Image représentant l’étape de qualification créée")  
  
 Si la **préférence de voiture** = **nouveau**, le processus se branche à la nouvelle étape de **vente de voitures** , sinon, il passe à l’étape de vente de **voiture** précédée, dans la deuxième branche, comme indiqué ci-dessous.  
  
 ![Image représentant la nouvelle étape de vente de voitures](media/example-car-sales-new-stage-1.JPG "Image représentant la nouvelle étape de vente de voitures")  
  
 ![Étape&#45;de vente de voiture détenue](media/example-car-sales-pre-owned-stage.JPG "Étape de vente de voiture prédétenue")  
  
 Une fois que vous avez effectué toutes les étapes de la nouvelle phase de **vente automobile** ou de l’étape de **vente de voitures détenues** , le processus est renvoyé au circuit principal, avec l’étape de **remise de devis** .  
  
 ![Étape de remise de devis](media/example-car-sales-deliver-quote-stage.JPG "Étape de remise de devis")  
  
<a name="PreventInformation"></a>   
## <a name="prevent-information-disclosure"></a>Empêcher la divulgation d’informations  
 Prenons l’exemple d’un processus d’entreprise avec des branches pour traiter une demande de prêt dans une banque, comme indiqué ci-dessous. Les entités personnalisées utilisées dans les étapes sont indiquées entre parenthèses.  
  
 ![Organigramme présentant les étapes d’un exemple de processus pour empêcher la divulgation d’informations](media/example-car-sales-flow-chart-process-prevent-information-disclosure.png "Organigramme présentant les étapes d’un exemple de processus pour empêcher la divulgation d’informations")  
  
 Dans ce scénario, le responsable du prêt bancaire doit accéder à l’enregistrement de la demande, mais le responsable du prêt ne doit pas avoir de visibilité sur l’investigation de la demande. À première vue, il semble que nous pouvons facilement le faire en affectant au responsable de prêt un rôle de sécurité qui ne spécifie aucun accès à l’entité investigation. Toutefois, examinons l’exemple plus en détail et voyons si c’est vraiment vrai.  
  
 Supposons qu’un client place la demande de prêt pour plus de $60 000 à la Banque. Le responsable du prêt examine la demande au cours de la première étape. Si la règle de branchement qui vérifie si le montant dû à la Banque dépasse $50 000 est respecté, l’étape suivante du processus consiste à examiner si la demande est frauduleuse. S’il est déterminé qu’il s’agit effectivement d’un cas de fraude, le processus passe à une action légale sur le demandeur. Le responsable des prêts ne doit pas avoir de visibilité sur les deux étapes d’investigation, car le responsable n’a pas accès à l’entité investigation.  
  
 Toutefois, si le responsable du prêt ouvre l’enregistrement de la demande, tout est en mesure de voir l’intégralité du processus de bout en bout. Non seulement le responsable des prêts sera en mesure de voir la phase d’investigation des fraudes, mais il sera également en mesure d’identifier le résultat de l’investigation en ayant pu voir l’étape de l’action légale dans le processus. En outre, le responsable sera en mesure d’afficher un aperçu des étapes des étapes d’investigation en choisissant l’étape. Alors que l’officier de prêt ne peut pas voir les données ou l’état d’achèvement de l’étape, il peut identifier les actions potentielles qui ont été effectuées sur le souscripteur de la demande pendant les étapes d’investigation et d’action légale.  
  
 Dans ce processus, le responsable des prêts sera en mesure de voir les étapes d’investigation et d’action légale, qui constituent une divulgation d’informations incorrecte. Nous vous recommandons d’accorder une attention particulière aux informations qui peuvent être divulguées en raison de la branche. Dans notre exemple, divisez le processus en deux processus distincts, un pour le traitement des demandes et un autre pour l’investigation de la fraude, afin d’éviter la divulgation d’informations. Le processus pour le responsable de prêt se présente comme suit :  
  
 ![Organigramme présentant les étapes supplémentaires du processus pour empêcher la divulgation d’informations](media/example-car-sales-flow-chart-additional-steps-prevent-information-disclosure.png "Organigramme présentant les étapes supplémentaires du processus pour empêcher la divulgation d’informations")  
  
 Le processus d’investigation sera autonome et inclura les étapes suivantes :  
  
 ![Organigramme présentant les étapes d’un processus d’investigation pour les cas de divulgation d’informations](media/example-car-sales-flow-chart-investigation-information-disclosure-case.png "Organigramme présentant les étapes d’un processus d’investigation pour les cas de divulgation d’informations")  
  
 Vous devrez fournir un flux de travail pour synchroniser la décision d’approbation/refus de l’enregistrement d’investigation à l’enregistrement de la demande.  
  
### <a name="next-steps"></a>Étapes suivantes  
 [Créer un  de workflow de processus d’entreprise](create-business-process-flow.md)  
 [Créer une logique métier personnalisée avec des processus](guide-staff-through-common-tasks-processes.md)   
 
