---
title: Remplacer des boîtes de dialogue par des flux de processus d’entreprise ou des applications de canevas | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- flow
ms.assetid: 046480e6-f2ff-4c56-9e03-f642c982ff7d
caps.latest.revision: 12
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: a7e8bac3c33fa5bb8cfb0501b981af65115036ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548814"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Remplacer des boîtes de dialogue par des flux de processus d’entreprise ou des applications de canevas
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les [boîtes de dialogue sont dépréciées](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated)et doivent être remplacées par les flux de processus d’entreprise ou les applications de canevas. Cette rubrique décrit les différentes fonctionnalités de ces options, ainsi que les situations où une application de workflow ou de canevas d’entreprise incorporée dans un formulaire piloté par modèle peut être utilisée pour remplacer une boîte de dialogue existante.

## <a name="feature-capability-comparison"></a>Comparaison des fonctionnalités des fonctionnalités

Ce tableau répertorie les fonctionnalités de dialogue et les fonctionnalités équivalentes des flux de processus d’entreprise et des applications de canevas.


|Fonctionnalité de dialogue  | La fonctionnalité dans les flux de processus métier ?  | Des fonctionnalités dans les applications Canvas ?  |
|---------|---------|---------|
|Pagination     | Oui <br/> (étape du processus d’entreprise)    | Oui <br/> (écran d’application)        |
|Invite uniquement   |  º    |  Oui <br/> celles        |
|Invite et réponse     |  Oui <br/> (attributs d’entité uniquement)    | Oui <br/> (étiquettes et champs d’entrée)    |
|Arguments d’entrée     |  Certaine <br/> (étapes de l’étape du processus d’entreprise)    | Oui <br/> (paramètres de chaîne de requête)     |
|Variables   |  º     |  Oui       |
|Variables de requête    |  º     |  Oui     |
|Logique de branchement conditionnel    |  Oui     | Oui <br/>  (accéder à n’importe quel écran de l’application)    |
|Soient <br/> (lancer en tant que boîte de dialogue enfant)   |  º     | Oui <br/> (accéder à n’importe quel écran de l’application, lancer une application différente dans une nouvelle fenêtre)     |
|Exécuter des workflows au début/à la fin    |   Oui      |  º <br/> (utilisez plutôt un Flow)  |
|Exécuter des workflows en entrée    | Oui    | º <br/> (utilisez plutôt un Flow)   |
|Exécuter des flux de travail lors de la transition de page   |  Oui       | º <br/> (utilisez plutôt un Flow)    |
|Commencer à utiliser une URL  |   º      |  Oui     |
|Journalisation de session    |  Oui       |  º     |
|Prise en charge du SDK   |  Oui     |  Oui     |

### <a name="additional-capabilities-with-business-process-flows"></a>Fonctionnalités supplémentaires avec les flux de processus d’entreprise
- Analyse des processus (vues, graphiques et temps passé dans une phase)
- Contrôles personnalisés

### <a name="additional-capabilities-with-canvas-apps"></a>Fonctionnalités supplémentaires avec les applications de canevas
- Analyse d’application (& de l’utilisation des applications)
- Composition de page à plusieurs entités
- Exécuter des flux
- Connecteurs de données (standard et personnalisé)
- Lancer en tant qu’application autonome
- Disposition configurable

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Choix entre un workflow de processus d’entreprise ou une application de canevas
Lorsque vous choisissez le remplacement de votre boîte de dialogue, il est important de tenir compte de l’expérience utilisateur que vous souhaitez fournir. Gardez également à l’esprit que la plupart des boîtes de dialogue peuvent être modélisées à l’aide d’une application Canvas.

Les flux de processus d’entreprise sont mieux adaptés au remplacement de boîtes de dialogue qui modélisent les processus fournissant des conseils sur un flux de travail global qui nécessite une collaboration entre des groupes de personnes et le contexte de l’application Dynamics 365. Par exemple, passez en revue les devis et le routage. 

