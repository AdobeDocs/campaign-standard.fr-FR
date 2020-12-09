---
solution: Campaign Standard
product: campaign
title: Modification des formats de texte brut, HTML et d'email mobile
description: Découvrez le texte simple et les modes HTML
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '828'
ht-degree: 100%

---


# Modification des formats de texte brut, HTML et d&#39;email mobile {#plain-text-and-html-modes}

Le Concepteur d&#39;emails permet de modifier différents rendus d&#39;emails. Il permet de générer une version textuelle de votre email, de modifier la source HTML d&#39;un email et de concevoir des emails visualisables sur les appareils mobiles.

## Générer une version texte de l&#39;email {#generating-a-text-version-of-the-email}

Par défaut, la version **[!UICONTROL Texte simple]** de votre email est automatiquement générée et synchronisée avec la version **[!UICONTROL Edition]**.

Les champs de personnalisation et les blocs de contenu ajoutés à la version HTML sont également synchronisés avec la version en texte brut.

>[!NOTE]
>
>Pour utiliser des blocs de contenu dans la version en texte brut, assurez-vous qu&#39;ils ne contiennent pas de code HTML.

Pour disposer d&#39;une version en texte brut différente de la version HTML, vous pouvez désactiver cette synchronisation en cliquant sur le sélecteur **[!UICONTROL Synchroniser avec le code HTML]** dans la vue **[!UICONTROL Texte brut]** de votre email.

![](assets/email_designer_textversion.png)

Vous pouvez ensuite éditer la version en texte brut comme vous le souhaitez.

>[!NOTE]
>
>Si vous éditez la version **[!UICONTROL Texte brut]** alors que la synchronisation est désactivée, la prochaine fois que vous activerez l&#39;option **[!UICONTROL Synchroniser avec le code HTML]**, toutes les modifications que vous avez apportées à la version en texte brut seront remplacées par la version HTML. Les modifications effectuées dans la vue **[!UICONTROL Texte brut]** ne peuvent pas être reflétées dans la vue **[!UICONTROL HTML]**.

## Editer la source de contenu en HTML d&#39;un email {#editing-an-email-content-source-in-html}

Pour les utilisateurs les plus expérimentés et pour des raisons de débogage, vous pouvez afficher et éditer le contenu de l&#39;email directement dans la version HTML.

Vous pouvez éditer la version HTML de l&#39;email de deux façons différentes :

* Sélectionnez **[!UICONTROL Edition]** > **[!UICONTROL HTML]** pour ouvrir la version HTML de l&#39;ensemble de l&#39;email.

   ![](assets/email_designer_html1.png)

* Dans l&#39;interface WYSIWYG, sélectionnez un élément et cliquez sur l&#39;icône **[!UICONTROL Code source]**.

   Seule la source de l&#39;élément sélectionné s&#39;affiche. Vous pouvez éditer le code source si l&#39;élément sélectionné est un composant de contenu **[!UICONTROL HTML]**. D&#39;autres composants sont en lecture seule, mais peuvent toujours être édités dans la version HTML complète de l&#39;email.

   ![](assets/email_designer_html2.png)

Si vous modifiez le code HTML, la réactivité de l&#39;email peut être altérée. Veillez à le tester à l&#39;aide du bouton **[!UICONTROL Prévisualiser]**. Voir [Prévisualiser le message](../../sending/using/previewing-messages.md).

## Conception d&#39;emails pour le rendu sur appareils mobiles {#switching-to-mobile-view}

Vous pouvez affiner le responsive design d&#39;un email en éditant séparément toutes les options de style pour l&#39;affichage mobile. Par exemple, vous pouvez adapter les marges et la marge intérieure, utiliser des polices de plus grande ou plus petite taille, modifier les boutons ou appliquer différentes couleurs de fond qui seront spécifiques à la version mobile de votre email.

Toutes les options de style sont disponibles dans la vue mobile. Les paramètres de style du Concepteur d&#39;email sont présentés plus haut sur cette page.

1. Créez un email et commencez à éditer le contenu. Voir à ce propos la section [Concevoir entièrement un contenu d&#39;email](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Pour accéder à la vue mobile dédiée, cliquez sur le bouton **[!UICONTROL Passer en vue Mobile]**.

   ![](assets/email_designer_mobile_view_switch.png)

   La version mobile de l&#39;email s&#39;affiche. Elle contient tous les composants et styles définis dans la vue de poste de travail.

1. Editez indépendamment tous les paramètres de style tels que la couleur de fond, l&#39;alignement, la marge intérieure, la marge, la famille de polices, la couleur du texte, etc.

   ![](assets/email_designer_mobile_view.png)

1. Lorsque vous éditez un paramètre de style dans la vue mobile, les modifications ne s&#39;appliquent qu&#39;à l&#39;affichage mobile.

   Par exemple, réduisez la taille d&#39;une image, ajoutez un fond vert et modifiez la marge intérieure dans la vue mobile.

   ![](assets/email_designer_mobile_view_change.png)

1. Vous pouvez masquer un composant lorsqu&#39;il est affiché sur un appareil mobile. Pour cela, sélectionnez **[!UICONTROL Afficher uniquement sur les postes de travail]** dans les **[!UICONTROL Options d&#39;affichage]**.

   Vous pouvez également choisir de masquer ce composant sur les postes de travail. Il ne s&#39;affichera donc plus que sur les appareils mobiles. Pour cela, sélectionnez **[!UICONTROL Afficher uniquement sur les appareils mobiles]**.

   Par exemple, cette option vous permet d&#39;afficher une image spécifique sur les appareils mobiles et une autre image sur les postes de travail.

   Vous pouvez définir cette option à partir de la vue mobile ou de poste de travail.

   ![](assets/email_designer_mobile_hide.png)

1. Cliquez de nouveau sur le bouton **[!UICONTROL Passer en vue Mobile]** pour retourner à la vue de poste de travail standard. Les changements de style que vous venez d&#39;effectuer ne sont pas pris en compte.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >La seule exception concerne les paramètres de **[!UICONTROL style intégré]**. Toute modification des paramètres de style intégré est également appliquée à la vue de poste de travail standard.

1. Toute autre modification apportée à la structure ou au contenu de l&#39;email, telle que des modifications de texte, le téléchargement d&#39;une nouvelle image, l&#39;ajout d&#39;un nouveau composant, etc. est également appliquée à la vue standard.

   Par exemple, passez en vue mobile, modifiez du texte et remplacez une image.

   ![](assets/email_designer_mobile_view_change_content.png)

1. Cliquez de nouveau sur le bouton **[!UICONTROL Passer en vue Mobile]** pour retourner à la vue de poste de travail standard. Les modifications sont prises en compte.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. La suppression d&#39;un style dans la vue mobile vous ramène au style appliqué en mode de poste de travail.

   Par exemple, dans la vue mobile, appliquez une couleur de fond verte à un bouton.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Passez en vue de poste de travail et appliquez un fond gris au même bouton.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Passez de nouveau en vue mobile, puis désactivez le paramètre **[!UICONTROL Couleur de fond]**.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   La couleur de fond définie dans la vue de poste de travail est maintenant appliquée : elle devient grise (non vide).

   La seule exception concerne le paramètre **[!UICONTROL Couleur de bordure]**. Lorsqu&#39;il est désactivé dans la vue mobile, aucune bordure n&#39;est plus appliquée, même si une couleur de bordure est définie dans la vue de poste de travail.

>[!NOTE]
>
>La vue mobile n&#39;est pas disponible dans les [fragments](../../designing/using/using-reusable-content.md#about-fragments).
