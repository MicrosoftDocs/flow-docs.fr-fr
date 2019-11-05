---
title: Créer une logique métier personnalisée via des processus avec PowerApps | MicrosoftDocs
description: En savoir plus sur les différents types de logique métier que vous pouvez utiliser dans votre application
ms.custom: ''
ms.date: 05/01/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: b3072cc5897b8a2ef5a2a92ec3a07a0e31b57898
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73545321"
---
# <a name="create-custom-business-logic-through-processes"></a>Créer une logique métier personnalisée via des processus
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

La définition et l’application de processus d’entreprise cohérents constituent l’une des principales raisons pour lesquelles les utilisateurs utilisent des applications basées sur des modèles. Des processus cohérents permettent de s’assurer que les personnes qui utilisent le système peuvent se concentrer sur leur travail et non sur la mémorisation pour effectuer un ensemble d’étapes manuelles. Les processus peuvent être simples ou complexes et peuvent changer au fil du temps.  
  
PowerApps comprend plusieurs types de processus, chacun conçu pour un objectif différent :  
  
-   Flux de processus d’entreprise  
  
-   Flux de tâches mobiles  
  
-   Workflows  
  
-   Interventions  
  
 Comme pour les processus, vous pouvez également créer des règles d’entreprise et des recommandations. Pour plus d’informations, consultez [créer des règles d’entreprise et des recommandations pour appliquer une logique dans un formulaire](/powerapps/maker/model-driven-apps/create-business-rules-recommendations-apply-logic-form)  

> [!NOTE]
>  L’utilisation de processus peut avoir un impact sur les conditions de licence pour les PowerApps et les flux. Pour plus d’informations, consultez [conditions de licence d’entité](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-entity-licenses). 


<a name="BKMK_BP"></a>   
## <a name="when-to-use-business-process-flows"></a>Quand utiliser des flux de processus d’entreprise  
 Utilisez un workflow de processus d’entreprise lorsque vous souhaitez que le personnel passe par les mêmes étapes et suivez les mêmes étapes pour interagir avec un client. Par exemple, utilisez un workflow de processus d’entreprise si vous souhaitez que tout le monde gère les demandes de service client de la même manière, ou pour demander au personnel d’obtenir l’approbation d’une facture avant de soumettre une commande.  
  
 Votre environnement comprend plusieurs flux de processus d’entreprise prêts à l’emploi pour des tâches de vente, de service et de marketing courantes que vous pouvez utiliser avec peu ou pas de modifications requises. Ou vous pouvez créer les vôtres. Pour plus d’informations sur les flux de processus d’entreprise, consultez la rubrique suivante :  
  
-   [Créer un workflow de processus d’entreprise](create-business-process-flow.md)  
  
<a name="BKMK_WF"></a>   
## <a name="when-to-use-workflows"></a>Quand utiliser des flux de travail  
 Utilisez les flux de travail pour automatiser les processus d’entreprise en arrière-plan. Les workflows sont généralement initiés par des événements système, de sorte que l’utilisateur n’a pas besoin de savoir qu’ils sont en cours d’exécution. Les flux de travail qui fonctionnent en arrière-plan sont « asynchrones ». Les flux de travail peuvent également être configurés pour que les utilisateurs puissent les initier manuellement. Lorsque vous souhaitez automatiser des tâches courantes, telles que l’envoi automatique d’un e-mail de confirmation à un client lors de la livraison d’une commande. Les flux de travail qui fonctionnent en temps réel sont « synchrones ». Pour plus d’informations sur les workflows, consultez [processus de workflow](workflow-processes.md) .  

<a name="BKMK_Actions"></a>   
## <a name="when-to-use-actions"></a>Quand utiliser des actions  
 Utilisez des actions lorsque vous souhaitez automatiser une série de commandes dans le système. Les actions développent le vocabulaire disponible pour permettre aux développeurs d’exprimer les processus d’entreprise. Avec les verbes de base tels que créer, mettre à jour, supprimer et assigner fournis par le système, une action utilise ces verbes principaux pour créer des verbes plus expressifs, tels que approuver, remonter, acheminer ou planifier. Si la définition d’un processus d’entreprise change, une personne qui n’est pas développeur peut modifier l’action, de sorte que le code n’a pas besoin d’être modifié.  Pour plus d’informations sur les actions, consultez [actions](create-actions.md) .  
  
