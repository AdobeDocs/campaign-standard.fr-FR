---
title: Messages transactionnels basés sur un profil
seo-title: Messages transactionnels basés sur un profil
description: Messages transactionnels basés sur un profil
seo-description: Découvrez comment créer et publier un message transactionnel basé sur un profil.
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
translation-type: ht
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Messages transactionnels basés sur un profil{#profile-transactional-messages}

Vous avez la possibilité d'envoyer des messages transactionnels selon les profils marketing des utilisateurs, ce qui vous permet de réaliser les actions suivantes :

* appliquer des règles de typologie marketing telles que **[!UICONTROL Adresse en blackliste]** ou des [règles de fatigue](../../administration/using/fatigue-rules.md) ;
* inclure le lien de désinscription dans les messages ;
* ajouter les messages transactionnels au reporting de diffusion globale ;
* utiliser les messages transactionnels dans le parcours client.

Une fois que vous avez créé et publié l'événement de votre choix (dans l'[exemple](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle) ci-dessus, l'abandon de panier), le message transactionnel correspondant est automatiquement créé.

Les étapes de configuration sont présentées dans la section [Configurer un événement pour envoyer un message transactionnel basé sur un profil](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Pour que l'événement entraîne l'envoi d'un message transactionnel, vous devez personnaliser le message, le tester et le publier.

>[!NOTE]
>
>Pour accéder aux messages transactionnels, vous devez disposer des droits d'administration ou figurer dans le groupe de sécurité **[!UICONTROL Agents Message Center]** (mcExec). Les règles de fatigue sont compatibles avec les messages transactionnels basés sur un profil. Voir [Règles de fatigue](../../administration/using/fatigue-rules.md).

## Envoyer un message transactionnel basé sur un profil  {#sending-a-profile-transactional-message}

Les étapes pour créer, personnaliser et publier un message transactionnel de profil sont les mêmes que pour un message transactionnel d'événement. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).

Les différences sont énumérées ci-dessous.

1. Accédez au message transactionnel qui a été créé afin de l'éditer.
1. Dans le message transactionnel, cliquez sur la section **[!UICONTROL Contenu]**. Outre le modèle transactionnel, vous pouvez également choisir le modèle d'email par défaut qui cible **[!UICONTROL Profil]**.

   ![](assets/message-center_marketing_templates.png)

1. Sélectionnez le modèle d'email par défaut.

   Comme tous les emails marketing, il contient un lien de désinscription.

   ![](assets/message-center_marketing_perso_unsubscription.png)

   De plus, contrairement aux configurations reposant sur des événements temps réel, vous disposez d'un accès direct à toutes les informations de profil pour personnaliser votre message. Voir [Insertion d'un champ de personnalisation](../../designing/using/inserting-a-personalization-field.md).

1. Enregistrez vos modifications et publiez le message. Voir [Publier un message transactionnel](../../channels/using/event-transactional-messages.md#publishing-a-transactional-message).

## Contrôler la diffusion d'un message transactionnel selon les profils  {#monitoring-a-profile-transactional-message-delivery}

Une fois le message publié et l'intégration à un site effectuée, vous pouvez contrôler la diffusion.

1. Pour visualiser le log de diffusion du message, cliquez sur l'icône située en bas à droite du bloc **[!UICONTROL Déploiement]**.

   Pour plus d'informations sur l'accès aux logs, voir [Contrôler la diffusion](../../sending/using/monitoring-a-delivery.md).

1. Sélectionnez l'onglet **[!UICONTROL Envois]**. Dans la colonne **[!UICONTROL Statut]**, la mention **[!UICONTROL Envoyé]** indique qu'un profil s'est inscrit.

   ![](assets/message-center_marketing_sending_logs.png)

1. Sélectionnez l'onglet **[!UICONTROL Logs d'exclusion]** pour visualiser les destinataires qui ont été exclus de la cible du message, par exemple les adresses en blackliste.

   ![](assets/message-center_marketing_exclusion_logs.png)

Pour un profil qui s'est désinscrit, la règle de typologie **[!UICONTROL Adresse en blackliste]** a exclu le destinataire correspondant.

Cette règle fait partie d'une typologie spécifique qui s'applique à tous les messages transactionnels qui reposent sur la table **[!UICONTROL Profile]**.

![](assets/message-center_marketing_typology.png)

**Rubriques connexes** :

* [Intégration à un site](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)
* [Typologies](../../administration/using/about-typology-rules.md)

