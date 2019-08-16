---
title: Insertion d'un champ de personnalisation
seo-title: Insertion d'un champ de personnalisation
description: Insertion d'un champ de personnalisation
seo-description: Découvrez comment insérer dans votre message un champ provenant de la base de données, par exemple le prénom du profil.
page-status-flag: never-activated
uuid: 8f810c7f-2599-4fde-8422-4d261bea7db8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: personalizing-content
discoiquuid: bd39406d-aa20-4f91-8fb8-2e4cdf112a85
internal: n
snippet: y
translation-type: ht
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Insertion d'un champ de personnalisation{#inserting-a-personalization-field}

Adobe Campaign vous permet d'insérer dans votre page un champ provenant de la base de données, par exemple le prénom du profil.

>[!NOTE]
>
>Les images ci-après illustrent l'insertion d'un champ de personnalisation à l'aide du [Concepteur d'email](../../designing/using/about-email-content-design.md#about-the-email-designer).

Pour ajouter un champ de personnalisation au contenu :

1. Cliquez dans un bloc de texte. Cliquez ensuite sur l'icône **[!UICONTROL Personnaliser]** dans la barre d'outils contextuelle et sélectionnez **[!UICONTROL Insérer un champ de personnalisation]**. Pour plus d'informations sur l'interface du Concepteur d'email, consultez [cette section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_perso_field_1.png)

1. Sélectionnez le champ à insérer dans le contenu de votre page.

   ![](assets/email_perso_field_2.png)

1. Cliquez sur **[!UICONTROL Confirmer]**.

Le nom du champ apparaît dans l'éditeur et est surligné.

![](assets/email_perso_field_3.png)

Une fois la personnalisation générée (lors de la prévisualisation et de la préparation de l'email, par exemple), ce champ est remplacé par la valeur qui correspond au profil ciblé.

>[!NOTE]
>
>Si l'email est créé depuis un workflow, les données additionnelles calculées dans le workflow sont aussi disponibles dans les champs de personnalisation. Pour plus d'informations sur l'ajout de données additionnelles depuis un workflow, consultez la section [Enrichir les données](../../automating/using/targeting-data.md#enriching-data).

