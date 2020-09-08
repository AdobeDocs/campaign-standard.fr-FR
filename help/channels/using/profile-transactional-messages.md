---
title: Messages transactionnels basés sur un profil
description: Découvrez comment créer et publier un message transactionnel basé sur un profil.
page-status-flag: never-activated
uuid: a8efe979-74ae-46ff-a305-b86a90679581
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: dcb90afc-42c3-419e-8345-79cddf969e41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 88%

---


# Messages transactionnels basés sur un profil{#profile-transactional-messages}

Vous avez la possibilité d&#39;envoyer des messages transactionnels selon les profils marketing des utilisateurs, ce qui vous permet de réaliser les actions suivantes :

* Apply marketing typology rules such as **[!UICONTROL Denylisted address]** or [fatigue rules](../../sending/using/fatigue-rules.md).
* inclure le lien de désinscription dans les messages ;
* ajouter les messages transactionnels au reporting de diffusion globale ;
* utiliser les messages transactionnels dans le parcours client.

Une fois que vous avez créé et publié l&#39;événement de votre choix (dans l&#39;[exemple](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) ci-dessus, l&#39;abandon de panier), le message transactionnel correspondant est automatiquement créé.

Les étapes de configuration sont présentées dans la section [Configurer un événement pour envoyer un message transactionnel basé sur un profil](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Pour que l&#39;événement entraîne l&#39;envoi d&#39;un message transactionnel, vous devez personnaliser le message, le tester et le publier.

>[!NOTE]
>
>Pour accéder aux messages transactionnels, vous devez faire partie du groupe de sécurité **[!UICONTROL Administrateurs (toutes entités)]**.
>
>Les règles de fatigue sont compatibles avec les messages transactionnels basés sur un profil. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

## Envoyer un message transactionnel basé sur un profil    {#sending-a-profile-transactional-message}

Les étapes pour créer, personnaliser et publier un message transactionnel de profil sont les mêmes que pour un message transactionnel d&#39;événement. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).

Les différences sont énumérées ci-dessous.

1. Accédez au message transactionnel qui a été créé afin de l&#39;éditer.
1. Dans le message transactionnel, cliquez sur la section **[!UICONTROL Contenu]**. Outre le modèle transactionnel, vous pouvez également choisir tout modèle d&#39;email par défaut qui cible **[!UICONTROL Profil]**.

   ![](assets/message-center_marketing_templates.png)

1. Sélectionnez le modèle d&#39;email par défaut.

   Comme tous les emails marketing, il contient un lien de désinscription.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   De plus, contrairement aux configurations reposant sur des événements temps réel, vous disposez d&#39;un accès direct à toutes les informations de profil pour personnaliser votre message. Voir [Insertion d&#39;un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field).

1. Enregistrez vos modifications et publiez le message. Voir [Publier un message transactionnel](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Contrôler la diffusion d&#39;un message transactionnel selon les profils    {#monitoring-a-profile-transactional-message-delivery}

Une fois le message publié et l&#39;intégration à un site effectuée, vous pouvez contrôler la diffusion.

1. Pour visualiser le log de diffusion du message, cliquez sur l&#39;icône située en bas à droite du bloc **[!UICONTROL Déploiement]**.

   Pour plus d&#39;informations sur l&#39;accès aux logs, voir [Contrôler la diffusion](../../sending/using/monitoring-a-delivery.md).

1. Sélectionnez l&#39;onglet **[!UICONTROL Envois]**. Dans la colonne **[!UICONTROL Statut]**, la mention **[!UICONTROL Envoyé]** indique qu&#39;un profil s&#39;est inscrit.

   ![](assets/message-center_marketing_sending_logs.png)

1. Select the **[!UICONTROL Exclusions logs]** tab to view recipients who have been excluded from the message target, such as denylisted addresses.

   ![](assets/message-center_marketing_exclusion_logs.png)

For any profile that has opted out, the **[!UICONTROL Denylisted address]** typology rule excluded the corresponding recipient.

Cette règle fait partie d&#39;une typologie spécifique qui s&#39;applique à tous les messages transactionnels qui reposent sur la table **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Rubriques connexes** :

* [Intégration à un site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologies](../../sending/using/about-typology-rules.md)

