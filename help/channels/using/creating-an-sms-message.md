---
title: Créer un SMS
description: Suivez ces étapes pour créer une diffusion SMS unique dans Adobe Campaign.
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '528'
ht-degree: 100%

---


# Créer un SMS{#creating-an-sms-message}

La création d&#39;une diffusion SMS est très similaire à celle d&#39;un email classique. Les étapes suivantes présentent la configuration qui est spécifique à ce canal. Pour plus d&#39;informations sur d&#39;autres options, reportez-vous à la section [Créer un email](../../channels/using/creating-an-email.md).

Les paramètres avancés des SMS sont détaillés dans la section [Configuration des SMS](../../administration/using/configuring-sms-channel.md).

Pour créer et diffuser des SMS vers un téléphone mobile, vous devez avoir :

* un compte externe de type **[!UICONTROL Routage]** paramétré sur le canal **[!UICONTROL Mobile (SMS)]** avec le mode de diffusion **[!UICONTROL Envoi en masse]**. Voir à ce propos la section [Routage](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).
* un modèle de diffusion correctement lié à ce compte externe.

1. Créez une diffusion SMS depuis la [page d&#39;accueil](../../start/using/interface-description.md#home-page) Adobe Campaign, au sein d&#39;une [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou dans la [liste des activités marketing](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   Vous pouvez également ajouter une activité SMS à un workflow. Voir à ce propos le guide [Workflows](../../automating/using/sms-delivery.md).

   Lors de la création d&#39;un message, un assistant s&#39;affiche pour vous guider tout le long des étapes les plus importantes. Les éléments définis par le biais de l&#39;assistant peuvent toujours être édités par la suite depuis le tableau de bord du message.

1. Sélectionnez le modèle que vous souhaitez utiliser. Vous pouvez sélectionner le modèle d&#39;usine SMS ou l&#39;un de vos propres modèles.

   ![](assets/sms_creation_1.png)

   Pour diffuser vers un téléphone mobile, le modèle de diffusion doit être correctement lié au compte externe de routage des SMS.

1. Renseignez les propriétés générales du SMS.

   ![](assets/sms_creation_2.png)

   Le libellé de l&#39;activité et son identifiant apparaissent dans l&#39;interface, mais ne sont pas visibles par les destinataires des messages.

1. Indiquez l&#39;audience que vous souhaitez cibler. Vous pouvez sélectionner une audience existante ou cibler directement une population en définissant et en associant des règles.

   ![](assets/sms_creation_3.png)

1. Ajoutez du contenu à votre SMS. Vous pouvez également définir le contenu en cliquant sur la section **[!UICONTROL Contenu]** du tableau de bord de la diffusion, une fois la création du SMS terminée. Voir [A propos de la conception du contenu d&#39;un SMS](../../channels/using/about-sms-and-push-content-design.md).

   Si vous avez inséré des champs de personnalisation ou du texte conditionnel dans le contenu de votre SMS, la longueur du message varie d&#39;un destinataire à l&#39;autre, car cela peut introduire des caractères non pris en charge par l&#39;encodage GSM. La longueur du message doit être évaluée une fois la personnalisation effectuée. Voir [Personnaliser un SMS](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Validez la création du message. Son tableau de bord est alors affiché.
1. Planifiez l&#39;envoi. Le SMS peut être envoyé manuellement juste après la préparation du message ou automatiquement à une date planifiée. Voir [Planifier des messages](../../sending/using/about-scheduling-messages.md).
1. Préparez le message pour analyser sa validité, sa personnalisation et sa cible.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Vous pouvez définir des règles de fatigue cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

1. Envoyez des bons à tirer pour vérifier et valider votre message et contrôlez l&#39;inbox rendering. Voir à ce sujet la section [Envoyer un bon à tirer (BAT)](../../sending/using/sending-proofs.md).
1. Validez l&#39;envoi du message. L&#39;envoi débutera selon le planning que vous avez défini.

   ![](assets/sms_creation_7.png)

Le message est envoyé. Vous pouvez vérifier sa diffusion par le biais du tableau de bord du message et des logs.

Une fois l&#39;envoi terminé, vous pouvez commencer à mesurer l&#39;impact de votre message avec les rapports de diffusion intégrés ou personnalisés.

**Rubriques connexes :**

* [A propos de l&#39;édition du contenu d&#39;un SMS et d&#39;une notification push](../../channels/using/about-sms-and-push-content-design.md)
* [Gestion des modèles](../../start/using/marketing-activity-templates.md)
* Vidéo [Créer une diffusion SMS](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html)
