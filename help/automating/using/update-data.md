---
title: Mise à jour de données
description: L'activité Mise à jour de données permet de mettre à jour en masse les champs de la base de données.
page-status-flag: never-activated
uuid: 1dc55db5-affd-4688-b673-adfb8c1338b5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 4db83c95-4b75-4a16-8dbf-bd8940431fa9
context-tags: writer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 100%

---


# Mise à jour de données{#update-data}

## Description {#description}

![](assets/data_update.png)

L&#39;activité **[!UICONTROL Mise à jour de données]** permet de mettre à jour en masse les champs de la base de données.

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **Mise à jour de données** peut notamment être utilisée suite à un import de fichier, afin d&#39;insérer les données récupérées dans la base de données Adobe Campaign. Plusieurs options permettent de personnaliser la mise à jour des données.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Mise à jour de données]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Définissez le **[!UICONTROL Type d&#39;opération]** à réaliser :

   * **[!UICONTROL Ajouter ou mettre à jour]** : ajouter des données ou les mettre à jour si des enregistrements existent déjà dans la base.
   * **[!UICONTROL Ajouter uniquement]** : ajouter des données uniquement. Les enregistrements déjà existants ne sont pas mis à jour. Si des critères de réconciliation sont définis, seuls les enregistrements non réconciliés sont ajoutés.

      Cochez la case **[!UICONTROL Générer une transition sortante pour les rejets]** si les données importées comportent certains enregistrements déjà présents en base afin d&#39;éviter toute erreur.

   * **[!UICONTROL Mettre à jour]** : mettre à jour des données des enregistrements déjà présents en base uniquement.
   * **[!UICONTROL Supprimer]** : supprimer des données.
   >[!NOTE]
   >
   >Le champ **[!UICONTROL Taille du lot]** permet de définir la taille maximale du lot des données à télécharger.

1. Dans l&#39;onglet **[!UICONTROL Identification]**, indiquez comment identifier les enregistrements dans la base de données :

   * **[!UICONTROL En utilisant des clés de réconciliation]** : sélectionnez la **[!UICONTROL Dimension à mettre à jour]**, puis définissez les **[!UICONTROL Clés permettant de retrouver les enregistrements]**. Voir à ce sujet [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Si les données en entrée correspondent à une dimension de ciblage existante, sélectionnez l&#39;option **[!UICONTROL En utilisant directement la dimension de ciblage]**. Sélectionnez alors la **[!UICONTROL Dimension à mettre à jour]**.
   Si le type d&#39;opération sélectionné implique une mise à jour, vous devez obligatoirement utiliser des clés de réconciliation.

1. Dans l&#39;onglet **[!UICONTROL Champs à mettre à jour]**, définissez les champs sur lesquels appliquer la mise à jour et, au besoin, ajoutez des conditions pour que cette mise à jour soit réalisée. Pour cela, utilisez la colonne **[!UICONTROL Prise en compte si]**. Les conditions sont appliquées les unes après les autres, dans l&#39;ordre de la liste. Utilisez les flèches situées à droite pour modifier l&#39;ordre des mises à jour. Vous pouvez utiliser plusieurs fois le même champ de destination.

   Vous pouvez associer automatiquement les champs à l&#39;aide du bouton ![](assets/wkf_magic_wand-24px.png). L&#39;association automatique détecte les champs portant le même nom.

   Dans le cadre d&#39;une opération de type **[!UICONTROL Ajouter ou mettre à jour]**, vous pouvez sélectionner individuellement, pour chaque champ, l&#39;opération à appliquer. Pour cela, sélectionnez la valeur souhaitée dans la colonne **[!UICONTROL Opération]**.

   >[!NOTE]
   >
   >**Gestion des mises à jour** Les champs **[!UICONTROL lastModified]**, **[!UICONTROL modifiedBy]**, **[!UICONTROL created]** et **[!UICONTROL createdBy]** sont automatiquement mis à jour lors d&#39;une mise à jour de données, sauf si leur gestion est explicitement paramétrée dans le tableau de mise à jour des champs. La mise à jour des enregistrements n&#39;est réalisée que pour les enregistrements pour lesquels au moins une différence a été détectée. Si les valeurs sont les mêmes, aucune mise à jour n&#39;est effectuée.

1. Si besoin, gérez les [Transitions](../../automating/using/activity-properties.md) de l&#39;activité afin d&#39;accéder à des options avancées sur la population transmise en sortie.

   Si vous avez sélectionné **[!UICONTROL Ajouter uniquement]** et que les données importées peuvent comporter des enregistrements déjà présents en base, cochez la case **[!UICONTROL Générer une transition sortante pour les rejets]** afin d&#39;éviter toute erreur.

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Exemple {#example}

L&#39;exemple suivant montre le paramétrage d&#39;une activité de **[!UICONTROL Mise à jour de données]** suite à un **[!UICONTROL Chargement de fichier]**. Le but du workflow est d&#39;ajouter ou de mettre à jour les profils de la base Adobe Campaign avec les données récupérées depuis le fichier. La clé de réconciliation utilisée est l&#39;adresse email.

Le fichier chargé est un fichier au format **.txt** contenant les données d&#39;exemple suivantes :

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

L&#39;activité de **[!UICONTROL Mise à jour de données]** est paramétrée comme suit :

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

