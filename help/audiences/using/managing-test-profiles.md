---
title: Gestion des profils de test
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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ff9d0c3ca42606f097a34b1835d285541061e57b

---


# Gestion des profils de test {#managing-test-profiles}

## Profils de test {#about-test-profiles}

Les profils de test permettent de cibler des destinataires additionnels, qui ne correspondent pas aux critères de ciblage définis. Ils sont ajoutés à l&#39;audience d&#39;un message afin de détecter une utilisation frauduleuse de votre base de destinataire ou de contrôler la bonne réception de vos messages.

Vous pouvez gérer vos profils de test à partir du menu avancé **[!UICONTROL Profiles & audiences > Test profiles]**.

Un profil de test est un profil contenant des informations de contact fictives ou contrôlées par l&#39;expéditeur et pouvant être utilisé dans un message dans les contextes suivants :

* Pour envoyer un **Bon à tirer** : le bon à tirer (BAT) est un message spécifique qui permet de valider le message avant l&#39;envoi de la diffusion finalisée aux destinataires. Un profil de test de type Bon à tirer est chargé de la validation de la diffusion, tant sur son contenu que sur sa forme. Voir [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).
* Pour le **Rendu des emails** : un profil de test de type Rendu des emails est utilisé pour contrôler l&#39;affichage d&#39;un message en fonction de la boîte de messagerie qui le réceptionne. Par exemple : webmail, service de messagerie, mobile, etc. Voir [Rendu des emails](../../sending/using/email-rendering.md).

   L&#39;usage **Rendu des emails** est en lecture seule. Des profils de test disposant de cet usage sont disponibles uniquement nativement dans Adobe Campaign.

* Comme **Piège** : le message est envoyé au profil de test tel qu&#39;il est envoyé à la cible principale. Voir [Utilisation des pièges](../../sending/using/using-traps.md).
* Pour la **Prévisualisation** des messages : un profil de test peut être sélectionné lors de la prévisualisation d&#39;un message afin de tester les éléments de personnalisation. Voir [Prévisualiser un message](/help/sending/using/previewing-messages.md).

![](assets/test_profile.png)

## Créer un profil de test {#creating-test-profiles}

1. Pour accéder à la liste des profils de test, sélectionnez **Profils &amp; audiences > Profils de test** dans le menu de navigation (via le logo Adobe Campaign).

   ![](assets/test_profile_creation_1.png)

1. Dans le **[!UICONTROL Test profiles]** tableau de bord, cliquez sur **Créer**.

   ![](assets/test_profile_creation_2.png)

1. Renseignez les données de ce profil.

   ![](assets/test_profile_creation_3.png)

1. Sélectionnez l&#39;usage du profil de test.

   ![](assets/test_profile_creation_4.png)

1. Entrez les canaux de contact **[!UICONTROL Email, Telephone, Mobile, Mobile app]**, ainsi que l’adresse du profil de test, le cas échéant.

   >[!NOTE]
   >
   >You can define a preferred email format: **[!UICONTROL Text]** or **[!UICONTROL HTML]**.

1. Spécifiez un type d&#39;événement et les données de cet événement si vous souhaitez utiliser ce profil de test pour tester la personnalisation d&#39;un message transactionnel.
1. Click **[!UICONTROL Create]** to save the test profile.

Le profil de test est alors ajouté dans la liste des profils.

**Rubrique connexe :**

Vidéo [Créer un profil de test](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/test-profiles.html)

## Editer un profil de test {#editing-test-profiles}

Pour éditer un profil de test et consulter les données qui lui sont associées, ou pour le modifier, les étapes sont les suivantes :

1. Sélectionnez le profil de test voulu en cliquant sur son image.
1. Consultez ou modifiez les champs.

   ![](assets/test_profile_edit.png)

1. Click **[!UICONTROL Save]** if you have entered your changes, or select the name of the test profile then **[!UICONTROL Test profiles]** in the section at the top of the screen to go back to the test profiles dashboard.
