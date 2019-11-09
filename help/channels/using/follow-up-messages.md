---
title: Messages de relance
description: Découvrez comment créer et publier un message de relance.
page-status-flag: never-activated
uuid: d2a17da2-e935-420a-8531-78ed6a1fe68b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 9615e369-754f-4f6a-a1b1-14462f946666
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Messages de relance{#follow-up-messages}

Vous pouvez envoyer un message de relance aux clients qui ont reçu un message transactionnel spécifique. Pour cela, vous devez configurer un workflow ciblant l'événement correspondant.

Reprenons l'exemple présenté dans la section [Principe de fonctionnement des messages transactionnels](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) : un email d'abandon de panier est envoyé aux visiteurs de votre site Web ayant ajouté des produits dans leur panier, mais ayant quitté le site sans poursuivre leurs achats.

Vous souhaitez envoyer un rappel à tous les clients ayant reçu la notification d'abandon de panier, mais ne l'ayant pas ouverte au bout de trois jours.

Chaque client concerné recevra alors un message de relance basé sur les mêmes données que celles utilisées dans le premier email qui a été envoyé.

## Accéder aux messages de relance   {#accessing-the-follow-up-messages}

Une fois que vous avez créé et publié l'événement de votre choix (dans l'[exemple](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) ci-dessus, l'abandon de panier), le message transactionnel et le message de relance correspondants sont automatiquement créés.

Les étapes de configuration sont présentées dans la section [Configurer un événement pour envoyer un message de relance](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Pour gérer un événement dans un workflow, un modèle de diffusion est nécessaire. Le [message transactionnel](../../channels/using/event-transactional-messages.md) créé lors de la publication de l'événement ne peut cependant pas être utilisé comme modèle. Vous devez donc créer un modèle de diffusion de relance spécifique qui prend en charge ce type d'événement et qui peut être utilisé comme modèle dans un workflow.

Pour accéder à ce modèle :

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche.
1. Sélectionnez **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles]** &gt; **[!UICONTROL Modèles de diffusion]**.
1. Cochez la case **[!UICONTROL Messages de relance]** dans le volet de gauche.

   ![](assets/message-center_follow-up-search.png)

Seuls les messages de relance sont affichés.

>[!NOTE]
>
>Pour accéder aux messages transactionnels, vous devez faire partie du groupe de sécurité **[!UICONTROL Administrateurs (toutes entités)]**.

## Envoyer un message de relance {#sending-a-follow-up-message}

Une fois que vous avez créé le modèle de diffusion de relance, vous pouvez l'utiliser dans un workflow pour envoyer un message de relance.

1. Accédez à la liste des activités marketing et créez un workflow.

   Voir à ce propos la section [Créer un workflow](../../automating/using/building-a-workflow.md#creating-a-workflow).

1. Placez une activité **[!UICONTROL Planificateur]** dans le workflow, puis ouvrez-la. Définissez la fréquence d'exécution sur une fois par jour.

   L'activité Planificateur est présentée dans la section [Planificateur](../../automating/using/scheduler.md).

1. Placez une activité **[!UICONTROL Requête]** dans votre workflow, puis ouvrez-la.

   L'activité Requête est présentée dans la section [Requête](../../automating/using/query.md).

1. Pour effectuer la requête sur une autre ressource que celle des profils, accédez à l'onglet **[!UICONTROL Propriétés]** de l'activité et cliquez sur la liste déroulante **[!UICONTROL Ressource]**.

   ![](assets/message-center_follow-up-query-properties.png)

   >[!NOTE]
   >
   >Par défaut, l'activité est pré-paramétrée pour rechercher des profils.

1. Sélectionnez l'événement à cibler. Vous aurez ainsi uniquement accès aux données de cet événement.

   ![](assets/message-center_follow-up-query-resource.png)

1. Accédez à l'onglet **[!UICONTROL Cible]**, puis faites glisser l'élément **[!UICONTROL Logs de diffusion (logs)]** depuis la section **[!UICONTROL Email]** dans l'espace de travail.

   ![](assets/message-center_follow-up-delivery-logs.png)

   Sélectionnez **[!UICONTROL Existe]** pour cibler tous les clients ayant reçu l'email.

   ![](assets/message-center_follow-up-delivery-logs-exists.png)

1. Déplacez l'élément **[!UICONTROL Tracking (tracking)]** de la palette vers l'espace de travail, puis sélectionnez **[!UICONTROL N'existe pas]** pour cibler tous les clients qui n'ont pas ouvert l'email.

   ![](assets/message-center_follow-up-delivery-and-tracking-logs.png)

1. Déplacez l'événement que vous ciblez (**Abandon de panier** dans cet exemple) depuis la section **[!UICONTROL Email]** vers l'espace de travail. Définissez ensuite une règle pour cibler tous les messages envoyés il y a trois jours.

   ![](assets/message-center_follow-up-created.png)

   Tous les destinataires qui ont reçu le message transactionnel trois jours avant l'exécution du workflow et qui ne l'ont pas encore ouvert sont donc ciblés.

   Cliquez sur **[!UICONTROL Confirmer]** pour enregistrer la requête.

1. Placez une activité **Diffusion Email** dans votre workflow.

   L'activité Diffusion Email est présentée dans la section [Diffusion Email](../../automating/using/email-delivery.md).

   ![](assets/message-center_follow-up-workflow.png)

   Vous pouvez également utiliser une activité [Diffusion SMS](../../automating/using/sms-delivery.md) ou [Diffusion sur des applications mobiles](../../automating/using/push-notification-delivery.md). Dans ce cas, vous devez sélectionner le canal **[!UICONTROL Mobile (SMS)]** ou **[!UICONTROL Application mobile]** lors de la configuration de l'événement. Voir la section [Créer un événement](../../administration/using/configuring-transactional-messaging.md#creating-an-event).

1. Ouvrez l'activité **Diffusion Email.** Dans l'assistant de création, cochez la case **[!UICONTROL Messages de relance]** et sélectionnez le modèle de diffusion de relance qui a été créé après la publication de l'événement.

   ![](assets/message-center_follow-up-template.png)

1. Dans le contenu du message de relance, vous pouvez utiliser le contenu de l'événement en ajoutant des champs de personnalisation.

   ![](assets/message-center_follow-up-content.png)

1. Pour rechercher les champs que vous avez définis lors de la création de votre événement, sélectionnez **[!UICONTROL Contexte]** &gt; **[!UICONTROL Evénement temps réel]** &gt; **[!UICONTROL Contexte de l'événement]**. Voir [Personnaliser un message transactionnel](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

   ![](assets/message-center_follow-up-personalization.png)

   Ainsi, vous pouvez utiliser le même contenu, notamment les données enrichies, qui a été utilisé lors du premier envoi de l'événement, afin de créer un rappel personnalisé.

1. Enregistrez l'activité et démarrez le workflow.

Une fois le workflow lancé, chaque client ayant reçu une notification d'abandon de panier il y a trois jours, mais ne l'ayant pas ouverte, recevra un message de relance reposant sur les mêmes données que dans cette première notification.

>[!NOTE]
>
>Si vous avez sélectionné la dimension de ciblage **[!UICONTROL Profil]** lors de la création de la configuration de l'événement, le message de relance utilisera également la base de données marketing d'Adobe Campaign. Voir [Messages transactionnels basés sur un profil](../../channels/using/profile-transactional-messages.md).

