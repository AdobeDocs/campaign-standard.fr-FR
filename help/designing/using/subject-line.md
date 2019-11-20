---
title: Définition de l'objet et de l'expéditeur d'un email
description: Découvrez comment définir l'objet et l'expéditeur d'un email dans le Concepteur d'email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Définition de l'objet et de l'expéditeur d'un email{#defining-the-subject-line-of-an-email}

L'objet de l'email est obligatoire pour préparer et envoyer le message.

>[!NOTE]
>
>Si l'objet est vide, un avertissement apparaît dans le dashboard du message ainsi que dans le Concepteur d'email.

Pour configurer l'objet de l'email, accédez à l'onglet **[!UICONTROL Propriétés]** de la page d'accueil du Concepteur d'email (accessible via l'icône de maison) et remplissez la section **[!UICONTROL Objet]**.

**Pour définir l'objet d'un email** :

1. Créez un email.
1. Fermez la page d'accueil.
1. Accédez à l'onglet **[!UICONTROL Propriétés]** de la page d'accueil du Concepteur d'email (accessible par le biais de l'icône Accueil) et renseignez la section **Objet[!UICONTROL .]**

![](assets/email_designer_subject.png)

Vous pouvez également ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique à la ligne d'objet en cliquant sur les icônes correspondantes.

**Rubriques connexes :**

* [Insertion d'un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block)
* [Définir du contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Optimisation prédictive de l'objet {#predictive-subject-line}

Lors de l'édition d'un email, vous pouvez tester différents objets et obtenir une estimation de son taux d'ouverture avant l'envoi.

Cette fonctionnalité est désactivée par défaut. Elle est activée lors de l'import d'un premier modèle. Un modèle est créé à partir de jeux de données d'apprentissage spécifiques à un secteur d'activité donné. Les modèles permettent au système d'estimer le taux d'ouverture d'un email lorsqu'un nouvel objet est soumis.

>[!NOTE]
>
>Cette fonctionnalité est disponible pour les emails et les bases de données dont le contenu est en anglais uniquement. Si votre instance contient des emails dans d'autres langues, le modèle entraîné sera incohérent et donnera des résultats erronés. L'option permettant de tester un objet n'est visible que si un modèle est disponible dans votre instance.

**Rubriques connexes**

* [Test de l'objet d'un email](../../sending/using/testing-subject-line-email.md)

## Expéditeur des emails {#email-sender}

Pour définir le nom de l'expéditeur qui apparaîtra dans l'en-tête des messages, accédez à l'onglet **[!UICONTROL Propriétés]** de la page d'accueil du Concepteur d'email (accessible par le biais de l'icône Accueil).

![](assets/delivery_content_edition16.png)

* Le champ **[!UICONTROL De : nom]** permet de saisir le nom de l'expéditeur. Par défaut, le bloc **Nom de l'expéditeur** par défaut est automatiquement inscrit dans le champ. Adobe Campaign se réfère à la configuration du canal email (depuis le menu avancé **[!UICONTROL Administration &gt; Canaux &gt; Email &gt; Comptes emails]** via le logo Adobe Campaign) pour désigner cet expéditeur.

   Vous pouvez changer le nom de l'expéditeur en cliquant sur le bloc **Nom de l'expéditeur**. Le champ devient éditable et vous pouvez y inscrire le nom que vous souhaitez.

   Le champ peut être personnalisé. Pour cela, vous pouvez ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique en cliquant sur les icônes situées sous le nom de l'expéditeur.

* Le champ **[!UICONTROL De : adresse email]** n'est pas éditable depuis cette section. Vous pouvez le modifier en éditant les propriétés de l'email depuis son tableau de bord. Pour plus d'informations, voir [Liste des paramètres avancés des emails](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Les paramètres d'en-tête ne doivent pas être vides. L'adresse de l'expéditeur est obligatoire pour permettre l'envoi d'un email (norme RFC). Adobe Campaign effectue une vérification syntaxique des adresses email saisies.

**Rubriques connexes :**

* [Insertion d'un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block)
* [Définir du contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
