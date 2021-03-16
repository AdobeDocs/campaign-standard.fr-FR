---
solution: Campaign Standard
product: campaign
title: Principales étapes pour envoyer un message
description: Suivez ces étapes pour créer et envoyer des messages avec Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: 'Vue d’ensemble '
role: Professionnel
level: Début
translation-type: tm+mt
source-git-commit: a7a1aa2841410674597264927325c073fef4ce26
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 19%

---


# Principales étapes pour envoyer un message{#key-steps-to-send-a-message}

Dans cette section, vous apprendrez comment créer et envoyer des messages personnalisés à une audience ciblée à l’aide d’Adobe Campaign Standard.

Des informations spécifiques sur la création et la configuration de chaque canal de communication sont disponibles dans les sections suivantes :

* [Créer un email](../../channels/using/creating-an-email.md) 
* [Création d&#39;un SMS](../../channels/using/creating-an-sms-message.md)
* [Créer une diffusion courrier](../../channels/using/creating-the-direct-mail.md)
* [Création d’une notification](../../channels/using/preparing-and-sending-a-push-notification.md) Push.
* [Préparation et envoi d’un message In-App](../../channels/using/preparing-and-sending-an-in-app-message.md)

Pour découvrir les bonnes pratiques de diffusion, consultez la section [Bonnes pratiques de diffusion](../../sending/using/delivery-best-practices.md).

## Créer votre message

Tirez parti des activités marketing [Campaign Standard](../../start/using/marketing-activities.md) pour créer un courriel, un SMS, un courrier direct, une notification Push ou un message in-app.

![](assets/marketing-activities.png)

Les messages peuvent être créés à partir de la liste des activités marketing ou à partir d&#39;un flux de travail à l&#39;aide d&#39;[activités dédiées](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Définition de l’audience

Définissez les destinataires de votre message. Pour ce faire, utilisez l&#39;[éditeur de requête](../../automating/using/editing-queries.md) du volet gauche pour filtrer les données contenues dans votre base de données et créer des règles pour cible à votre audience.

Plusieurs types d’audiences sont disponibles :

* **** Target est la cible principale de votre courrier électronique,
* **[!UICONTROL Les]** profils de test sont les profils utilisés pour tester et valider votre courrier électronique (voir  [Gestion des profils](../../audiences/using/managing-test-profiles.md) de test).

![](assets/steps-audience.png)

## Conception et personnalisation de contenu

Dans le bloc **[!UICONTROL Contenu]**, concevez et personnalisez le contenu de votre message à l&#39;aide des champs de votre base de données. Pour plus d&#39;informations sur la conception de contenu pour un canal spécifique, consultez les sections répertoriées en haut de cette page.

![](assets/steps-content.png)

## Préparation et test

[](../../sending/using/preparing-the-send.md) Préparez le message. Ce processus calcule la population cible et prépare le message personnalisé.

![](assets/steps-prepare.png)

**Vérifiez et testez votre** message avant de l’envoyer à l’aide des fonctionnalités de Campaign Standard : prévisualisation, rendu de courrier électronique, vérification de l’exactitude, etc. Voir à ce propos [cette section](../../sending/using/previewing-messages.md).

Utilisez le bloc **[!UICONTROL Planification]** pour définir quand vos messages seront envoyés (voir [Planification des messages](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Envoi et suivi

Une fois votre message prêt, vous pouvez confirmer l’envoi. Le bloc **[!UICONTROL Déploiement]** affiche la progression de l&#39;envoi et le résultat.

![](assets/steps-send.png)

Plusieurs journaux sont disponibles pour vous aider à surveiller la diffusion de vos messages (voir [surveillance d&#39;une diffusion](../../sending/using/monitoring-a-delivery.md)). Vous pouvez également suivre le comportement de vos destinataires de diffusion grâce au Campaign Standard [fonctionnalités de suivi](../../sending/using/tracking-messages.md).

![](../../sending/using/assets/tracking_logs.png)

Mesurez l&#39;efficacité de vos messages et l&#39;évolution de vos envois et campagnes à l&#39;aide de divers indicateurs et graphiques (voir [Accès aux rapports](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
