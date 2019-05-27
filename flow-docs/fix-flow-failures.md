---
title: Résoudre les problèmes de flux | Microsoft Docs
description: Résoudre certaines des raisons les plus courantes pour lesquelles les flux échouent
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
ms.openlocfilehash: 0e151f3c5cd69fe07263e5fa36d46eb3b8be19f5
ms.sourcegitcommit: 93f8bac60cebb783b3a8fc8887193e094d4e27e2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "64992719"
---
# <a name="troubleshooting-a-flow"></a>Résolution des problèmes de flux

## <a name="repair-tips-in-email"></a>Conseils de réparation par courrier électronique

Conseils de réparation sont envoyés aux propriétaires de flux par courrier électronique chaque fois qu’un flux échoue. Ces e-mails de conseils de réparation contiennent des commentaires spécifiques et exploitables sur certaines erreurs. Par exemple, une erreur courante consiste à configurer un flux qui tente d’obtenir le responsable d’une personne dans Office 365, mais il n’existe aucun gestionnaire configuré dans Azure Active Directory (Azure AD). Si cela ou plusieurs autres conditions entraînent votre flux échoue, vous obtenez un e-mail de conseils de réparation comme suit :

![Conseils de réparation](media/fix-flow-failures/repair-tips-email.png)

L’e-mail de conseils de réparation contient les sections suivantes :

Nom|Description
---|---
Heure|Affiche le temps que le flux du premier échec.
Que s'est-il passé|Fournit une description du problème ayant provoqué l’échec dans le flux.
Que dois-je faire|Fournit des conseils pour résoudre le problème qui provoque l’échec dans le flux.
Conseils de dépannage|Fournit des détails, notamment le nombre de fois où le flux a échoué et un lien vers le flux avec les mêmes données d’entrée de nouvelle tentative.

Pour corriger les erreurs signalées, sélectionnez **corriger mon flux** et suivez les étapes décrites dans l’e-mail de conseils de réparation.

E-mails de conseils de réparation sont facultatifs. Si vous ne souhaitez pas les recevoir, simplement les désactiver dans le menu de propriétés pour le flux spécifique.

Si votre flux échoue, vous pouvez également le résoudre directement dans Microsoft Flow.  Voici quelques scénarios courants de défaillance et des conseils sur la façon de les corriger.

## <a name="identify-the-error"></a>Identifier l’erreur
Avant de résoudre un flux, vous devez identifier la raison de l’échec. Cliquez ou appuyez sur l’icône de notifications en haut du portail web (ou ouvrez l’onglet **Activité** dans l’application mobile), puis cliquez ou appuyez sur le flux dans la liste.

![Notifications](./media/fix-flow-failures/notifications-toolbar.png)

Des informations sur le flux apparaissent et au moins une étape affiche une icône de point d’exclamation rouge. Ouvrez cette étape et passez en revue le message d’erreur.

![Message d’erreur](./media/fix-flow-failures/flow-run-failure.png)


## <a name="authentication-failures"></a>Échecs d’authentification
Dans de nombreux cas, les flux échouent en raison d’une erreur d’authentification. Si vous rencontrez ce type d’erreur, le message d’erreur contient **Non autorisé** ou un code d’erreur **401** ou **403** s’affiche. Vous pouvez généralement corriger l’erreur d’authentification en mettant à jour la connexion :

1. En haut du portail web, cliquez ou appuyez sur l’icône d’engrenage pour ouvrir le **paramètres** menu, puis cliquez ou appuyez sur **connexions**.
2. Faites défiler jusqu’à la connexion pour laquelle vous avez vu le message d’erreur **Non autorisé**.
3. En regard de la connexion, cliquez ou appuyez sur le lien **Vérifier le mot de passe** dans le message concernant la connexion non authentifiée.
4. Vérifiez vos informations d’identification en suivant les instructions qui s’affichent, revenez à votre flux ayant échoué, puis cliquez ou appuyez sur **Resubmit (Soumettre à nouveau)**.
   
    Le flux doit maintenant s’exécuter comme prévu.

## <a name="action-configuration"></a>Configuration des actions
Les flux échouent également si le paramètre d’action du flux ne fonctionne pas comme prévu. Dans ce cas, le message d’erreur contient **Demande incorrecte** ou **Introuvable** ou le code d’erreur **400** ou **404** s’affiche.

Le message d’erreur doit indiquer comment corriger l’erreur. Vous devez cliquer ou appuyer sur le bouton **Modifier**, puis corriger le problème à l’intérieur de la définition de flux. Enregistrez le flux mis à jour, puis cliquez ou appuyez sur **Resubmit (Soumettre à nouveau)** pour retenter l’exécution avec la configuration mise à jour.

## <a name="other-failures"></a>Autres erreurs
Si le code d’erreur **500** ou **502** s’affiche, l’échec est temporaire. Cliquez ou appuyez sur **Resubmit (Soumettre à nouveau)** pour réessayer le flux.

## <a name="getting-help-from-support-or-the-community"></a>Obtention d’aide à partir de la prise en charge ou de la Communauté

Lorsque vous avez besoin d’aide, vous pouvez utiliser notre **Self aide** options, ou vous pouvez **demander de l’aide** des autres.

### <a name="self-help"></a>Aide autonome 

1. Accédez à la [site de support](https://flow.microsoft.com/support/).
1. Accédez à la **Self aide** catégorie et sélectionnez une des options d’auto-assistance.

    ![Demandez à l’aide sur. Contactez le support technique.](media/fix-flow-failures/self-help-section.png)
### <a name="ask-for-help-from-others"></a>Demander de l’aide d’autres personnes

1. Accédez à la [site de support](https://flow.microsoft.com/support/).
1. Sélectionnez **contacter le support technique** dans le **demander de l’aide** section.
    
    ![Demandez à l’aide sur. Contactez le support technique.](media/fix-flow-failures/ask-for-help.png)

1. Terminer la **type de problème**, **catégorie**et le **dites-nous ce que vous avez besoin d’aide avec** champs, puis sélectionnez **consultez solutions**. 

1. Notez que le **Solutions** section affiche une fois que vous sélectionnez **consultez solutions**. Il contient une liste de résultats que vous pouvez utiliser pour permettre de résoudre le problème qu'auquel vous êtes confronté. 

    ![Détails d’assistance intégrée](media/fix-flow-failures/integrated-helper-details.png)

Si vous devez résoudre un problème, aide est disponible à partir de notre [Communauté](https://go.microsoft.com/fwlink/?LinkID=787467) et Microsoft. 

