---
title: Remplacer les boîtes de dialogue par des flux de processus métier ou des applications de canevas | Microsoft Docs
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
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
ms.openlocfilehash: 87a12345c72fd3dd3e93c1afecd282a688e4d4d1
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44691086"
---
# <a name="replace-dialogs-with-business-process-flows-or-canvas-apps"></a>Remplacer les boîtes de dialogue par des flux de processus métier ou des applications de canevas

[Les boîtes de dialogue sont dépréciées](https://docs.microsoft.com/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Elles doivent être remplacées par des flux de processus métier ou des applications de canevas. Cette rubrique décrit plusieurs fonctionnalités offertes par ces options et présente des scénarios où vous pouvez remplacer une boîte de dialogue existante par un flux de processus métier ou une application de canevas incorporé dans un formulaire basé sur des modèles.

## <a name="feature-capability-comparison"></a>Fonctionnalités et équivalences disponibles

Ce tableau liste l’ensemble des fonctionnalités de boîte de dialogue ainsi que les fonctionnalités équivalentes dans les flux de processus métier et les applications de canevas.


|Fonctionnalité de boîte de dialogue  | Fonctionnalité équivalente dans les flux de processus métier ?  | Fonctionnalité équivalente dans les applications de canevas ?  |
|---------|---------|---------|
|Page     | Oui <br/> (phase de processus métier)    | Oui <br/> (écran d’application)        |
|Invite uniquement   |  Non    |  Oui <br/> (étiquettes)        |
|Invite et réponse     |  Oui <br/> (attributs d’entité uniquement)    | Oui <br/> (étiquettes et champs d’entrée)    |
|Arguments d’entrée     |  Limitée <br/> (étapes dans une phase de processus métier)    | Oui <br/> (paramètres de chaîne de requête)     |
|Variables   |  Non     |  Oui       |
|Variables de requête    |  Non     |  Oui     |
|Logique de création de branche conditionnelle    |  Oui     | Oui <br/>  (navigation entre tous les écrans au sein de l’application)    |
|Réutilisation <br/> (lancement en tant que boîte de dialogue enfant)   |  Non     | Oui <br/> (navigation entre tous les écrans au sein de l’application, lancement d’une autre application dans une nouvelle fenêtre)     |
|Exécution des workflows au début/à la fin    |   Oui      |  Non <br/> (remplacement par un flux)  |
|Exécution des workflows en entrée    | Oui    | Non <br/> (remplacement par un flux)   |
|Exécution des workflows à la transition de page   |  Oui       | Non <br/> (remplacement par un flux)    |
|Démarrage avec une URL  |   Non      |  Oui     |
|Journalisation de session    |  Oui       |  Non     |
|Prise en charge de SDK   |  Oui     |  Oui     |

### <a name="additional-capabilities-with-business-process-flows"></a>Autres fonctionnalités disponibles dans les flux de processus métier
- Analytique métier (vues, graphiques et durée d’une phase)
- Contrôles personnalisés

### <a name="additional-capabilities-with-canvas-apps"></a>Autres fonctionnalités disponibles dans les applications de canevas
- Analytique d’application (usage et performances de l’application)
- Composition de page à plusieurs entités
- Exécution de flux
- Connecteurs de données (standard et personnalisés)
- Lancement en tant qu’application autonome
- Disposition configurable

## <a name="choosing-between-a-business-process-flow-or-canvas-app"></a>Choix entre un flux de processus métier ou une application de canevas
Au moment du choix de l’option de remplacement de vos boîtes de dialogue existantes, il est important de prendre en compte l’expérience utilisateur que vous souhaitez offrir au final. Gardez également à l’esprit que vous pouvez modéliser presque toutes les boîtes de dialogue à l’aide d’une application de canevas.

Les flux de processus métier sont plus appropriés si vous devez remplacer des boîtes de dialogue qui modélisent des processus d’assistance dans un flux de travail global nécessitant une collaboration entre plusieurs groupes d’utilisateurs dans un contexte d’application Dynamics 365. Par exemple, ils sont recommandés pour les processus d’approbation et d’envoi de devis. 

Sinon, vous pouvez utiliser des applications de canevas pour remplacer des boîtes de dialogue qui modélisent des tâches préconisées, comme un script d’appel de prospects, ou pour simplifier d’autres tâches utilisateur, telles que la mise à jour d’une opportunité commerciale. Notez que l’utilisation d’une application de canevas autonome peut également être adaptée dans ces scénarios. 

## <a name="dialog-replacement-using-business-process-flow-scenario"></a>Scénario de remplacement d’une boîte de dialogue par un flux de processus métier
Supposons que vous avez une boîte de dialogue qui, sur plusieurs pages, demande diverses informations nécessaires à l’utilisateur, génère un devis, envoie un e-mail aux approbateurs pour accepter ou rejeter le devis, avant de l’envoyer par e-mail au client. La modélisation de ce type de processus est plus efficace à l’aide d’un flux de processus métier. 

Pour remplacer la boîte de dialogue, commencez par identifier les phases principales du processus. Par exemple, le processus peut comporter une phase *Préparer le contenu* pour vérifier que tous les produits sont listés et que toutes les remises sont appliquées, une phase *Générer le devis* pour créer le devis et vérifier que son format est correct, une phase *Premier examen* pour faire vérifier et approuver le devis, une phase *Deuxième examen* pour faire vérifier le devis dans certains cas et enfin, une phase *Envoyer le devis* pour envoyer le devis au client.

Ensuite, identifiez les étapes principales que les utilisateurs auront à suivre au cours du processus. Par exemple, la phase *Préparer le contenu* peut contenir une étape simple de type vrai/faux où l’utilisateur vérifie l’exactitude des produits à inclure dans le devis, une étape de recherche obligatoire pour sélectionner une liste de prix et une étape numérique pour saisir une remise avant de passer à la phase suivante. La phase *Générer le devis* peut comporter une [étape d’action](create-business-process-flow.md#add-an-on-demand-action-to-a-business-process-flow) pour créer un devis basé sur toutes les informations ayant été capturées avant à la phase *Préparer le contenu* et dans l’enregistrement Dynamics 365 associé. Les phases *Premier examen* et *Deuxième examen* peuvent avoir plusieurs étapes de type vrai/faux pour faciliter la vérification du devis, ainsi qu’une étape obligatoire pour capturer l’état d’approbation et s’assurer que le processus ne peut pas passer à la phase suivante sans avoir reçu l’approbation préalable du devis. Configurez la [sécurité au niveau des champs](/customer-engagement/admin/field-level-security) à cette étape pour vous assurer que seuls les approbateurs autorisés peuvent approuver le devis.  Vous pouvez aussi ajouter un workflow aux phases *Premier examen* et *Deuxième examen* pour envoyer une notification par e-mail à tous les approbateurs. 

Enfin, configurez les phases et les étapes du flux de processus métier, en ajoutant la logique conditionnelle souhaitée pour simplifier le flux de processus. Dans cet exemple, vous pouvez ajouter une [branche conditionnelle](enhance-business-process-flows-branching.md) après la phase *Premier examen*. De cette façon, si une étape indique la nécessité d’un deuxième niveau d’examen, le processus lance la phase *Deuxième examen* avant la phase *Envoyer le devis*.

Pour mettre ce flux de processus métier à la disposition des utilisateurs, accordez les privilèges d’accès appropriés aux utilisateurs concernés, puis activez le flux.

Pour plus d’informations sur la création d’un flux de processus métier, consultez [Tutoriel : Créer un flux de processus métier pour standardiser les processus](create-business-process-flow.md).

## <a name="dialog-replacement-using-canvas-app-scenario"></a>Scénario de remplacement d’une boîte de dialogue par une application de canevas

Supposons que vous avez une boîte de dialogue qui suit un script d’appel conçu pour assister les commerciaux lors des appels de prospection à froid. Ce processus peut facilement être capturé à l’aide d’une application de canevas.

Commencez par créer une connexion aux sources de données dont vous aurez besoin pour lire et écrire des données. Cet exemple utilise une [connexion à Dynamics 365](/powerapps/maker/canvas-apps/connections/connection-dynamics-crmonline) pour obtenir les informations de prospect, de compte et de contact.

Tout d’abord, déterminez le nombre d’écrans dont vous avez besoin. Dans cet exemple, il y aura cinq écrans. 
-   Écran 1. Pour sélectionner un prospect dans une liste de prospects à appeler.
-   Écran 2. Pour se présenter au prospect, vérifier si le prospect est disponible pour engager une conversation et planifier un rappel du prospect à une date ultérieure. 
-   Écran 3. Pour déterminer les variables BANT (budget, autorité décisionnaire, besoin et échéance). 
-   Écran 4. Pour capturer les étapes suivantes et planifier des appels de suivi. 
-   Écran 5. Pour remercier le prospect pour sa disponibilité à la fin de l’appel.

Ensuite, concevez chaque écran. Dans le premier écran, [créez une galerie](/powerapps/maker/canvas-apps/customize-layout-sharepoint) de prospects à appeler. Dans le deuxième écran, ajoutez des étiquettes pour donner un titre à l’écran et fournir le script d’appel, et utilisez des contrôles de type cases d’option qui permettent de capturer le moment opportun pour contacter le prospect. Si c’est le bon moment, utilisez une logique conditionnelle qui active un bouton d’accès à l’écran suivant. Si ce n’est pas le bon moment, affichez un script dans le même écran pour essayer de planifier un rappel ultérieur du client. De la même façon, définissez votre script d’appel dans tous les écrans suivants.

Enfin, [définissez le mode de navigation entre les différents écrans](/powerapps/maker/canvas-apps/functions/function-navigate). Dans cet exemple, en plus d’une navigation entre les écrans de manière séquentielle, vous pouvez prévoir de faire passer l’utilisateur du deuxième écran directement au dernier écran (fin du script destiné à remercier le prospect pour sa disponibilité) quand le prospect ne souhaite pas engager une conversation.

Pour mettre cette application à la disposition des utilisateurs, publiez-la. Réfléchissez en quoi ce scénario pourrait être différent si vous aviez une application autonome qui fournit des scripts d’appel et permet une saisie rapide des données.

Imaginons que vous souhaitez incorporer cette expérience dans Dynamics 365 for Sales. Pour cela, commencez par créer un iframe dans un formulaire Dynamics 365 for Sales. Ensuite, accédez à la section **Applications** à partir du menu PowerApps, sélectionnez l’application que vous venez de publier, copiez le lien web sous l’onglet **Détails** et collez-le comme URL de l’iframe. 

Allons maintenant un peu plus loin. Imaginons que vous souhaitez que cette application soit accessible à partir du formulaire principal du prospect, et qu’elle s’ouvre directement dans le contexte du prospect afin de ne pas avoir à demander à l’utilisateur de sélectionner un prospect dans le premier écran. Pour passer les informations nécessaires à l’application, modifiez simplement l’URL de l’iframe en y ajoutant une chaîne de requête avec ces informations, telles que les identifiants du prospect ou du compte. Utilisez JavaScript qui s’exécute au déclenchement d’un événement spécifique, comme le chargement d’un formulaire. Ensuite, mettez à jour l’application pour supprimer le premier écran (sélection du prospect) et, à la place, accéder aux valeurs passées à l’application par la chaîne de requête à l’aide de la [fonction Param](/powerapps/maker/canvas-apps/functions/function-param).

## <a name="dialog-replacement-faq"></a>Questions fréquentes (FAQ) sur le remplacement de boîtes de dialogue

Les dépendances dans les applications de canevas sont-elles suivies ? 
- Les dépendances dans les applications de canevas sont suivies de la même façon que les dépendances dans l’engagement client Dynamics 365.

Puis-je lancer une application de canevas en tant que fenêtre contextuelle à partir d’un bouton de la barre de commandes ?
- Oui. Pour cela, définissez simplement l’URL cible à celle de votre application de canevas. Cette URL est indiquée dans la section **Détails** de l’application, comme décrit précédemment.

Les workflows peuvent-ils être appelés à partir d’une application de canevas ?
- Non, cela n’est pas pris en charge. Nous vous recommandons d’utiliser un flux à la place. Pour plus d’informations, consultez [Présentation des flux de bouton avec entrée utilisateur](button-flow-with-user-input-tokens.md)

Puis-je convertir automatiquement des boîtes de dialogue en flux de processus métier ou en applications de canevas ?
- Non, il n’existe pas de méthode permettant d’effectuer cette conversion automatiquement.


## <a name="see-also"></a>Voir aussi
[Tutoriel : Créer un flux de processus métier pour standardiser les processus](create-business-process-flow.md) </br>
[Que sont les applications de canevas dans PowerApps ?](/powerapps/maker/canvas-apps/getting-started)


