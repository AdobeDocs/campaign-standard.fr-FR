---
title: Extraction de fichier
description: L'activité Extraction de fichier permet d'exporter des données présentes dans Adobe Campaign sous la forme d'un fichier externe.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 15e5aebdd67e8f5ddee89506c0469a101d94d2e8
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 91%

---


# Extraction de fichier{#extract-file}

## Description {#description}

![](assets/export.png)

L&#39;activité **[!UICONTROL Extraction de fichier]** permet d&#39;exporter des données présentes dans Adobe Campaign sous la forme d&#39;un fichier externe.

## Contexte d&#39;utilisation {#context-of-use}

La façon dont les données seront extraites est définie lors du paramétrage de l&#39;activité.

>[!CAUTION]
>
>L&#39;activité **[!UICONTROL Extraction de fichier]** doit être obligatoirement placée à la suite d&#39;une activité **[!UICONTROL Requête]** pour pouvoir être utilisée.

**Rubriques connexes :**

* [Cas d’utilisation : Exportation de profils dans un fichier externe](../../automating/using/exporting-profiles-in-file.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Extraction de fichier]** dans votre workflow.

   ![](assets/wkf_data_export1.png)

1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Indiquez le libellé du **Fichier de sortie**. Le libellé du fichier sera automatiquement complété avec la date et l&#39;heure de création pour être unique. Par exemple : destinataires_20150815_081532.txt pour un fichier généré le 15 août 2015 à 08h15 et 32 secondes.

   >[!NOTE]
   >
   >Il est possible d&#39;utiliser la fonction **[!UICONTROL formatDate]** dans ce champ pour spécifier le nom du fichier.

1. Si vous le souhaitez, vous pouvez compresser le fichier de sortie en sélectionnant **[!UICONTROL Compression]** au niveau du champ **[!UICONTROL Ajouter une étape de pré-traitement]**. Le fichier de sortie sera compressé dans un fichier GZIP (.gz).

   Le champ **[!UICONTROL Ajouter une étape]** de prétraitement vous permet également de chiffrer un fichier avant de l’extraire. Pour plus d’informations sur la façon de travailler avec des fichiers chiffrés, reportez-vous à [cette section](../../automating/using/managing-encrypted-data.md)

1. Sélectionnez le bouton ![](assets/add_darkgrey-24px.png) ou **[!UICONTROL Ajouter un élément]** pour ajouter une colonne de sortie.

   ![](assets/wkf_data_export2.png)

   Une nouvelle fenêtre s&#39;affiche.

   ![](assets/wkf_data_export3.png)

1. Composez une expression. Pour cela, vous pouvez sélectionner une expression existante ou en créer une nouvelle avec l&#39;**éditeur d&#39;expression**.
1. Validez votre expression.

   L&#39;expression est ajoutée aux colonnes de sortie.

1. Créez autant de colonnes que nécessaire. Vous pouvez éditer les colonnes en cliquant sur leur expression et leur libellé.

   Si vous exportez des profils et si vous souhaitez les utiliser dans un outil externe, veillez à exporter un identifiant unique. Par défaut, tous les profils ne disposent pas d&#39;un identifiant unique. Cela dépend de la façon dont ils ont été ajoutés dans la base de données. Pour plus d&#39;informations, voir la section [Générer un identifiant unique pour les profils](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

1. Cliquez sur l&#39;onglet **[!UICONTROL Structure de fichier]** pour paramétrer les formats de sortie, des dates et des nombres du fichier qui sera exporté.

   Cochez l&#39;option **[!UICONTROL Exporter les libellés plutôt que les valeurs internes des énumérations]** si vous exportez des valeurs d&#39;énumération. Cette option permet de récupérer des libellés plus courts qui sont compréhensibles à la place d&#39;identifiants.

1. Dans l&#39;onglet **[!UICONTROL Propriétés]**, sélectionnez l&#39;option **[!UICONTROL Ne pas générer de fichier si la transition entrante est vide]** pour éviter de créer et télécharger des fichiers vides sur les serveurs SFTP si la transition entrante est vide.
1. Validez le paramétrage de l’activité et enregistrez le workflow.
