---
title: Déduplication
description: L'activité Déduplication permet de supprimer les doublons dans le ou les résultats des activités entrantes.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21faea89b3b38f3e667ed6c4de0be6d07f0b7197
workflow-type: tm+mt
source-wordcount: '1166'
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

## Exemple 1 : identifier des doublons avant une diffusion {#example-1--identifying-duplicates-before-a-delivery}

L&#39;exemple suivant illustre une déduplication permettant d&#39;exclure les doublons d&#39;une cible avant l&#39;envoi d&#39;un email. Cela permet d&#39;éviter d&#39;envoyer une communication plusieurs fois à un même profil.

Le workflow est constitué comme suit :

![](assets/deduplication_example_workflow.png)

* Une **[!UICONTROL Requête]** permettant de définir la cible de l&#39;email. Ici, le workflow cible tous les profils ayant entre 18 et 25 ans et faisant partie de la base clients depuis plus d&#39;un an.

   ![](assets/deduplication_example_query.png)

* Une **[!UICONTROL Déduplication]** permettant d&#39;identifier les doublons issus de la requête précédente. Dans cet exemple, un seul enregistrement est conservé pour chaque doublon. Les doublons sont identifiés grâce à l&#39;adresse email. Ainsi, la diffusion email ne pourra être envoyée qu&#39;une fois pour chaque adresse email présente dans le ciblage.

   La méthode de déduplication sélectionnée est **[!UICONTROL Valeur non vide]**. Cela permet de s&#39;assurer que les enregistrements conservés en cas de doublons soient prioritairement ceux dont le champ **Prénom** est renseigné. Cela permettra plus de cohérence si le prénom est utilisé dans les champs de personnalisation du contenu de l&#39;email.

   De plus, une transition complémentaire est ajoutée afin de conserver les doublons et de pouvoir les lister.

   ![](assets/deduplication_example_dedup.png)

* Une **[!UICONTROL Diffusion email]** placée à la suite de la transition sortante principale de la déduplication. Le paramétrage des diffusions email est détaillé dans la section [Diffusion Email](../../automating/using/email-delivery.md).
* Une **[!UICONTROL Sauvegarde d&#39;audience]** placée à la suite de la transition complémentaire de la déduplication afin de sauvegarder les doublons dans une audience **Doublons**. Cette audience pourra être réutilisée afin d&#39;exclure directement ses membres de toute diffusion email.

## Exemple 2 : dédupliquer les données d&#39;un fichier importé {#example-2--deduplicating-the-data-from-an-imported-file}

Cet exemple montre comment dédupliquer les données d&#39;un fichier importé avant de les charger dans la base de données. Ce procédé permet d&#39;améliorer la qualité des données chargées dans la base.

Le workflow est constitué comme suit :

![](assets/deduplication_example2_workflow.png)

* Un fichier contenant une liste profils est importé à l&#39;aide d&#39;un **[!UICONTROL Chargement de fichier]**. Dans cet exemple, le fichier importé est au format .csv et contient 10 profils :

   ```
   lastname;firstname;dateofbirth;email
   Smith;Hayden;23/05/1989;hayden.smith@example.com
   Mars;Daniel;17/11/1987;dannymars@example.com
   Smith;Clara;08/02/1989;hayden.smith@example.com
   Durance;Allison;15/12/1978;allison.durance@example.com
   Lucassen;Jody;28/03/1988;jody.lucassen@example.com
   Binder;Tom;19/01/1982;tombinder@example.com
   Binder;Tommy;19/01/1915;tombinder@example.com
   Connor;Jade;10/10/1979;connor.jade@example.com
   Mack;Clarke;02/03/1985;clarke.mack@example.com
   Ross;Timothy;04/07/1986;timross@example.com
   ```

   Ce fichier peut également servir de fichier d&#39;exemple pour détecter et définir le format des colonnes. Depuis l&#39;onglet **[!UICONTROL Définition des colonnes]**, assurez-vous que chaque colonne du fichier importé est correctement paramétrée.

   ![](assets/deduplication_example2_fileloading.png)

* Une activité de **[!UICONTROL Déduplication]**. La déduplication est réalisée directement après l&#39;import du fichier et avant que les données soient insérées dans la base. Il faut donc se baser sur la **[!UICONTROL Ressource temporaire]** issue de l&#39;activité de **[!UICONTROL Chargement de fichier]**.

   Pour cet exemple, nous souhaitons conserver une seule entrée par adresse email unique contenue dans le fichier. L&#39;identification des doublons est donc réalisée sur la colonne **email** de la ressource temporaire. Or, deux adresses email apparaissent deux fois dans le fichier. Deux lignes seront donc considérées comme des doublons.

   ![](assets/deduplication_example2_dedup.png)

* Une activité de **[!UICONTROL Mise à jour de données]**, permettant d&#39;insérer dans la base de données les données conservées à l&#39;issue de la déduplication. Ce n&#39;est qu&#39;au moment de la mise à jour de données que les données importées sont identifiées comme appartenant à la dimension des profils.

   Nous souhaitons ici **[!UICONTROL Ajouter uniquement]** les profils qui n&#39;existent pas déjà dans la base, en utilisant la colonne email du fichier et le champ email de la dimension **Profil** comme clé de réconciliation.

   ![](assets/deduplication_example2_writer1.png)

   Indiquez les correspondances entre les colonnes du fichier dont vous souhaitez insérer les données et les champs de la base depuis l&#39;onglet **[!UICONTROL Champs à mettre à jour]**.

   ![](assets/deduplication_example2_writer2.png)

Lancez ensuite le workflow. Les enregistrements conservés à l&#39;issue de la déduplication sont alors ajoutés aux profils de votre base de données.
