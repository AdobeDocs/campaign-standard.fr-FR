---
solution: Campaign Standard
product: campaign
title: Notifications push transactionnelles
description: Découvrez comment créer et publier une notification push transactionnelle.
audience: channels
content-type: reference
topic-tags: transactional-messaging
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 100%

---


# Notifications push transactionnelles{#transactional-push-notifications}

Vous pouvez utiliser Adobe Campaign pour envoyer des notifications push transactionnelles sur des appareils mobiles iOS et Android. Ces messages sont reçus sur des applications mobiles que vous configurez dans Adobe Campaign à l&#39;aide du SDK Experience Cloud Mobile.

>[!NOTE]
>
>Le canal des notifications push est en option. Veuillez vérifier votre contrat de licence. Pour plus d&#39;informations sur les notifications push standard, voir [Notifications push](../../channels/using/about-push-notifications.md).

Vous pouvez envoyer deux types de notification push transactionnelle :

* Notifications push transactionnelles ciblant un événement.
* Notifications push transactionnelles ciblant des profils de la base de données Adobe Campaign

Une fois que vous avez créé et publié l&#39;événement de votre choix (l&#39;abandon de panier, comme expliqué dans [cette section](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle)), la notification push transactionnelle correspondante est automatiquement créée.

Les étapes de configuration sont présentées dans la section [Configurer un événement pour envoyer une notification push transactionnelle](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Pour que l&#39;événement entraîne l&#39;envoi d&#39;un message transactionnel, vous devez personnaliser le message, le tester et le publier.

>[!NOTE]
>
>Pour accéder aux messages transactionnels, vous devez faire partie du groupe de sécurité **[!UICONTROL Administrateurs (toutes entités)]**.

## Notifications push transactionnelles ciblant un événement {#transactional-push-notifications-targeting-an-event}

Vous pouvez envoyer une notification push transactionnelle anonyme à tous les utilisateurs qui se sont inscrits pour recevoir des notifications de votre application mobile.

Dans ce cas, seules les données contenues dans l&#39;événement sont utilisées pour définir la cible de la diffusion. Aucune donnée de la base de données de profils intégrée d&#39;Adobe Campaign n&#39;est utilisée.

### Envoyer une notification push transactionnelle ciblant un événement {#sending-a-transactional-push-notification-targeting-an-----------event}

Par exemple, une compagnie aérienne souhaite inviter les utilisateurs de son application mobile à se rendre à la porte adéquate pour l&#39;embarquement.

Pour ce faire, la compagnie enverra une notification push transactionnelle par utilisateur (identifié avec un jeton d&#39;enregistrement), à l&#39;aide d&#39;une application mobile sur un seul appareil.

1. Accédez au message transactionnel qui a été créé afin de l&#39;éditer. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).

   ![](assets/message-center_push_message.png)

1. Cliquez sur le bloc **[!UICONTROL Contenu]** pour modifier le titre et le corps de votre message.

   Vous pouvez insérer des champs de personnalisation pour ajouter les éléments que vous avez définis lors de la création de votre événement.

   ![](assets/message-center_push_content.png)

   Pour trouver ces champs, cliquez sur le crayon situé en regard d’un élément, cliquez sur **[!UICONTROL Insérer un champ de personnalisation]** et sélectionnez **[!UICONTROL Contexte]** > **[!UICONTROL Événement en temps réel]** > **[!UICONTROL Contexte de l’événement]**.

   ![](assets/message-center_push_personalization.png)

   Pour plus d&#39;informations sur l&#39;édition du contenu d&#39;une notification push, voir [Création d&#39;une notification push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Enregistrez vos modifications et publiez le message. Voir [Publier un message transactionnel](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

1. A l&#39;aide de l&#39;API REST Adobe Campaign Standard, envoyez un événement à un jeton d&#39;enregistrement (ABCDEF123456789), à l&#39;aide d&#39;une application mobile (WeFlight) sur Android (gcm), contenant les informations d&#39;embarquement.

   ```
   {
     "registrationToken":"ABCDEF123456789",
     "application":"WeFlight",
     "pushPlatform":"gcm",
     "ctx":
     {
       "gateNumber":"Gate B18",
       "lastname":"Green",
       "firstname":"Jane"
     }
   }
   ```

   Pour plus d&#39;informations sur l&#39;intégration du déclenchement d&#39;un événement dans un système externe, voir [Intégration à un site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Si le jeton d&#39;enregistrement existe, l&#39;utilisateur correspondant reçoit une notification push transactionnelle comprenant le contenu suivant :

&quot;Bonjour Jeanne Lambert, l&#39;embarquement vient de commencer à la porte B18.&quot;

## Notifications push transactionnelles ciblant un profil    {#transactional-push-notifications-targeting-a-profile}

Vous pouvez envoyer une notification push transactionnelle aux profils Adobe Campaign qui se sont abonnés à votre application mobile. Cette diffusion peut contenir des champs de [personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field) comme le prénom du destinataire.

Dans ce cas, l&#39;événement doit contenir certains champs permettant la réconciliation avec un profil de la base de données Adobe Campaign.

Lors du ciblage des profils, une notification push transactionnelle est envoyée par application mobile et par appareil. Par exemple, si un utilisateur Adobe Campaign s&#39;est abonné à deux applications, il recevra deux notifications. Si un utilisateur s&#39;est abonné à une même application à partir de deux appareils différents, il recevra une notification sur chaque appareil.

Les applications mobiles auxquelles un profil s’est abonné sont répertoriées dans l’onglet **[!UICONTROL Abonnements à l’application mobile]** de ce profil. Pour accéder à cet onglet, sélectionnez un profil et cliquez sur le bouton **[!UICONTROL Éditer les propriétés du profil]** à droite.

![](assets/push_notif_subscriptions.png)

Pour plus d&#39;informations sur l&#39;accès aux profils et leur édition, voir la section [Profils](../../audiences/using/creating-profiles.md).

### Envoyer une notification push transactionnelle ciblant un profil     {#sending-a-transactional-push-notification-targeting-a-----------profile}

Par exemple, une compagnie aérienne souhaite envoyer un dernier appel pour l&#39;embarquement à tous les utilisateurs Adobe Campaign qui se sont abonnés à son application mobile.

1. Accédez au message transactionnel qui a été créé afin de l&#39;éditer. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).

1. Cliquez sur le bloc **[!UICONTROL Contenu]** pour modifier le titre et le corps de votre message.

   Contrairement aux configurations reposant sur des événements temps réel, vous disposez d&#39;un accès direct à toutes les informations de profil pour personnaliser votre message. Voir [Insertion d&#39;un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field).

   Pour plus d&#39;informations sur l&#39;édition du contenu d&#39;une notification push, voir la section [Création d&#39;une notification push](../../channels/using/preparing-and-sending-a-push-notification.md).

1. Enregistrez vos modifications et publiez le message. Voir [Publier un message transactionnel](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).
1. A l&#39;aide de l&#39;API REST Adobe Campaign Standard, envoyez un événement à un profil.

   ```
   {
     "ctx":
     {
       "email":"janegreen@email.com",
       "gateNumber":"D16",
     }
   }
   ```

   Pour plus d&#39;informations sur l&#39;intégration du déclenchement d&#39;un événement dans un système externe, voir [Intégration à un site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

   >[!NOTE]
   >
   >Il n&#39;y a pas de champ de jeton d&#39;enregistrement, d&#39;application ni de plateforme push. Dans cet exemple, la réconciliation est effectuée avec le champ email.
