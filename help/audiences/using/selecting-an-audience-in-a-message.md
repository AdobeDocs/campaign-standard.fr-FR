---
title: Sélectionner une audience dans un message
description: '"Cette section contient une procédure détaillée pour sélectionner les audiences d''un email : population cible principale et profils de test."'
page-status-flag: never-activated
uuid: 7d8f8446-f2e0-49c1-83f6-9667b29bc228
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 158da6ff-8899-4e7b-b925-8a42c3de46a1
context-tags: deliveryCreation,wizard;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Sélectionner une audience dans un message{#selecting-an-audience-in-a-message}

Adobe Campaign vous permet de paramétrer plusieurs types de profils dans les audiences d&#39;un message.

Les audiences peuvent être définies au moment de la création du message via l&#39;assistant de création ou depuis le tableau de bord du message s&#39;il a déjà été créé.

>[!NOTE]
>
>Si l&#39;audience a été créée dans un workflow et enrichie de données additionnelles, vous ne pourrez pas utiliser ces données pour personnaliser une diffusion autonome. Elles ne peuvent être utilisées qu&#39;à partir d&#39;une diffusion exécutée dans un workflow.

1. Depuis le tableau de bord, sélectionnez le bloc de définition des audiences.

   ![](assets/delivery_audience_definition_1.png)

   L&#39;écran de définition des audiences s&#39;ouvre. Il dispose de deux onglets permettant de définir distinctement la population de chaque type d&#39;audience qui recevra le message :

   * Cible
   * Profils de test
   ![](assets/delivery_audience_definition_2.png)

1. Define the main **[!UICONTROL Target]** of the email. Il s&#39;agit de l&#39;audience cible standard de l&#39;email.

   The target is defined in the **[!UICONTROL Target]** tab and is made up of identified profiles from your database.

   Vous pouvez constituer votre cible principale à l&#39;aide des fonctionnalités de l&#39;[éditeur de requêtes](../../automating/using/editing-queries.md#creating-queries).

   In this tab, the **[!UICONTROL Shortcuts]** palette only contains predefined filters and the audiences that have been defined in the identified profiles. The **[!UICONTROL Explorer]** tab allows you to access additional configurations.

   Vous pouvez ainsi réutiliser et combiner des audiences existantes, leur appliquer des filtres supplémentaires, etc.

1. Define the **[!UICONTROL Test profiles]** you want to use for the email. Les profils de test recevront les bons à tirer que vous pouvez envoyer pour tester l&#39;email avant son envoi à la cible principale.

   Pour plus d&#39;informations sur le paramétrage des profils de test, consultez la section [Profils de test](../../audiences/using/managing-test-profiles.md).

Le bloc des audiences est mis à jour et affiche qu&#39;une cible ainsi que des profils de test ont été sélectionnés pour cet email.

![](assets/delivery_audience_definition_3.png)

