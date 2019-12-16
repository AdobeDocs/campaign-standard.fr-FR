---
title: ' Exportation/importation de ressources personnalisées'
description: Ce didacticiel explique comment exporter et importer un package de ressources personnalisées.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 71ee939b6ef256be8c693ec6e15d9609c7e80677

---


# Exporting / importing custom resources {#exporting-importing-custom-resources}

Ce tutoriel a pour objectif d'exporter et d'importer un package de ressources personnalisées d'un environnement de développement vers un environnement de production.

Cet exemple est destiné aux administrateurs fonctionnels liés à Adobe Campaign.

Les prérequis sont :

* **Une ou plusieurs ressources** personnalisées disponibles et publiées.

   En outre, vous devez avoir défini une clé unique pour ces ressources, car les clés primaires automatiques ne sont pas exportées dans les packages. La ressource peut donc avoir une clé primaire et une clé unique supplémentaire pour garantir l'unicité des documents.
* **Avoir les droits nécessaires** pour créer et exporter un package.

Ressources supplémentaires :

* [Gestion des packages](../../automating/using/managing-packages.md)
* [Déploiement des packages : Principe de fonctionnement](../../developing/using/data-model-concepts.md)
* [Ajouter ou étendre une ressource](../../developing/using/key-steps-to-add-a-resource.md)

## Step 1: Exporting the structure {#exporting-the-structure}

Dans cette partie, nous allons faire un premier export de package qui décrit la structure physique des données de la ressource personnalisée.

Cet exemple comporte deux ressources personnalisées **Produits** et **Commandes**.

1. Accédez au menu d’exportation **** Administration **[!UICONTROL /]** Déploiement **[!UICONTROL /]** Package.

   Nous allons créer un package pour exporter la ressource **[!UICONTROL personnalisée (cusResource)]** filtrée avec les deux ressources personnalisées, "Produits" et "Commandes".

1. Dans la page **[!UICONTROL Exports de package]**, cliquez sur **Créer]pour créer un nouveau package.[!UICONTROL **
1. Remplissez le libellé, puis cliquez sur **[!UICONTROL Créer un élément]**.

   ![](assets/cusresources_export1.png)

1. Recherchez et sélectionnez la ressource **[!UICONTROL Ressource personnalisée (cusResource)]**.

   ![](assets/cusresources_export2.png)

1. Configure the details of the **[!UICONTROL Custom resource]** by selecting the two resources, **Products** and **Orders**, in the filtering conditions.

   N'oubliez pas de modifier l'opérateur logique. La valeur doit être **OU** pour que la structure de la ressource produits et la structure de la ressource commandes soient intégrées dans le package.

   ![](assets/cusresources_export3.png)

1. Validez et enregistrez la définition du package.

Vous pouvez maintenant cliquer sur **[!UICONTROL Démarrer l'export]**.

![](assets/cusresources_export4.png)

Le package généré est disponible dans le dossier Téléchargements. Le nom du fichier zip est généré aléatoirement. Vous pouvez le renommer.

## Exporter les données {#exporting-the-data}

Ce second export va permettre d'exporter les données des ressources personnalisées **Produits** et **Commandes**.

En se basant sur le même type d'export que l'export de la structure, vous allez créér un deuxième package contenant les données.

1. Dans la page **[!UICONTROL Exports de package]**, cliquez sur **Créer]pour créer un nouveau package.[!UICONTROL **
1. Complétez le libellé avec le label **[!UICONTROL Export données de mes ressources]** puis cliquez sur **[!UICONTROL Créer un élément]dans l'onglet** Définition de l'export **.**
1. Recherchez et sélectionnez la ressource **Produits**.

   ![](assets/cusresources_exportdata1.png)

1. Configurez une condition **de** filtrage avancée avec **@Label IS NOT NULL**.

   ![](assets/cusresources_exportdata2.png)

1. Vérifiez le décompte.

   ![](assets/cusresources_exportdata3.png)

1. Répétez la même opération pour la ressource personnalisée **Commandes**.

   ![](assets/cusresources_exportdata4.png)

1. Validez et enregistrez la définition du package.

Vous pouvez maintenant cliquer sur **[!UICONTROL Démarrer l'export]**.

![](assets/cusresources_exportdata5.png)

Le package généré est disponible dans le dossier Téléchargements. Le nom du fichier zip est généré aléatoirement. Vous pouvez le renommer.

## Importer la structure {#importing-the-structure}

### Importer le package {#importing-the-structure-package}

1. Connectez vous à l'**instance cible** sur laquelle vous voulez importer les packages qui viennent d'être créés.
1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** menu to create a new package to import the file from the first export.
1. Glissez / déposez le **fichier structure** dans la zone prévue. Les formats acceptés sont ZIP ou XML.

   ![](assets/cusresources_import2.png)

1. Modifiez le libellé, par exemple **Import structure** puis cliquez sur **[!UICONTROL Enregistrer]**.
1. Cliquez sur **[!UICONTROL Démarrer l'import]**.

   ![](assets/cusresources_import3.png)

### Publier {#publish-structure}

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** menu.
1. Cliquez sur **[!UICONTROL Préparer la publication]** puis sur **Publier]afin de mettre à jour l'instance avec les nouvelles ressources personnalisées.[!UICONTROL **
1. Les entrées de menu correspondant au package installé vont s'insérer dans le menu **[!UICONTROL Données client].**

   ![](assets/cusresources_import1.png)

## Importer les données {#importing-the-data}

Dans cette partie, nous allons **importer les données** liées au package installé sur l'instance dans l'étape précédente.

De la même manière, l'étape se découpe en deux parties: l'import du package et une publication.

### Importer le package {#importing-the-data-package}

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Deployment]** / **[!UICONTROL Package imports]** menu to create a new package to import the file containing the data.
1. Glissez / déposez le fichier des données dans la zone prévue. Les formats acceptés sont ZIP ou XML.
1. Modify the label, for example "Import data", then click **[!UICONTROL Save]**.
1. Cliquez sur **[!UICONTROL Démarrer l'import]**.

   ![](assets/cusresources_importdata.png)

### Publier {#publish-data}

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Publication]** menu.
1. Cliquez sur **[!UICONTROL Préparer la publication]** puis sur **Publier]afin de mettre à jour l'instance avec les données des ressources personnalisées.[!UICONTROL **
