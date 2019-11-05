---
title: Créer un workflow de tâches mobile avec PowerApps | MicrosoftDocs
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: conceptual
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
ms.openlocfilehash: ccd3b6c0e8cf97a490d01bb9ba5e5c3c4043fda5
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546426"
---
# <a name="create-a-mobile-task-flow"></a>Créer un workflow de tâche mobile
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Créez un fluide dans Dynamics 365 pour les téléphones ou Dynamics 365 pour les tablettes en fonction des tâches courantes effectuées par vos utilisateurs. Par exemple, s’ils ont besoin d’effectuer régulièrement une série d’étapes de suivi après les réunions des clients, créez un workflow de tâches. Lorsque les utilisateurs appuient sur la nouvelle tâche dans leur application mobile, ils vont passer du début à la fin, afin qu’ils n’oublient pas une étape importante.  
  
 Les flux de tâches peuvent utiliser des formes et la logique de plusieurs entités, et peuvent avoir une logique de formulaire qui s’exécute sur les pages de flux de tâches.  
  
## <a name="create-a-task-flow"></a>Créer un workflow de tâche
  
1. Assurez-vous que vous disposez du rôle de sécurité administrateur système ou personnalisateur du système ou des autorisations équivalentes. Le responsable, vice-président ou PDG-Business Manager, les rôles de sécurité peuvent également créer des flux de tâches mobiles. 
  
2. Ouvrez [l’Explorateur de solutions](/powerapps/maker/model-driven-apps/advanced-navigation#solution-explorer) et sélectionnez **processus**.  
  
3.  Dans la barre d’outils **actions** , sélectionnez **nouveau**.  
  
4.  Dans la boîte de dialogue **créer un processus** , renseignez les champs obligatoires :  
  
    -   Entrez un nom de processus.  
  
    -   Dans la liste **catégorie** , sélectionnez **Workflow du processus d’entreprise**.  
  
    -   Dans la liste **entité** , sélectionnez l’entité de votre choix.  
  
5.  Sélectionnez l’option **exécuter le processus en tant que Workflow (mobile online)** .  
  
6.  Sélectionnez **OK**.
  
     Le concepteur de déroulement des tâches s’ouvre dans une nouvelle fenêtre.  
  
     ![Fenêtre du concepteur de déroulement des tâches](media/task-flow-designer-window.png "Fenêtre du concepteur de déroulement des tâches") 
  
7.  Si vos utilisateurs progressent d’une page à l’autre dans l’ordre, faites glisser le composant **page** de l’onglet **composants** sur le côté droit de l’écran et déposez-le sur le signe + dans l’emplacement approprié. Pour ajouter un nom pour une page, sélectionnez la page, sélectionnez l’onglet **Propriétés** , tapez un nouveau nom, puis sélectionnez **appliquer**.  
  
8.  Pour ajouter une branche au déroulement des tâches, faites glisser le composant **condition** à partir de l’onglet **composants** et déposez-le sur le signe + dans l’emplacement approprié. Pour définir les propriétés de la condition, sélectionnez la condition, définissez les propriétés sous l’onglet **Propriétés** , puis sélectionnez **appliquer**.  
  
    > [!NOTE]
    >  Au fur et à mesure que vous ajoutez des pages et des conditions au workflow, vous verrez un minicarte dans le coin inférieur gauche de la fenêtre qui affiche toutes les pages et conditions dans le déroulement des tâches.  
  
9. Pour ajouter une étiquette de champ, d’étiquette ou de section à une page, faites glisser l’étiquette de **champ** **, d’étiquette ou**de **section** de l’onglet **composants** vers la page appropriée. Pour modifier les propriétés de l’un de ces éléments, sélectionnez l’élément, définissez les propriétés sous l’onglet **Propriétés** , puis sélectionnez **appliquer**.  
  
10. Pour valider le déroulement des tâches, sélectionnez **valider** sur la barre d’action.  
  
11. Pour enregistrer le processus en tant que brouillon, sélectionnez **Enregistrer** en haut de l’écran. (Tant qu’un processus est un brouillon, les utilisateurs ne seront pas en mesure de l’utiliser.)  
  
12. Pour activer le déroulement des tâches afin que les utilisateurs puissent l’utiliser, sélectionnez **activer**.  
  
> [!TIP]
>  Voici quelques conseils à garder à l’esprit quand vous travaillez sur votre workflow dans la fenêtre du concepteur :  
>   
> -  Pour prendre un instantané de tous les éléments de la fenêtre déroulement des tâches, sélectionnez **instantané** dans la barre d’action.  
> -  Pour connecter un composant valide à un autre composant valide dans le concepteur, sélectionnez **connecteur** dans la barre d’action.  
> -  Vous pouvez agrandir ou réduire les images à l’écran en sélectionnant les boutons **augmenter le niveau de zoom** ou **diminuer le niveau de zoom** dans l’angle supérieur droit de l’écran. Sélectionnez le bouton **ajuster à la zone de dessin** pour souffler les images jusqu’à la plus grande taille adaptée à l’écran.  
  
## <a name="next-steps"></a>Étapes suivantes  
 [Créer un workflow de processus d’entreprise](create-business-process-flow.md)   

