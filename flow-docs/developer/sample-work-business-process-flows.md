---
title: 'Exemple : utiliser des flux de processus d’entreprise | MicrosoftDocs'
description: L’exemple montre comment travailler par programmation avec des flux de processus d’entreprise, tels que la récupération des instances de flux de processus d’entreprise pour un enregistrement d’entité, la récupération du chemin d’accès actif pour une instance de flux de processus d’entreprise et ses étapes de processus, et la modification de la étape active.
ms.custom: ''
ms.date: 04/05/2018
ms.reviewer: ''
ms.service: flow
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
ms.assetid: 7d378504-b4b2-4a09-838c-69ee094072ef
caps.latest.revision: 15
author: msftman
ms.author: deonhe
search.app:
- Flow
search.audienceType:
- developer
ms.openlocfilehash: 2eb6f7586ddc8d5bf51b9c57f91bbc5c7c10131b
ms.sourcegitcommit: 510706f5699b6cf9dda9dcafbed715f9f6d559e8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2019
ms.locfileid: "73547749"
---
# <a name="sample-work-with-business-process-flows"></a>Exemple : utiliser des flux de processus d’entreprise
[!INCLUDE [view-pending-approvals](../includes/cc-rebrand.md)]

Cet exemple montre comment travailler par programmation avec des flux de processus d’entreprise, tels que la récupération des instances de flux de processus d’entreprise pour un enregistrement d’entité, la récupération du chemin d’accès actif pour une instance de flux de processus d’entreprise et ses étapes de processus, et la modification de la étape active. Pour plus d’informations sur ces concepts, consultez [utiliser des flux de processus d’entreprise à l’aide de code](business-process-flows-code.md)  

 Cet exemple peut être téléchargé à partir de l' [exemple : travailler avec des flux de processus d’entreprise](https://go.microsoft.com/fwlink/p/?LinkId=846108).  

<a name="BKMK_Prerequisites"></a>   
## <a name="prerequisites"></a>Conditions préalables  
 Avant de pouvoir exécuter l’exemple :  

1. Avoir accès à un environnement de Common Data Service.  

2. Disposer des privilèges appropriés sur les entités Prospect, opportunité et flux de travail, ainsi que sur les enregistrements d’entité de définition de flux de processus d’entreprise utilisés dans cet exemple.  

3. Disposer de Visual Studio 2015 ou version ultérieure pour exécuter l’exemple.  

4. Disposer d’une connexion Internet pour télécharger l’exemple de projet et restaurer les packages NuGet utilisés dans l’exemple de projet.  

<a name="BKMK_WhatThisSampleDoes"></a>   
## <a name="what-this-sample-does"></a>Ce que fait cet exemple  

1.  Crée un exemple d’enregistrement de prospect. Cette opération crée automatiquement une instance du processus d’entreprise « Prospect-processus de vente des opportunités » pour l’enregistrement du prospect.  

2.  Convertit l’enregistrement de prospect en enregistrement opportunité.  


4.  Récupère les instances de workflow de processus d’entreprise associées à l’enregistrement « opportunité » à l’aide du message de `RetrieveProcessInstances`. Dans ce cas, le premier enregistrement de la collection retournée correspond à l’instance active de workflow de processus d’entreprise pour l’enregistrement d’opportunité.  

5.  Récupère le chemin d’accès actif et les étapes de processus pour l’instance « Prospect to opportunité Sales Process » à l’aide du message `RetrieveActivePath`.  

6.  Récupère l’étape actuellement active pour l’instance « Prospect to opportunité Sales process » et invite l’utilisateur à passer à l’étape suivante. À la confirmation du déplacement, définit l’étape suivante dans le chemin d’accès actif comme étape active pour l’instance « diriger vers le processus de vente d’opportunités ».  

7.  Enfin, demande à l’utilisateur s’il faut supprimer les enregistrements créés au cours de l’exécution de l’exemple.  

     Voici la sortie de l’exemple :  

    ![Exemple de sortie](media/work-with-bpf-sample-output.png "Exemple de sortie")  

<a name="BKMK_runSample"></a>   
## <a name="run-the-sample"></a>Exécuter l’exemple  

1. [Téléchargez](https://go.microsoft.com/fwlink/p/?LinkId=846108) l’exemple de projet WorkWithBPF Visual Studio et extrayez-le dans un dossier sur votre ordinateur.  

2. Localisez le fichier `WorkWithBPF.sln` dans votre dossier extrait, puis ouvrez-le dans Visual Studio.  

3. L’exemple de projet utilise des packages NuGet qui doivent être restaurés avant l’exécution de l’exemple. Assurez-vous que la restauration automatique des packages NuGet est activée dans Visual Studio. Pour plus d’informations : [activation et désactivation de la restauration des packages NuGet](https://go.microsoft.com/fwlink/?linkid=846106)  

    Vous pouvez également sélectionner **projet** > **gérer les packages NuGet**, puis sélectionner **restaurer** pour restaurer manuellement les packages utilisés dans l’exemple.  

4. Appuyez sur F5 ou sélectionnez **Déboguer** > **Démarrer le débogage**.  

5. Si vous n’avez pas encore exécuté l’un des exemples auparavant, vous devez entrer des informations pour exécuter le code. sinon, entrez le numéro de l’une des instances que vous avez configurées précédemment.  


   |                                 Prompt                                  |                                                                                             Descriptive                                                                                             |
   |-------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |      Entrez un nom et un port de serveur Dynamics 365 [crm.dynamics.com]       | Tapez le nom de votre serveur Dynamics 365. La valeur par défaut est Dynamics 365 (Online) (crm.dynamics.com) dans Amérique du Nord.<br /><br /> Tels <br />crm5.dynamics.com |
   | Cette organisation est-elle approvisionnée dans Microsoft services en ligne (y/n) [n] |                                                 Tapez **o** s’il s’agit d’une organisation Microsoft services en ligne configurée. Sinon, tapez **n**.                                                  |
   |                          Entrer domaine\nom_utilisateur                          |                                                                                    Tapez votre compte Microsoft.                                                                                     |
   |                             Entrer le mot de passe                              |                      Tapez votre mot de passe. Les caractères s’affichent sous la forme «\*» dans la fenêtre. Votre mot de passe est enregistré en toute sécurité dans le gestionnaire d’informations d’identification Microsoft pour une réutilisation ultérieure.                       |
   |                Spécifier un numéro d’organisation (1-n) [1]                 |                      Dans la liste des organisations à laquelle vous appartenez, tapez le nombre correspondant. La valeur par défaut est 1, ce qui indique la première organisation de la liste.                       |


6. L’exemple effectue les opérations décrites dans ce [que fait cet exemple](#what-this-sample-does) et peut vous demander des options supplémentaires.  

7. Une fois l’exemple terminé, appuyez sur entrée pour fermer la fenêtre de console.  

