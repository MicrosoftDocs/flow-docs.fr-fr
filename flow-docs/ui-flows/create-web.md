---
title: Apprenez à créer des flux d’interface utilisateur pour les sites Web | Microsoft Docs
description: Apprenez à automatiser des applications Web avec des flux d’interface utilisateur.
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
ms.openlocfilehash: 010b6632a60f2c81c138fa98d850df79be814f68
ms.sourcegitcommit: 53f049dc7e7cad652e728941ee426b7ad2a116da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73589879"
---
# <a name="create-and-test-your-web-ui-flows"></a>Créer et tester vos flux d’interface utilisateur Web

[Cette rubrique est une documentation préliminaire et peut faire l’objet de modifications.]

[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Procédez comme suit pour créer un fluide d’interface utilisateur Web simple :

## <a name="create-a-web-ui-flow"></a>Créer un workflow d’interface utilisateur Web

1. Ouvrez la [prochaine version de Microsoft Edge](https://www.microsoftedgeinsider.com/) ou Google Chrome, puis accédez à [Power automate](https://flow.microsoft.com/).

1. Connectez-vous avec votre compte professionnel si nécessaire.

1. Sélectionnez **mes flux** > **flux de l’interface utilisateur (version préliminaire)**  > **nouveau**.

   ![Créer un nouveau workflow d’interface utilisateur](../media/create-windows-ui-flow/create-new.png "Créer un nouveau workflow d’interface utilisateur")

1. Sélectionner l' **application Web** > **suivant**
    
   ![Sélectionner une application Web](../media/create-web-ui-flow/select-web-app.png "Sélectionner une application Web")

1. Entrez un nom pour le workflow de votre interface utilisateur dans le champ **nom du workflow** .

1. Entrez l’URL du site Web que vous souhaitez automatiser dans le champ **URL de base** , puis sélectionnez **lancer l’enregistreur**.

   ![Donnez un nom et une URL](../media/create-web-ui-flow/give-a-name.png "Donnez un nom et une URL") 

   L’IDE de sélénium démarre.

   >[!TIP] 
   >Conseil : vous pouvez enregistrer des actions sur plusieurs sites Web HTTP ou HTTPs au sein du même onglet.  

1. Dans l’IDE de sélénium, sélectionnez le bouton rouge **Rec** en haut à droite de l’écran pour lancer l’enregistreur.

   L’URL que vous avez choisie à l’étape précédente s’ouvre.

   ![Sélectionner Rec](../media/create-web-ui-flow/select-rec.png "Sélectionner Rec")

1.  Effectuez les actions que vous souhaitez enregistrer sur le site Web. 
    
    >[!TIP]
    >En bas à droite, vous pouvez voir l’état de l’enregistrement.

    ![État de l’enregistrement](../media/create-web-ui-flow/recording-status.png "État de l’enregistrement")

1.  Une fois l’enregistrement terminé, sélectionnez le bouton d' **arrêt** rouge dans le coin supérieur droit de l’IDE de sélénium.

    ![Bouton arrêter](../media/create-web-ui-flow/stop-button.png "Bouton arrêter" )

1. Sélectionnez le bouton **exécuter le test actuel** à partir du côté supérieur gauche de l’écran pour afficher le workflow de l’interface utilisateur que vous venez de créer.

    ![Exécuter le test actuel](../media/create-web-ui-flow/run-test.png "Exécuter le test actuel")

   >[!TIP]
   >Vous pouvez définir le délai d’attente entre les étapes pour ralentir la lecture locale à des fins de test. Ce paramètre est utilisé à des fins de test uniquement et n’a aucun impact lorsque votre workflow d’interface utilisateur est déployé.  
  
1. Sélectionnez le bouton **enregistrer le projet** en haut à droite de l’IDE de sélénium. Cela ferme, puis charge le projet.

Maintenant que vous avez créé un flux d’interface utilisateur Web, utilisez-le dans vos autres flux.

## <a name="limitations-and-known-issues-for-web-ui-flows"></a>Limitations et problèmes connus pour les flux d’interface utilisateur Web

>[!WARNING]
>**Les mots de passe dans l’IDE de sélénium sont stockés en texte brut.**  


**L’interface utilisateur flux n’enregistre plus ou ne lit plus les applications Windows après l’installation d’une nouvelle version.**

Vous devez désinstaller la version précédente avant d’en installer une nouvelle.

Pour cela, ouvrez le menu Démarrer, accédez à **paramètres** > **applications**, recherchez flux de l' **interface utilisateur** dans la liste des applications > **flux de l’interface utilisateur (** préversion), puis sélectionnez Désinstaller. L’Assistant va vous guider tout au long du processus.

**Profil utilisateur temporaire pour la lecture**

Les enregistrements de l’IDE de sélénium s’effectuent avec le profil de l’utilisateur actuel, mais la lecture s’effectue à l’aide d’un profil utilisateur temporaire. Cela signifie que les sites Web qui ont besoin d’une authentification peuvent ne pas demander d’informations d’identification pendant une session d’enregistrement, mais les étapes d’authentification seront nécessaires pendant la lecture. 

Pour résoudre ce cas, l’utilisateur doit modifier manuellement le script pour insérer les commandes nécessaires au processus de connexion.

**Autres limitations**

-   Enregistrement des applications de bureau pendant une session d’enregistrement Web. Si vous devez automatiser des applications Web et de bureau, vous pouvez créer des flux d’interface utilisateur distincts pour chaque type, puis les combiner dans un flux.

-   Multi-Factor Authentication (MFA) n’est pas pris en charge, utilisez un locataire qui ne requiert pas MFA.

-   Ces commandes IDE de sélénium ne sont pas prises en charge : Run, AnswerOnNextPrompt, ChooseCancelOnNextConfirmation, ChooseCancelOnNextPrompt, ChooseOkOnNextConfirmation, Debugger, ClickAt, DoubleClickAt, ECHO, MouseOut, MouseUpAt et MouseDownAt.

-   Le clic droit n’est pas pris en charge. 

-   Des entrées de workflow d’interface utilisateur Web supplémentaires sont générées lorsque vous utilisez des commandes foreach. Pour contourner ce problème, entrez une valeur dans les champs supplémentaires. Elle n’a aucun impact sur la lecture.

-   Si le fichier. Side contient plusieurs projets de test, seul le premier qui a été créé s’exécute. 

     >[!TIP]
     >Notez que l’IDE de sélénium classe les tests par nom, et non par date de création. le premier test créé peut donc ne pas être le premier de la liste.

-   La lecture directement dans l’IDE de sélénium peut ne pas se comporter comme prévu. Toutefois, la lecture au moment de l’exécution via l’infrastructure de workflow de l’interface utilisateur se comporte correctement.

## <a name="next-steps"></a>Étapes suivantes

- Découvrez comment [exécuter des flux d’interface utilisateur](run-ui-flow.md).

- Si vous souhaitez en faire plus avec les flux d’interface utilisateur, vous pouvez également essayer des flux d’interface utilisateur avec des paramètres [d’entrée et de sortie](inputs-outputs-web.md) .

