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
source-git-commit: e725ef966bcd6df84ed0c82e17fad65f289fd013
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

1. Définissez la **[!UICONTROL cible]** principale de l&#39;email. Il s&#39;agit de l&#39;audience cible standard de l&#39;email.

   La cible est définie dans l&#39;onglet **[!UICONTROL Cible]**. Elle est constituée des profils identifiés de votre base de données.

   Vous pouvez constituer votre cible principale à l&#39;aide des fonctionnalités de l&#39;[éditeur de requêtes](../../automating/using/editing-queries.md#creating-queries).

   Lorsque vous vous trouvez sur cet onglet, la palette **[!UICONTROL Raccourcis]** contient uniquement les filtres prédéfinis et les audiences ayant été définis sur les profils identifiés. L&#39;onglet **[!UICONTROL Explorateur]** vous permet d&#39;accéder à des paramétrages supplémentaires.

   Vous pouvez ainsi réutiliser et combiner des audiences existantes, leur appliquer des filtres supplémentaires, etc.

1. Définissez les **[!UICONTROL profils de test]** que vous souhaitez utiliser pour l&#39;email. Les profils de test recevront les bons à tirer que vous pouvez envoyer pour tester l&#39;email avant son envoi à la cible principale.

   Pour plus d&#39;informations sur le paramétrage des profils de test, consultez la section [Profils de test](../../audiences/using/managing-test-profiles.md).

1. Si nécessaire, vous pouvez définir une Population témoin à l’aide de l’onglet correspondant. Cela vous permettra de retirer certains profils de votre cible afin qu&#39;ils ne reçoivent pas le message. For more on this, see [Adding a control group](../../sending/using/control-group.md).

1. Vous pouvez également utiliser des adresses de substitution pour obtenir une représentation exacte du message que le profil recevra.  Pour plus d’informations, voir [Test des emails à l’aide des profils ciblés](../../sending/using/testing-messages-using-target.md).

Le bloc des audiences est mis à jour et affiche qu&#39;une cible ainsi que des profils de test ont été sélectionnés pour cet email.

![](assets/delivery_audience_definition_3.png)