<a name="useMSFlow"></a>   
## <a name="when-to-use-microsoft-flow"></a>Quand utiliser Microsoft Flow  
 Utilisez Microsoft Flow lorsque vous devez créer des flux de travail automatisés qui effectuent des actions entre votre environnement et votre application ou service favori, tels que Dynamics 365, Twitter, Dropbox, Google services, Office 365 et SharePoint. Vous pouvez déclencher un Flow en fonction d’une action spécifique ou appeler à partir de votre application. Pour plus d’informations, [consultez Microsoft Flow pour automatiser les processus entre les services](https://docs.microsoft.com/dynamics365/customer-engagement/basics/use-flow-automate-processes-across-services
) .  
  
<a name="BKMK_Where"></a>   
## <a name="where-do-i-go-to-create-processes"></a>Où puis-je créer des processus ?  
 Il existe deux chemins d’accès pour accéder aux processus :  
  
- Ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) et accédez à **composants > processus.** Ce chemin d’accès facilite l’accès lorsque vous effectuez d’autres tâches de personnalisation dans les outils de personnalisation.  

- **Les [paramètres](/powerapps/maker/model-driven-apps/advanced-navigation#settings) > les processus.** Ce chemin d’accès vous permet d’utiliser des vues définies pour l’entité processus, y compris des vues personnalisées.  
  
 Des flux de processus d’entreprise individuels peuvent également être modifiés à l’aide du bouton **modifier le processus** de la barre de commandes du formulaire dans lequel le flux de processus d’entreprise est actif.  
  
<a name="BKMK_WhoCreate"></a>   
## <a name="who-can-create-processes"></a>Qui peut créer des processus ?  
 Seules les personnes ayant le rôle de sécurité administrateur système, Personnalisateur de système ou PDG-Business Manager peuvent créer des processus qui s’appliquent à l’ensemble de l’environnement. Les personnes avec d’autres rôles peuvent créer des processus avec un niveau d’accès limité. Par exemple, les personnes ayant le niveau d’accès utilisateur peuvent créer des flux de travail pour leur propre utilisation avec les enregistrements dont ils sont propriétaires.  
  
 Le tableau suivant indique le niveau d’accès des processus en fonction des rôles de sécurité par défaut.  
  
|||  
|-|-|  
|**Rôle de sécurité**|**Niveau d’accès**|  
|PDG-directeur commercial|Dernière|  
|Administrateur système|Dernière|  
|Personnalisateur système|Dernière|  
|Vice-président marketing|Parent : divisions enfants|  
|Vice-Président des ventes|Parent : divisions enfants|  
|Service Manager|Division|  
|Directeur marketing|Division|  
|Responsable des ventes|Division|  
|Gestionnaire de planification|Division|  
|Représentant du service clientèle|Utilisateur|  
|Professionnel du marketing|Utilisateur|  
|Equipe|Utilisateur|  
|Planificateur|Utilisateur|  
  
> [!NOTE]
>  Bien que les utilisateurs puissent créer un flux de processus d’entreprise, un flux de travail en temps réel ou des processus d’action, ils doivent disposer des privilèges **activer les flux de processus d’entreprise** ou activer les **processus en temps réel** pour les activer.  
  
<a name="BKMK_WhatCanProcessesDo"></a>   
## <a name="more-about-workflows-and-actions"></a>En savoir plus sur les flux de travail et les actions  
 Les processus peuvent vérifier des conditions, appliquer une logique de branchement et effectuer des actions. Elles effectuent ces actions dans une série d’étapes. Le tableau suivant décrit les étapes disponibles dans les processus de flux de travail et d’action. Pour plus d’informations, consultez les rubriques pour chaque type de processus.  
  
|Première|Type de processus|Descriptive|  
|----------|------------------|-----------------|  
|**Mode**|Workflow, action|Les étapes rendent la logique du workflow plus facile à lire et expliquent la logique du flux de travail. Toutefois, les étapes n’affectent pas la logique ou le comportement des workflows. Si un processus a des étapes, toutes les étapes du processus doivent être contenues dans une étape.|  
|**Vérifier la condition**|Workflow, action|Instruction « if-\<> » logique.<br /><br /> Vous pouvez vérifier les valeurs de l’enregistrement sur lequel le workflow s’exécute, les enregistrements liés à cet enregistrement dans une relation N :1 ou tous les enregistrements créés par les étapes précédentes. En fonction de ces valeurs, vous pouvez définir des étapes supplémentaires lorsque la condition est `true`.|  
|**Branche conditionnelle**|Workflow, action|Une instruction « Else-If-Then » logique, l’éditeur utilise le texte « sinon, si \<condition > Then : »<br /><br /> Sélectionnez une condition de vérification que vous avez définie précédemment et vous pouvez ajouter une branche conditionnelle pour définir des étapes supplémentaires lorsque la condition de vérification retourne `false`.|  
|**Action par défaut**|Workflow, action|Instruction « Else » logique. l’éditeur utilise le texte « sinon : »<br /><br /> Sélectionnez une condition de vérification, une branche conditionnelle, une condition d’attente ou une branche d’attente parallèle que vous avez définie précédemment et vous pouvez utiliser une action par défaut pour définir les étapes de tous les cas qui ne correspondent pas aux critères définis dans les éléments de condition ou de branche.|  
|**Condition d’attente**|Flux de travail en arrière-plan uniquement|Permet à un flux de travail en arrière-plan de s’interrompre jusqu’à ce que les critères définis par la condition soient satisfaits. Le flux de travail démarre automatiquement à nouveau lorsque les critères de la condition d’attente sont satisfaits.|  
|**Branche d’attente parallèle**|Flux de travail en arrière-plan uniquement|Définit une condition d’attente alternative pour un flux de travail en arrière-plan avec un ensemble d’étapes supplémentaires correspondantes qui sont exécutées uniquement lorsque le critère initial est respecté. Vous pouvez utiliser des branches d’attente parallèles pour créer des limites de temps dans votre logique de Workflow. Elles permettent d’empêcher le workflow d’attendre indéfiniment jusqu’à ce que les critères définis dans une condition d’attente soient satisfaits.|  
|**Affecter une valeur**|Transactionnel|Affecte une valeur à une variable ou à un paramètre de sortie dans le processus.|  
|**Créer un enregistrement**|Workflow, action|Crée un nouvel enregistrement pour une entité et assigne des valeurs aux attributs.|  
|**Mettre à jour l’enregistrement**|Workflow, action|Vous pouvez mettre à jour l’enregistrement sur lequel le workflow s’exécute, l’un des enregistrements liés à cet enregistrement dans une relation N :1 ou tous les enregistrements créés par des étapes précédentes.|  
|**Attribuer un enregistrement**|Workflow, action|Vous pouvez affecter l’enregistrement sur lequel le workflow s’exécute, l’un des enregistrements liés à cet enregistrement avec une relation N :1 ou tout enregistrement créé par les étapes précédentes.|  
|**Envoyer un E-mail**|Workflow, action|Envoie un e-mail. Vous pouvez choisir de créer un nouveau message électronique ou d’utiliser un modèle de message électronique configuré pour l’entité de l’enregistrement sur lequel le workflow s’exécute, ou pour toutes les entités qui ont une relation N :1 avec l’entité, ou l’entité pour tous les enregistrements créés par des étapes précédentes.|  
|**Démarrer le flux de travail enfant**|Workflow, action|Démarre un processus de flux de travail qui a été configuré en tant que Workflow enfant.|  
|**Modifier l’État**|Workflow, action|Modifie l’état de l’enregistrement sur lequel le processus s’exécute, les enregistrements liés à cet enregistrement avec une relation N :1 ou les enregistrements créés par les étapes précédentes.|  
|**Arrêter le flux de travail**|Workflow, action|Arrête le flux de travail ou l’action en cours. Vous pouvez définir un état de **réussite** ou d' **annulation** et spécifier un message d’État.|  
|**Étape personnalisée**|Workflow, action|Fournit des extensions aux éléments logiques disponibles par défaut. Les étapes peuvent inclure des conditions, des actions, d’autres étapes ou une combinaison de ces éléments. Les développeurs peuvent créer des étapes de flux de travail personnalisées. Par défaut, aucune étape personnalisée n’est disponible.|

  

