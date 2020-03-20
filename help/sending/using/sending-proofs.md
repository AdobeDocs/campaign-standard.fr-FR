---
title: Envoyer un bon à tirer
description: Découvrez comment envoyer des bons à tirer.
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
source-git-commit: f7f90991ed4c7323e3a2f8ac7d38da9ff165ef76

---


# Envoyer un bon à tirer {#sending-proofs}

## A propos des {#about-proofs}

Le bon à tirer (BAT) est un message spécifique qui permet de tester un message avant son envoi à la cible principale. Les destinataires du BAT sont chargés de la validation du message (contenu et forme).

Il existe deux types de :

* **Les** de test vous permettent de  autresqui ne correspondent pas aux critères de ciblage définis.

   Ils peuvent être ajoutés au  d’un message pour détecter toute utilisation frauduleuse de votre base de données de ou pour s’assurer que les courriels arrivent dans les boîtes de réception. Voir à ce sujet la section [Gérer les profils de test](../../audiences/using/managing-test-profiles.md).

   >[!NOTE]
   >
   >Pour pouvoir envoyer un bon à tirer, des profils de test doivent être inclus dans l&#39;audience de votre message.

* **Le** de substitution vous permet de vous placer à la position de l&#39;un des ciblés et d&#39;obtenir une représentation exacte du message que l&#39; recevra. Pour plus d’informations, voir [Test des messages électroniques à l’aide de](../../sending/using/testing-messages-using-target.md)de ciblés.

   >[!NOTE]
   >
   >Cette fonctionnalité est disponible uniquement pour les  par courriel.

## Envoyer un bon à tirer {#sending-a-proof}

Pour envoyer des, procédez comme suit :

1. Vérifiez que les ont été configurés :
   * **Le** de test doit être inclus dans la  de de votre message.
   * **Le** de substitution doit être ajouté une fois que la préparation du message a réussi (voir [cette section](../../sending/using/testing-messages-using-target.md)).

1. Cliquez sur le **[!UICONTROL Send a test]** bouton.

   ![](assets/bat_select.png)

1. Sélectionnez le type de BAT que vous souhaitez utiliser :

   * **[!UICONTROL Email rendering]**: sélectionnez cette option pour tester la manière dont votre message est reçu en fonction des boîtes de réception ciblées. Pour plus d&#39;informations, voir [Rendu des emails](../../sending/using/email-rendering.md).
   * **[!UICONTROL Proof]**: sélectionnez cette option pour tester le message avant de l’envoyer au principal. Les destinataires du BAT sont chargés de la validation de la diffusion, tant sur son contenu que sur sa forme.
   * **[!UICONTROL Proof + Email rendering]**: cette option combine les deux options précédentes.
   ![](assets/bat_select1.png)

   >[!NOTE]
   >
   >Le rendu du courrier électronique est disponible avec les  de test uniquement. Si aucun de test n’a été ajouté au message, seule l’ **[!UICONTROL Proof]** option est disponible pour la sélection.

1. Validez votre choix.

   Les sont envoyés aux qui ont été configurés.

   ![](assets/bat_select2.png)

1. You can view your proofs using the **[!UICONTROL Proofs]** drop-down list.

   ![](assets/bat_view.png)

1. Sélectionnez un BAT pour accéder à son résumé. For an email, if you have selected the **Email rendering** option as the proof type, the **[!UICONTROL Access email rendering]** icon is displayed on the right of the proof label. Voir [Rendu des emails](../../sending/using/email-rendering.md).

   ![](assets/bat_view2.png)

En fonction des remarques des personnes qui reçoivent le BAT, vous serez amené à modifier le contenu de la diffusion. Une fois vos modifications effectuées, vous devez relancer la préparation de l&#39;email puis envoyer à nouveau un BAT. Each new proof can be accessed using the **[!UICONTROL Show proofs]** button.

Vous devez envoyer autant de BAT que nécessaire jusqu&#39;à ce que le contenu de votre diffusion soit finalisé. Dès lors, vous pouvez envoyer la diffusion à la cible principale et clore le cycle de validation.

## Configuration de la ligne d’objet  du {#configuring-proofs-subject-line}

Lorsqu’un est envoyé, sa ligne d’objet est configurée par défaut avec le préfixe **&quot;&quot;** , ainsi qu’un compteur indiquant le numéro de la  de l’objet.

![](assets/proof-prefix.png)

Pour modifier la ligne d’objet par défaut à utiliser, procédez comme suit :

1. Dans le  du message, cliquez sur le **[!UICONTROL Open properties]** bouton.
1. Dans la **[!UICONTROL Advanced parameters]** section, définissez le préfixe que vous souhaitez utiliser par défaut dans la ligne d’objet.

Pour masquer le numéro de  du dans la ligne d’objet, activez l’ **[!UICONTROL Hide proof prefix counter]** option.

>[!NOTE]
>
>Si vous souhaitez masquer l’intégralité du préfixe du, laissez le **[!UICONTROL Subject line prefix]** champ vide.

![](assets/proof-prefix-configuration.png)

1. Clics **[!UICONTROL Confirm]**. Les paramètres seront appliqués par défaut à tous les envoyés pour le message sélectionné.

**Rubrique connexe :**

* Vidéo [Envoyer un test, préparer un email et l&#39;envoyer](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/sending-test-preparing-sending-email.html)
* [Test des messages électroniques à l’aide de](../../sending/using/testing-messages-using-target.md)de ciblés.
* [Gestion des profils de test](../../audiences/using/managing-test-profiles.md).
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Configuration du canal Email](../../administration/using/configuring-email-channel.md)
