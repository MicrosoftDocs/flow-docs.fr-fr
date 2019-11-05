---
title: Utiliser des boîtes de dialogue Common Data Service pour les processus guidés (déconseillé) | MicrosoftDocs
description: Les boîtes de dialogue sont les processus interactifs ou synchrones qui collectent et traitent les informations en utilisant des scripts pas à pas pour diriger les utilisateurs via un processus
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
ms.service: flow
ms.assetid: d17f8ae2-854b-4f67-a115-5a03d4f0b8ce
caps.latest.revision: 25
author: msftman
ms.author: deonhe
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 05f0b9b72f2f9e2d7f02356ec40eeb520214a0cb
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73548741"
---
# <a name="use-common-data-service-dialogs-for-guided-processes-deprecated"></a>Utiliser des boîtes de dialogue Common Data Service pour les processus guidés (déconseillé)
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

[Les boîtes de dialogue sont dépréciées](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Vous devez remplacer les dialogues par des flux de processus d’entreprise ou des applications de canevas. Pour plus d’informations : [remplacer des boîtes de dialogue par des flux de processus d’entreprise ou des applications de canevas](replace-dialogs.md) 

Les boîtes de dialogue sont les processus interactifs ou synchrones dans Common Data Service qui collectent et traitent des informations en utilisant des scripts pas à pas pour diriger les utilisateurs via un processus. Par exemple, vous pouvez créer des boîtes de dialogue qui serviront de guide à vos représentants de service pour la résolution de cas et la remontée de cas. De même, vous pouvez créer des boîtes de dialogue pour standardiser les processus de vente, telles que la qualification des opportunités et le score des prospects.

## <a name="differences-between-workflows-and-dialogs"></a>Différences entre les workflows et les boîtes de dialogue

Le tableau suivant fournit des informations sur les différences entre Common Data Service flux de travail et les boîtes de dialogue.  


| Workflows     |    Boîtes      |
|---------------|--------------|
|                                                                                                  Peut être démarré par un utilisateur ou être automatisé.                                                                                                   |                                                                                          Doit être démarré par un utilisateur.                                                                                          |
|                                  Sont des processus asynchrones ou en temps réel, et ne nécessitent pas l’exécution de l’entrée utilisateur jusqu’à la fin. Les processus asynchrones s’exécutent en arrière-plan pendant que les processus en temps réel s’exécutent immédiatement.                                   | Sont des processus en temps réel qui nécessitent une entrée d’utilisateur pour s’exécuter jusqu’à leur achèvement. Lorsque vous exécutez ces processus, une interface de type assistant vous est présentée afin que vous puissiez effectuer les sélections appropriées pour exécuter les processus. |
|                                                    L’entité qui stocke les détails relatifs à un flux de travail asynchrone en cours d’exécution est `AsyncOperation` lorsqu’un `Process` est utilisé pour un workflow en temps réel.                                                     |                                                       L’entité qui stocke les informations générées par une boîte de dialogue en cours d’exécution est l’entité `ProcessSession`.                                                       |
|                  Les déclencheurs sont pris en charge pour les flux de travail. Pour obtenir la liste des déclencheurs pris en charge, consultez [types pris en charge, déclencheurs et entités pour les processus](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Les déclencheurs ne sont pas pris en charge pour les boîtes de dialogue.                                                                                    |
  
### <a name="see-also"></a>Voir aussi
[Remplacer des boîtes de dialogue par des flux de processus d’entreprise ou des applications de canevas](replace-dialogs.md)
