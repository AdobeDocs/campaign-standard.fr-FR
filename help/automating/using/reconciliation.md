---
solution: Campaign Standard
product: campaign
title: Réconciliation
description: L'activité Réconciliation permet de relier des données non identifiées à des ressources existantes.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 100%

---


# Réconciliation{#reconciliation}

## Description {#description}

![](assets/reconciliation.png)

L&#39;activité **[!UICONTROL Réconciliation]** permet de relier des données non identifiées à des ressources existantes.

## Contexte d’utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Réconciliation]** est essentiellement utilisée à des fins de Data Management et répond à deux cas d&#39;utilisation distincts :

* Ajout de relations : un onglet **[!UICONTROL Liens]** permet d&#39;ajouter des liens entre les données entrantes et plusieurs autres dimensions de la base de données Adobe Campaign.

   Par exemple, un fichier contenant des données d&#39;achats peut également contenir des informations permettant d&#39;identifier les produits achetés ainsi que l&#39;acheteur. Deux dimensions supplémentaires (en plus de celle des **Achats**) sont alors concernées par les données du fichier : la dimension des **Produits** et la dimension des **Profils**. Il faut ainsi créer des relations entre ces dernières et la dimension des **Achats** (voir exemple ci-après).

   Lorsqu&#39;une relation est définie, une colonne est ajoutée aux données entrantes afin de référencer la clé étrangère de la dimension liée.

   >[!NOTE]
   >
   >Cette opération suppose que les données des dimensions liées sont déjà présentes en base. Par exemple, si vous importez un fichier d&#39;actes d&#39;achats indiquant quel produit a été acheté, à quelle heure, par quel client, etc., le produit ainsi que le client doivent déjà exister en base.

* Identification de données : un onglet **[!UICONTROL Identification]** vous permet de simplement associer les données entrantes à des colonnes d&#39;une dimension existante dans la base de données Adobe Campaign. En sortie de l&#39;activité, les données sont identifiées comme appartenant à la dimension définie.

   Vous pouvez par exemple ensuite réaliser une sauvegarde d&#39;audience, mettre à jour les données de la base, etc.

L&#39;activité **[!UICONTROL Réconciliation]** peut par exemple être placée après une activité de chargement de données visant à importer des données non standard dans la base.

**Rubriques connexes :**

* [Cas pratique : réconciliation des données à l’aide des relations](../../automating/using/reconciliation-using-relations.md)
* [Cas pratique : mise à jour des données à l’aide de la réconciliation](../../automating/using/data-update-reconciliation.md)
* [Cas pratique : réconcilier une audience de type fichier avec la base de données](../../automating/using/reconcile-file-audience-with-database.md)

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Réconciliation]** dans votre workflow, à la suite d&#39;une transition contenant une population dont la dimension de ciblage ne provient pas directement d&#39;Adobe Campaign. Voir à ce sujet [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources).
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Si vous souhaitez définir des liens entre les données entrantes et d&#39;autres dimensions de la base, accédez à l&#39;onglet **[!UICONTROL Liens]**.

   Ajoutez autant de relations que nécessaire. Pour chaque relation, sélectionnez d&#39;abord la dimension liée puis dans le détail du lien, indiquez les champs correspondants.

1. Si vous souhaitez simplement identifier les données entrantes, accédez à l&#39;onglet **[!UICONTROL Identification]** et cochez la case **[!UICONTROL Identifier le document de ciblage à partir des données de travail]**.

   Sélectionnez la dimension de ciblage vers laquelle vous souhaitez réconcilier les données entrantes.

   Ajoutez des critères de réconciliation permettant d&#39;associer un enregistrement de la transition entrante à un enregistrement de la dimension de ciblage sélectionnée. Si plusieurs critères sont indiqués, ils doivent tous être vérifiés pour que le l&#39;association entre les données puisse se faire.

   Choisissez le mode de **[!UICONTROL Traitement des lignes sources non identifiées]** :

   * **[!UICONTROL Les ignorer]** : seules les données ayant pu être identifiées sont conservées dans la transition sortante de l&#39;activité.
   * **[!UICONTROL Les conserver dans la population de sortie]** : toutes les données de la transition entrante sont conservées dans la transition sortante de l&#39;activité.

1. Validez le paramétrage de l’activité et enregistrez le workflow.
