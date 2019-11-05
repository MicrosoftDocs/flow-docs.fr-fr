---
title: Apprenez à créer des flux d’interface utilisateur de bureau | Microsoft Docs
description: Apprenez à créer des flux d’interface utilisateur de bureau pour les applications Windows.
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: kvivek
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/04/2019
ms.author: DeonHe
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: e03b23387f5c3837b9b3f7e9ce023f8c31ce79a3
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589797"
---
# <a name="create-and-test-desktop-ui-flows"></a>Créer et tester des flux d’interface utilisateur de bureau

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]


Créer des flux d’interface utilisateur de bureau pour automatiser les applications de bureau Windows. 

Consultez les [problèmes connus](create-desktop.md#known-issues-and-solutions) plus loin dans cette rubrique pour en savoir plus sur les problèmes que vous pouvez rencontrer, les solutions de contournement pour ces problèmes et les scénarios qui ne sont pas pris en charge dans cette version préliminaire.


> [!TIP]
> Vous pouvez automatiser d’autres applications de bureau Windows en suivant un modèle similaire.

## <a name="create-a-desktop-ui-flow"></a>Créer un workflow d’interface utilisateur de bureau

Dans les étapes suivantes, nous allons montrer comment automatiser l’application calculatrice pour additionner deux nombres, puis stocker le résultat pour une utilisation ultérieure. 

1. Assurez-vous que votre [appareil est prêt](setup.md) à créer des flux d’interface utilisateur. <!--Todo: link to the prereqs section-->

1. Utilisez la [version de chrome de Microsoft Edge](https://www.microsoftedgeinsider.com) ou Google Chrome pour ouvrir [Power automate](https://flow.microsoft.com), puis connectez-vous avec un compte de messagerie professionnel ou scolaire.

1. Sélectionnez **mes flux** > **flux de l’interface utilisateur (version préliminaire)**  > **nouveau**.

   ![Créer un nouveau workflow d’interface utilisateur](../media/create-windows-ui-flow/create-new.png "Créer un nouveau workflow d’interface utilisateur")

1. Sélectionnez **application de bureau** , puis **suivant**.

   ![Sélectionner le Bureau](../media/create-windows-ui-flow/select-desktop.png "Sélectionner le Bureau") 

1. Entrez un nom pour le workflow de votre interface utilisateur dans le champ **nom du flot** , puis sélectionnez **suivant**.

   ![Sélectionner le Bureau](../media/create-windows-ui-flow/give-a-name.png "Sélectionner le Bureau") 

1. Sélectionnez **suivant** en bas pour ignorer l’écran facultatif **configurer les entrées** puisque nous n’utilisons pas d’entrées dans cette procédure pas à pas.

1. Sélectionnez la carte d' **application d’enregistrement** pour la développer.

   ![Sélectionner l’application d’enregistrement](../media/create-windows-ui-flow/select-record-app.png "Sélectionner l’application d’enregistrement")

1. Sélectionnez **lancer l’enregistreur**.

   ![Sélectionnez lancer l’enregistreur](../media/create-windows-ui-flow/select-launch-recorder.png "Sélectionnez lancer l’enregistreur")

   Le contrôle d’enregistreur s’affiche en haut de l’écran.

   ![Enregistreur-contrôle](../media/create-windows-ui-flow/recorder-control.png "Enregistreur-contrôle")

1. Démarrez l’application Calculatrice.

     >[!TIP]
     >Lorsque la souris pointe sur les contrôles de l’application, vous remarquerez qu’un contour bleu met en évidence chaque contrôle. Attendez toujours la mise en surbrillance bleue avant de sélectionner un contrôle.
     >
     >Si la mise en surbrillance bleue ne s’affiche pas autour de l’élément, il est possible qu’il ne soit pas correctement enregistré.

1. Sélectionnez **enregistrement** dans le contrôle d’enregistreur.
1. Sélectionnez le premier nombre, sélectionnez **+** , sélectionnez le deuxième nombre, puis sélectionnez **=** .

    ![Application Calculatrice](../media/create-windows-ui-flow/app-to-record.png "Application Calculatrice")

1. Sélectionnez **terminé** sur le contrôle d’enregistreur après avoir effectué les actions que vous souhaitez enregistrer.

1. Fermez l’application que vous avez enregistrée.

1. Sélectionnez la carte qui commence par « exécuter <app name> script » pour afficher les captures d’écran des étapes enregistrées.

     >[!TIP]
     >Sélectionnez **...**  > **supprimer** pour supprimer toutes les étapes supplémentaires que vous souhaitez peut-être supprimer.

    ![Afficher les étapes enregistrées](../media/create-windows-ui-flow/show-recorded-steps.png "Afficher les étapes enregistrées")

1. Sélectionnez **suivant**. 

1. Sélectionnez **suivant** pour ignorer l’étape de **définition des sorties** facultatives, car nous n’utilisons pas de sorties dans cette procédure pas à pas.

## <a name="test-your-ui-flow"></a>Tester votre workflow d’interface utilisateur

Il est toujours intéressant de tester le workflow de votre interface utilisateur. Pour ce faire, sélectionnez le bouton **tester maintenant** , puis observez l’exécution de votre workflow d’interface utilisateur.
    
 >[!IMPORTANT]
 >Pour de meilleurs résultats, n’interagissez pas avec votre appareil pendant la durée de la lecture.

1. Sélectionnez **enregistrer et quitter** pour enregistrer votre flux et quitter la fonctionnalité flux de l’interface utilisateur.


## <a name="known-issues-and-solutions"></a>Problèmes connus et solutions

- Ouvrez et agrandissez les *applications que vous souhaitez enregistrer avant de* commencer l’enregistrement.

- Vous pouvez ajouter une [action **Fermer** ](edit-desktop.md#add-a-manual-action) à la fin du flux de l’interface utilisateur, car le flux de l’interface utilisateur lance une nouvelle instance des applications avec chaque test ou exécution.

- Sélectionnez **...**  > **supprimer** sur la carte des actions enregistrées pour supprimer toutes les actions inutiles/dupliquées. Des actions en double peuvent être créées en fonction du type et de la vitesse d’enregistrement. 

- Les clics droits peuvent ne pas être lus correctement. Dans ce cas, pendant l’enregistrement, cliquez sur gauche pour concentrer les flux de l’interface utilisateur sur l’élément d’interface utilisateur cible, puis cliquez avec le bouton droit.

- Si le flux de l’interface utilisateur n’enregistre plus ou ne lit plus les applications Windows après l’installation d’une nouvelle version, désinstallez la version précédente, puis installez une nouvelle version.


### <a name="unsupported-application-types"></a>Types d’applications non pris en charge

-   Interactions sur Windows (Explorateur de fichiers, menu Démarrer, barre des tâches, etc.).

-   Navigateurs Web (chrome, Internet Explorer, Edge, chrome, Firefox, Mozilla, etc.).
    Au lieu de cela, consultez [créer un workflow d’interface utilisateur Web](edit-web.md) pour automatiser les sites Web.

-   Applications Java.

-   Cliquez sur applications.

-   Applications avec une vue Web telle que les applications d’électrons.

-   Microsoft Office 2016 et versions antérieures. 

-   Microsoft Office en ligne.

### <a name="unsupported-configurations"></a>Configurations non prises en charge

-   Plusieurs écrans.

-   Enregistrement via un client de machine virtuelle (Bureau à distance, Citrix, etc.), soit avec l’interface de l’interface utilisateur qui s’exécute sur le périphérique hôte, soit sur l’ordinateur virtuel. Aucun n’est pris en charge.

-   Plusieurs instances d’une application où les titres de fenêtre principaux sont identiques.

-   Fenêtres d’application avec des titres identiques, par exemple, Microsoft Outlook avec plusieurs nouvelles fenêtres de messagerie sans **titre (html)** actives en même temps.

-   Sessions simultanées d’enregistrement sur un appareil donné.

-   Sessions de lecture simultanées sur un appareil donné. En cas d’exécution simultanée de workflows d’interface utilisateur, la première est prioritaire et les suivantes échouent jusqu’à ce que la première soit terminée.

-   Lecture sur un appareil avec une disposition de clavier différente de celle de l’appareil sur lequel il a été enregistré.

-   Enregistrement sur un appareil ou une session Windows lorsque le navigateur avec Microsoft Flow se trouve sur un autre appareil ou une autre session Windows.

### <a name="unsupported-action-types-and-behaviors"></a>Types d’actions et comportements non pris en charge

Les actions suivantes ne seront pas enregistrées :

-   Double-cliquez sur.

-   Déplacement de la souris.

-   Pointage de la souris.

-   Cliquez et faites glisser.

-   Entrée tactile ou de stylet.

-   Ouvrir l’application avant l’enregistrement.

-   Application fermée avant le démarrage de la lecture.

## <a name="unreliable-behaviors-and-workarounds-for-microsoft-office-desktop"></a>Comportements et solutions de contournement non fiables pour Microsoft Office (Desktop)
- Épinglez le ruban avant de commencer la lecture afin d’éviter les problèmes qui peuvent se produire si le ruban est configuré pour se Masquer automatiquement pendant la lecture.
- Ne sélectionnez pas d’éléments en cliquant et en faisant glisser. Par exemple, n’utilisez pas Maj + clic pour sélectionner des cellules dans Microsoft Excel et ne sélectionnez pas de texte dans Microsoft Word ou Microsoft PowerPoint en faisant glisser la souris.
- Certains éléments peuvent ne pas fonctionner correctement dans les flux d’interface utilisateur (version préliminaire) pour les applications de bureau Microsoft Word et Microsoft PowerPoint. Par exemple, les options du menu fichier, telles que démarrer à partir d’un espace, ou cliquer avec le bouton droit sur des contrôles tels que l’ajout d’un paragraphe dans Microsoft Word ou la modification de la disposition des diapositives dans Microsoft PowerPoint peuvent ne pas fonctionner.

## <a name="next-steps"></a>Étapes suivantes

- Découvrez comment [déclencher le workflow de l’interface utilisateur](run-ui-flow.md) que vous venez de créer.

- Si vous souhaitez en faire plus avec les flux d’interface utilisateur, vous pouvez également essayer des flux d’interface utilisateur avec des paramètres [d’entrée et de sortie](inputs-outputs-web.md) .

