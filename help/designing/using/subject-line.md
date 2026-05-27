---
title: Définition de l’objet et de l’expéditeur d’un email
description: Découvrez comment définir l'objet et l'expéditeur d'un email dans le concepteur d’e-mail.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Beginner
exl-id: 22112517-40f7-4966-84bf-40794e5d0f79
TQID: https://experienceleague.adobe.com/yT1UWD2C-BxfMymuwxE0vL3dYIOnnAjTf3O8Owx2S4g
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2: id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 352
ht-degree: 100%

---

# Définition de l’objet et de l’expéditeur d’un email{#defining-the-subject-line-of-an-email}

## Définition de l’objet d’un email {#subject-line}

L’objet de l’email est obligatoire pour préparer et envoyer le message.

>[!NOTE]
>
>Si l’objet est vide, un avertissement apparaît dans le tableau de bord du message ainsi que dans le concepteur d’e-mail.

1. Créez un email.
1. Accédez à l’onglet **[!UICONTROL Propriétés]** de la page d’accueil du concepteur d’e-mail (accessible par le biais de l’icône Accueil).
1. Renseignez la section **[!UICONTROL Objet]**.

   ![](assets/email_designer_subject.png)

1. Vous pouvez également ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique à la ligne d’objet en cliquant sur les icônes correspondantes. Pour plus d’informations à ce sujet, voir [Personnalisation](../../designing/using/personalization.md).

## Définition de l’expéditeur d’un email {#email-sender}

Pour définir le nom de l&#39;expéditeur qui apparaîtra dans l&#39;en-tête des messages, accédez à l&#39;onglet **[!UICONTROL Propriétés]** de la page d&#39;accueil du concepteur d’e-mail (accessible par le biais de l&#39;icône Accueil).

![](assets/delivery_content_edition16.png)

* Le champ **[!UICONTROL De : nom]** permet de saisir le nom de l’expéditeur. Par défaut, le bloc **Nom de l’expéditeur** par défaut est automatiquement inscrit dans le champ. L’adresse email de l’expéditeur et le nom de l’expéditeur par défaut sont définis dans **[!UICONTROL Marques]** et accessibles via le logo Adobe Campaign sous le menu avancé **[!UICONTROL Administration > Paramètres de l’instance > Paramétrage des marques]**.

  Vous pouvez changer le nom de l’expéditeur en cliquant sur le bloc **Nom de l’expéditeur**. Le champ devient éditable et vous pouvez y inscrire le nom que vous souhaitez.

  Le champ peut être personnalisé. Pour cela, vous pouvez ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique en cliquant sur les icônes situées sous le nom de l’expéditeur. Pour plus d’informations à ce sujet, voir [Personnalisation](../../designing/using/personalization.md).

* Le champ **[!UICONTROL De : adresse email]** n’est pas éditable depuis cette section. Vous pouvez le modifier en éditant les propriétés de l’email depuis son tableau de bord. Pour plus d’informations, voir [Liste des paramètres avancés des emails](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Les paramètres d’en-tête ne doivent pas être vides. L&#39;adresse de l&#39;expéditeur est obligatoire pour permettre l&#39;envoi d&#39;un email (norme RFC). Adobe Campaign effectue une vérification syntaxique des adresses email saisies.

**Rubriques connexes :**

* [Insertion d&#39;un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajout d&#39;un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block)
* [Définir du contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
