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
ms.date: 01/17/2017
ms.author: stepsic
search.app:
- Flow
search.audienceType:
- flowmaker
- enduser
ms.openlocfilehash: 30efc05dad57bc86a99b90e849fd1c9459930e54
ms.sourcegitcommit: a20fbed9941f0cd8b69dc579277a30da9c8bb31b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44689476"
---
# <a name="troubleshooting-a-flow"></a>Résolution des problèmes de flux
## <a name="identify-the-error"></a>Identifier l’erreur
Avant de résoudre un flux, vous devez identifier la raison de l’échec. Cliquez ou appuyez sur l’icône de notifications en haut du portail web (ou ouvrez l’onglet **Activité** dans l’application mobile), puis cliquez ou appuyez sur le flux dans la liste.

![Notifications](./media/fix-flow-failures/notifications-toolbar.png)

Des informations sur le flux apparaissent et au moins une étape affiche une icône de point d’exclamation rouge. Ouvrez cette étape et passez en revue le message d’erreur.

![Message d’erreur](./media/fix-flow-failures/flow-run-failure.png)

## <a name="authentication-failures"></a>Échecs d’authentification
Dans de nombreux cas, les flux échouent en raison d’une erreur d’authentification. Si vous rencontrez ce type d’erreur, le message d’erreur contient **Non autorisé** ou un code d’erreur **401** ou **403** s’affiche. Vous pouvez généralement corriger l’erreur d’authentification en mettant à jour la connexion :

1. En haut du portail web, cliquez ou appuyez sur l’icône d’engrenage pour ouvrir le menu **Paramètres**, puis cliquez ou appuyez sur **Connexions**.
2. Faites défiler jusqu’à la connexion pour laquelle vous avez vu le message d’erreur **Non autorisé**.
3. En regard de la connexion, cliquez ou appuyez sur le lien **Vérifier le mot de passe** dans le message concernant la connexion non authentifiée.
4. Vérifiez vos informations d’identification en suivant les instructions qui s’affichent, revenez à votre flux ayant échoué, puis cliquez ou appuyez sur **Resubmit (Soumettre à nouveau)**.
   
    Le flux doit maintenant s’exécuter comme prévu.

## <a name="action-configuration"></a>Configuration des actions
Les flux échouent également si le paramètre d’action du flux ne fonctionne pas comme prévu. Dans ce cas, le message d’erreur contient **Demande incorrecte** ou **Introuvable** ou le code d’erreur **400** ou **404** s’affiche.

Le message d’erreur doit indiquer comment corriger l’erreur. Vous devez cliquer ou appuyer sur le bouton **Modifier**, puis corriger le problème à l’intérieur de la définition de flux. Enregistrez le flux mis à jour, puis cliquez ou appuyez sur **Resubmit (Soumettre à nouveau)** pour retenter l’exécution avec la configuration mise à jour.

## <a name="other-failures"></a>Autres erreurs
Si le code d’erreur **500** ou **502** s’affiche, l’échec est temporaire. Cliquez ou appuyez sur **Resubmit (Soumettre à nouveau)** pour réessayer le flux.

Si vous rencontrez un autre problème, [posez vos questions à notre communauté](https://go.microsoft.com/fwlink/?LinkID=787467), car d’autres utilisateurs ont peut-être rencontré des problèmes similaires.

