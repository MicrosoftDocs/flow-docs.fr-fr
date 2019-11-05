---
title: Configurer des actions pour les workflows dans PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: 6dbc0f10-7ac5-4685-ab74-22d24bf7102d
caps.latest.revision: 19
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: d0b680c5c38b31b915482c435e7bc2ba83586dae
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547571"
---
# <a name="configure-custom-actions-from-a-workflow"></a>Configurer des actions personnalisées à partir d’un flux de travail
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Vous pouvez activer une action personnalisée à partir d’un flux de travail sans écrire de code. Informations supplémentaires : [appeler des actions personnalisées à partir d’un flux de travail](invoke-custom-actions-workflow-dialog.md).  
  
 Vous pouvez également créer une action afin qu’un développeur puisse l’utiliser dans le code, ou vous devrez peut-être modifier une action précédemment définie. Comme les processus de flux de travail, tenez compte des éléments suivants :  
  
-   Que doit faire l’action ?  
  
-   Dans quelles conditions l’action doit-elle être effectuée ?  
  
 
Contrairement aux processus de workflow, vous n’avez pas besoin de définir les options suivantes :  
  
- **Démarrer quand**: les actions démarrent lorsque le code appelle le message généré pour eux.  
  
- **Étendue**: les actions s’exécutent toujours dans le contexte de l’utilisateur appelant.  
  
- **Exécuter en arrière-plan : les**actions sont toujours des flux de travail en temps réel.  
  
