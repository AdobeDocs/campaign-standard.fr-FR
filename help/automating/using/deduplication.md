---
solution: Campaign Standard
product: campaign
title: Déduplication
description: L'activité Déduplication permet de supprimer les doublons dans le ou les résultats des activités entrantes.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '606'
ht-degree: 100%

---


# Déduplication{#deduplication}

## Description {#description}

![](assets/deduplication.png)

L&#39;activité **[!UICONTROL Déduplication]** permet de supprimer les doublons dans le ou les résultats des activités entrantes.

## Contexte d’utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Déduplication]** est généralement utilisée à la suite des activités de ciblage ou d&#39;un import de fichier et avant les activités permettant de consommer les données ciblées.

Lors d&#39;une déduplication, les transitions entrantes sont traitées séparément. Si par exemple, un profil « A » est présent dans le résultat de la requête 1 et également dans le résultat de la requête 2, il ne sera pas dédupliqué.

Il est ainsi conseillé de faire en sorte qu&#39;une déduplication ne possède qu&#39;une transition entrante. Pour cela, vous pouvez réunir vos différentes requêtes par des activités répondant aux besoins de votre ciblage telles qu&#39;une union, une intersection, etc. Par exemple :

![](assets/dedup_bonnepratique.png)

**Rubriques connexes :**

* [Cas pratique : identifier des doublons avant une diffusion](../../automating/using/identifying-duplicated-before-delivery.md)
* [Cas pratique : dédupliquer les données d’un fichier importé](../../automating/using/deduplicating-data-imported-file.md)

## Configuration {#configuration}

Pour paramétrer une déduplication, vous devez renseigner son libellé, la méthode et les critères de déduplication, ainsi que les options relatives au résultat.

1. Placez une activité **[!UICONTROL Déduplication]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.

   ![](assets/deduplication_1.png)

1. Sélectionnez le **[!UICONTROL Type de ressource]** sur lequel doit être effectuée la déduplication :

   * **[!UICONTROL Ressource de la base]** si la déduplication porte sur des données déjà existantes en base de données. Sélectionnez la **[!UICONTROL Dimension de filtrage]** et la **[!UICONTROL Dimension de ciblage]** en fonction des données que vous souhaitez dédupliquer. Par défaut, la déduplication porte sur les **profils**.
   * **[!UICONTROL Ressource temporaire]** si la déduplication porte sur des données temporaires du workflow : sélectionnez l&#39;**[!UICONTROL Ensemble ciblé]** contenant les données à dédupliquer. Ce cas peut être rencontré à la suite d&#39;un import de fichier ou si des données de la base ont été enrichies (par exemple avec un code segment).

1. Sélectionnez le **[!UICONTROL Nombre d&#39;enregistrements uniques à conserver]**. La valeur par défaut de ce champs est 1. La valeur 0 permet de conserver tous les doublons.

   Par exemple, si des enregistrements A et B sont considérés comme des doublons d&#39;un enregistrement Y, et un enregistrement C est considéré comme un doublon d&#39;un enregistrement Z :

   * Si la valeur du champ est 1 : seuls les enregistrements Y et Z sont conservés.
   * Si la valeur du champ est 0 : tous les enregistrements sont conservés.
   * Si la valeur du champ est 2 : les enregistrements C et Z sont conservés et deux enregistrements parmi A, B et Y sont conservés, au hasard ou en fonction de la méthode de déduplication choisie par la suite.

1. Définissez les critères d&#39;**[!UICONTROL Identification des doublons]** en ajoutant des conditions dans la liste prévue à cet effet. Indiquez les champs et/ou expressions pour lesquels des valeurs identiques permettent d&#39;identifier les doublons : adresse email, nom, prénom etc. L&#39;ordre des conditions permet d&#39;indiquer lesquelles traiter en priorité.
1. Sélectionnez dans la liste déroulante la **[!UICONTROL Méthode de déduplication]** à utiliser :

   * **[!UICONTROL Choisir pour moi]** : sélectionne au hasard parmi les doublons l&#39;enregistrement à conserver.
   * **[!UICONTROL Par ordonnancement de valeurs]** : permet de définir un ordre de priorité des valeurs pour un ou plusieurs champs. Pour définir les valeurs, sélectionnez un champ ou créez une expression puis ajoutez la ou les valeurs dans le tableau correspondant. Cliquez sur le bouton **[!UICONTROL Ajouter]** situé au-dessus de la liste des valeurs pour définir un nouveau champ.

      ![](assets/deduplication_2.png)

   * **[!UICONTROL Valeur non vide]** : permet de conserver en priorité les enregistrements pour lesquels la valeur de l&#39;expression sélectionnée n&#39;est pas vide.

      ![](assets/deduplication_3.png)

   * **[!UICONTROL A partir d&#39;une expression]** : permet de conserver les enregistrements dont la valeur de l&#39;expression renseignée est la plus petite ou la plus grande.

      ![](assets/deduplication_4.png)

1. Si besoin, gérez les [Transitions](../../automating/using/activity-properties.md) de l&#39;activité afin d&#39;accéder à des options avancées sur la population transmise en sortie.
1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.
