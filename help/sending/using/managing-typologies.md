---
title: Gestion des typologies
description: Découvrez comment utiliser les typologies.
page-status-flag: never-activated
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: typology,overview;typologyRule,main;typologyRule,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ec0af8c06e36f51ddaf6e3d4190fa6acd56d2da6

---


# Gestion des typologies {#managing-typologies}

## A propos des typologies {#about-typologies}

Les typologies sont des ensembles de règles qui vous permettent de vérifier la validité de votre message avant de l’envoyer. Par exemple : Le contenu du message n’est pas vide, un  est présent, l’exclusion des  de, etc.

Les typologies sont accessibles via le menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** . Par défaut, une typologie par défaut est disponible dans l’application. Selon vos besoins, vous pouvez créer vos propres typologies ou modifier celles qui existent déjà.

![](assets/typologies-list.png)

Pour chaque typologie, la **[!UICONTROL Typology rules]** section  l’ensemble de règles qui sont exécutées lors de l’utilisation de la typologie avec un message.

![](assets/typology_typo-rule-list.png)

>[!NOTE]
>
>Pour plus d’informations sur l’un des  du, -cliquez dessus en. La règle s’affiche en mode lecture seule.

## Creating a typology {#creating-a-typology}

Pour créer une typologie, procédez comme suit :

1. Accédez au menu **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** .

1. Le  de typologies s’affiche. Cliquez sur le **[!UICONTROL Create]** bouton.

   ![](assets/typologies-list.png)

1. Définissez la typologie **[!UICONTROL Label]**, puis cliquez sur le **[!UICONTROL Add an element]** bouton pour sélectionner le que vous souhaitez y inclure. For more on typology rules, refer to [this section](../../sending/using/managing-typology-rules.md).

   ![](assets/typology_addrules.png)

   >[!NOTE]
   >
   >The **[!UICONTROL IP affinity]** field allows you to manage the affinities according to your configuration. Elles sont définies dans le fichier de configuration de l’instance. Si vous souhaitez utiliser le , contactez votre administrateur.

1. Cliquez sur **[!UICONTROL Create]** pour confirmer votre sélection. Votre typologie est maintenant prête à être utilisée dans les messages.

## Application de typologies aux messages {#applying-typologies-to-messages}

Lors de l’association d’une typologie à un message ou à un modèle de message, le  inclus dans la typologie est exécuté pour vérifier la validité du message.

>[!NOTE]
>
>Chaque message ou modèle de message ne peut être affecté qu’à une seule typologie.

Pour lier une typologie à un message, procédez comme suit :

1. Accédez aux propriétés du message. Notez que les modèles de message sont accessibles à partir du menu de **[!UICONTROL Resources]** > **[!UICONTROL Templates]** navigation.

1. Dans la section **[!UICONTROL Advanced parameters]** > **[!UICONTROL Prearation]** , sélectionnez la typologie à lier au message.

   ![](assets/typology_message.png)

1. Clics **[!UICONTROL Confirm]**.

   La typologie sélectionnée est maintenant liée au message. Tous les  associés seront exécutés pour vérifier la validité du message.
