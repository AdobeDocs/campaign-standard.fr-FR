---
solution: Campaign Standard
product: campaign
title: Définir un modèle d'import
description: Les modèles d'import permettent de réduire les paramètres nécessaires et d'importer plus rapidement les données.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 100%

---


# Définir un modèle d&#39;import{#defining-import-templates}

Les modèles d&#39;import permettent à l&#39;administrateur de prédéfinir un certain nombre de configurations d&#39;import techniques. Ces modèles peuvent être ensuite mis à la disposition des utilisateurs standard pour gérer et charger les fichiers.

Un modèle d&#39;import est défini par l&#39;administrateur fonctionnel et peut être géré depuis le menu **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles d&#39;import]**.

![](assets/import_template_list.png)

Trois modèles par défaut sont disponibles en lecture seule :

* **[!UICONTROL Mettre à jour les logs de diffusion et les mises en quarantaine Courrier]** : ce modèle peut servir de base pour de nouveaux imports permettant de mettre à jour les mises en quarantaine et les logs de diffusion du canal Courrier. Le workflow de ce modèle contient les activités suivantes :
* **[!UICONTROL Import de données]** : ce modèle peut servir de base pour de nouveaux imports permettant d&#39;insérer les données d&#39;un fichier dans la base de données. Le workflow de ce modèle contient les activités suivantes :

   * **[!UICONTROL Chargement de fichier]** : cette activité permet de télécharger un fichier de données sur le serveur Adobe Campaign.
   * **[!UICONTROL Mise à jour de données]** : cette activité permet d&#39;insérer les données du fichier dans la base de données.

* **[!UICONTROL Import de liste]** : ce modèle peut servir de base pour de nouveaux imports permettant de créer une audience de type **Liste** à partir des données d&#39;un fichier. Le workflow de ce modèle contient les activités suivantes :

   * **[!UICONTROL Chargement de fichier]** : cette activité permet de télécharger un fichier de données sur le serveur Adobe Campaign.
   * **[!UICONTROL Réconciliation]** : cette activité permet d&#39;associer une dimension de ciblage aux données importées. Cela permet ensuite de créer une audience de type **Liste**. Si la dimension de ciblage des données importées n&#39;est pas connue, l&#39;audience est de type **Fichier**. Voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * **[!UICONTROL Sauvegarde d&#39;audience]** : cette activité permet d&#39;enregistrer les données importées sous la forme d&#39;audience de type **Liste**. Le nom de l&#39;audience sauvegardée correspondra au nom du fichier importé par l&#39;utilisateur, auquel sera ajouté un suffixe précisant la date et l&#39;heure de l&#39;import. Par exemple : &#39;profiles_20150406_151448&#39;.

Ces modèles par défaut sont en lecture seule et ne sont pas visibles par les utilisateurs standards. Pour créer un modèle mis à la disposition des utilisateurs, procédez comme suit :

1. Dupliquez le modèle par défaut de votre choix. Le modèle dupliqué contient trois onglets :

   * **[!UICONTROL Propriétés]** : paramètres généraux du modèle d&#39;import. Cet onglet permet notamment d&#39;activer le modèle et de charger un fichier d&#39;exemple.
   * **[!UICONTROL Workflow]** : workflow d&#39;import. Cet onglet permet de définir les activités du workflow. Ces activités ne seront pas visibles lors des imports simplifiés réalisés par les utilisateurs.
   * **[!UICONTROL Imports exécutés]** : liste des imports réalisés à l&#39;aide de ce modèle. Vous pouvez visualiser le statut, le détail et les résultats de chaque import réalisé à partir du modèle. Vous pouvez accéder directement au workflow (exécuté de manière transparente pour l&#39;utilisateur) à partir de cette liste.

1. Depuis l&#39;onglet **[!UICONTROL Propriétés]**, renommez le modèle et ajoutez une description. La description sera visible par les utilisateurs lorsque le modèle sera disponible.

   ![](assets/simplified_import_model1.png)

1. Accédez à l&#39;onglet **[!UICONTROL Workflow]**. Vous pouvez ici enrichir le workflow proposé par défaut en y ajoutant de nouvelles activités, selon vos besoins.

   Pour plus d&#39;informations sur la configuration des activités de workflow, reportez-vous au cas d&#39;utilisation de la section suivante : [Exemple : modèle de workflow d&#39;import](../../automating/using/creating-import-workflow-templates.md). Ce cas d&#39;utilisation vous aidera à configurer un workflow réutilisable pour importer des profils provenant d&#39;un CRM dans la base de données Adobe Campaign.

1. Enregistrez votre modèle pour que le paramétrage du workflow soit correctement pris en compte.
1. Chargez un fichier d&#39;exemple depuis l&#39;onglet **[!UICONTROL Propriétés]**. Le fichier chargé peut contenir uniquement les colonnes nécessaires aux futurs imports ou des données d&#39;exemple. La présence de données dans le fichier d&#39;exemple permet de tester l&#39;import simplifié une fois le workflow défini.

   ![](assets/import_template_sample.png)

   Ce fichier d&#39;exemple sera par la suite disponible pour les utilisateurs utilisant le modèle pour réaliser un import. Ils pourront le télécharger sur leur poste afin par exemple de le remplir avec les données à importer. Prenez ce facteur en compte au moment d&#39;ajouter le fichier d&#39;exemple.

1. Enregistrez votre modèle. Le fichier d&#39;exemple est désormais bien pris en compte. Vous pouvez à tout moment le télécharger sur votre poste afin d&#39;en vérifier le contenu, ou le modifier en cochant l&#39;option **[!UICONTROL Déposer un nouveau fichier d&#39;exemple]**.

   ![](assets/simplified_import_model2.png)

1. Revenez à l&#39;onglet **[!UICONTROL Workflow]** et ouvrez l&#39;activité de **[!UICONTROL Chargement de fichier]** afin de vérifier et ajuster le paramétrage des colonnes du fichier d&#39;exemple chargé à l&#39;étape précédente.
1. Testez l&#39;import en lançant l&#39;exécution du workflow. Le fichier d&#39;exemple chargé à l&#39;étape **5** doit contenir des données.

   Les données du fichier d&#39;exemple sont alors réellement importées. Veillez à utiliser des données factices et peu nombreuses afin de ne pas compromettre votre base de données.

1. Accédez au journal d&#39;exécution du workflow, disponible via la barre d&#39;actions. En cas d&#39;erreurs vérifiez le paramétrage des activités.

   ![](assets/simplified_import_model3.png)

1. Depuis l&#39;onglet **[!UICONTROL Propriétés]**, définissez le **[!UICONTROL Statut du modèle d&#39;import]** sur **[!UICONTROL Disponible]**, puis enregistrez le modèle. Si vous souhaitez arrêter l&#39;utilisation de ce modèle, vous pouvez définir le **[!UICONTROL Statut du modèle d&#39;import]** sur **[!UICONTROL Archivé]**.

Le workflow du modèle peut être modifié en chargeant de nouveau le fichier d&#39;exemple et en vérifiant la configuration de l&#39;activité **[!UICONTROL Chargement de fichier]**.

Le modèle d&#39;import est à présent disponible pour les utilisateurs et peut être utilisé pour charger les fichiers.

**Rubriques connexes :**

* [Workflows](../../automating/using/get-started-workflows.md)
* [Import et export de données](../../automating/using/about-data-import-and-export.md)
* [Exemple : modèle de workflow d&#39;import ](../../automating/using/creating-import-workflow-templates.md)

