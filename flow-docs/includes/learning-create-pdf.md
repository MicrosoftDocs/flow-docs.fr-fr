Cette rubrique décrit comment Contoso Flooring utilise Microsoft Flow pour convertir automatiquement des documents dans un format standard les stocker dans SharePoint Online afin de les garder en lieu sûr dans le cloud. Vous allez créer un flux qui détecte l’ajout d’un fichier à un dossier OneDrive Entreprise, puis convertit ce fichier au format PDF et le stocke dans un dossier SharePoint Online. 

## <a name="prerequisites"></a>Prérequis
Pour ce scénario, vous devez disposer d’un compte **Muhimbi**, un service de conversion au format PDF. Si vous n’avez pas de compte Muhimbi, vous pouvez vous inscrire pour une [évaluation gratuite de 30 jours](http://www.muhimbi.com/Products/PDF-Converter-for-SharePoint/Products-PDF-Converter-for-SharePoint-Free-Trial.aspx). Suivez les instructions de cette page pour déployer l’application sur votre site SharePoint Online. 

## <a name="create-the-source-and-target-folders"></a>Créer les dossiers source et cible
Tout d’abord, vous devez créer les dossiers source et cible sur OneDrive Entreprise et SharePoint Online. 

1. Sur OneDrive Entreprise, sous **Fichiers**, créez un dossier nommé **Documents terminés**. 
   
    ![](./media/learning-create-pdf/onedrive-folder.png)
2. Sur SharePoint Online, dans **Documents partagés**, créez un dossier nommé **PDF – Fichiers terminés**. 
   
    ![](./media/learning-create-pdf/sharepoint-folder.png)

## <a name="create-the-flow"></a>Créer le flux
1. Dans Microsoft Flow, sélectionnez **Mes flux**, puis **Créer entièrement**. 
   
    ![](./media/learning-create-pdf/create-blank-flow.png)
2. Sélectionnez **Rechercher parmi des centaines de connecteurs et déclencheurs**.
3. Recherchez **OneDrive**, sélectionnez **OneDrive Entreprise**, puis le déclencheur **OneDrive Entreprise - Lorsqu’un fichier est créé**. Dans **Dossier**, sélectionnez l’icône de dossier, puis choisissez le dossier **Documents terminés** créé à l’étape précédente. 
   
    ![](./media/learning-create-pdf/onedrive-trigger.png)
4. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**. 
   
    ![](./media/learning-create-pdf/new-action.png)
5. Recherchez **Muhimbi**, sélectionnez le connecteur **PDF Muhimbi**puis l’action **PDF Muhimbi – Convertir le document**.
   
    ![](./media/learning-create-pdf/muhimbi-action.png)
6. À ce stade, Microsoft Flow peut vous inviter à vous authentifier auprès de Muhimbi. Pour que Microsoft Flow utilise le service Muhimbi, vous devrez vous inscrire auprès de Muhimbi en utilisant votre **ID de client SharePoint**. 
   
   1. Pour trouver celui-ci, dans SharePoint Online, sélectionnez l’**Paramètres**, puis choisissez **Paramètres du site**.
   2. Sous **Administration de la collection de sites**, sélectionnez **Autorisations des applications de la collection de sites**. Votre ID de client est l’identificateur qui suit le symbole « **@**» dans toute liste d’applications. 
      
       ![](./media/learning-create-pdf/tenant-id.png)
7. Dans l’action **Convertir le document**, définissez les valeurs suivantes :
   
   * **Nom du fichier source** : dans la liste de contenu dynamique, sélectionnez **Nom du fichier**.
   * **Contenu du fichier source** : dans la liste de contenu dynamique, sélectionnez **Contenu du fichier**.
   * **Format de sortie** : dans la liste déroulante, sélectionnez **PDF**.
     
     ![](./media/learning-create-pdf/muhimbi-configuration.png)

À ce stade, vous avez configuré votre flux comme suit : 

1. Le flux est déclenché à chaque ajout d’un fichier à un dossier OneDrive Entreprise spécifique. 
2. Le service Muhimbi convertit ce fichier au format PDF. 

Pour la dernière étape, vous allez ajouter une action qui déplace le document PDF vers un dossier SharePoint Online où l’équipe peut y accéder.  

1. Sélectionnez **Nouvelle étape**, puis **Ajouter une action**.  Recherchez **SharePoint**, puis sélectionnez l’action **SharePoint – Créer un fichier**. 
   
    ![](./media/learning-create-pdf/sharepoint-create-file.png)
2. Dans l’action **Créer un fichier**, définissez les valeurs suivantes :
   
   * **Adresse du site** : URL de votre site SharePoint.  
   * **Chemin d’accès du dossier** : sélectionnez l’icône de dossier, puis accédez au dossier **PDF - Fichiers terminés**.
   * **Nom de fichier** : dans la liste de contenu dynamique, pour **Convertir le document**, sélectionnez **Nom de fichier de base**, puis ajoutez «  **.pdf** » de façon à ce qu’il soit enregistré dans SharePoint avec cette extension de fichier. 
   * **Contenu du fichier** : dans la liste de contenu dynamique, pour **Convertir le document**, sélectionnez **Contenu de fichier traité**.
3. Sélectionnez **Créer un flux** en haut de la page pour enregistrer votre travail.
   
    ![](./media/learning-create-pdf/sharepoint-configure-file.png)

## <a name="test-the-flow"></a>Tester le flux
1. Pour tester le flux, ajoutez un fichier à votre dossier **Documents terminés** sur OneDrive Entreprise. 
2. Dans Microsoft Flow, sélectionnez **Mes flux**, puis le nouveau flux pour afficher l’historique des exécutions. Par défaut, le flux est configuré pour s’exécuter toutes les cinq minutes. 
3. Une fois le flux exécuté, vérifiez que le fichier a été converti au format PDF et enregistré dans le dossier SharePoint **PDF – Fichiers terminés**. 
   
    ![](./media/learning-create-pdf/test-the-flow.png)