Vous pouvez également utiliser les applications de canevas pour remplacer des boîtes de dialogue qui modélisent des tâches normatives telles qu’un script d’appel pour le Prospecting ou simplifier l’expérience utilisateur pour d’autres tâches, telles que la mise à jour d’une opportunité. Notez que ces scénarios peuvent même tirer parti d’une application de canevas autonome. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Remplacement de la boîte de dialogue à l’aide du scénario de workflow de processus métier
Imaginez que vous avez une boîte de dialogue qui, sur une série de pages, demande à l’utilisateur des informations clés, génère un devis, envoie un e-mail aux réviseurs pour accepter ou refuser le devis, avant de l’envoyer par courrier électronique au client. Ce type de processus est modélisé plus efficacement à l’aide d’un workflow de processus d’entreprise. 

Pour remplacer la boîte de dialogue, commencez par identifier les principales étapes du processus. Celles-ci peuvent inclure une étape *préparer le contenu* pour s’assurer que tous les produits sont répertoriés et que des remises sont appliquées, une étape *générer un devis* pour créer le devis et le vérifier pour obtenir une précision de format, une étape de *révision principale* pour laquelle envoyer le devis examen et approbation, une étape de *vérification secondaire* pour passer en revue le devis dans certaines circonstances et enfin, une étape de *remise* de devis pour envoyer le devis au client.

Ensuite, identifiez les principales étapes que les utilisateurs doivent suivre dans le processus. Par exemple, l’étape *préparer le contenu* peut contenir une simple étape true ou false permettant à l’utilisateur de vérifier les produits à mettre entre guillemets, une étape de recherche obligatoire pour sélectionner une liste de prix et une étape numérique pour entrer une remise avant de passer à l’étape suivante. L’étape *générer un devis* peut comporter une étape d' [action](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) pour créer un devis basé sur toutes les informations précédemment capturées dans l’étape préparer le *contenu* et sur l’enregistrement Dynamics 365 associé. Les étapes *principales de révision* et de *révision secondaire* peuvent avoir plusieurs étapes vraies ou fausses pour guider la révision des devis, ainsi qu’une étape requise pour capturer l’état d’approbation et vous assurer que le processus ne peut être déplacé vers l’étape suivante qu’une fois l’approbation lettré. Configurez la [sécurité au niveau des champs](/customer-engagement/admin/field-level-security) à cette étape pour vous assurer que seuls les réviseurs autorisés peuvent fournir l’approbation sur le devis.  En outre, vous pouvez ajouter un flux de travail aux étapes de révision *principale* et de *révision secondaire* , de telle sorte qu’à la saisie, une notification par courrier électronique est envoyée à tous les réviseurs. 

Enfin, configurez vos étapes et étapes de workflow de processus d’entreprise, ainsi que la logique conditionnelle pour guider le processus. Pour cet exemple, vous pouvez ajouter une [branche conditionnelle](enhance-business-process-flows-branching.md) après l’étape de *révision principale* , de telle sorte que, si une étape indique la nécessité d’un deuxième niveau de révision, l’étape suivante du processus est la phase de *vérification secondaire* , sinon,  *Fournissez* l’étape de devis.

Pour que ce processus d’entreprise soit disponible pour les utilisateurs, assurez-vous que les utilisateurs appropriés disposent de privilèges sur le workflow de processus d’entreprise, puis activez-le.

