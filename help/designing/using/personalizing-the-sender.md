---
title: Personnaliser l'expéditeur
seo-title: Personnaliser l'expéditeur
description: Personnaliser l'expéditeur
seo-description: Découvrez comment personnaliser le nom de l'adresse de l'expéditeur pour vos messages.
page-status-flag: never-activated
uuid: 7aa08d5d-9e6c-4dac-bff8-6fde85368c2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: personalizing-content
discoiquuid: 49532f6b-3cd0-4d03-932e-bcb7d05c74d4
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Personnaliser l'expéditeur{#personalizing-the-sender}

## Expéditeur des emails {#email-sender}

Pour définir le nom de l'expéditeur qui apparaîtra dans l'en-tête des messages, accédez à l'onglet **[!UICONTROL Propriétés]** de la page d'accueil du Concepteur d'email (accessible par le biais de l'icône Accueil).

![](assets/delivery_content_edition16.png)

* Le champ **[!UICONTROL De : nom]** permet de saisir le nom de l'expéditeur. Par défaut, le bloc **Nom de l'expéditeur** par défaut est automatiquement inscrit dans le champ. Adobe Campaign se réfère à la configuration du canal email (depuis le menu avancé **[!UICONTROL Administration &gt; Canaux &gt; Email &gt; Comptes emails]** via le logo Adobe Campaign) pour désigner cet expéditeur.

   Vous pouvez changer le nom de l'expéditeur en cliquant sur le bloc **Nom de l'expéditeur**. Le champ devient éditable et vous pouvez y inscrire le nom que vous souhaitez.

   Le champ peut être personnalisé. Pour cela, vous pouvez ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique en cliquant sur les icônes situées sous le nom de l'expéditeur.

* Le champ **[!UICONTROL De : adresse email]** n'est pas éditable depuis cette section. Vous pouvez le modifier en éditant les propriétés de l'email depuis son tableau de bord. Voir à ce propos la section [Liste des paramètres avancés des emails](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Les paramètres d'en-tête ne doivent pas être vides. L'adresse de l'expéditeur est obligatoire pour permettre l'envoi d'un email (norme RFC). Adobe Campaign effectue une vérification syntaxique des adresses email saisies.

**Rubriques connexes :**

* [Insertion d'un champ de personnalisation](../../designing/using/inserting-a-personalization-field.md)
* [Ajouter un bloc de contenu](../../designing/using/adding-a-content-block.md)
* [Définir du contenu dynamique dans un email](../../designing/using/defining-dynamic-content-in-an-email.md)

## Expéditeur des SMS {#sms-sender}

Vous pouvez personnaliser le nom de l'expéditeur du SMS. Pour en savoir plus, consultez la section [Configuration des SMS](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).
