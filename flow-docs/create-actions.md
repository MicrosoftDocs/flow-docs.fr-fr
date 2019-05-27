---
title: Créer une action personnalisée | Microsoft Docs
description: Utilisez des actions personnalisées quand vous souhaitez automatiser une série de commandes dans le système. Les actions développent le vocabulaire dont disposent les développeurs pour exprimer les processus métier.
ms.custom: ''
ms.date: 08/06/2018
ms.reviewer: matp
ms.service: flow
ms.topic: article
author: msftman
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 92db054d5e9fab7ef6077146260ce46f540697c9
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455792"
---
# <a name="create-a-custom-action"></a>Créer une action personnalisée

Utilisez des actions personnalisées quand vous souhaitez automatiser une série de commandes dans le système. Les actions développent le vocabulaire dont disposent les développeurs pour exprimer les processus métier. À partir de verbes principaux tels que Créer, Mettre à jour, Supprimer et Attribuer fournis par le système, une action crée des verbes plus expressifs tels qu’Approuver, Réaffecter, Acheminer ou Planifier. Si la définition d’un processus métier change, une personne qui n’est pas développeur peut modifier l’action personnalisée, si bien que le code n’a pas besoin d’être changé.  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Créer une action  
  
> [!IMPORTANT]
>  Si vous créez une action à inclure dans le cadre d’une solution destinée à être distribuée, créez-la dans le contexte de la solution. Accédez à **[Paramètres](/powerapps/maker/model-driven-apps/advanced-navigation#settings)** > **Solutions** et recherchez la solution non managée dont cette action fera partie. Ensuite, dans la barre de menus, sélectionnez **Nouveau** > **Processus**. Ainsi, le préfixe de personnalisation associé au nom de l’action sera cohérent avec les autres composants de la solution. Après avoir créé l’action, vous ne pouvez pas changer le préfixe.  
  
 Comme les processus de workflow, les actions ont les propriétés suivantes dans la boîte de dialogue **Créer un processus**.  
  
 **Nom du processus**  
 Une fois que vous avez entré un nom pour le processus, un nom unique est créé pour celui-ci (les espaces et caractères spéciaux éventuels sont supprimés du nom du processus).  
  
 **Catégorie**  
 Cette propriété établit qu’il s’agit d’un processus d’action. Vous ne pouvez pas changer ce paramètre après avoir enregistré le processus.  
  
 **Entité**  
 Avec les processus d’actions, vous pouvez sélectionner une entité afin de fournir un contexte pour le workflow comme pour tout autre type de processus, mais vous avez également la possibilité de choisir **Aucun (global)**. Utilisez cette option si votre action ne requiert pas le contexte d’une entité spécifique. Vous ne pouvez pas changer ce paramètre après avoir enregistré le processus.  
  
 **Type**  
 Utilisez cette propriété pour indiquer si vous souhaitez générer une nouvelle action à partir de zéro ou démarrer à partir d’un modèle existant.  
 
Contrairement aux processus de workflow, vous n’avez pas besoin de définir les options suivantes :  
  
- **Démarrer quand** : Les actions démarrent quand le code appelle le message généré pour celles-ci.  
  
- **Étendue** : Les actions sont toujours exécutées dans le contexte de l’utilisateur appelant.  
  
- **Exécuter en arrière-plan** : Les actions sont toujours des workflows en temps réel.  
  
Les actions ont également quelque chose que les processus de workflow n’ont pas : des arguments d’entrée et de sortie.

> [!NOTE]
> Vous pouvez activer une action personnalisée à partir d’un workflow sans écrire de code. Plus d’informations : [Appeler des actions personnalisées à partir d’un workflow](invoke-custom-actions-workflow-dialog.md).
 
<a name="edit"></a>   
## <a name="edit-an-action"></a>Ajouter une action  
 Vous devez désactiver les processus pour pouvoir les modifier.  
  
 Vous pouvez modifier une action qui a été créée dans le cadre d’une solution non managée ou incluse dans une solution installée dans votre organisation. Si la solution est une solution managée, vous n’êtes peut-être pas en mesure de la modifier. L’éditeur de solutions a la possibilité de modifier les propriétés managées afin que l’action installée avec une solution managée ne soit pas modifiable.  
  
 Quand une action est enregistrée, un nom unique est généré en fonction du nom du processus. Le préfixe de personnalisation ajouté à ce nom unique provient de l’éditeur de solutions. Il s’agit du nom du message qu’un développeur utilise dans son code.  
  
 Quand vous modifiez une action, vous disposez des options suivantes :  
  
 **Nom du processus**  
 Une fois que le processus est créé et que le nom unique est généré à partir du nom du processus, vous pouvez modifier ce nom. Vous souhaiterez peut-être appliquer une convention de nommage pour faciliter la recherche de processus spécifiques.  
  
 **Nom unique**  
 Quand une action est enregistrée, un nom unique est généré en fonction du nom du processus. Le préfixe de personnalisation ajouté à ce nom unique provient de l’éditeur de solutions. Il s’agit du nom du message qu’un développeur utilise dans son code. Ne changez pas ce nom unique si le processus n’a pas été activé et que du code susceptible d’appeler l’action à l’aide de ce nom est en place.  
  
> [!IMPORTANT]
>  Une fois que l’action est activée et que du code est écrit pour utiliser un nom unique, ce dernier ne peut être changé que si le code qui le référence l’est également.  
  
 **Activer la restauration**  
 En règle générale, les processus qui prennent en charge des transactions « annulent » (ou restaurent) toute l’opération si une partie d’entre eux échoue. Il existe quelques exceptions à cela. Certaines actions que les développeurs peuvent faire dans le code lancé par l’action ne prennent pas en charge les transactions. C’est par exemple le cas si le code effectue des actions dans d’autres systèmes qui sortent du cadre de la transaction. Ces actions ne peuvent pas être restaurées par l’action en cours d’exécution dans une application. Certains messages dans la plateforme ne prennent pas en charge les transactions. Cependant, tout ce que vous pouvez faire avec l’interface utilisateur de l’action prend en charge les transactions. Toutes les actions qui font partie d’un workflow en temps réel sont considérées comme appartenant à la transaction, mais avec des actions, vous avez la possibilité de le refuser.  
  
 Vous devez consulter le développeur qui utilisera ce message pour déterminer s’il doit faire partie de la transaction ou non. En règle générale, une action doit faire partie de la transaction si les actions effectuées par le processus métier ne font sens que si elles sont toutes exécutées avec succès. L’exemple classique est le transfert de fonds entre deux comptes bancaires. Si vous retirez des fonds d’un compte, vous devez les déposer sur l’autre. Si une action échoue, les deux doivent échouer.  
  
> [!NOTE]
>  Vous ne pouvez pas activer la restauration si une action personnalisée est appelée directement à partir d’un workflow. Vous pouvez activer la restauration si une action est déclenchée par un message de services web PowerApps.  
  
 **Activer en tant que**  
 Comme tous les processus, vous pouvez activer le processus en tant que modèle et l’utiliser comme point de départ avancé pour les processus qui suivent un modèle similaire.  
  
 **Définir les arguments de processus**  
 Dans cette zone, vous spécifiez toutes les données que l’action attend pour démarrer et les données à transmettre au terme de l’action. Plus d’informations : [Définir les arguments de processus](#define-process-arguments)  
  
 **Ajouter des phases et des étapes**  
 Comme pour les autres processus, vous spécifiez les actions à effectuer et à quel moment les effectuer. Plus d’informations : [Ajouter des phases et des étapes](#add-stages-and-steps)

<a name="BKMK_DefineProcessArgs"></a>   
## <a name="define-process-arguments"></a>Définir les arguments de processus  
 Quand un développeur utilise un message, il peut commencer avec des données à passer au message. Par exemple, dans le cadre de la création d’un enregistrement d’incident, la valeur du titre de l’incident peut être passée comme argument d’entrée.  
  
 Quand le message est terminé, le développeur peut avoir besoin de transmettre des données qui ont été changées ou générées par le message à une autre opération dans son code. Ces données sont l’argument de sortie.  
  
 Les arguments d’entrée et de sortie doivent avoir un nom, un type et des informations indiquant si les arguments sont toujours requis. Vous pouvez également fournir une description.  
  
 Le nom du message et les informations sur tous les arguments de processus représentent la « signature » du message. Une fois qu’une action est activée et utilisée dans le code, la signature ne doit pas changer. Si cette signature change, tout code qui utilise le message échoue. La seule exception peut être le changement de l’un des paramètres afin qu’il ne soit pas toujours nécessaire.  
  
 Vous pouvez changer l’ordre des arguments en les triant ou en les déplaçant vers le haut ou vers le bas, car ils sont identifiés par nom, pas par l’ordre. En outre, la modification de la description n’interrompt pas le code qui utilise le message.  
  
### <a name="action-process-argument-types"></a>Types d’arguments de processus pour les actions  
 Le tableau suivant décrit les types d’arguments de processus pour les actions.  
  
|Type|Description|  
|----------|-----------------|  
|Booléen|Valeur `true` ou `false`.|  
|Date/Heure|Valeur qui stocke les informations de date/heure.|  
|Décimal|Valeur numérique avec une précision décimale. Utilisée quand la précision est extrêmement importante.|  
|Entité|Enregistrement pour l’entité spécifiée. Quand vous sélectionnez Entité, la liste déroulante est activée, ce qui vous permet de sélectionner le type d’entité.|  
|EntityCollection|Collection d’enregistrements d’entité.|  
|EntityReference|Objet qui contient le nom, l’ID et le type d’un enregistrement d’entité qui identifient ce dernier de façon unique. Quand vous sélectionnez EntityReference, la liste déroulante est activée, ce qui vous permet de sélectionner le type d’entité.|  
|Flottant|Valeur numérique avec une précision décimale. Utilisé quand les données proviennent d’une mesure qui n’est pas absolument précise.|  
|Entier|Nombre entier.|  
|Monétaire|Valeur qui stocke les données relatives à une somme d’argent.|  
|Liste déroulante|Valeur qui représente une option pour un attribut Groupe d’options.|  
|Chaîne|Valeur de texte.|  
  
> [!NOTE]
> Les valeurs de l’argument **EntityCollection** ne peuvent pas être définies dans l’interface utilisateur des conditions ou des actions. Ces valeurs sont fournies par les développeurs dans le code personnalisé en vue de leur utilisation. Plus d’informations : [Créer vos propres actions](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Ajouter des phases et des étapes  
 Les actions sont un type de processus très similaire aux workflows en temps réel. Toutes les étapes utilisables dans les workflows en temps réel sont utilisables dans les actions. Pour plus d’informations sur les étapes utilisables pour les workflows en temps réel et les actions, consultez [Phases et étapes de workflow](configure-workflow-steps.md).  
  
 Outre les étapes utilisables pour les workflows en temps réel, les actions ont l’étape **Attribuer une valeur**.  Dans les actions, vous ne pouvez utiliser ces étapes que pour définir les arguments de sortie. Vous pouvez utiliser l’Assistant Formulaire pour définir les arguments de sortie sur des valeurs spécifiques ou, plus vraisemblablement, sur des valeurs issues de l’enregistrement sur lequel l’action est en cours d’exécution, d’enregistrements liés à cet enregistrement par une relation plusieurs-à-un, d’enregistrements créés au cours d’une étape précédente ou sur des valeurs qui font partie du processus lui-même.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Appeler des actions personnalisées à partir d’un workflow](invoke-custom-actions-workflow-dialog.md)   

 
 
