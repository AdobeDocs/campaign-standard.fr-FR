---
solution: Campaign Standard
product: campaign
title: Sélectionner une audience dans un message
description: '"Cette section contient une procédure détaillée pour sélectionner les audiences d’un email : population cible principale et profils de test."'
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: deliveryCreation,wizard;delivery,audience,back
translation-type: tm+mt
source-git-commit: bdeb3e0c81cf729436a722bfd349a39d5dcad351
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 88%

---


# Sélectionner une audience dans un message{#selecting-an-audience-in-a-message}

Adobe Campaign vous permet de paramétrer plusieurs types de profils dans les audiences d’un message.

Les audiences peuvent être définies au moment de la création du message via l’assistant de création ou depuis le tableau de bord du message s’il a déjà été créé.

>[!NOTE]
>
>Si l’audience a été créée dans un workflow et enrichie de données additionnelles, vous ne pourrez pas utiliser ces données pour personnaliser une diffusion autonome. Elles ne peuvent être utilisées qu’à partir d’une diffusion exécutée dans un workflow.

1. Depuis le tableau de bord, sélectionnez le bloc de définition des audiences.

   ![](assets/delivery_audience_definition_1.png)

   L’écran de définition des audiences s’ouvre. Il dispose de deux onglets permettant de définir distinctement la population de chaque type d’audience qui recevra le message :

   * Cible
   * Profils de test

   ![](assets/delivery_audience_definition_2.png)

1. Définissez la **[!UICONTROL cible]** principale de l’email. Il s’agit de l’audience cible standard de l’email.

   La cible est définie dans l’onglet **[!UICONTROL Cible]**. Elle est constituée des profils identifiés de votre base de données. Vous pouvez constituer votre cible principale à l’aide des fonctionnalités de l’[éditeur de requêtes](../../automating/using/editing-queries.md#creating-queries).

   Lorsque vous vous trouvez sur cet onglet, la palette **[!UICONTROL Raccourcis]** contient uniquement les filtres prédéfinis et les audiences ayant été définis sur les profils identifiés. L’onglet **[!UICONTROL Explorateur]** vous permet d’accéder à des paramétrages supplémentaires.

   Vous pouvez ainsi réutiliser et combiner des audiences existantes, leur appliquer des filtres supplémentaires, etc.

   >[!NOTE]
   >
   >Lors du ciblage d’une audience, notez que la définition de la audience n’est pas référencée mais **copiée** dans la requête. Si vous apportez des modifications à l’audience une fois qu’elle a été ciblée dans une requête, veillez à la configurer de nouveau pour tenir compte de la nouvelle définition.

1. Définissez les **[!UICONTROL profils de test]** que vous souhaitez utiliser pour l’email. Les profils de test recevront les bons à tirer que vous pouvez envoyer pour tester l’email avant son envoi à la cible principale.

   Pour plus d’informations sur le paramétrage des profils de test, consultez la section [Profils de test](../../audiences/using/managing-test-profiles.md).

1. Si nécessaire, vous pouvez définir une population témoin à l’aide de l’onglet correspondant. Vous pourrez ainsi retirer certains profils de votre cible afin qu’ils ne reçoivent pas le message. Pour plus d’informations, voir [Ajout d’une population témoin](../../sending/using/control-group.md).

1. Vous pouvez également utiliser des adresses de substitution pour obtenir une représentation exacte du message que le profil recevra.  Pour plus d’informations, voir [Test des emails à l’aide des profils ciblés](../../sending/using/testing-messages-using-target.md).

Le bloc des audiences est mis à jour et affiche qu’une cible ainsi que des profils de test ont été sélectionnés pour cet email.

![](assets/delivery_audience_definition_3.png)

