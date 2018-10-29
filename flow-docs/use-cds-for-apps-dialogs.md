---
title: Utiliser des dialogues CDS for Apps pour les processus guidés (déprécié) | Microsoft Docs
description: Les dialogues sont les processus synchrones ou interactifs qui collectent et traitent des informations à l’aide de scripts pas à pas pour diriger les utilisateurs dans un processus
ms.custom: ''
ms.date: 10/31/2017
ms.reviewer: ''
ms.topic: article
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
ms.openlocfilehash: f8b2e87bdb9aed63e9f180d446349779cd37c25c
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689660"
---
# <a name="use-cds-for-apps-dialogs-for-guided-processes-deprecated"></a>Utiliser des dialogues CDS for Apps pour les processus guidés (déprécié)

[Les dialogues sont dépréciés](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming#dialogs-are-deprecated). Vous devez remplacer les dialogues par des flux de processus métier ou des applications de canevas. Pour plus d’informations, consultez [Remplacer les dialogues par des flux de processus métier ou des applications de canevas](replace-dialogs.md). 

Les dialogues sont les processus synchrones ou interactifs dans Common Data Service (CDS) for Apps qui collectent et traitent des informations à l’aide de scripts pas à pas pour diriger les utilisateurs dans un processus Par exemple, vous pouvez créer des dialogues destinés à guider vos conseillers du service clientèle dans la résolution et le signalement d’incidents. De même, vous pouvez créer des dialogues pour standardiser les processus de vente tels que la qualification d’opportunité et la notation des prospects. Pour plus d’informations, consultez [Utiliser des dialogues pour les processus guidés](/dynamics365/customer-engagement/developer/use-dialogs-guided-processes) dans le Guide du développeur Dynamics 365 for Customer Engagement.

## <a name="differences-between-workflows-and-dialogs"></a>Différences entre workflows et dialogues

Le tableau suivant compare les dialogues et les workflows CDS for Apps.  


| Workflows     |    Dialogues      |
|---------------|--------------|
|                                                                                                  Peuvent être démarrés par un utilisateur ou automatisés.                                                                                                   |                                                                                          Doivent être démarrés par un utilisateur.                                                                                          |
|                                  Sont des processus asynchrones ou en temps réel et ne requièrent pas d’entrée utilisateur pour s’exécuter de bout en bout. Les processus asynchrones sont exécutés en arrière-plan, tandis que les processus en temps réel sont exécutés immédiatement.                                   | Sont des processus en temps réel qui requièrent une entrée utilisateur pour s’exécuter de bout en bout. Quand vous exécutez ces processus, une interface de type Assistant vous est présentée afin que vous puissiez effectuer les sélections appropriées à cette fin. |
|                                                    L’entité qui stocke les détails sur un workflow asynchrone en cours d’exécution est `AsyncOperation`, tandis que `Process` est utilisé pour un workflow en temps réel.                                                     |                                                       L’entité qui stocke les informations générées par un dialogue en cours d’exécution est l’entité `ProcessSession`.                                                       |
|                  Les déclencheurs sont pris en charge pour les workflows. Pour obtenir la liste des déclencheurs pris en charge, consultez [Types, déclencheurs et entités pris en charge pour les processus](/dynamics365/customer-engagement/developer/supported-types-triggers-entities-actions-processes).                   |                                                                                   Les déclencheurs ne sont pas pris en charge pour les dialogues.                                                                                    |
  
### <a name="see-also"></a>Voir aussi
[Remplacer les dialogues par des flux de processus métier ou des applications de canevas](replace-dialogs.md)