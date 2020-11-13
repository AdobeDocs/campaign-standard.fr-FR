---
title: Créer un email
description: Suivez ces étapes pour créer une diffusion email unique dans Adobe Campaign.
page-status-flag: never-activated
uuid: 74c7ef35-82c0-4bc4-b1f6-8e74fdcaea3c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: b27e0170-e73f-4782-8568-02927fb374f4
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '553'
ht-degree: 100%

---


# Créer un email{#creating-an-email}

La création d&#39;un email est possible au sein d&#39;une [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity), à partir de la [page d&#39;accueil](../../start/using/interface-description.md#home-page) Adobe Campaign ou dans la [liste des activités marketing](../../start/using/marketing-activities.md#about-marketing-activities). Il est également possible de créer des emails à envoi unique ou récurrent à partir d’un workflow.

1. Une fois que vous avez commencé la création d&#39;une activité marketing de type email, choisissez le modèle que vous souhaitez utiliser.

   Chaque activité marketing propose plusieurs modèles par défaut. Cela vous permet de préconfigurer certains paramètres selon vos besoins, mais également d&#39;assigner une marque à votre diffusion. Voir à ce propos [Gérer les modèles](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Les modèles de relance et de test A/B sont masqués par défaut. Cochez les cases situées à gauche (au niveau du panneau latéral **[!UICONTROL Filtrer]**) si vous souhaitez les afficher.

1. Renseignez les propriétés générales de l&#39;email. Vous pouvez saisir un nom dans le champ **Libellé** et modifier l&#39;identifiant. Le nom de l&#39;activité et son identifiant apparaissent dans l&#39;interface, mais ne sont pas visibles par les destinataires des messages.

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

   Vous pouvez concevoir votre message directement au moyen d&#39;un modèle de contenu prédéfini, ou utiliser Dreamweaver ou Adobe Experience Manager. Si vous ne souhaitez pas concevoir le contenu par vous-même, vous pouvez également charger un contenu qui a été préparé pour vous ou importer un contenu existant depuis une URL. Voir [Sélectionner un contenu existant](../../designing/using/using-existing-content.md).

1. Prévisualisez votre message. Voir [Prévisualiser le message](../../sending/using/previewing-messages.md).
1. Validez la création de l&#39;email.

   >[!NOTE]
   >
   >Pour pouvoir enregistrer votre email, vous devez éditer le contenu. Si vous cliquez sur **[!UICONTROL Annuler]** à cette étape, vous ne terminerez pas l&#39;assistant et votre email ne sera pas créé.

   Le tableau de bord de l&#39;email s&#39;affiche alors. Il vous permet de vérifier votre message et de [préparer l&#39;envoi](../../sending/using/preparing-the-send.md).

   Le bouton **[!UICONTROL Editer les propriétés]** dans le coin supérieur droit permet d&#39;éditer les propriétés de l&#39;email. Vous pouvez, par exemple, configurer l&#39;email de sorte que son libellé soit calculé au moment de la préparation de la diffusion. Les paramètres disponibles sont répertoriés dans [cette section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Planifiez l&#39;envoi. Voir [Planifier des messages](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Préparez votre message afin d&#39;analyser sa cible. Voir [Préparer l&#39;envoi](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Vous pouvez définir des règles de fatigue cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes. Voir à ce propos [Règles de fatigue](../../sending/using/fatigue-rules.md).

1. Envoyez des bons à tirer à vérifier, validez votre message et suivez son rendu dans la boîte de réception. Voir [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Envoyez le message et vérifiez sa diffusion à l&#39;aide du dashboard de message et des logs. Voir [Envoyer un message](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mesurez l&#39;impact de votre message avec des rapports de diffusion. Pour plus d&#39;informations sur le reporting, voir [cette section](../../reporting/using/about-dynamic-reports.md).

**Rubriques connexes** :

* Vidéo [Créer un email](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)  
* Guide détaillé [Créer un email personnalisé](https://helpx.adobe.com/fr/campaign/kb/acs-get-started-with-emails.html)
* Vidéo [Intégration d&#39;Adobe Campaign et de Dreamweaver](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html)
* [Intégrer avec Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)
