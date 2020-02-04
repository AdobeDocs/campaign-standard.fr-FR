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
source-git-commit: 259f7033310982298024462c0134989404c096f4

---


# Définition de l&#39;objet et de l&#39;expéditeur d&#39;un email{#defining-the-subject-line-of-an-email}

L&#39;objet de l&#39;email est obligatoire pour préparer et envoyer le message.

>[!NOTE]
>
>Si l&#39;objet est vide, un avertissement apparaît dans le dashboard du message ainsi que dans le Concepteur d&#39;email.

Pour configurer l&#39;objet de l&#39;email, accédez à l&#39;onglet **[!UICONTROL Propriétés]**de la page d&#39;accueil du Concepteur d&#39;email (accessible via l&#39;icône de maison) et remplissez la section**[!UICONTROL  Objet]**.

**Pour définir l&#39;objet d&#39;un email** :

1. Créez un email.
1. Fermez la page d&#39;accueil.
1. Accédez à l&#39;onglet **[!UICONTROL Propriétés]**de la page d&#39;accueil du Concepteur d&#39;email (accessible par le biais de l&#39;icône Accueil) et renseignez la section**[!UICONTROL  Objet.]**

![](assets/email_designer_subject.png)

Vous pouvez également ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique à la ligne d&#39;objet en cliquant sur les icônes correspondantes.

## Optimisation prédictive de l&#39;objet {#predictive-subject-line}

Lors de l&#39;édition d&#39;un email, vous pouvez tester différents objets et obtenir une estimation de son taux d&#39;ouverture avant l&#39;envoi.

Cette fonctionnalité est désactivée par défaut. Elle est activée lors de l&#39;import d&#39;un premier modèle. Un modèle est créé à partir de jeux de données d&#39;apprentissage spécifiques à un secteur d&#39;activité donné. Les modèles permettent au système d&#39;estimer le taux d&#39;ouverture d&#39;un email lorsqu&#39;un nouvel objet est soumis.

>[!NOTE]
>
>Cette fonctionnalité est disponible pour les emails et les bases de données dont le contenu est en anglais uniquement. Si votre instance contient des emails dans d&#39;autres langues, le modèle entraîné sera incohérent et donnera des résultats erronés. L&#39;option permettant de tester un objet n&#39;est visible que si un modèle est disponible dans votre instance.

**Rubriques connexes**

* [Test de l&#39;objet d&#39;un email](../../sending/using/testing-subject-line-email.md)

## Définition de l’expéditeur d’un email{#email-sender}

Pour définir le nom de l&#39;expéditeur qui apparaîtra dans l&#39;en-tête des messages, accédez à l&#39;onglet **[!UICONTROL Propriétés]**de la page d&#39;accueil du Concepteur d&#39;email (accessible par le biais de l&#39;icône Accueil).

![](assets/delivery_content_edition16.png)

* Le champ **[!UICONTROL De : nom]**permet de saisir le nom de l&#39;expéditeur. Par défaut, le bloc** Nom de l&#39;expéditeur **par défaut est automatiquement inscrit dans le champ. L’adresse email de l’expéditeur et le nom de l’expéditeur par défaut sont définis dans**[!UICONTROL  Marques]** et accessibles via le logo Adobe Campaign sous le menu avancé **[!UICONTROL Administration > Paramètres de l’instance > Paramétrage des marques]**.

   Vous pouvez changer le nom de l&#39;expéditeur en cliquant sur le bloc **Nom de l&#39;expéditeur**. Le champ devient éditable et vous pouvez y inscrire le nom que vous souhaitez.

   Le champ peut être personnalisé. Pour cela, vous pouvez ajouter des champs de personnalisation, des blocs de contenu et du contenu dynamique en cliquant sur les icônes situées sous le nom de l&#39;expéditeur.

* Le champ **[!UICONTROL De : adresse email]**n&#39;est pas éditable depuis cette section. Vous pouvez le modifier en éditant les propriétés de l&#39;email depuis son tableau de bord. Pour plus d&#39;informations, voir[Liste des paramètres avancés des emails](../../administration/using/configuring-email-channel.md#advanced-parameters).

>[!NOTE]
>
>Les paramètres d&#39;en-tête ne doivent pas être vides. L&#39;adresse de l&#39;expéditeur est obligatoire pour permettre l&#39;envoi d&#39;un email (norme RFC). Adobe Campaign effectue une vérification syntaxique des adresses email saisies.

**Rubriques connexes :**

* [Insertion d&#39;un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block)
* [Définir du contenu dynamique dans un email](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)
