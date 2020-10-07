---
title: 'Gestion des profils de test '
description: Découvrez comment gérer les profils de test.
page-status-flag: never-activated
uuid: eb4d893b-3724-4b15-9312-1ec74784368d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: preparing-and-testing-messages
discoiquuid: 37320ec5-196c-4260-8156-98932da3e4a5
context-tags: seedMember,overview
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Gestion des profils de test  {#managing-test-profiles}

## Profils de test {#about-test-profiles}

Les profils de test permettent de cibler des destinataires additionnels, qui ne correspondent pas aux critères de ciblage définis. Ils sont ajoutés à l&#39;audience d&#39;un message afin de détecter une utilisation frauduleuse de votre base de destinataire ou de contrôler la bonne réception de vos messages.

Vous pouvez gérer vos profils de test depuis le menu avancé **[!UICONTROL Profils &amp; audiences > Profils de test]**.

Un profil de test est un profil contenant des informations de contact fictives ou contrôlées par l&#39;expéditeur et pouvant être utilisé dans un message dans les contextes suivants :

* For sending **Proofs**: The Proof is a specific message used to check the message before sending the finalized delivery to recipients. Un profil de test de type Bon à tirer est chargé de la validation de la diffusion, tant sur son contenu que sur sa forme. Voir [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).
* For **Email rendering**: The Email rendering test profile is used to check the way in which a message is displayed according to the message inbox that receives it. Par exemple : webmail, service de messagerie, mobile, etc. Voir [Rendu des emails](../../sending/using/email-rendering.md).

   L&#39;usage **Rendu des emails** est en lecture seule. Des profils de test disposant de cet usage sont disponibles uniquement nativement dans Adobe Campaign.

* As a **Trap**: The message is sent to the test profile just as it is sent to the main target. Voir [Utilisation de pièges](../../sending/using/using-traps.md).
* To **Preview** messages: A test profile can be selected when previewing a message to test the personalization elements. Voir [Prévisualiser le message](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Créer un profil de test {#creating-test-profiles}

1. Pour accéder à la liste des profils de test, sélectionnez **Profils &amp; audiences > Profils de test** dans le menu de navigation (via le logo Adobe Campaign).

   ![](assets/test_profile_creation_1.png)

1. Depuis le tableau de bord des **[!UICONTROL Profils de test]**, cliquez sur **Créer**.

   ![](assets/test_profile_creation_2.png)

1. Renseignez les données de ce profil.

   ![](assets/test_profile_creation_3.png)

1. Sélectionnez l&#39;usage du profil de test.

   ![](assets/test_profile_creation_4.png)

1. Renseignez les canaux de contacts **[!UICONTROL Email, Téléphone, Mobile, Application mobile]**, ainsi que l&#39;adresse du profil de test si besoin.

   >[!NOTE]
   >
   >Vous pouvez définir une préférence de format d&#39;email : **[!UICONTROL Texte]** ou **[!UICONTROL HTML]**.

1. Spécifiez un type d&#39;événement et les données de cet événement si vous souhaitez utiliser ce profil de test pour tester la personnalisation d&#39;un message transactionnel.
1. Cliquez sur **[!UICONTROL Créer]** pour enregistrer le profil de test.

Le profil de test est alors ajouté dans la liste des profils.

**Rubrique connexe :**

Vidéo [Créer un profil de test](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html)

## Editer un profil de test {#editing-test-profiles}

Pour éditer un profil de test et consulter les données qui lui sont associées, ou pour le modifier, les étapes sont les suivantes :

1. Sélectionnez le profil de test voulu en cliquant sur son image.
1. Consultez ou modifiez les champs.

   ![](assets/test_profile_edit.png)

1. Choisissez **[!UICONTROL Enregistrer]** si vous avez saisi des modifications ; ou sélectionnez le nom du profil de test puis **[!UICONTROL Profils de test]** dans la section supérieure de l&#39;écran pour revenir au tableau de bord des profils de test.
