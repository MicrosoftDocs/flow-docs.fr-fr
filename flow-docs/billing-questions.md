---
title: Questions sur la facturation et le contrôle | Microsoft Docs
description: Réponses aux questions fréquemment posées sur la facturation et le contrôle des Microsoft Flow
services: ''
suite: flow
documentationcenter: na
author: msftman
manager: aftowen
editor: ''
tags: ''
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/30/2019
ms.author: deonhe
search.app:
- Flow
- Powerplatform
search.audienceType:
- admin
ms.openlocfilehash: 69fecb42ba2b89f7a3f5b7541f62a4ee984832ea
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73546199"
---
# <a name="billing-and-metering-questions"></a>Questions sur la facturation et le contrôle
[!INCLUDE [view-pending-approvals](includes/cc-rebrand.md)]

Cet article répond aux questions fréquemment posées sur la facturation et le contrôle dans Microsoft Flow.

>[!NOTE]
> PowerApps et Microsoft Flow utiliseront un [nouveau modèle de licence](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq) à partir du 1er octobre 2019. 

## <a name="where-can-i-find-out-what-pricing-plans-are-available"></a>Où puis-je trouver les plans de tarification disponibles ?

Consultez la [page](https://flow.microsoft.com/pricing/)relative à la tarification.

## <a name="where-can-i-find-out-what-my-plan-is"></a>Où puis-je trouver mon plan ?

Consultez la [page](https://flow.microsoft.com/pricing/)relative à la tarification.

## <a name="how-do-i-switch-plans"></a>Comment faire changer de plan ?

Dans le menu de navigation supérieur, sélectionnez **en savoir plus** > **tarification**, puis sélectionnez le plan vers lequel vous souhaitez basculer.

![En savoir plus > tarification](./media/billing-questions/learn-pricing.png)

## <a name="how-do-i-know-how-much-ive-used"></a>Comment faire savez combien j’ai utilisé ?

Si vous utilisez un plan gratuit ou une version d’évaluation, cliquez ou appuyez sur l’icône d’engrenage dans la barre de navigation supérieure pour afficher votre utilisation actuelle par rapport à votre plan. 

![Bouton Paramètres](./media/billing-questions/settings.png)

Si vous êtes sur un plan payant, les exécutions sont regroupées pour tous les utilisateurs de votre organisation. Nous travaillons actuellement sur les fonctionnalités pour exposer le quota et l’utilisation disponibles au sein d’une organisation.

## <a name="what-happens-if-my-usage-exceeds-the-limits"></a>Que se passe-t-il si mon utilisation dépasse les limites ?

Microsoft Flow limite vos exécutions de Flow.

## <a name="where-can-i-find-more-information-regarding-the-usage-limits"></a>Où puis-je trouver plus d’informations sur les limites d’utilisation ?

Sur la [page de tarification](https://flow.microsoft.com/pricing/), consultez la section **Forum aux questions** .

## <a name="what-happens-if-i-try-to-execute-runs-too-frequently"></a>Que se passe-t-il si j’essaie d’exécuter des exécutions trop fréquemment ?

Votre plan détermine la fréquence à laquelle vos flux s’exécutent. Par exemple, vos flux peuvent être exécutés toutes les 15 minutes si vous êtes dans le plan gratuit. Si un workflow est déclenché moins de 15 minutes après sa dernière exécution, il est mis en file d’attente jusqu’à 15 minutes.

## <a name="what-counts-as-a-run"></a>Qu’est-ce qui compte comme une exécution ?

Lorsqu’un workflow est déclenché, qu’il s’agisse d’un déclencheur automatique ou d’un démarrage manuel, il est considéré comme une exécution. Vérifie que les nouvelles données ne sont pas comptabilisées comme des exécutions.

## <a name="are-there-differences-between-microsoft-accounts-and-work-or-school-accounts-for-billing"></a>Existe-t-il des différences entre les comptes Microsoft et les comptes professionnels ou scolaires pour la facturation ?

Oui. Si vous vous connectez avec un compte Microsoft (par exemple, un compte qui se termine par @outlook.com ou @gmail.com), vous pouvez utiliser uniquement le plan gratuit. Pour tirer parti des fonctionnalités du plan payant, connectez-vous à l’aide d’une adresse e-mail professionnelle ou scolaire.

## <a name="im-trying-to-upgrade-but-im-told-my-account-isnt-eligible"></a>J’essaie de mettre à niveau, mais j’ai dit que mon compte n’est pas éligible.

Pour mettre à niveau, utilisez un compte professionnel ou scolaire, ou créez un [compte d’essai Office 365](https://powerbi.microsoft.com/documentation/powerbi-admin-signing-up-for-power-bi-with-a-new-office-365-trial/).

## <a name="why-did-i-run-out-of-runs-when-my-flow-only-ran-a-few-times"></a>Pourquoi ai-je manqué de s’exécuter quand mon Flow n’a été exécuté que quelques fois ?

Certains flux peuvent s’exécuter plus fréquemment que prévu. Par exemple, vous pouvez créer un workflow qui vous envoie une notification push chaque fois que votre responsable vous envoie un e-mail. Ce Flow doit s’exécuter chaque fois que vous recevez un e-mail (d’une personne), car celui-ci doit vérifier si l’e-mail provient de votre responsable. Cette action compte comme une exécution.

Vous pouvez contourner ce problème en plaçant tout le filtre dont vous avez besoin dans le déclencheur. Dans l’exemple de notification push, développez le menu **Options avancées** , puis indiquez l’adresse e-mail de votre responsable dans le champ **de** .

## <a name="other-limits-and-caveats"></a>Autres limites et avertissements

* Chaque compte peut avoir jusqu’à :
  * 250 flux.
  * 15 connecteurs personnalisés.
  * 20 connexions par API et 100 de connexion au total.
* Vous pouvez installer une passerelle uniquement dans l’environnement par défaut.
* Certains connecteurs externes, tels que Twitter, implémentent la limitation des connexions pour contrôler la qualité de service. Vos flux échouent lorsque la limitation est appliquée. Si vos flux échouent, passez en revue les détails de l’exécution qui a échoué dans l’historique des exécutions du flux.
