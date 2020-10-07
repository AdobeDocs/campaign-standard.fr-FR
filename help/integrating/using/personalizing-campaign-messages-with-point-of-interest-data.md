---
title: Personnaliser des messages Campaign avec les données de points ciblés
description: Découvrez comment créer un message personnalisé en fonction de la localisation de vos abonnés grâce à l'intégration des données de points ciblés.
page-status-flag: never-activated
uuid: d74c3e55-f130-441b-bc2a-06ddcd5d9784
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: a1736ba3-5121-4d01-bf04-ebb7e701e2e0
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 100%

---


# Personnaliser des messages Campaign avec les données de points ciblés{#personalizing-campaign-messages-with-point-of-interest-data}

Dans Adobe Campaign, vous pouvez utiliser les données de points ciblés collectées auprès des abonnés de votre application mobile pour leur envoyer des messages marketing personnalisés, comme un email.

Seules les diffusions standard vous permettent d&#39;utiliser des données de points ciblés. Les [messages transactionnels](../../channels/using/getting-started-with-transactional-msg.md) ne sont pas compatibles avec cette fonctionnalité.

Il faut compter au moins 10 minutes avant de pouvoir utiliser les données reçues.

Dans cet exemple, vous décidez d&#39;envoyer un email à tous vos abonnés s&#39;étant rendus dans votre boutique de Lyon au cours des quinze derniers jours.

1. Créez une activité marketing de type Email.
1. Lors de la définition de l’audience de la diffusion, placez l’élément **[!UICONTROL Abonnements à une application]** dans l’espace de travail.

   ![](assets/poi_subscriptions_app.png)

   La gestion des audiences est présentée dans la section [Définir les audiences](../../audiences/using/creating-audiences.md).

1. Dans la fenêtre **[!UICONTROL Ajouter une règle - Profil/Abonnements à une application]**, placez l’élément **[!UICONTROL Inscription à la localisation Point ciblé]** dans l’espace de travail.

   ![](assets/poi_add_rule_profile_subscription.png)

1. Dans la fenêtre **[!UICONTROL Ajouter une règle - Inscription à la localisation Point ciblé]**, saisissez le libellé du point ciblé que vous souhaitez utiliser.

   ![](assets/poi_location_subscription.png)

1. Dans le champ **[!UICONTROL Type de filtre]**, sélectionnez **[!UICONTROL Relatif]**.
1. Cochez l’option **[!UICONTROL Les derniers jours]** et saisissez **[!UICONTROL 15]** dans le champ correspondant.
1. Définissez le nombre de fois que l’utilisateur doit avoir fréquenté le point ciblé.
1. Cliquez sur **[!UICONTROL Confirmer]** pour sauvegarder votre audience.

   ![](assets/poi_subscriptions_app_audience_defined.png)

1. Ajoutez du contenu à votre email.

   ![](assets/poi_email_content.png)

1. Confirmez la création de l&#39;activité pour voir le tableau de bord de l&#39;email.
1. Envoyez votre message.

L&#39;email contenant la réduction de 10 % sera envoyé aux abonnés :

* qui se sont rendus dans votre boutique de Lyon au moins une fois au cours des quinze derniers jours ;
* qui ont eu votre application mobile au premier plan au moins une fois dans votre boutique.

**Rubriques connexes :**

* [Créer un email](../../channels/using/creating-an-email.md)
* [Définir le contenu](../../designing/using/personalization.md#example-email-personalization)
* [Envoyer les messages](../../sending/using/confirming-the-send.md)

