---
solution: Campaign Standard
product: campaign
title: Ajout de liens
description: Découvrez comment gérer des liens avec le Concepteur d'email.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 100%

---


# Ajout de liens {#links}

## Insérer un lien {#inserting-a-link}

L&#39;éditeur vous permet de personnaliser un email ou une landing page en insérant des liens dans les éléments du contenu HTML.

Vous pouvez insérer un lien sur tout élément de la page : image, mot, groupe de mots, bloc de texte, etc.

>[!NOTE]
>
>Les images ci-après illustrent l&#39;insertion d&#39;un lien à l&#39;aide du [Concepteur d&#39;email](../../designing/using/designing-content-in-adobe-campaign.md).

1. Sélectionnez un élément et cliquez sur **[!UICONTROL Insérer un lien]** dans la barre d&#39;outils contextuelle.

   ![](assets/des_insert_link.png)

1. Sélectionnez le type de lien que vous souhaitez créer :

   * **Lien externe** : insérez un lien vers une URL externe.

      Vous pouvez définir la personnalisation des URL. Voir [Personnaliser une URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Landing page** : donnez accès à une landing page Adobe Campaign.
   * **Lien d&#39;abonnement** : insérez un lien pour s&#39;abonner à un service Adobe Campaign.
   * **Lien de désabonnement** : insérez un lien pour se désabonner d&#39;un service Adobe Campaign.
   * **Lien définissant une action** : définissez une action qui se produit lors d&#39;un clic sur la landing page.

      >[!NOTE]
      >
      >Ce type de lien est uniquement disponible pour les landing pages.

1. Vous pouvez modifier le texte qui s&#39;affiche pour le destinataire.
1. Vous pouvez définir le comportement du navigateur lorsque l&#39;utilisateur clique sur le lien (ouverture d&#39;une nouvelle fenêtre, par exemple).

   >[!NOTE]
   >
   >La définition du comportement du navigateur s&#39;applique uniquement aux landing pages.

1. Enregistrez vos modifications.

Une fois le lien créé, vous pouvez encore le modifier dans le volet Paramètres. Cliquez sur l&#39;icône de crayon pour éditer ses paramètres.

![](assets/des_link_edit.png)

Lorsque vous éditez un email à l&#39;aide du [Concepteur d&#39;email](../../designing/using/designing-content-in-adobe-campaign.md), vous pouvez facilement accéder aux liens créés à partir du tableau répertoriant toutes les URL incluses dans l&#39;email et les modifier. Cette liste permet d&#39;avoir une vue centrale et de localiser chaque URL dans le contenu de l&#39;email. Pour y accéder, reportez-vous à la section [A propos des URL trackées](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>Les URL personnalisées telles que l&#39;**URL de la page miroir** ou le lien de **désabonnement** ne peuvent pas être modifiées depuis cette liste. Tous les autres liens sont modifiables.

**Rubriques connexes** :

* [Insertion d&#39;un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Ajouter un bloc de contenu](../../designing/using/personalization.md#adding-a-content-block)
* [Définir un contenu dynamique](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## A propos des URL trackées {#about-tracked-urls}

Adobe Campaign vous permet de tracker le comportement de vos destinataires lorsqu&#39;ils cliquent sur une URL incluse dans un email. Pour plus d’informations sur le tracking, consultez [cette section](../../sending/using/tracking-messages.md#about-tracking).

L&#39;icône **[!UICONTROL Liens]** de la barre d&#39;action affiche automatiquement la liste des toutes les URL de votre contenu qui seront trackées.

![](assets/des_links.png)

>[!NOTE]
>
>Par défaut, le tracking est activé. Cette fonctionnalité n&#39;est disponible que pour les emails, même si le tracking a été activé dans Adobe Campaign. Pour plus d&#39;informations sur les paramètres de tracking, voir [cette section](../../administration/using/configuring-email-channel.md#tracking-parameters).

L&#39;URL, la catégorie, le libellé et le type de tracking de chaque lien peuvent être modifiés à partir de cette liste. Pour éditer un lien, cliquez sur l&#39;icône de crayon correspondante.

![](assets/des_links_tracking.png)

Pour chaque URL trackée, vous pouvez définir le mode de tracking sur l&#39;une des valeurs suivantes :

* **Tracké** : active le tracking sur cette URL.
* **Page miroir** : considère cette URL comme une URL de page miroir.
* **Jamais** : n&#39;active jamais le tracking de cette URL. Ces informations sont enregistrées : si l&#39;URL apparaît à nouveau dans un message futur, son tracking est automatiquement désactivé.
* **Opt-out** : considère cette URL comme une option d&#39;opt-out ou une URL de désabonnement.

![](assets/des_link_tracking_type.png)

Vous pouvez aussi désactiver ou activer le tracking pour chaque URL.

>[!NOTE]
>
>Dans Adobe Campaign, toutes les URL de contenu sont trackées par défaut, à l&#39;exception de l&#39;**URL de la page miroir** et du lien de **désabonnement**.

Vous avez la possibilité de regrouper vos URL en éditant le champ **[!UICONTROL Catégorie]** en fonction de l&#39;utilisation des URL dans le message. Ces catégories peuvent être des rapports affichés, comme dans le cas de [URL et flux de clics](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

Lorsque vous créez un rapport, dans l&#39;onglet **[!UICONTROL Composants]**, sélectionnez **[!UICONTROL Dimension]** et faites défiler la liste vers le bas afin d&#39;accéder aux composants de tracking. Par exemple, faites glisser **[!UICONTROL Catégorie de l&#39;URL de tracking]** et déposez-la dans l&#39;espace de travail de façon à afficher les résultats en fonction de la catégorie de tracking de chaque URL faisant l&#39;objet d&#39;un clic.

![](assets/des_link_tracking_report.png)

Pour plus d&#39;informations sur la création de rapports personnalisés, voir [cette section](../../reporting/using/about-dynamic-reports.md).
