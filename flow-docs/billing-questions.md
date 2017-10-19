---
title: Questions sur la facturation et les compteurs | Microsoft Docs
description: "Réponses aux questions fréquemment posées sur la facturation et la mesure dans Microsoft Flow"
services: 
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: 
tags: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/21/2016
ms.author: deonhe
ms.openlocfilehash: b627c008e1483360f35b6de579e2c0da32e60c93
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="billing-and-metering-questions"></a>Questions relatives à la facturation et à la mesure
Cet article répond aux questions fréquemment posées relatives à la facturation et à la mesure dans Microsoft Flow.

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Où puis-je me renseigner sur les plans de tarification disponibles ?
Consultez la [page de tarification](https://flow.microsoft.com/pricing/).

## <a name="where-can-i-find-out-what-my-plan-is"></a>Comment identifier mon plan ?
Consultez la [page de tarification](https://flow.microsoft.com/pricing/).

## <a name="how-do-i-switch-plans"></a>Comment changer de plans ?
Dans le menu de navigation situé en haut, cliquez ou appuyez sur **Formation**, puis sur **Tarification**.

![En savoir plus > Tarification.](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Comment connaître ma consommation ?
Cliquez ou appuyez sur **Activité** pour afficher les journaux de vos exécutions, ainsi que les notifications et les échecs.

![Lien Activité](./media/billing-questions/activity-link.png)

Si vous avez une offre gratuite ou un essai, cliquez ou appuyez sur l’icône d’engrenage dans la barre de navigation en haut pour afficher l’utilisation actuelle associée à votre offre.   

![Bouton Paramètres](./media/billing-questions/settings.png)

Dans les autres cas, les exécutions sont regroupées pour tous les utilisateurs de votre organisation. Nous travaillons sur des fonctionnalités permettant d’exposer le quota disponible et l’utilisation dans une organisation.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Que se passe-t-il si ma consommation dépasse les limites ?
Il se peut que Microsoft Flow commence à limiter les exécutions.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Où puis-je trouver plus d’informations sur les limites d’utilisation ?
Sur la [page de tarification](https://flow.microsoft.com/pricing/), consultez la section **FAQ**.

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Que se passe-t-il si je lance trop fréquemment des exécutions ?
Votre offre détermine la fréquence à laquelle vos flux s’exécutent. Par exemple, si vous bénéficiez de l’offre gratuite, vos flux peuvent être exécutés toutes les 15 minutes. Si un flux est déclenché moins de 15 minutes après son exécution la plus récente, il est mis en file d’attente jusqu’à ce que les 15 minutes soient écoulées. Les recherches de nouvelles données ne sont pas comptabilisées en tant qu’exécutions.

## <a name="what-counts-as-a-run"></a>Qu’entend-on par exécution ?
Chaque fois qu’un flux est déclenché, qu’il s’agisse d’un lancement automatique ou manuel, nous parlons d’une exécution.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Existe-t-il des différences entre les comptes Microsoft et les comptes scolaires ou professionnels en matière de facturation ?
Oui. Si vous vous connectez avec un compte Microsoft (tel qu’un compte qui se termine par @outlook.com ou @gmail.com), vous pouvez utiliser uniquement l’offre gratuite. Pour tirer parti des fonctionnalités de l’offre payante, connectez-vous avec un ID de messagerie professionnel ou scolaire.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>J’essaie de procéder à une mise à niveau, mais on m’informe de l’inéligibilité de mon compte.
Pour effectuer une mise à niveau, utilisez un compte professionnel ou scolaire ou créez un essai Office 365 en suivant les instructions de [cet article Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Pourquoi suis-je à court d’exécutions alors que mon flux n’a été lancé qu’un faible nombre de fois ?
Certains flux peuvent s’exécuter plus fréquemment que prévu. Par exemple, vous pouvez créer un flux qui envoie une notification Push lorsque votre responsable vous envoie un e-mail. Ce flux doit s’exécuter chaque fois que vous recevez un e-mail (quel que soit l’expéditeur), car il doit vérifier si l’e-mail est envoyé par votre responsable. Cette action est comptabilisée en tant qu’exécution.

Pour contourner ce problème, placez le filtrage nécessaire dans le déclencheur. Dans l’exemple ci-dessus, développez le menu **Options avancées** et spécifiez l’adresse e-mail de votre responsable dans le champ **De**.

## <a name="other-limits-and-caveats"></a>Autres limites et avertissements
* Chaque compte a les limites suivantes :
  * 50 flux
  * 15 connecteurs personnalisés
  * 20 connexions par API et 100 connexions au total
* Vous pouvez installer une passerelle uniquement dans l’environnement par défaut.   
* Certains connecteurs externes, tels que Twitter, implémentent la limitation des connexions afin de contrôler la qualité de service. Une fois que la limitation est effective, vos flux sont mis en échec. Pour consulter les détails de cette limitation, affichez le flux ayant échoué dans l’historique d’exécution du flux.

