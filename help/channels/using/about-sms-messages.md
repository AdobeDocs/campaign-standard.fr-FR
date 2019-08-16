---
title: A propos des SMS
seo-title: A propos des SMS
description: A propos des SMS
seo-description: Découvrez les spécificités principales du canal SMS dans Adobe Campaign.
page-status-flag: never-activated
uuid: 14dc7434-8171-4ad1-9540-52ca637659a9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 6134fe72-77de-4fd0-b794-4d966effaccf
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# A propos des SMS{#about-sms-messages}

Adobe Campaign permet de distribuer des messages SMS (Short Message Service).

>[!NOTE]
>
>Le canal SMS est un composant additionnel. Veuillez vérifier votre accord de licence.

Pour les SMS, vous pouvez créer, modifier et personnaliser les messages, au format texte uniquement. Vous pouvez également prévisualiser vos SMS avant leur envoi.

La longueur des messages SMS est limitée à 160 caractères si l'encodage GSM est utilisé, à 70 caractères seulement si le message est rédigé en Unicode. Par ailleurs, certains caractères spéciaux peuvent avoir une influence sur la longueur du message. Pour en savoir plus, consultez la section [Encodage des SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

La création d'un SMS est possible depuis le menu **[!UICONTROL Activités marketing]**, à partir d'une campagne ou dans un workflow. Voir [Créer un SMS](../../channels/using/creating-an-sms-message.md).

Pour diffuser des SMS vers un téléphone mobile, il vous faut :

* un compte externe de type **[!UICONTROL Routage]** paramétré sur le canal **[!UICONTROL Mobile (SMS)]** avec le mode de diffusion **[!UICONTROL Envoi en masse]**. Voir à ce propos la section [Routage](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing),
* un modèle de diffusion correctement lié à ce compte externe.

**Rubriques connexes :**

* [Gestion des modèles](../../start/using/about-templates.md)
* [Configuration des SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)

## Modèle de diffusion SMS {#sms-delivery-template}

Adobe Campaign met à votre disposition un modèle de diffusion vers les mobiles. Ce modèle doit être correctement associé au compte externe utilisé pour le canal **[!UICONTROL Mobile (SMS)]**. Pour y accéder et le modifier :

1. Sélectionnez **[!UICONTROL Ressources]** &gt; **[!UICONTROL Modèles]** &gt; **[!UICONTROL Modèles de diffusion]** dans le menu avancé.
1. Survolez le modèle **[!UICONTROL Envoyer par SMS]** avec la souris et sélectionnez l'option **Dupliquer l'élément**.
1. Sélectionnez le nouveau modèle.
1. Cliquez sur le bouton **[!UICONTROL Editer les propriétés]**.
1. Dans la section **[!UICONTROL Paramètres avancés]** des propriétés du modèle, assurez-vous que ce dernier est bien lié au compte externe à utiliser pour la diffusion des SMS.

   ![](assets/sms_template.png)

**Rubriques connexes :**

* [Gestion des modèles](../../start/using/about-templates.md)

