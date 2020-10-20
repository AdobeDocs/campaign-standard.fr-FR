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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 100%

---


# Créer le courrier{#creating-the-direct-mail}

La création d&#39;une diffusion courrier est très similaire à celle d&#39;un email classique. Les étapes suivantes présentent la configuration qui est spécifique à ce canal. Pour plus d&#39;informations sur d&#39;autres options, reportez-vous à la section [Créer un email](../../channels/using/creating-an-email.md).

>[!NOTE]
>
>Vous pouvez également ajouter une activité de courrier à un workflow. Voir à ce propos le guide [Workflows](../../automating/using/direct-mail-delivery.md).

1. Créez une diffusion courrier depuis la [page d&#39;accueil](../../start/using/interface-description.md#home-page) Adobe Campaign, au sein d&#39;une [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou dans la [liste des activités marketing](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   ![](assets/direct_mail_1.png)

1. Sélectionnez le modèle d&#39;usine **[!UICONTROL Courrier]** ou l&#39;un de vos propres modèles. Pour plus d&#39;informations sur les modèles, reportez-vous à la section [Gestion des modèles](../../start/using/marketing-activity-templates.md).

   ![](assets/direct_mail_2.png)

1. Renseignez les propriétés générales de la diffusion.

   ![](assets/direct_mail_3.png)

1. Définissez l&#39;audience que vous souhaitez inclure dans le fichier d&#39;extraction ainsi que les profils de test et de type piège. Voir [Définir l&#39;audience du courrier](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La définition de l&#39;audience est très similaire à celle d&#39;un email classique. Voir [Créer une audience](../../audiences/using/creating-audiences.md).

1. Modifiez le contenu de votre fichier : colonnes à inclure pour chaque profil, structure du fichier, en-tête et pied de page. Voir [Définir le contenu du courrier](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Cliquez sur la section **[!UICONTROL Planning]** du tableau de bord de la diffusion pour définir la date de contact. La date de contact est obligatoire pour les courriers. Pour plus d&#39;informations, reportez-vous à la section [Planifier l&#39;envoi](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Si vous avez ajouté des profils de test (voir la section [Ajouter des profils de test et de type piège](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), vous pouvez tester votre diffusion avant de préparer le fichier final. Vous pouvez ainsi créer un fichier d&#39;exemple contenant uniquement les profils de test sélectionnés.

   Cliquez sur **[!UICONTROL Tester]** pour générer le fichier d&#39;exemple. Cliquez sur **[!UICONTROL Résumé]**, en haut à gauche, puis sélectionnez **[!UICONTROL Bons à tirer]**. Dans la partie gauche de l&#39;écran, sélectionnez le BAT et cliquez ensuite sur **[!UICONTROL Télécharger le fichier]**.

   >[!NOTE]
   >
   >Le rôle **[!UICONTROL Export]** est requis pour qu&#39;Adobe Campaign puisse exporter le fichier et permettre de le télécharger. Veuillez contacter votre administrateur.

   ![](assets/direct_mail_19.png)

1. Une fois que vous avez défini le contenu, l&#39;audience et la date de contact de la diffusion, cliquez sur le bouton **[!UICONTROL Préparer]** dans le tableau de bord de la diffusion.

   ![](assets/direct_mail_16.png)

   Les règles de typologie sont appliquées. Toutes les adresses postales non renseignées sont par exemple exclues de la cible, et c&#39;est pourquoi vous devez vérifier que la case **[!UICONTROL Adresse renseignée]** est cochée dans les informations des profils (voir [Recommandations](../../channels/using/about-direct-mail.md#recommendations)). Si vous avez défini un **[!UICONTROL Volume maximal de messages]** dans les propriétés du courrier ou au niveau du modèle, cette limite est également appliquée à ce stade.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Vous pouvez définir des règles de fatigue cross-canal globales qui excluront automatiquement les profils sur-sollicités des campagnes. Voir [Règles de fatigue](../../sending/using/fatigue-rules.md).

1. Cliquez sur **[!UICONTROL Explorer le fichier]** pour prévisualiser les 100 premières lignes du fichier.

   ![](assets/direct_mail_18.png)

   Le fichier complet peut être téléchargé en local dans la partie gauche de l&#39;écran. Le téléchargement du fichier génère une entrée de journal dans le menu **[!UICONTROL Audits des exports]**. Pour plus d&#39;informations sur les audits des exports, consultez la section [Audits des exports](../../administration/using/auditing-export-logs.md).

   >[!NOTE]
   >
   >Le rôle **[!UICONTROL Export]** est requis pour qu&#39;Adobe Campaign puisse exporter le fichier et permettre de le télécharger. Veuillez contacter votre administrateur.

   Si vous devez modifier le contenu de la diffusion, il vous suffit de cliquer sur le bouton **[!UICONTROL Regénérer le fichier]** pour que la modification soit prise en compte. Il n&#39;est pas nécessaire de recommencer la préparation.

   ![](assets/direct_mail_21.png)

1. Pour confirmer que le fichier est final, cliquez sur le bouton **[!UICONTROL Confirmer]** dans le tableau de bord de la diffusion.

   ![](assets/direct_mail_20.png)

Vous pouvez à présent envoyer le fichier d&#39;extraction à l&#39;opérateur de services postaux. Pour cela, vous disposez de plusieurs options :

* Vous pouvez l&#39;envoyer en pièce jointe dans un email classique.
* Vous pouvez l&#39;envoyer via Adobe Campaign : créez votre diffusion courrier dans un [workflow](../../automating/using/direct-mail-delivery.md) de campagne et ajoutez une activité **[!UICONTROL Transfert de fichier]** pour envoyer le fichier via FTP, par exemple. Voir à ce propos la section [Transfert de fichier](../../automating/using/transfer-file.md).

L’opérateur récupère la liste des adresses erronées et l’envoie à Adobe Campaign qui place automatiquement ces adresses dans la liste bloquée. Voir [Retour à l’expéditeur](../../channels/using/return-to-sender.md).
