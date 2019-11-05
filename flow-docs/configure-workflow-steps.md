---
title: Configurer des étapes et des étapes de flux de travail dans PowerApps | MicrosoftDocs
description: En savoir plus sur la configuration des étapes de flux de travail
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
author: Mattp123
ms.assetid: 0b47dfd5-76db-464f-90c0-c64a0173dcdd
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 4239e939f9522b4b3a22e56dfc69275482b017a7
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547072"
---
# <a name="configure-workflow-stages-and-steps"></a>Configurer des étapes et des étapes de flux de travail
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Lorsque vous concevez des flux de travail, vous avez la possibilité de contenir la logique que vous souhaitez exécuter en étapes et en étapes.  
  
 **Étapes**  
 Les étapes rendent la logique du workflow plus facile à lire et expliquent la logique du flux de travail. Toutefois, les étapes n’affectent pas la logique ou le comportement des workflows. Si un processus a des étapes, toutes les étapes du processus doivent être contenues dans une étape.  
  
 **Étapes**  
 Les étapes sont une unité de logique métier au sein d’un flux de travail. Les étapes peuvent inclure des conditions, des actions, d’autres étapes ou une combinaison de ces éléments.  
  
<a name="BKMK_ActionsWorkflowProcessesCanPerform"></a>  
 
## <a name="actions-that-workflow-processes-can-perform"></a>Actions que les processus de flux de travail peuvent effectuer  

 Les processus de workflow peuvent effectuer les actions indiquées dans le tableau suivant.  
  
|Transactionnel|Descriptive|  
|------------|-----------------|  
|**Créer un enregistrement**|Crée un nouvel enregistrement pour une entité et assigne des valeurs que vous choisissez aux attributs.|  
|**Mettre à jour l’enregistrement**|Vous pouvez mettre à jour l’enregistrement sur lequel le workflow s’exécute, l’un des enregistrements liés à cet enregistrement dans une relation N :1 ou tout enregistrement créé par les étapes précédentes.|  
|**Attribuer un enregistrement**|Vous pouvez affecter l’enregistrement sur lequel le workflow s’exécute, l’un des enregistrements liés à cet enregistrement avec une relation N :1 ou tout enregistrement créé par les étapes précédentes.|  
|**Envoyer un E-mail**|Envoie un e-mail. Vous pouvez choisir de créer un nouveau message électronique ou d’utiliser un modèle de message électronique configuré pour l’entité de l’enregistrement sur lequel le workflow s’exécute, ou pour toutes les entités qui ont une relation N :1 avec l’entité, ou l’entité pour tous les enregistrements créés par des étapes précédentes.|  
|**Démarrer le flux de travail enfant**|Démarre un processus de flux de travail qui a été configuré en tant que Workflow enfant.|  
|**Modifier l’État**|Modifie l’état de l’enregistrement sur lequel le processus s’exécute, les enregistrements liés à cet enregistrement avec une relation N :1 ou les enregistrements créés par les étapes précédentes.|  
|**Arrêter le flux de travail**|Arrête le flux de travail actuel. Vous pouvez définir un état de **réussite** ou d' **annulation** et spécifier un message d’État.<br /><br /> Lorsque les flux de travail en temps réel sont configurés pour un événement, l’arrêt d’un workflow dont l’État est annulé empêchera l’exécution de l’action de l’événement. Pour plus d’informations, consultez [utilisation des flux de travail en temps réel](configure-workflow-steps.md#BKMK_SynchronousWorkflows) .|  
|**Étape personnalisée**|Les développeurs peuvent créer des étapes de flux de travail personnalisées qui définissent des actions. Aucune étape personnalisée n’est disponible par défaut.|  
  
### <a name="setting-record-values"></a>Définition des valeurs d’enregistrement  

 Lorsque vous créez un enregistrement, vous pouvez définir des valeurs pour l’enregistrement. Lorsque vous mettez à jour un enregistrement, vous pouvez définir, ajouter, incrémenter, décrémenter, multiplier ou effacer des valeurs.  
  
 Lorsque vous sélectionnez **définir les propriétés**, une boîte de dialogue s’ouvre et affiche le formulaire par défaut de l’entité.  
  
 En bas de la boîte de dialogue, vous pouvez voir une liste de champs supplémentaires absents du formulaire.  
  
 Pour n’importe quel champ, vous pouvez définir une valeur statique et celle-ci sera définie par le flux de travail.  
  
 Sur le côté droit de la boîte de dialogue, l' **Assistant formulaire** vous donne la possibilité de définir ou d’ajouter des valeurs dynamiques à partir du contexte de l’enregistrement actif. Cela comprend les valeurs des enregistrements connexes qui sont accessibles à partir des relations N :1 (plusieurs-à-un) pour l’entité.  
  
 Les options disponibles dans l' **Assistant formulaire** dépendent du champ que vous avez sélectionné dans le formulaire. Lorsque vous définissez une valeur dynamique, vous verrez un espace réservé jaune appelé « Slug » qui indique où les données dynamiques seront incluses. Si vous souhaitez supprimer la valeur, sélectionnez simplement la ligne-bloc et supprimez-la. Pour les champs de texte, vous pouvez utiliser une combinaison de données statiques et dynamiques.  
  
 Avec les valeurs dynamiques, vous ne savez pas si un champ ou une entité associée possède la valeur que vous souhaitez définir. Vous pouvez en fait définir un certain nombre de champs pour essayer de définir la valeur et les trier dans l’ordre à l’aide des flèches vertes. Si le premier champ n’a pas de données, le deuxième champ sera essayé, et ainsi de suite. Si aucun des champs ne contient de données, vous pouvez spécifier une valeur par défaut à utiliser.  
  
