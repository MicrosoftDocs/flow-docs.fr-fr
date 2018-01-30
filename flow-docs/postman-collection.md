---
title: "Décrire un connecteur personnalisé avec Postman | Microsoft Docs"
description: "Créer un fichier Postman Collection pour l’inscription des connecteurs personnalisés"
services: 
suite: flow
documentationcenter: 
author: sunaysv
manager: anneta
editor: 
ms.service: flow
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: sunayv
ms.openlocfilehash: fe98999ea307367c7f3b032974fef9be6ca3f388
ms.sourcegitcommit: 4f2cb27d392f46aa1d8680d6278876780ed3871b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/15/2017
---
# <a name="describe-a-custom-connector-with-postman"></a>Décrire un connecteur personnalisé avec Postman
[Postman](https://www.getpostman.com/) est un outil qui permet de créer des développements d’API plus rapides et faciles. Ce tutoriel montre comment créer un fichier Postman Collection, que vous pouvez ensuite utiliser pour créer facilement des [connecteurs personnalisés](register-custom-api.md) dans Microsoft Flow.

## <a name="prerequisites"></a>Conditions préalables
* Installez l’[application Postman](https://www.getpostman.com/apps).

## <a name="create-a-postman-collection"></a>Créer un fichier Postman Collection
Commençons par créer un fichier Postman Collection pour l’[API Analyse de texte](https://www.microsoft.com/cognitive-services/text-analytics-api) Azure Cognitive Services. Cette API identifie la langue, les sentiments et les expressions clés dans le texte que vous lui transmettez.

1. La première étape de création d’un fichier Postman Collection consiste à créer une demande. Lors de la création de la demande, vous pouvez définir le verbe HTTP, l’URL de demande, les paramètres de requête ou de chemin d’accès, les en-têtes et le corps. Pour plus d’informations, consultez [Envoi de demandes](https://www.getpostman.com/docs/requests) dans la documentation Postman. Pour le point de terminaison API Détecter la langue, définissez les valeurs comme suit :
   
    ![Demande Postman](./media/postman-collection/request.png)
   
    Détails des paramètres et valeurs utilisés :
   
   | Paramètre | Valeur |
   | --- | --- |
   | Verbe |POST |
   | URL de demande |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Paramètres |numberOfLanguagesToDetect |
   | Autorisation |« Aucune authentification » |
   | En-têtes |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Corps |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Cliquez sur **Envoyer** pour effectuer la demande et obtenir la réponse.
3. Cliquez sur **Enregistrer** pour enregistrer la demande dans un fichier Postman Collection.
   
    ![Réponse Postman](./media/postman-collection/request-response-save.png)
4. Indiquez le **nom** et la **description** de la demande dans la boîte de dialogue **Save Request (Enregistrer la demande)**. Vous utiliserez ces valeurs dans votre connecteur personnalisé.
   
    ![Postman Collection - Enregistrer](./media/postman-collection/save-request-note.png)
   
    Vous pouvez également enregistrer la réponse dans la demande. Les connecteurs personnalisés prennent actuellement en charge une seule réponse par demande. Si vous enregistrez plusieurs réponses par demande, seule la première est utilisée.
   
    ![Postman - Enregistrer la réponse](./media/postman-collection/save-response.png)
5. Poursuivez l’élaboration de votre fichier Postman Collection en créant et en enregistrant d’autres demandes et réponses.
6. Une fois que vous avez terminé la génération du fichier Postman Collection pour toutes les demandes et réponses, exportez la collection.
   
    ![Exportation Postman](./media/postman-collection/export.png)
7. Choisissez **Collection v1** comme format d’exportation.
   
    ![Exportation Postman](./media/postman-collection/export2.png)

Vous pouvez maintenant utiliser ce fichier Postman Collection pour créer un connecteur personnalisé dans Microsoft Flow.

> [!IMPORTANT]
> Lorsque vous créez un connecteur personnalisé à partir d’une collection Postman, veillez à supprimer l’en-tête `Content-type` des actions et déclencheurs, car il est automatiquement ajouté par Microsoft Flow. Les en-têtes d’authentification (par exemple `Ocp-Apim-Subscription-Key`) doivent être définis dans la section **Sécurité** et être supprimés des actions et déclencheurs. 
> 
> 

Pour plus d’informations, consultez [Inscrire et utiliser des connecteurs personnalisés dans Microsoft Flow](register-custom-api.md).

