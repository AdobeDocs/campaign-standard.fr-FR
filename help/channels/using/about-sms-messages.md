---
title: À propos des SMS
description: Découvrez les spécificités principales du canal SMS dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
feature: SMS
role: User
level: Beginner
exl-id: a7f22d92-dbf9-4c2b-8fc1-1e31d1e5e79c
TQID: 'https://experienceleague.adobe.com/d0IcWAf5j-JUAKKeC84Fxm-mZsfuMJ2k6GmhQfdQeFk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
    internal-label: Communication channels
subfeature_v2:
  - id: b1bd1421-1927-4c59-9bc6-ce292360e43b
    internal-label: SMS Messaging
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 100%
---
# À propos des SMS{#about-sms-messages}

Adobe Campaign permet de distribuer des messages SMS (Short Message Service).

>[!NOTE]
>
>Le canal SMS est un composant additionnel. Veuillez vérifier votre accord de licence.

Pour les SMS, vous pouvez créer, modifier et personnaliser des messages au format texte uniquement. Vous pouvez également prévisualiser les SMS avant leur envoi.

La longueur des messages SMS est limitée à 160 caractères si l&#39;encodage GSM est utilisé, à 70 caractères seulement si le message est rédigé en Unicode. Par ailleurs, certains caractères spéciaux peuvent avoir une influence sur la longueur du message. Pour en savoir plus, consultez la section [Encodage des SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

La création d’un SMS est possible depuis le menu **[!UICONTROL Activités marketing]**, à partir d’une campagne ou dans un workflow. Voir [Créer un SMS](../../channels/using/creating-an-sms-message.md).

Pour diffuser des SMS vers un téléphone mobile, il vous faut :

* un compte externe de type **[!UICONTROL Routage]** paramétré sur le canal **[!UICONTROL Mobile (SMS)]** avec le mode de diffusion **[!UICONTROL Envoi en masse]**. Pour plus d&#39;informations, consultez la section [Routage](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* un modèle de diffusion correctement lié à ce compte externe.

**Rubriques connexes :**

* [Gestion des modèles](../../start/using/marketing-activity-templates.md)
* [Configuration des SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)
* [Rapport SMS](../../reporting/using/sms-report.md)
* [Guide de Campaign Standard Mobile](../../channels/using/get-started-communication-channels.md)

## Modèle de diffusion SMS {#sms-delivery-template}

Adobe Campaign met à votre disposition un modèle de diffusion vers les appareils mobiles. Ce modèle doit être correctement associé au compte externe utilisé pour le canal **[!UICONTROL Mobile (SMS)]**. Pour y accéder et le modifier :

1. Sélectionnez **[!UICONTROL Ressources]** > **[!UICONTROL Modèles]** > **[!UICONTROL Modèles de diffusion]** depuis le menu avancé.
1. Survolez le modèle **[!UICONTROL Envoyer par SMS]** avec la souris et sélectionnez l&#39;option **Dupliquer l&#39;élément**.
1. Sélectionnez le nouveau modèle.
1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés]**.
1. Dans la section **[!UICONTROL Paramètres avancés]** des propriétés du modèle, assurez-vous que ce dernier est bien lié au compte externe à utiliser pour la diffusion des SMS.

   ![](assets/sms_template.png)

**Rubriques connexes :**

* [Gestion des modèles](../../start/using/marketing-activity-templates.md)
