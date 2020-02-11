---
title: Rendu des emails
description: Découvrez la fonctionnalité de rendu des emails.
page-status-flag: never-activated
uuid: c423e237-ad39-4797-ac3a-4320894a8f99
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 2b5b13c8-2e51-4985-a161-c1d7f0fc32b4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Rendu des emails{#email-rendering}

Before hitting the **[!UICONTROL Send]** button, make sure that your message will be displayed in an optimal way on a variety of web clients, web mails and devices.

Pour vous aider, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez visualiser l&#39;affichage du message envoyé dans les différents contextes de réception.

Les clients mobiles, de messagerie et webmail disponibles pour le **Rendu des emails** dans Adobe Campaign sont répertoriés sur le [site web](https://litmus.com/email-testing) de Litmus (cliquez sur **View all email clients**).

## Consulter le rapport de rendu des emails {#checking-the-email-rendering-report}

Une fois que vous avez créé votre diffusion email et défini son contenu ainsi que la population ciblée, suivez la procédure décrite ci-après.

1. Click **Audience** to access the **[!UICONTROL Test profiles]** tab.

   ![](assets/email_rendering_05.png)

1. Utilisez l&#39;éditeur de requêtes pour définir les profils de test à utiliser, notamment ceux destinés à l&#39;utilisation du **Rendu des emails**. Voir [À propos des profils de test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Validez votre requête, puis enregistrez vos modifications.
1. Click the **[!UICONTROL Test]** button in the action bar.

   ![](assets/email_rendering_07.png)

1. Sélectionnez l’ **[!UICONTROL Email rendering]** option, puis cliquez sur **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Proof + Email rendering]** option enables you to send a proof and use the email rendering feature simultaneously. Votre message peut être validé par les destinataires du BAT et sa réception testée en même temps en fonction des boîtes de messagerie ciblées. Dans ce cas, vous devez également sélectionner les profils de test du BAT. Voir [À propos des profils de test](../../audiences/using/managing-test-profiles.md).

   La diffusion de test est envoyée.

1. Les vignettes de rendu sont accessibles quelques minutes après l&#39;envoi des messages. To access them, select **[!UICONTROL Proofs]** in the **[!UICONTROL Summary]** drop-down list.

   ![](assets/email_rendering_03.png)

1. Dans la **[!UICONTROL Proofs]** liste, cliquez sur l’ **[!UICONTROL Access email rendering]** icône .

   ![](assets/email_rendering_04.png)

Le rapport dédié au rendu des emails s&#39;affiche. Voir [Description du rapport de rendu des emails](#email-rendering-report-description).

**Rubriques connexes** :

* Vidéo [Créer un email](../../channels/using/creating-an-email.md)  
* [Envoyer un bon à tirer](../../sending/using/sending-proofs.md)
* [Editeur de requête](../../automating/using/editing-queries.md#about-query-editor)

## Description du rapport de rendu des emails {#email-rendering-report-description}

Ce rapport présente les rendus des emails tels qu&#39;ils apparaissent côté destinataire. Les rendus des emails peuvent être différents selon le mode d&#39;ouverture de la diffusion email par le destinataire : dans un navigateur, sur un appareil mobile ou via une application de messagerie.

>[!NOTE]
>
>Le nombre de rendus disponibles est listé dans votre accord de licence. Chaque diffusion pour laquelle le **Rendu des emails** est activé réduit vos rendus disponibles (également appelés jetons) d&#39;une unité. Si vous êtes un client Litmus, vous pouvez utiliser votre compte Litmus pour activer et utiliser l&#39;option Rendu des emails dans Adobe Campaign. Pour plus d&#39;informations, contactez votre gestionnaire de compte Adobe.

La synthèse du rapport présente le nombre de messages reçus, indésirables, non reçus ou en attente de réception.

![](assets/inbox_rendering_report.png)

Le rapport se divise en trois parties : **[!UICONTROL Mobile]**, **[!UICONTROL Messaging clients]** et **[!UICONTROL Webmails]**. Faites défiler le rapport pour afficher tous les rendus regroupés dans ces trois catégories.

![](assets/inbox_rendering_report_3.png)

Pour voir les détails de chaque rapport, cliquez sur la vignette correspondante. Le rendu s&#39;affiche pour le moyen de réception sélectionné.

![](assets/inbox_rendering_report_2.png)

The **[!UICONTROL Technical data]** tab allows you to get more information, such as the receiving and capture dates, and the complete headers of emails.
