---
title: Utiliser des actions | Microsoft Docs
description: Avec des actions, vous pouvez effectuer des opérations, telles que Créer, Mettre à jour, Supprimer, Assigner ou Effectuer une action. En interne, une action crée un message personnalisé
ms.custom: ''
ms.date: 08/07/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1475985f-d3c4-429d-beac-cb455965e792
caps.latest.revision: 20
ms.author: matp
manager: kvivek
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: cf5c0e488f1d01c514f509b9d2a8afae265cf487
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64455931"
---
# <a name="use-actions"></a>Utiliser des actions

Les actions ouvrent un éventail de possibilités pour la composition de la logique métier. Avec des actions, vous pouvez effectuer des opérations, telles que Créer, Mettre à jour, Supprimer, Assigner ou Effectuer une action. En interne, une action crée un message personnalisé. Les développeurs font référence à ces actions en tant que « messages ». Chacun de ces messages est basé sur des actions effectuées sur un enregistrement d’entité. Si l’objectif d’un processus est de créer un enregistrement, de le mettre à jour, puis de l’assigner, il existe trois étapes distinctes. Ce sont les fonctionnalités de l’entité, et pas nécessairement votre processus métier, qui définissent chaque étape.  
  
Les actions donnent la possibilité de définir un verbe unique (ou message) qui correspond à une opération que vous devez effectuer pour votre entreprise. Ces nouveaux messages sont basés sur un processus ou un comportement plutôt que sur ce qui peut être fait avec une entité. Ces messages peuvent correspondre à des verbes comme Réaffecter, Convertir, Planifier, Acheminer ou Approuver, en fait, tout ce dont vous avez besoin. L’ajout de ces verbes aboutit à un vocabulaire plus riche dont vous pouvez vous servir pour définir aisément vos processus métier. Vous pouvez appliquer ce vocabulaire plus riche à partir des clients ou des intégrations au lieu de devoir écrire l’action au sein des clients. Cela est d’autant plus facilité que vous pouvez gérer et journaliser la réussite ou l’échec de l’action entière en tant qu’unité unique.  
  
<a name="BKMK_ConfigurableMessages"></a>   
## <a name="configurable-messages"></a>Messages configurables  
 Une fois qu’une action est définie et activée, un développeur peut utiliser ce message comme tout autre message fourni par la plateforme. Toutefois, il y a une différence importante : désormais, une personne qui n’est pas développeur peut appliquer des modifications à ce qui doit être fait quand ce message est utilisé. Vous pouvez configurer l’action pour modifier les étapes à mesure que vos processus métier changent. Aucun code personnalisé qui utilise ce message n’a besoin d’être changé tant que les arguments de processus ne changent pas.  
  
 Les processus de workflow et les plug-ins continuent de fournir des fonctionnalités similaires pour la définition de l’automatisation. Les processus de workflow donnent toujours à un développeur la possibilité d’appliquer des modifications. Mais la différence réside dans la façon dont les processus métier sont composés et dont un développeur peut écrire son code. Une action est un message qui opère au même niveau que les messages fournis par la plateforme. Les développeurs peuvent inscrire des plug-ins pour les actions.  
  
<a name="BKMK_GlobalMessages"></a>   
## <a name="global-messages"></a>Messages globaux 
 
 Contrairement aux [plug-ins](/powerapps/developer/common-data-service/apply-business-logic-with-code?branch=master#create-a-plug-in) ou workflows Common Data Service, une action n’a pas besoin d’être associée à une entité spécifique. Vous pouvez définir des actions « globales » qui peuvent être appelées toutes seules.

## <a name="next-steps"></a>Étapes suivantes

[Créer une action personnalisée](create-actions.md)  
  

