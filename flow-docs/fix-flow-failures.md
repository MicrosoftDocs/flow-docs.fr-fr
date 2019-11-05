---
title: Résolution des problèmes liés à un Flow | Microsoft Docs
description: Résoudre certaines des raisons les plus courantes de l’échec des flux
services: ''
suite: flow
documentationcenter: na
author: stepsic-microsoft-com
manager: anneta
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/01/2019
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 2981c125d722cb766a1cc840f404d84dfa57ac96
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547876"
---
# <a name="troubleshooting-a-flow"></a>Résolution des problèmes d’un Flow
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

## <a name="repair-tips-in-email"></a>Conseils de réparation dans l’e-mail

Les conseils de réparation sont envoyés aux propriétaires de Flow par courrier électronique chaque fois qu’un workflow échoue. Ces conseils de réparation contiennent des commentaires spécifiques et exploitables pour certaines erreurs. Par exemple, une erreur courante consiste à configurer un Flow qui tente d’obtenir le responsable d’une personne dans Office 365, mais aucun gestionnaire n’est configuré dans Azure Active Directory (Azure AD). Si une ou plusieurs autres conditions provoquent l’échec de votre workflow, vous recevez un e-mail de conseils de réparation comme suit :

![Conseils de réparation](media/fix-flow-failures/repair-tips-email.png)

L’e-mail sur les conseils de réparation contient les sections suivantes :

Nomme|Descriptive
---|---
Simultanément|Affiche l’heure à laquelle le workflow a échoué pour la première fois.
Que s'est-il passé|Fournit une description du problème qui a provoqué l’échec dans le Workflow.
Correctif Comment faire|Fournit des conseils pour résoudre le problème qui provoque l’échec du Workflow.
Conseils de dépannage|Fournit des détails, notamment le nombre de fois où le workflow a échoué et un lien pour retenter le workflow avec les mêmes données d’entrée.

Pour corriger les erreurs signalées, sélectionnez **corriger mon Flow** et suivez les étapes de l’e-mail conseils de réparation.

Les courriels de conseils de réparation sont facultatifs. Si vous ne souhaitez pas les recevoir, il suffit de les désactiver dans le menu des propriétés du workflow spécifique.

Si votre workflow échoue, vous pouvez également le résoudre directement dans Microsoft Flow.  Voici quelques scénarios d’échec courants et des conseils sur la façon de les résoudre.

## <a name="identify-the-error"></a>Identifier l’erreur
Avant de pouvoir résoudre un fluide, vous devez identifier la raison de l’échec. Cliquez ou appuyez sur l’icône notifications en haut du portail Web (ou ouvrez l’onglet **activité** dans l’application mobile), puis cliquez ou appuyez sur votre Flow dans la liste qui s’affiche.

![Fonctionnalité](./media/fix-flow-failures/notifications-toolbar.png)

Des détails sur le déroulement s’affichent, et au moins une étape affiche une icône d’exclamation rouge. Ouvrez cette étape et passez en revue le message d’erreur.

![Message d’erreur](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Échecs d’authentification
Dans de nombreux cas, les flux échouent en raison d’une erreur d’authentification. Si vous avez ce type d’erreur, le message d’erreur contient **non autorisé** ou un code d’erreur **401** ou **403** s’affiche. Vous pouvez généralement corriger une erreur d’authentification en mettant à jour la connexion :

1. En haut du portail Web, cliquez ou appuyez sur l’icône d’engrenage pour ouvrir le menu **paramètres** , puis cliquez ou appuyez sur **connexions**.
2. Faites défiler jusqu’à la connexion pour laquelle vous avez vu le message d’erreur **non autorisé** .
3. À côté de la connexion, cliquez ou appuyez sur le lien **vérifier le mot de passe** dans le message relatif à la connexion qui n’est pas authentifiée.
4. Vérifiez vos informations d’identification en suivant les instructions qui s’affichent, revenez à l’échec de l’exécution de votre workflow, puis cliquez ou appuyez sur **renvoyer**.
   
    Le Flow doit maintenant s’exécuter comme prévu.

## <a name="action-configuration"></a>Configuration de l’action
Les flux échouent également si un paramètre dans une action du flux ne fonctionne pas comme prévu. Dans ce cas, le message d’erreur contient une **Demande incorrecte** ou est **introuvable**, ou un code d’erreur **400** ou **404** s’affiche.

Le message d’erreur doit indiquer comment corriger l’échec. Vous devez cliquer ou appuyer sur le bouton **modifier** , puis corriger le problème à l’intérieur de la définition de Workflow. Enregistrez le Flow mis à jour, puis cliquez ou appuyez sur **soumettre** à nouveau pour retenter l’exécution avec la configuration mise à jour.

## <a name="other-failures"></a>Autres échecs
Si le code d’erreur **500** ou **502** s’affiche, l’échec est temporaire ou transitoire. Cliquez ou appuyez sur **soumettre** à nouveau pour retenter le Flow.

## <a name="getting-help-from-support-or-the-community"></a>Obtenir de l’aide du support technique ou de la communauté

Lorsque vous avez besoin d’aide, vous pouvez utiliser nos options **d’aide automatique** , ou vous pouvez **demander de l’aide** auprès d’autres utilisateurs.

### <a name="self-help"></a>Aide autonome 

1. Accédez au [site de support](https://flow.microsoft.com/support/).
1. Accédez à la catégorie **d’aide libre** et sélectionnez l’une des options d’auto-assistance.

    ![Section demander de l’aide. Contactez le support technique.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Demander de l’aide auprès d’autres utilisateurs

1. Accédez au [site de support](https://flow.microsoft.com/support/).
1. Sélectionnez **contacter le support technique** dans la section **demander de l’aide** .
    
    ![Section demander de l’aide. Contactez le support technique.](media/fix-flow-failures/ask-for-help.png)

1. Renseignez les champs **type de problème**, **catégorie**, et **dites-nous ce dont vous avez besoin d’aide avec** les champs, puis sélectionnez **afficher les solutions**. 

1. Notez que la section **solutions** s’affiche une fois que vous avez sélectionné **afficher les solutions**. Il contient une liste de résultats que vous pouvez utiliser pour résoudre le problème auquel vous êtes confronté. 

    ![Détails de l’aide intégrée](media/fix-flow-failures/integrated-helper-details.png)

Si vous avez besoin d’aide pour résoudre un problème, l’aide est disponible auprès de notre [communauté](https://go.microsoft.com/fwlink/?LinkID=787467) et de Microsoft. 