<a name="BKMK_SettingConditionsForWorkflowActions"></a>   

## <a name="setting-conditions-for-workflow-actions"></a>Définition de conditions pour les actions de flux de travail  

 Les actions que vous allez appliquer dépendent souvent des conditions. Les processus de workflow offrent plusieurs moyens de définir des conditions et de créer une logique de branchement pour obtenir les résultats souhaités. Vous pouvez vérifier les valeurs de l’enregistrement sur lequel s’exécute le processus de workflow, les enregistrements liés à cet enregistrement avec une relation N :1 ou les valeurs dans le processus lui-même.  
  
|Type de condition|Descriptive|  
|--------------------|-----------------|  
|**Vérifier la condition**|Instruction « if-\<> » logique.<br /><br /> Vous pouvez vérifier les valeurs actuelles de l’enregistrement sur lequel le workflow s’exécute, de l’un des enregistrements liés à cet enregistrement dans une relation N :1 ou de tout enregistrement créé par les étapes précédentes. En fonction de ces valeurs, vous pouvez définir des étapes supplémentaires lorsque la condition a la valeur true.<br /><br /> Dans l’instruction « if-\<> Then », vous pouvez utiliser les opérateurs suivants : **est égal**à, **n’est pas égal**à, **contient des données**, **ne contient pas de données**, **sous** et **non sous**. **Remarque :**  Le **sous** et **non sous** sont des opérateurs hiérarchiques. Elles ne peuvent être utilisées que sur les entités qui ont une relation hiérarchique définie. Si vous essayez d’utiliser ces opérateurs sur les entités qui n’ont pas de relation hiérarchique définie, le message d’erreur suivant s’affiche : «vous utilisez un opérateur hiérarchique sur une entité qui n’a pas de relation hiérarchique définie. Créez l’entité hiérarchique (en marquant une relation comme hiérarchique) ou utilisez un opérateur différent.» Pour plus d’informations sur les relations hiérarchiques, consultez [définir et interroger des données hiérarchiquement associées](/powerapps/maker/common-data-service/define-query-hierarchical-data). Une capture d’écran qui suit le tableau est un exemple de la définition du processus de workflow qui utilise le **sous** et **non sous** les opérateurs hiérarchiques.|  
|**Branche conditionnelle**|Une instruction « Else-If-Then » logique, l’éditeur utilise le texte « sinon, si \<condition > Then : »<br /><br /> Sélectionnez une condition de vérification que vous avez définie précédemment et vous pouvez ajouter une branche conditionnelle pour définir des étapes supplémentaires lorsque la condition de vérification retourne la valeur false.|  
|**Action par défaut**|Instruction « Else » logique. l’éditeur utilise le texte « sinon : »<br /><br /> Sélectionnez une condition de vérification, une branche conditionnelle, une condition d’attente ou une branche d’attente parallèle que vous avez définie précédemment et vous pouvez utiliser une action par défaut pour définir les étapes de tous les cas qui ne correspondent pas aux critères définis dans les éléments de condition ou de branche.|  
|**Condition d’attente**|Permet à un flux de travail en arrière-plan de s’interrompre jusqu’à ce que les critères définis par la condition soient satisfaits. Le flux de travail démarre automatiquement à nouveau lorsque les critères de la condition d’attente sont satisfaits.<br /><br /> Les workflows en temps réel ne peuvent pas utiliser les conditions d’attente.|  
|**Branche d’attente parallèle**|Définit une condition d’attente alternative pour un flux de travail en arrière-plan avec un ensemble d’étapes supplémentaires correspondantes qui sont exécutées uniquement lorsque le critère initial est respecté. Vous pouvez utiliser des branches d’attente parallèles pour créer des limites de temps dans votre logique de Workflow. Elles permettent d’empêcher le workflow d’attendre indéfiniment jusqu’à ce que les critères définis dans une condition d’attente soient satisfaits.|  
|**Étape personnalisée**|Les développeurs peuvent créer des étapes de flux de travail personnalisées qui définissent des conditions. Aucune étape personnalisée n’est disponible par défaut.|  
  
 La capture d’écran suivante contient un exemple de définition de processus de flux de travail avec le **sous** et **non sous** les opérateurs hiérarchiques. Dans notre exemple, nous appliquons deux remises différentes à deux groupes de comptes. Dans **Ajouter une étape**, nous avons sélectionné la **condition de vérification** pour spécifier la condition **Si** , qui contient les opérateurs **sous** ou **non sous** . La première condition **si-Then** s’applique à tous les comptes qui se trouvent **sous** le compte Alpine Ski House. Ces comptes bénéficient d’une remise de 10% sur les bons et les services achetés. La seconde condition **If-Then** s’applique à tous les comptes qui **ne sont pas sous** le compte Alpine Ski House et qui bénéficient d’une remise de 5%. Ensuite, nous avons sélectionné **mettre à jour l’enregistrement** pour définir l’action à effectuer en fonction de la condition.  
  
 ![Processus de workflow avec&#47;sous-opérateurs non sous](media/wfp-under-not-under.PNG "Processus de workflow avec les opérateurs sous/non sous")  
  
<a name="BKMK_SynchronousWorkflows"></a>   

## <a name="using-real-time-workflows"></a>Utilisation des flux de travail en temps réel  

 Vous pouvez configurer des flux de travail en temps réel, mais vous devez les utiliser avec précaution. Les flux de travail en arrière-plan sont généralement recommandés, car ils permettent au système de les appliquer à mesure que des ressources sur le serveur sont disponibles. Cela permet de lisser le travail que le serveur doit effectuer et de maintenir des performances optimales pour tous les utilisateurs du système. L’inconvénient est que les actions définies par les flux de travail en arrière-plan ne sont pas immédiates. Vous ne pouvez pas prédire à quel moment ils seront appliqués, mais cela prend généralement quelques minutes. Pour une plus grande automatisation des processus d’entreprise, cela est parfait, car les personnes qui utilisent le système n’ont pas besoin d’être axents que le processus est en cours d’exécution.  
  
 Utilisez des flux de travail en temps réel lorsqu’un processus d’entreprise demande à un utilisateur de voir immédiatement les résultats du processus ou si vous souhaitez pouvoir annuler une opération. Par exemple, vous souhaiterez peut-être définir certaines valeurs par défaut pour un enregistrement la première fois qu’il est enregistré, ou vous voulez vous assurer que certains enregistrements ne sont pas supprimés.  
  
### <a name="converting-between-real-time-and-background-workflows"></a>Conversion entre les flux de travail en temps réel et en arrière-plan  

 Vous pouvez modifier un flux de travail en temps réel dans un flux de travail en arrière-plan en choisissant **convertir en flux de travail en arrière-plan** dans la barre d’outils.  
  
 Vous pouvez modifier un flux de travail en arrière-plan en flux de travail en temps réel en choisissant **convertir en flux de travail en temps réel** dans la barre d’outils. Si le flux de travail en arrière-plan utilise des conditions d’attente, il devient non valide et vous ne pouvez pas l’activer tant que vous n’avez pas supprimé la condition d’attente.  
  
### <a name="initiating-real-time-workflows-before-or-after-status-changes"></a>Lancement de flux de travail en temps réel avant ou après les modifications d’État  

 Quand vous configurez **des options pour les processus automatiques** pour les flux de travail en temps réel, l’événement **Démarrer quand** les options de l’État changes vous permet de sélectionner **après** ou **avant** les modifications de l’État. L’option par défaut est **après**.  
  
 Lorsque vous sélectionnez **avant** d’indiquer que vous souhaitez que la logique du flux de travail soit appliquée avant l’enregistrement des données de modification de l’État. Cela vous permet de vérifier les valeurs avant l’application d’une autre logique après l’opération et d’empêcher l’exécution d’une logique supplémentaire. Par exemple, vous pouvez avoir une logique supplémentaire dans un plug-in ou une action de flux de travail personnalisé qui peut lancer des actions sur un autre système. En arrêtant le traitement, vous pouvez éviter les cas où des systèmes externes sont affectés. L’application de flux de travail en temps réel avant cet événement signifie également que les autres actions de flux de travail ou de plug-in qui peuvent avoir enregistré des données n’ont pas besoin d’être « restaurées » lorsque l’opération est annulée.  
  
### <a name="using-the-stop-workflow-action-with-real-time-workflows"></a>Utilisation de l’action arrêter le flux de travail avec des flux de travail en temps réel  

 Lorsque vous appliquez une action **arrêter le workflow** dans un flux de travail, vous avez la possibilité de spécifier une condition d’État qui peut être **réussie** ou **annulée**. Lorsque vous définissez l’État sur annulé, vous empêchez l’opération. Un message d’erreur contenant le texte du message d’état de l’action d’arrêt s’affiche pour l’utilisateur avec l’en-tête **Erreur du processus d’entreprise**.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Créer une logique métier personnalisée avec des processus](guide-staff-through-common-tasks-processes.md)   
 [Vue d’ensemble des processus de flux de travail](workflow-processes.md)   
 [Surveiller et gérer les processus de flux de travail](monitor-manage-processes.md)   
 [Meilleures pratiques pour les processus de flux de travail](best-practices-workflow-processes.md)
