---
title: Rendu des emails
description: Découvrez la fonctionnalité de rendu des emails.
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
feature: Send Time Optimization
role: User
level: Intermediate
exl-id: 31f4e557-55b3-4bf5-8d5d-9d412b7670a6
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 100%

---

# Rendu des e-mails{#email-rendering}

Avant d&#39;appuyer sur le bouton **[!UICONTROL Envoyer]**, vérifiez que l&#39;affichage de votre message sera optimal sur divers clients web, webmails et appareils.

Pour vous aider, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez visualiser l&#39;affichage du message envoyé dans les différents contextes de réception.

Les clients mobiles, de messagerie et webmail disponibles pour le **Rendu des emails** dans Adobe Campaign sont répertoriés sur le [site web](https://litmus.com/email-testing) de Litmus (cliquez sur **View all email clients**).

## Génération du rendu des emails {#checking-the-email-rendering-report}

Une fois que vous avez créé votre diffusion email et défini son contenu ainsi que la population ciblée, suivez la procédure décrite ci-après.

1. Cliquez sur **Audiences** afin d&#39;accéder à l&#39;onglet **[!UICONTROL Profils de test]**.

   ![](assets/email_rendering_05.png)

1. Utilisez l&#39;éditeur de requêtes pour définir les profils de test à utiliser, notamment ceux destinés à l&#39;utilisation du **Rendu des emails**. Voir [À propos des profils de test](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_rendering_06.png)

1. Validez votre requête, puis enregistrez vos modifications.
1. Cliquez sur le bouton **[!UICONTROL Tester]** présent dans la barre d&#39;actions.

   ![](assets/email_rendering_07.png)

1. Sélectionnez l&#39;option **[!UICONTROL Rendu des emails]**, puis cliquez sur **[!UICONTROL OK]**.

   ![](assets/email_rendering_08.png)

   >[!NOTE]
   >
   >L&#39;option **[!UICONTROL Bon à tirer + Rendu des emails]** vous permet d&#39;envoyer un bon à tirer et d&#39;utiliser la fonctionnalité de rendu des emails simultanément. Votre message peut être validé par les destinataires du BAT et sa réception testée en même temps en fonction des boîtes de messagerie ciblées. Dans ce cas, vous devez également sélectionner les profils de test du BAT. Voir [À propos des profils de test](../../audiences/using/managing-test-profiles.md).

   La diffusion de test est envoyée.

1. Les vignettes de rendu sont accessibles quelques minutes après l&#39;envoi des messages. Pour y accéder, sélectionnez **[!UICONTROL Bons à tirer]** dans la liste déroulante **[!UICONTROL Résumé]**.

   ![](assets/email_rendering_03.png)

1. Dans la liste **[!UICONTROL Bons à tirer]**, cliquez sur l&#39;icône **[!UICONTROL Accéder au rendu des emails]**.

   ![](assets/email_rendering_04.png)

Le rapport dédié au rendu des emails s&#39;affiche. Voir [Description du rapport de rendu des emails](#email-rendering-report-description).

**Rubriques connexes** :

* [Créer un e-mail](../../channels/using/creating-an-email.md)
* [Envoi d&#39;un bon à tirer](../../sending/using/sending-proofs.md)
* [Éditeur de requête](../../automating/using/editing-queries.md#about-query-editor)

## Rapport de rendu des emails {#email-rendering-report-description}

Ce rapport présente les rendus des emails tels qu&#39;ils apparaissent côté destinataire. Les rendus des emails peuvent être différents selon le mode d&#39;ouverture de la diffusion email par le destinataire : dans un navigateur, sur un appareil mobile ou via une application de messagerie.

### Jetons de rendu des emails

Le nombre de rendus disponibles est listé dans votre accord de licence. Chaque diffusion pour laquelle le **Rendu des emails** est activé réduit vos rendus disponibles (également appelés jetons) d&#39;une unité.

Les jetons représentent chaque rendu et non le rapport de rendu des emails complet, ce qui signifie que :

* **Chaque fois** que le rapport Rendu des emails est généré, un jeton est déduit par client de messagerie : un jeton pour le rendu Outlook 2000, un pour le rendu Outlook, un pour le rendu Apple Mail, etc.

* **Pour une même diffusion**, si vous régénérez le rapport de rendu des emails, le nombre de jetons disponibles est à nouveau réduit en fonction du nombre de rendus générés.

### Synthèse du rapport

La synthèse du rapport présente le nombre de messages reçus, indésirables, non reçus ou en attente de réception.

![](assets/inbox_rendering_report.png)

Le rapport se divise en trois parties : **[!UICONTROL Mobile]**, **[!UICONTROL Clients de messagerie]** et **[!UICONTROL Webmails]**. Faites défiler le rapport pour afficher tous les rendus regroupés dans ces trois catégories.

![](assets/inbox_rendering_report_3.png)

Pour voir les détails de chaque rapport, cliquez sur la vignette correspondante. Le rendu s&#39;affiche pour le moyen de réception sélectionné.

![](assets/inbox_rendering_report_2.png)

L&#39;onglet **[!UICONTROL Données techniques]** permet d&#39;obtenir plus d&#39;informations, telles que les dates de réception et de capture et les en-têtes complets des emails.
