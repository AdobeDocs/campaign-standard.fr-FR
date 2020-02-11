---
title: Envoyer un bon à tirer
description: Apprenez à envoyer des épreuves.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# Envoyer un bon à tirer {#sending-proofs}

Le bon à tirer (BAT) est un message spécifique qui permet de tester un message avant son envoi à la cible principale.

Les destinataires du BAT sont chargés de la validation du message (contenu et forme). Ils sont définis dans les **Profils de test**. Voir à ce sujet la section [Gérer les profils de test](../../audiences/using/managing-test-profiles.md).

Pour pouvoir envoyer un bon à tirer, des profils de test doivent être inclus dans l&#39;audience de votre message.

Au niveau d&#39;un message :

1. Cliquez sur le **[!UICONTROL Send a test]** bouton.

   ![](assets/bat_select.png)

1. Sélectionnez le type de BAT que vous souhaitez utiliser :

   * **[!UICONTROL Email rendering]**: sélectionnez cette option pour tester la manière dont votre message est reçu en fonction des boîtes de réception ciblées. Pour plus d&#39;informations, voir [Rendu des emails](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: sélectionnez cette option pour tester le message avant de l’envoyer à la cible principale. Les destinataires du BAT sont chargés de la validation de la diffusion, tant sur son contenu que sur sa forme.
   * **[!UICONTROL Proof + Email rendering]**: cette option combine les deux options précédentes.
   ![](assets/bat_select1.png)

1. Validez votre choix.

   Les BAT sont envoyés aux profils de test.

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. Sélectionnez un BAT pour accéder à son résumé. For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. Voir [Rendu des emails](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

En fonction des remarques des personnes qui reçoivent le BAT, vous serez amené à modifier le contenu de la diffusion. Une fois vos modifications effectuées, vous devez relancer la préparation de l&#39;email puis envoyer à nouveau un BAT. Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

Vous devez envoyer autant de BAT que nécessaire jusqu&#39;à ce que le contenu de votre diffusion soit finalisé. Dès lors, vous pouvez envoyer la diffusion à la cible principale et clore le cycle de validation.

**Rubrique connexe :**

Vidéo [Envoyer un test, préparer un email et l&#39;envoyer](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
