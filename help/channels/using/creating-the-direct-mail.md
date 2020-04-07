---
title: Créer le courrier
description: Suivez ces étapes pour créer une diffusion courrier dans Adobe Campaign.
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Créer le courrier{#creating-the-direct-mail}

La création d&#39;une diffusion courrier est très similaire à celle d&#39;un email classique. Les étapes suivantes présentent la configuration qui est spécifique à ce canal. Pour plus d&#39;informations sur d&#39;autres options, reportez-vous à la section [Créer un email](../../channels/using/creating-an-email.md).

1. Créez une diffusion courrier depuis la [page d&#39;accueil](../../start/using/interface-description.md#home-page) Adobe Campaign, au sein d&#39;une [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou dans la [liste des activités marketing](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >Vous pouvez également ajouter une activité de courrier à un workflow. Voir à ce propos le guide [Workflows](../../automating/using/direct-mail-delivery.md).

   ![](assets/direct_mail_1.png)

1. Choose either the out-of-the-box **[!UICONTROL Direct mail]** template or one of your own templates. Pour plus d&#39;informations sur les modèles, reportez-vous à la section [Gestion des modèles](../../start/using/marketing-activity-templates.md).

   ![](assets/direct_mail_2.png)

1. Renseignez les propriétés générales de la diffusion.

   ![](assets/direct_mail_3.png)

1. Définissez l&#39;audience que vous souhaitez inclure dans le fichier d&#39;extraction ainsi que les profils de test et de type piège. Voir [Définir l&#39;audience du courrier](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La définition de l&#39;audience est très similaire à celle d&#39;un email classique. Voir [Créer une audience](../../audiences/using/creating-audiences.md).

1. Editez le contenu de votre fichier : colonnes à inclure pour chaque profil, structure du fichier, en-tête et pied de page. Voir [Définir le contenu du courrier](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Click on the **[!UICONTROL Schedule]** section of the delivery dashboard to define the contact date. La date de contact est obligatoire pour les courriers. Pour plus d&#39;informations, reportez-vous à la section [Planifier l&#39;envoi](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Si vous avez ajouté des profils de test (voir la section [Ajouter des profils de test et de type piège](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), vous pouvez tester votre diffusion avant de préparer le fichier final. Vous pouvez ainsi créer un fichier d&#39;exemple contenant uniquement les profils de test sélectionnés.

   Click on **[!UICONTROL Test]** to generate the sample file. Click on **[!UICONTROL Summary]**, in the top left corner, then select **[!UICONTROL Proofs]**. On the left part of the screen, select the proof and click on **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >Le rôle **[!UICONTROL Export]** est requis pour qu&#39;Adobe Campaign puisse exporter le fichier et permettre de le télécharger. Veuillez contacter votre administrateur.

   ![](assets/direct_mail_19.png)

1. Once you have defined your delivery content, audience and contact date, click on the **[!UICONTROL Prepare]** button, on the delivery dashboard.

   ![](assets/direct_mail_16.png)

   Les règles de typologie sont appliquées. Toutes les adresses postales non renseignées sont par exemple exclues de la cible, This is why you need to make sure you have checked the **[!UICONTROL Address specified]** box in your profiles&#39; information (see [Recommendations](../../channels/using/about-direct-mail.md#recommendations)). If you have defined a **[!UICONTROL Maximum volume of message]** in the direct mail properties or at the template level, it will also be applied here.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Vous pouvez définir des règles de fatigue cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

1. Click on **[!UICONTROL Explore file]** to preview the first 100 lines of the file.

   ![](assets/direct_mail_18.png)

   Le fichier complet peut être téléchargé en local dans la partie gauche de l&#39;écran. Downloading the file generates a log entry in the **[!UICONTROL Export audits]** menu. Pour plus d&#39;informations sur les audits des exports, consultez la section [Audits des exports](../../administration/using/auditing-export-logs.md).

   >[!NOTE]
   >
   >Le rôle **[!UICONTROL Export]** est requis pour qu&#39;Adobe Campaign puisse exporter le fichier et permettre de le télécharger. Veuillez contacter votre administrateur.

   If you need to change the delivery content, you only have to click on the **[!UICONTROL Regenerate file]** button to take the change into account. Il n&#39;est pas nécessaire de recommencer la préparation.

   ![](assets/direct_mail_21.png)

1. To confirm that the file is final, click on **[!UICONTROL Confirm]** in the delivery dashboard.

   ![](assets/direct_mail_20.png)

Vous pouvez à présent envoyer le fichier d&#39;extraction à l&#39;opérateur de services postaux. Pour cela, vous disposez de plusieurs options :

* Vous pouvez l&#39;envoyer en pièce jointe dans un email classique.
* Send it via Campaign: perform your direct mail within a campaign [workflow](../../automating/using/direct-mail-delivery.md) and add a **[!UICONTROL Transfer file]** to send the file via FTP for example. Voir à ce propos la section [Transfert de fichier](../../automating/using/transfer-file.md).

L&#39;opérateur récupère la liste des adresses erronées et l&#39;envoie à Adobe Campaign qui blackliste automatiquement ces adresses. Voir [Retour à l&#39;expéditeur](../../channels/using/return-to-sender.md).
