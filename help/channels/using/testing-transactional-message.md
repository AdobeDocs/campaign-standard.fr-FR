---
solution: Campaign Standard
product: campaign
title: Tester un message transactionnel
description: Découvrez comment tester un message transactionnel dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: f19d4b5c1837f3f03789958abb1539d4edea0744
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 100%

---


# Tester un message transactionnel {#testing-a-transactional-message}

Avant de publier votre message transactionnel, vous pouvez créer un profil de test spécifique qui vous permettra de vérifier correctement le message.

## Définition d’un profil de test spécifique {#defining-specific-test-profile}

Définissez un profil de test qui sera lié à votre événement, ce qui vous permettra de prévisualiser votre message et d’envoyer un BAT approprié.

1. Dans le [tableau de bord du message transactionnel](../../channels/using/editing-transactional-message.md#accessing-transactional-messages), cliquez sur le bouton **[!UICONTROL Créer un profil de test]**.

   ![](assets/message-center_test-profile.png)

1. Indiquez les informations à transmettre au format JSON dans la section **[!UICONTROL Données de l’événement utilisées pour la personnalisation]**. C’est le contenu qui sera utilisé lors de la prévisualisation du message et que recevra le profil de test à l’envoi du BAT.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Si vous avez enrichi votre message, vous pouvez également saisir des informations relatives à une autre table, comme **[!UICONTROL Profil]**. Voir [Enrichir l&#39;événement](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) et [Personnaliser un message transactionnel](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).

1. Une fois créé, le profil de test est pré-renseigné dans le message transactionnel. Cliquez sur le bloc **[!UICONTROL Profils de test]** du message pour vérifier la cible de votre BAT.

   ![](assets/message-center_5.png)

Vous pouvez également créer un profil de test ou en utiliser un existant depuis le menu **[!UICONTROL Profils de test.]** Pour cela :

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Profils &amp; audiences]** > **[!UICONTROL Profils de test]**.
1. Dans la section **[!UICONTROL Événement]**, sélectionnez l’événement que vous venez de créer. Dans cet exemple, choisissez &quot;Abandon de panier (EVTcartAbandonment)&quot;.
1. Indiquez les informations à transmettre au format JSON dans la zone de texte **[!UICONTROL Données de l’événement]**.

   ![](assets/message-center_3.png)

1. Enregistrez vos modifications.
1. [Accédez au message](../../channels/using/editing-transactional-message.md#accessing-transactional-messages) que vous avez créé et sélectionnez le profil de test mis à jour.

**Rubriques connexes :**

* [Gestion des profils de test](../../audiences/using/managing-test-profiles.md)
* [Créer des audiences](../../audiences/using/creating-audiences.md)

## Envoyer le BAT {#sending-proof}

Une fois que vous avez créé un ou plusieurs profils de test spécifiques et enregistré votre message transactionnel, vous pouvez envoyer un BAT pour le tester.

![](assets/message-center_10.png)

Les étapes d’envoi d’un BAT sont présentées dans la section [Envoyer des BAT](../../sending/using/sending-proofs.md).
