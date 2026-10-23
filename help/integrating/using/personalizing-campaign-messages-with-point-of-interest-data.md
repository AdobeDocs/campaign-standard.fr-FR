---
title: Personnaliser des messages Campaign avec les données de points ciblés
description: Découvrez comment créer un message personnalisé en fonction de la localisation de vos abonnés grâce à l'intégration des données de points ciblés.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: fcc79829-902d-4547-87c5-8a213e1257b7
TQID: 'https://experienceleague.adobe.com/IaSdwDcX-TJSOGn9-9vbRi9zQmRkmyCXXlanq-FvGnQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: beb7a3c1-66ab-4786-b879-7621375b3c40
    internal-label: Email marketing
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '290'
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

* [Créer un e-mail](../../channels/using/creating-an-email.md)
* [Définir le contenu](../../designing/using/personalization.md#example-email-personalization)
* [Envoyer les messages](../../sending/using/confirming-the-send.md)
