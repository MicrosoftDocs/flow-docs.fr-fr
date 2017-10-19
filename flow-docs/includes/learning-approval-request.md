Dans une rubrique précédente, vous avez vu comment générer un processus d’approbation autour de tweets stockés dans une liste SharePoint.  Cette rubrique décrit ce qui se passe quand un approbateur reçoit une nouvelle demande d’approbation. 

## <a name="create-and-process-a-request"></a>Créer et traiter une demande
Avant de pouvoir traiter une demande d’approbation pour un élément, nous devons ajouter cet élément à notre liste SharePoint.

1. Ouvrez la liste SharePoint **TweetsContoso** établie dans le cadre d’une rubrique précédente.  Sélectionnez **Nouveau** pour créer un tweet. 
   
    ![Liste SharePoint](./media/learning-approval-request/sharepoint-list-home.png)
2. Ajoutez les valeurs suivantes aux champs, puis sélectionnez **Enregistrer**.
   
   * **Title** : Promotions.
   * **TweetContent** : extrayez la nouvelle ligne de Contoso Flooring #ohsocontoso.
   * **TweetDate** : date du jour.
     
     ![Nouvel élément SharePoint](./media/learning-approval-request/sharepoint-new-tweet.png)
3. Dans **Microsoft Flow**, sélectionnez **Mes flux**. 
4. Sélectionnez le flux **Postez des éléments de liste sur Twitter après approbation** configuré dans la rubrique précédente, puis choisissez le flux en cours d’exécution sous **Historique des exécutions**.
   
    ![Historique des exécutions](./media/learning-approval-request/run-history.png)
5. Sélectionnez le déclencheur **Lorsqu’un élément est créé**. Vérifiez que les informations relatives à l’élément de liste que vous venez de créer s’affichent.
   
    ![Déclencheur de flux](./media/learning-approval-request/approval-flow.png)
6. Dans **Outlook**, ouvrez l’e-mail d’approbation automatisé dans la boîte de réception, puis sélectionnez **Approuver**. 
   
    ![Demande Outlook](./media/learning-approval-request/outlook-mail.png)
7. Dans le **Centre d’approbation**, consultez les détails de la demande, ajoutez un commentaire, puis sélectionnez **Confirmer**. 
   
    ![Centre d’approbation](./media/learning-approval-request/approval-center.png)
8. Dans **SharePoint**, actualisez la liste **TweetsContoso**, puis vérifiez que **ÉtatApprobation** est **Oui**, et que le commentaire que vous avez entré est affiché. 
   
    ![Actualiser la liste SharePoint](./media/learning-approval-request/sharepoint-list-approved.png)

Dans cette rubrique, vous avez vu l’expérience du point de vue d’un approbateur : de la réception d’un e-mail de demande d’approbation au traitement de la demande dans le Centre d’approbation.

