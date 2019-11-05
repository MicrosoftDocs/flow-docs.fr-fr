---
title: Utiliser des actions | MicrosoftDocs
description: Avec les actions, vous pouvez effectuer des opérations, telles que créer, mettre à jour, supprimer, assigner ou exécuter une action. En interne, une action crée un message personnalisé
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
author: MSFTMAN
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: DEONHE
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: eb4fa4040611241dd2bd81706736738ad6774d38
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73544607"
---
# <a name="use-actions"></a>Utiliser des actions
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Les actions ouvrent une gamme de possibilités de composition de la logique métier. Avec les actions, vous pouvez effectuer des opérations, telles que créer, mettre à jour, supprimer, assigner ou exécuter une action. En interne, une action crée un message personnalisé. Les développeurs font référence à ces actions comme « messages ». Chacun de ces messages est basé sur des actions effectuées sur un enregistrement d’entité. Si l’objectif d’un processus est de créer un enregistrement, puis de le mettre à jour, puis de l’attribuer, il existe trois étapes distinctes. Chaque étape est définie par les fonctionnalités de l’entité, pas nécessairement par votre processus d’entreprise.  
  
Les actions permettent de définir un seul verbe (ou message) qui correspond à une opération que vous devez effectuer pour votre entreprise. Ces nouveaux messages sont contrôlés par un processus ou un comportement plutôt que par ce qui peut être fait avec une entité. Ces messages peuvent correspondre à des verbes tels que les escalades, les conversions, les planifications, les itinéraires ou les approbations, tout ce dont vous avez besoin. L’ajout de ces verbes vous permet de fournir un vocabulaire plus riche pour vous permettre de définir de façon Fluent vos processus d’entreprise. Vous pouvez appliquer ce vocabulaire plus riche à partir des clients ou des intégrations au lieu d’avoir à écrire l’action dans les clients. Cela facilite également la tâche, car vous pouvez gérer et enregistrer la réussite ou l’échec de l’action entière en tant qu’unité unique.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Messages configurables  
 Une fois qu’une action est définie et activée, un développeur peut utiliser ce message comme l’un des autres messages fournis par la plateforme. Toutefois, une différence significative est que, à présent, une personne qui n’est pas développeur peut appliquer des modifications à ce qui doit être fait quand ce message est utilisé. Vous pouvez configurer l’action pour modifier les étapes à mesure que vos processus d’entreprise changent. Tout code personnalisé qui utilise ce message n’a pas besoin d’être modifié tant que les arguments du processus ne changent pas.  
  
 Les processus de workflow et les plug-ins continuent à fournir des fonctionnalités similaires pour la définition de l’automatisation. Les processus de workflow offrent toujours la possibilité pour un non-développeur d’appliquer des modifications. Mais la différence réside dans la façon dont les processus d’entreprise sont composés et comment un développeur peut écrire son code. Une action est un message qui fonctionne au même niveau que l’un des messages fournis par la plateforme. Les développeurs peuvent inscrire des plug-ins pour les actions.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Messages globaux 
 
 Contrairement à Common Data Service flux de travail ou aux [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in), une action n’a pas besoin d’être associée à une entité spécifique. Vous pouvez définir des actions « globales » qui peuvent être appelées de manière autonome.

## <a name="next-steps"></a>Étapes suivantes

[Créer une action personnalisée](create-actions.md)  
  

