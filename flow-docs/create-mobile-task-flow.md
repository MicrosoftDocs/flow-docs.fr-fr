---
title: Créer un flux de tâches mobile avec PowerApps | Microsoft Docs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
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
ms.openlocfilehash: 7f15f11a4e66d80762384f8183af7973fcca76bf
ms.sourcegitcommit: 9ecf4956320d465a3bf618b79a9023b729d33c89
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57462760"
---
# <a name="create-a-mobile-task-flow"></a>Créer un flux de tâches mobile

Concevez un flux dans Dynamics 365 pour téléphones ou Dynamics 365 pour tablettes en fonction des tâches couramment effectuées par vos utilisateurs. Par exemple, s’ils doivent effectuer régulièrement une série d’étapes de suivi après des réunions avec des clients, créez un flux de tâches. Quand les utilisateurs appuient sur la nouvelle tâche dans leur application mobile, elle les guide du début à la fin pour qu’ils n’oublient aucune étape importante.  
  
 Les flux de tâches peuvent utiliser une logique et des formulaires à plusieurs entités, et peuvent avoir une logique de formulaire qui s’exécute sur les pages du flux de tâches.  
  
## <a name="create-a-task-flow"></a>Créer un flux de tâches
  
1. Assurez-vous que vous disposez du rôle de sécurité Administrateur système ou Personnalisateur de système ou d’autorisations équivalentes. Si vous utilisez Dynamics 365 for Customer Engagement, les rôles de sécurité Directeur, Vice-président ou Directeur général - Dirigeant d’entreprise peuvent également créer des flux de tâches mobiles. 
  
2. Ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) et sélectionnez **Processus**.  
  
3.  Dans la barre d’outils **Actions**, sélectionnez **Nouveau**.  
  
4.  Dans la boîte de dialogue **Créer un processus**, renseignez les champs obligatoires :  
  
    -   Entrez un nom de processus.  
  
    -   Dans la liste **Catégorie**, sélectionnez **Flux des processus d’entreprise**.  
  
    -   Dans la liste **Entité**, sélectionnez l’entité souhaitée.  
  
5.  Sélectionnez l’option **Exécuter le processus en tant que flux de tâches (mobile uniquement)**.  
  
6.  Sélectionnez **OK**.
  
     Le concepteur de flux de tâches s’ouvre dans une nouvelle fenêtre.  
  
     ![Fenêtre du concepteur de flux de tâches](media/task-flow-designer-window.png "Fenêtre du concepteur de flux de tâches") 
  
7.  Si vos utilisateurs sont supposés progresser d’une page à l’autre dans l’ordre, faites glisser le composant **Page** à partir de l’onglet **Composants** sur le côté droit de l’écran et déposez-le sur le signe + à l’emplacement approprié. Pour ajouter un nom pour une page, sélectionnez la page, sélectionnez l’onglet **Propriétés**, tapez un nouveau nom, puis sélectionnez **Appliquer**.  
  
8.  Pour ajouter une branche au flux de tâches, faites glisser le composant **Condition** à partir de l’onglet **Composants** et déposez-le sur le signe + à l’emplacement approprié. Pour définir les propriétés de la condition, sélectionnez celle-ci, définissez les propriétés sous l’onglet **Propriétés**, puis sélectionnez **Appliquer**.  
  
    > [!NOTE]
    >  Quand vous ajoutez des pages et des conditions au flux de tâches, vous voyez une minicarte dans l’angle inférieur gauche de la fenêtre qui affiche toutes les pages et conditions contenues dans le flux de tâches.  
  
9. Pour ajouter un champ, une étiquette ou une étiquette de section à une page, faites glisser **Champ**, **Étiquette** ou **Étiquette de section** à partir de l’onglet **Composants** vers la page appropriée. Pour changer les propriétés d’un des éléments, sélectionnez celui-ci, définissez les propriétés sous l’onglet **Propriétés**, puis sélectionnez **Appliquer**.  
  
10. Pour valider le flux de tâches, sélectionnez **Valider** dans la barre d’action.  
  
11. Pour enregistrer le processus en tant que brouillon, sélectionnez **Enregistrer** en haut de l’écran. (Tant qu’un processus est un brouillon, personne d’autre que vous ne peut l’utiliser.)  
  
12. Pour activer le flux de tâches afin de le rendre utilisable, sélectionnez **Activer**.  
  
> [!TIP]
>  Voici quelques conseils à prendre en compte quand vous créez votre flux de tâches dans la fenêtre du concepteur :  
>   
> -  Pour effectuer une capture instantanée du contenu de la fenêtre du flux de tâches, sélectionnez **Capture instantanée** dans la barre d’action.  
> -  Pour connecter un composant valide à un autre composant valide dans le concepteur, sélectionnez **Connecteur** dans la barre d’action.  
> -  Vous pouvez agrandir ou réduire les images à l’écran en sélectionnant les boutons **Augmenter le niveau de zoom** ou **Diminuer le niveau de zoom** dans le coin supérieur droit de l’écran. Sélectionnez le bouton **Ajuster au canevas** pour que les images s’agrandissent au maximum à l’écran.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Créer un flux de processus métier](create-business-process-flow.md)   

