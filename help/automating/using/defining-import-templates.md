---
title: Définir un modèle d'import
description: Les modèles d'import permettent de réduire les paramètres nécessaires et d'importer plus rapidement les données.
page-status-flag: never-activated
uuid: 651eb57c-adac-4e3e-b454-b39aea1f0484
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 85d13147-fb31-446a-8476-f112c841fb82
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Définir un modèle d&#39;import{#defining-import-templates}

Les modèles d&#39;import permettent à l&#39;administrateur de prédéfinir un certain nombre de configurations d&#39;import techniques. Ces modèles peuvent être ensuite mis à la disposition des utilisateurs standard pour gérer et charger les fichiers.

An import template is defined by the functional administrator and can be managed under the **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Import templates]** menu.

![](assets/import_template_list.png)

Trois modèles par défaut sont disponibles en lecture seule :

* **[!UICONTROL Update Direct mail quarantines and delivery logs]**: ce modèle peut servir de base à de nouvelles importations pour mettre à jour les quarantaines et les logs de diffusion pour le Courrier. Le workflow de ce modèle contient les activités suivantes :
* **[!UICONTROL Import data]**: ce modèle peut servir de base à de nouvelles importations pour insérer des données d&#39;un fichier dans la base de données. Le workflow de ce modèle contient les activités suivantes :

   * **[!UICONTROL Load file]**: cette activité vous permet de télécharger un fichier sur le serveur Adobe Campaign.
   * **[!UICONTROL Update data]**: cette activité vous permet d&#39;insérer des données du fichier dans la base de données.

* **[!UICONTROL Import list]**: ce modèle peut servir de base à de nouvelles importations pour créer une audience de type **Liste** à partir des données d’un fichier. Le workflow de ce modèle contient les activités suivantes :

   * **[!UICONTROL Load file]**: cette activité vous permet de télécharger un fichier sur le serveur Adobe Campaign.
   * **[!UICONTROL Reconciliation]**: cette activité vous permet de lier une dimension de ciblage à des données importées. Cela permet ensuite de créer une audience de type **Liste**. Si la dimension de ciblage des données importées n&#39;est pas connue, l&#39;audience est de type **Fichier**. Voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Save audience]**: cette activité vous permet d&#39;enregistrer des données importées sous la forme d&#39;une audience de type **Liste** . Le nom de l&#39;audience sauvegardée correspondra au nom du fichier importé par l&#39;utilisateur, auquel sera ajouté un suffixe précisant la date et l&#39;heure de l&#39;import. Par exemple : &#39;profiles_20150406_151448&#39;.

Ces modèles par défaut sont en lecture seule et ne sont pas visibles par les utilisateurs standards. Pour créer un modèle mis à la disposition des utilisateurs, procédez comme suit :

1. Dupliquez le modèle par défaut de votre choix. Le modèle dupliqué contient trois onglets :

   * **[!UICONTROL Properties]**: les paramètres généraux du modèle d&#39;import. Cet onglet permet notamment d&#39;activer le modèle et de charger un fichier d&#39;exemple.
   * **[!UICONTROL Workflow]**: processus d’importation. Cet onglet permet de définir les activités du workflow. Ces activités ne seront pas visibles lors des imports simplifiés réalisés par les utilisateurs.
   * **[!UICONTROL Executed imports]**: liste des importations effectuées à l&#39;aide de ce modèle. Vous pouvez visualiser le statut, le détail et les résultats de chaque import réalisé à partir du modèle. Vous pouvez accéder directement au workflow (exécuté de manière transparente pour l&#39;utilisateur) à partir de cette liste.

1. From the **[!UICONTROL Properties]** tab, rename the template and add a description. La description sera visible par les utilisateurs lorsque le modèle sera disponible.

   ![](assets/simplified_import_model1.png)

1. Go to the **[!UICONTROL Workflow]** tab. Vous pouvez ici enrichir le workflow proposé par défaut en y ajoutant de nouvelles activités, selon vos besoins.

   Pour plus d&#39;informations sur la configuration des activités de workflow, reportez-vous au cas d&#39;utilisation de la section suivante : [Exemple : modèle de workflow d&#39;import](../../automating/using/importing-data.md#example--import-workflow-template). Ce cas d&#39;utilisation vous aidera à configurer un workflow réutilisable pour importer des profils provenant d&#39;un CRM dans la base de données Adobe Campaign.

1. Enregistrez votre modèle pour que le paramétrage du workflow soit correctement pris en compte.
1. Upload a sample file from the **[!UICONTROL Properties]** tab. Le fichier chargé peut contenir uniquement les colonnes nécessaires aux futurs imports ou des données d&#39;exemple. La présence de données dans le fichier d&#39;exemple permet de tester l&#39;import simplifié une fois le workflow défini.

   ![](assets/import_template_sample.png)

   Ce fichier d&#39;exemple sera par la suite disponible pour les utilisateurs utilisant le modèle pour réaliser un import. Ils pourront le télécharger sur leur poste afin par exemple de le remplir avec les données à importer. Prenez ce facteur en compte au moment d&#39;ajouter le fichier d&#39;exemple.

1. Enregistrez votre modèle. Le fichier d&#39;exemple est désormais bien pris en compte. At any moment you can download it to your computer to check the content, or modify it by checking the **[!UICONTROL Drop a new sample file]** option.

   ![](assets/simplified_import_model2.png)

1. Go back to the **[!UICONTROL Workflow]** tab and open the **[!UICONTROL Load file]** activity to check and adjust the column configuration of the sample file that was uploaded at the previous step.
1. Testez l&#39;import en lançant l&#39;exécution du workflow. Le fichier d&#39;exemple chargé à l&#39;étape **5** doit contenir des données.

   Les données du fichier d&#39;exemple sont alors réellement importées. Veillez à utiliser des données factices et peu nombreuses afin de ne pas compromettre votre base de données.

1. Accédez au journal d&#39;exécution du workflow, disponible via la barre d&#39;actions. En cas d&#39;erreurs vérifiez le paramétrage des activités.

   ![](assets/simplified_import_model3.png)

1. Dans l’ **[!UICONTROL Properties]** onglet, définissez le paramètre **[!UICONTROL Import template status]** sur **[!UICONTROL Available]**, puis enregistrez le modèle. Pour arrêter d’utiliser ce modèle, vous pouvez définir le **[!UICONTROL Import template status]** paramètre sur **[!UICONTROL Archived]**.

The template workflow can be modified by re-uploading the sample file and checking the **[!UICONTROL Load file]** configuration.

Le modèle d&#39;import est à présent disponible pour les utilisateurs et peut être utilisé pour charger les fichiers.

**Rubriques connexes :**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Importer des données](../../automating/using/importing-data.md)
* [Exemple : modèle de workflow d&#39;import ](../../automating/using/importing-data.md#example--import-workflow-template)