Les actions ont également un comportement qui ne traite pas les arguments d’entrée et de sortie. Pour plus d’informations : [définir des arguments de processus](configure-actions.md#BKMK_DefineProcessArgs)  
  
<a name="create"></a>   
## <a name="create-an-action"></a>Créer une action  
  
> [!IMPORTANT]
>  Si vous créez une action à inclure dans le cadre d’une solution qui sera distribuée, créez-la dans le contexte de la solution. Accédez à **[paramètres](/powerapps/maker/model-driven-apps/advanced-navigation#settings)**  > **solutions** et recherchez la solution non gérée dont cette action fera partie. Puis, dans la barre de menus, sélectionnez **nouveau** > **processus**. Cela garantit que le préfixe de personnalisation associé au nom de l’action sera cohérent avec les autres composants de la solution. Après avoir créé l’action, vous ne pouvez pas modifier le préfixe.  
  
 Comme les processus de workflow, les actions ont les propriétés suivantes dans la boîte de dialogue **créer un processus** .  
  
 **Nom du processus**  
 Une fois que vous avez entré un nom pour le processus, un nom unique est créé pour celui-ci en supprimant les espaces ou les caractères spéciaux du nom du processus.  
  
 **Catégorie**  
 Cette propriété établit qu’il s’agit d’un processus d’action. Vous ne pouvez pas le modifier une fois que vous avez enregistré le processus.  
  
 **EDM**  
 Avec les processus d’actions, vous pouvez sélectionner une entité pour fournir le contexte du flux de travail, tout comme les autres types de processus, mais vous avez également la possibilité de choisir **aucun (Global)** . À utiliser si votre action ne nécessite pas le contexte d’une entité spécifique. Vous ne pouvez pas le modifier une fois que vous avez enregistré le processus.  
  
 **Entrer**  
 Utilisez cette propriété pour choisir si vous souhaitez générer une nouvelle action à partir de zéro ou démarrer à partir d’un modèle existant.  
  
<a name="edit"></a>   
## <a name="edit-an-action"></a>Modifier une action  
 Vous devez désactiver les processus avant de pouvoir les modifier.  
  
 Vous pouvez modifier une action qui a été créée dans le cadre d’une solution non gérée ou incluse dans une solution installée dans votre organisation. Si la solution est une solution gérée, vous ne pourrez peut-être pas la modifier. Le serveur de publication de solutions a la possibilité de modifier les propriétés gérées afin que l’action installée avec une solution gérée ne puisse pas être modifiée.  
  
 Lorsqu’une action est enregistrée, un nom unique est généré en fonction du nom du processus. Le préfixe de personnalisation est ajouté à ce nom unique à partir de l’éditeur de la solution. Il s’agit du nom du message qu’un développeur utilisera dans son code.  
  
 Lorsque vous modifiez une action, vous disposez des options suivantes :  
  
 **Nom du processus**  
 Une fois le processus créé et le nom unique généré à partir du nom du processus, vous pouvez modifier le nom du processus. Vous souhaiterez peut-être appliquer une convention d’affectation de noms pour faciliter la localisation de processus spécifiques.  
  
 **Nom unique**  
 Lorsqu’une action est enregistrée, un nom unique est généré en fonction du nom du processus. Ce nom unique a le préfixe de personnalisation de l’éditeur de solution ajouté. Il s’agit du nom du message qu’un développeur utilisera dans son code. Ne modifiez pas ce nom unique si le processus a été activé et si le code est en place, en attendant d’appeler l’action en utilisant ce nom.  
  
> [!IMPORTANT]
>  Une fois l’action activée et le code écrit pour utiliser un nom unique, le nom unique ne doit pas être modifié sans modifier également le code qui y fait référence.  
  
 **Activer la restauration**  
 En règle générale, les processus qui prennent en charge les transactions « annulent » (ou restaurent) l’intégralité de l’opération en cas d’échec d’une partie d’entre elles. Il existe quelques exceptions à cela. Certaines actions que les développeurs peuvent effectuer dans le code initié par l’action peuvent ne pas prendre en charge les transactions. Par exemple, si le code effectue des actions dans d’autres systèmes qui n’entrent pas dans le cadre de la transaction. Celles-ci ne peuvent pas être restaurées par l’action en cours d’exécution dans une application. Certains messages de la plateforme ne prennent pas en charge les transactions. Mais tout ce que vous pouvez faire avec l’interface utilisateur de l’action prend en charge les transactions. Toutes les actions qui font partie d’un flux de travail en temps réel sont prises en compte dans la transaction, mais avec des actions que vous avez l’option de refuser.  
  
 Vous devez consulter le développeur qui utilisera ce message pour déterminer s’il doit être dans la transaction. En règle générale, une action doit être dans la transaction si les actions effectuées par le processus d’entreprise n’ont aucun sens, sauf si toutes les opérations sont terminées avec succès. L’exemple classique consiste à transférer des fonds entre deux comptes bancaires. Si vous retirez des fonds d’un compte, vous devez les déposer dans l’autre. En cas d’échec de l’un ou l’autre, les deux doivent échouer.  
  
> [!NOTE]
>  Vous ne pouvez pas activer la restauration si une action personnalisée est appelée directement à partir d’un flux de travail. Vous pouvez activer la restauration si une action est déclenchée par un message de services Web PowerApps.  
  
 **Activer en tant que**  
 Comme tous les processus, vous pouvez activer le processus en tant que modèle et l’utiliser comme point de départ avancé pour les processus qui suivent un modèle similaire.  
  
 **Définir des arguments de processus**  
 Dans cette zone, vous spécifiez toutes les données que l’action attend de démarrer et les données qui seront transmises à l’action. Pour plus d’informations : [définir des arguments de processus](configure-actions.md#BKMK_DefineProcessArgs)  
  
 **Ajouter des étapes, des conditions et des actions**  
 Comme d’autres processus, vous spécifiez les actions à effectuer et le moment où les exécuter. Pour plus d’informations : [Ajouter des étapes, des conditions et des actions](configure-actions.md#BKMK_AddStagesConditionsAndActions)

<a name="BKMK_DefineProcessArgs"></a>   
### <a name="define-process-arguments"></a>Définir des arguments de processus  
 Lorsqu’un développeur utilise un message, il peut commencer par certaines données qu’il peut passer dans le message. Par exemple, pour créer un nouvel enregistrement de cas, il peut y avoir la valeur de nom de cas qui est transmise en tant qu’argument d’entrée.  
  
 Lorsque le message est terminé, le développeur peut avoir besoin de transmettre des données qui ont été modifiées ou générées par le message à une autre opération dans leur code. Ces données sont l’argument de sortie.  
  
 Les arguments d’entrée et de sortie doivent avoir un nom, un type et des informations indiquant si l’argument est toujours requis. Vous pouvez également fournir une description.  
  
 Le nom du message et les informations sur tous les arguments de processus représentent la « signature » du message. Une fois qu’une action est activée et qu’elle est utilisée dans le code, la signature ne doit pas changer. Si cette signature est modifiée, tout code qui utilise le message échoue. La seule exception à cela est la modification de l’un des paramètres afin qu’il ne soit pas toujours requis.  
  
 Vous pouvez modifier l’ordre des arguments en les triant ou en les déplaçant, car les arguments sont identifiés par nom, et non par ordre. En outre, la modification de la description n’interrompt pas le code à l’aide du message.  
  
#### <a name="action-process-argument-types"></a>Types d’arguments du processus d’action  
 Le tableau suivant décrit les types d’arguments du processus d’action.  
  
|Entrer|Descriptive|  
|----------|-----------------|  
|expression|Valeur `true` ou `false`.|  
|Date/heure|Valeur qui stocke les informations de date et d’heure.|  
|Sépar|Valeur numérique avec une précision décimale. Utilisé lorsque la précision est extrêmement importante.|  
|EDM|Enregistrement pour l’entité spécifiée. Lorsque vous sélectionnez entité, la liste déroulante est activée et vous permet de sélectionner le type d’entité.|  
|EntityCollection|Collection d’enregistrements d’entité.|  
|EntityReference|Objet qui contient le nom, l’ID et le type d’un enregistrement d’entité qui l’identifie de façon unique. Lorsque vous sélectionnez EntityReference, la liste déroulante est activée et vous permet de sélectionner le type d’entité.|  
|dissocié|Valeur numérique avec une précision décimale. Utilisé lorsque les données proviennent d’une mesure qui n’est pas absolument précise.|  
|entière|Nombre entier.|  
|paiement|Valeur qui stocke des données relatives à une somme d’argent.|  
|Liste déroulante|Valeur qui représente une option pour un attribut de l’option.|  
|chaîne|Valeur de texte.|  
  
> [!NOTE]
> Les valeurs d’argument **EntityCollection** ne peuvent pas être définies dans l’interface utilisateur pour les conditions ou les actions. Ils sont fournis pour être utilisés par les développeurs dans du code personnalisé. Plus d’informations : [créer vos propres actions](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-own-actions) 
  
<a name="BKMK_AddStagesConditionsAndActions"></a>   
### <a name="add-stages-and-steps"></a>Ajouter des étapes et des étapes  
 Les actions sont un type de processus très similaire aux flux de travail en temps réel. Toutes les étapes qui peuvent être utilisées dans les flux de travail en temps réel peuvent être utilisées dans les actions. Pour plus d’informations sur les étapes qui peuvent être utilisées pour les flux de travail et les actions en temps réel, consultez étapes [et étapes du flux de travail](configure-workflow-steps.md).  
  
 En plus des étapes qui peuvent être utilisées pour les flux de travail en temps réel, les actions ont également l’étape **attribuer une valeur** .  Dans les actions, elles ne peuvent être utilisées que pour définir des arguments de sortie. Vous pouvez utiliser l’Assistant formulaire pour définir des arguments de sortie à des valeurs spécifiques ou, plus vraisemblablement, aux valeurs de l’enregistrement sur lequel l’action est exécutée, aux enregistrements associés à cet enregistrement avec une relation plusieurs-à-un, aux enregistrements créés au cours d’une étape précédente ou aux valeurs qui font partie du processus lui-même.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Interventions](actions.md)  

 [Appeler des actions personnalisées à partir d’un flux de travail](invoke-custom-actions-workflow-dialog.md)   
 [Surveillance des flux de travail et des actions en temps réel](monitor-manage-processes.md#BKMK_MonitorSyncWorkflows)
 
 