Pour plus d’informations sur la création d’un workflow de processus d’entreprise, consultez [Didacticiel : créer un workflow de processus d’entreprise pour normaliser les processus](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Remplacement de la boîte de dialogue à l’aide du scénario d’application Canvas

Supposons que vous disposiez d’une boîte de dialogue, qui suit un script d’appel qui guide les représentants commerciaux via des prospects appelant à froid. Ce processus peut être facilement capturé à l’aide d’une application Canvas.

Commencez par vous connecter aux sources de données dont vous avez besoin pour lire et écrire des données. Dans cet exemple, une [connexion à Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) est utilisée pour les prospects, les comptes et les informations de contact.

Commencez par identifier le nombre d’écrans nécessaires. Pour cet exemple, vous pouvez décider d’avoir cinq écrans. 
-   Écran 1. Pour sélectionner un prospect dans une liste à appeler.
-   Écran 2. Pour les introductions, la vérification de la disponibilité d’une conversation et la planification d’un rappel à une date ultérieure. 
-   Écran 3. Pour déterminer les BANT (budget, autorité, besoin et chronologie). 
-   Écran 4. Pour capturer les étapes suivantes et planifier des appels de suivi. 
-   Écran 5. Merci à la fin de l’appel.

Ensuite, générez chaque écran. Dans le premier écran, [créez une galerie](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de clients qui doivent être appelés. Dans le second cas, utilisez des étiquettes pour intituler l’écran et fournir le script d’appel, tout en utilisant des contrôles tels que des cases d’option pour déterminer s’il est opportun pour la personne de parler. Si c’est le cas, utilisez la logique conditionnelle pour permettre à un bouton de naviguer jusqu’à l’écran suivant et, si ce n’est pas le cas, de révéler un script sur le même écran pour tenter de planifier un rappel avec le client. De même, définissez votre script d’appel sur les écrans suivants.

Enfin, [définissez la navigation sur les écrans](/powerapps/maker/canvas-apps/functions/function-navigate). Dans cet exemple, en plus de parcourir les écrans de manière séquentielle, vous souhaiterez peut-être parcourir l’utilisateur depuis le deuxième écran jusqu’au dernier écran (la fin du script remerciant le prospect pour le moment) si le responsable ne s’intéresse pas à une conversation.

Pour rendre cette application accessible aux utilisateurs, publiez l’application. Réfléchissez à la façon dont un tel scénario peut être transformé grâce à la disponibilité d’une application autonome qui fournit des scripts d’appel et prend en charge l’entrée de données rapide.

Imaginez que vous souhaitez incorporer cette expérience dans Dynamics 365 Sales. Pour ce faire, commencez par créer un IFRAME sur un formulaire Dynamics 365 Sales. Ensuite, accédez à la section **applications** dans le menu powerapps, sélectionnez l’application que vous venez de publier, copiez le lien Web sous l’onglet **Détails** , puis collez-le en tant qu’URL de l’IFRAME. 

Pour aller plus loin, supposons que vous souhaitiez que cette application soit disponible directement dans le formulaire principal du prospect et qu’elle soit dans le contexte du prospect, afin que l’application ne demande pas à l’utilisateur de sélectionner un prospect dans le premier écran. Pour transmettre des informations pertinentes à l’application, il vous suffit de modifier l’URL iframe pour ajouter une chaîne de requête contenant ces informations, telles que les ID de prospect ou de compte, à l’aide de JavaScript qui s’exécute sur un certain événement, par exemple lors du chargement du formulaire. Ensuite, mettez à jour l’application pour supprimer le premier écran (pour la sélection du prospect) et accédez à la place aux valeurs transmises à l’application via la chaîne de requête à l’aide de la [fonction param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>FAQ sur le remplacement de boîtes de dialogue

Les dépendances des applications de canevas sont-elles suivies ? 
- Les dépendances sur les applications de canevas sont suivies de la même façon que les dépendances dans les applications Dynamics 365.

Puis-je lancer une application Canvas sous forme de fenêtre contextuelle à partir d’un bouton de la barre de commandes ?
- Oui. Pour ce faire, il vous suffit de définir l’URL cible sur celle de votre application Canvas, obtenue à partir de la section des **Détails** de l’application, comme décrit précédemment.

Les flux de travail peuvent-ils être appelés à partir d’une application Canvas ?
- Cela n’est pas pris en charge. Nous vous recommandons d’utiliser un Flow à la place. Pour en savoir plus : [Présentation des flux de bouton avec entrée utilisateur](button-flow-with-user-input-tokens.md)

Puis-je convertir automatiquement les dialogues en flux de processus d’entreprise ou en applications de canevas ?
- Il n’existe aucune méthode automatisée pour convertir des dialogues en flux de processus d’entreprise ou en applications de canevas.


## <a name="see-also"></a>Voir aussi
[Didacticiel : créer un workflow de processus d’entreprise pour normaliser les processus](create-business-process-flow.md) </br>
[Que sont les applications de canevas dans PowerApp ?](/powerapps/maker/canvas-apps/getting-started)


