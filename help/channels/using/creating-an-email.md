---
title: Créer un e-mail
description: Suivez ces étapes pour créer une diffusion email unique dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 100%

---

# Créer un e-mail{#creating-an-email}

La création d&#39;un email est possible au sein d&#39;une [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity), à partir de la [page d&#39;accueil](../../start/using/interface-description.md#home-page) Adobe Campaign ou dans la [liste des activités marketing](../../start/using/marketing-activities.md#about-marketing-activities). Il est également possible de créer des emails à envoi unique ou récurrent à partir d’un workflow.

![](assets/do-not-localize/how-to-video.png) [Découvrez cette fonctionnalité en vidéo](#video)

1. Une fois que vous avez commencé la création d&#39;une activité marketing de type email, choisissez le modèle que vous souhaitez utiliser.

   Chaque activité marketing propose plusieurs modèles par défaut. Cela vous permet de préconfigurer certains paramètres selon vos besoins, mais également d&#39;assigner une marque à votre diffusion. Voir à ce propos [Gérer les modèles](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Les modèles de relance et de test A/B sont masqués par défaut. Cochez les cases situées à gauche (au niveau du panneau latéral **[!UICONTROL Filtrer]**) si vous souhaitez les afficher.

1. Renseignez les propriétés générales de l’e-mail. Vous pouvez saisir un nom dans le champ **Libellé** et modifier l’identifiant.

   >[!NOTE]
   >
   >Le nom de l’activité et son identifiant apparaissent dans l’interface, mais ne sont pas visibles par les destinataires des messages.
   >
   >Assurez-vous que le champ d’identifiant ne contient pas d’espace vide pour éviter toute discordance, par exemple lors de l’intégration à Adobe Analytics.

   Vous pouvez ajouter une description, qui sera visible par l’utilisateur dans le contenu de la campagne.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >A partir de la page d&#39;accueil ou de la liste des activités marketing, vous pouvez créer votre email à l&#39;intérieur d&#39;une campagne parente. Sélectionnez celle-ci parmi les campagnes déjà créées.

1. Définissez la cible de votre message en fonction des critères de votre entreprise. Voir [À propos des profils](../../audiences/using/about-profiles.md).

   Vous pouvez également définir les profils de test qui valideront le message. Voir [Gérer les profils de test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Définissez et personnalisez le contenu du message, le nom de l&#39;expéditeur et l&#39;objet à l&#39;aide du [Concepteur d&#39;email](../../designing/using/designing-content-in-adobe-campaign.md). Voir à ce propos [A propos de la conception du contenu d&#39;un email](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Vous pouvez concevoir votre message directement au moyen d&#39;un modèle de contenu prédéfini, ou utiliser Dreamweaver ou Adobe Experience Manager. Si vous ne souhaitez pas concevoir le contenu par vous-même, vous pouvez également charger un contenu qui a été préparé pour vous ou importer un contenu existant depuis une URL. Voir [Sélectionner un contenu existant](../../designing/using/using-existing-content.md).

1. Prévisualisez votre message. Voir [Prévisualiser le message](../../sending/using/previewing-messages.md).
1. Validez la création de l&#39;email.

   >[!NOTE]
   >
   >Pour pouvoir enregistrer votre email, vous devez éditer le contenu. Si vous cliquez sur **[!UICONTROL Annuler]** à cette étape, vous ne terminerez pas l&#39;assistant et votre email ne sera pas créé.

   Le tableau de bord de l&#39;email s&#39;affiche alors. Il vous permet de vérifier votre message et de [préparer l&#39;envoi](../../sending/using/preparing-the-send.md).

   Le bouton **[!UICONTROL Editer les propriétés]** dans le coin supérieur droit permet d&#39;éditer les propriétés de l&#39;email. Vous pouvez, par exemple, configurer l&#39;email de sorte que son libellé soit calculé au moment de la préparation de la diffusion. Les paramètres disponibles sont répertoriés dans [cette section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Planifiez l’envoi. Voir [Planifier des messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Préparez votre message afin d&#39;analyser sa cible. Voir [Préparer l&#39;envoi](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Vous pouvez définir des règles de fatigue cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes. Voir à ce propos [Règles de fatigue](../../sending/using/fatigue-rules.md).

1. Envoyez des BAT pour vérifier et valider votre message et suivre son rendu dans la boîte de réception. Voir [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Envoyez le message et vérifiez sa diffusion à l&#39;aide du dashboard de message et des logs. Voir [Envoyer un message](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mesurez l&#39;impact de votre message avec des rapports de diffusion. Pour plus d&#39;informations sur le reporting, voir [cette section](../../reporting/using/about-dynamic-reports.md).

**Rubriques connexes** :

* [Créer un e-mail personnalisé](../../channels/using/key-steps-to-send-a-message.md) : guide pas à pas
* [Intégration avec Adobe Campaign et de Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Intégration avec Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Tutoriel vidéo {#video}

Cette vidéo montre comment créer un e-mail.

>[!VIDEO](https://video.tv.adobe.com/v/30952?quality=12&captions=fre_fr)

D’autres vidéos pratiques sur Campaign Standard sont disponibles [ici](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=fr).
