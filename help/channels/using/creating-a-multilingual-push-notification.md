---
title: Création d'une notification push multilingue
description: Créez des notifications push multilingues pour cibler les utilisateurs dans leur langue et zone géographique préférées.
page-status-flag: never-activated
uuid: d4aff741-e969-47c6-bae8-787c6c673191
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: f9bb2235-d388-4025-9ace-734beb0c1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Création d&#39;une notification push multilingue{#creating-a-multilingual-push-notification}

## A propos des notifications push multilingues {#about-multilingual-push-notification}

Personnalisez le contenu des notifications push en envoyant des messages selon les préférences linguistiques et de zone géographique des utilisateurs. Vous pouvez directement importer des variantes de contenus de notification push multilingue dans l&#39;éditeur de contenus et envoyer une notification push multilingue dans une seule diffusion.

Cette fonctionnalité utilise les préférences linguistiques indiquées dans les profils des destinataires ou la préférence linguistique système des abonnés de l&#39;application mobile selon le modèle de diffusion utilisé pour la notification push. Si la préférence linguistique n&#39;est pas renseignée pour un utilisateur spécifique, le système utilise la variante par défaut qui est définie pendant la création d&#39;une notification push multilingue. Pour plus d&#39;informations sur la gestion des profils et des abonnés, consultez ce [guide](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Pour utiliser les variantes de contenus multilingues pour votre diffusion de notification push, suivez ces étapes :

* [Etape 1 : téléchargement d&#39;une variante de contenu multilingue ](#step-1--upload-multilingual-content-variant)
* [Etape 2 : aperçu et finalisation d&#39;une notification push à l&#39;aide de variantes de contenus multilingues ](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Etape 3 : envoi et analyse de la diffusion de notification push multilingue ](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Etape 1 : téléchargement d&#39;une variante de contenu multilingue  {#step-1--upload-multilingual-content-variant}

Avant de personnaliser votre notification push multilingue, vous devez télécharger les variantes de contenus dans un modèle de diffusion multilingue et créer la diffusion.

>[!NOTE]
>
>Vous pouvez également ignorer cette étape si vous souhaitez créer manuellement une variante pour chaque variante linguistique.

1. Dans la **[!UICONTROL Marketing activities]**, cliquez sur le **[!UICONTROL Create]** bouton, puis sélectionnez **[!UICONTROL Push notification]**.
1. Select the template **[!UICONTROL Send multilingual push to Campaign profiles]** if you want to target the Adobe Campaign profiles who have subscribed to your mobile application or the template **[!UICONTROL Send multilingual push to app subscriber]** to send a push notification to all users who have opted in to receive notifications from your mobile application.

   ![](assets/multivariant_push_2.png)

1. Saisissez vos propriétés de notification Push et sélectionnez votre application mobile dans le **[!UICONTROL Associate a Mobile App to a delivery]** champ.

   La liste déroulante contiendra les applications des SDK V4 et Adobe Experience Platform.

1. Dans la fenêtre **[!UICONTROL Audiences]**, déposez vos requêtes pour affiner votre audience.

   The queries added depend on the chosen template: if you chose the **[!UICONTROL Send multilingual push to Campaign profiles]** template you can query known recipients of your mobile application. Whereas if you chose the **[!UICONTROL Send multilingual push to app subscriber]** template, you can query all subscribers of a particular app who have opted in.
   >[!NOTE]
   >
   >Si vous ciblez des audiences avec des langues spécifiques, vous devez répertorier toutes les langues ciblées dans votre fichier CSV.

   ![](assets/push_notif_audience.png)

1. In the **[!UICONTROL Manage Content Variants]** window, drag and drop your file or select a file from your computer.

   The file has to be UTF8 encoded and must have a specific layout which can be found by clicking the **[!UICONTROL Download the sample file]** option. Vous devez également utiliser la syntaxe adéquate pour les valeurs des paramètres régionaux. Pour plus d&#39;informations sur le format de fichier et les paramètres régionaux pris en charge, consultez cette [technote](https://helpx.adobe.com/fr/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. After uploading your file, the language variants are automatically populated in the **[!UICONTROL Variants]** tab. Note that you can provide a **[!UICONTROL Default variant]** in the file which will be your default content variant if no preferred language is specified for the targeted user.

   ![](assets/multivariant_push_5.png)

1. The **[!UICONTROL Variant selection]** tab will provide a script to determine which language preference to take into account depending on the delivery template. Il s&#39;agit d&#39;un script d&#39;usine auquel vous n&#39;avez pas à apporter de modifications.
1. If you want to add more variants not present in the imported file, you can do so by clicking the **[!UICONTROL Add an element]** button and add as many new language variants as needed.

   Si vous ajoutez d&#39;autres variantes que celles téléchargées depuis le fichier, aucun contenu ne sera associé à cette langue. Vous devrez éditer le contenu directement dans le tableau de bord des diffusions.

   ![](assets/multivariant_push_6.png)

1. Click **[!UICONTROL Create]** when the configuration is done. You can always come back to the **[!UICONTROL Content variant]** window and make some changes from your delivery dashboard.

   ![](assets/multivariant_push_8.png)

Vous pouvez maintenant commencer à personnaliser votre notification push multilingue.

## Etape 2 : aperçu et finalisation d&#39;une notification push à l&#39;aide de variantes de contenus multilingues  {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Après avoir téléchargé le fichier comportant les variantes de contenus, vous pouvez prévisualiser différentes variantes depuis la diffusion de la notification push.

Vous avez également la possibilité de créer et éditer des variantes supplémentaires en plus de celles téléchargées à partir du fichier.

1. In the **[!UICONTROL Content]** window from the delivery dashboard, the drop-down allows you to preview your push notification content depending on the chosen language.

   ![](assets/multivariant_push_7.png)

1. Si une variante de contenu n&#39;est pas indiquée pour une langue spécifique, cliquez sur l&#39;icône représentant une cloche sous l&#39;aperçu pour commencer à ajouter du contenu à cette variante linguistique.

   By clicking the **[!UICONTROL Content]** window, the push notification represents the content from the language selected in the drop down. Les modifications apportées dans cette fenêtre n&#39;auront une incidence que sur une langue.

1. Vous pouvez également cliquer sur une variante de contenu pour la personnaliser davantage avec des champs de personnalisation par exemple.

   Pour plus d&#39;informations sur la personnalisation d&#39;un message transactionnel, consultez cette [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Click the **[!UICONTROL Content variant]** window if you want to add or delete language variants.

   Si vous ajoutez une nouvelle langue, vous devez ajouter manuellement du contenu à la notification push associée à la langue ajoutée.

   ![](assets/multivariant_push_10.png)

La diffusion de la notification push multilingue est prête à l&#39;envoi.

## Etape 3 : envoi et analyse de la diffusion de notification push multilingue  {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Les notifications push avec des variantes de contenus multilingues peuvent être maintenant envoyées à vos utilisateurs.

1. To start preparing the send, click the **[!UICONTROL Prepare]** button.
1. When the preparation is finished with no warnings, you can click the **[!UICONTROL Confirm]** button to start sending your multilingual push.

   ![](assets/multivariant_push_12.png)

1. After successfully sending your push notification, click the **[!UICONTROL Reports]** icon then **[!UICONTROL Dynamic reports]** to analyze the success of your delivery.

   ![](assets/multivariant_push_13.png)

1. Sélectionner **[!UICONTROL Push notification report]**.
1. Drag and drop the **[!UICONTROL Variant]** dimension to your panel to start filtering your data.

   ![](assets/multivariant_push_11.png)

Vous pouvez maintenant mesurer l&#39;impact de la diffusion de votre notification push multilingue sur vos destinataires.

**Rubriques connexes :**

* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Envoi d&#39;une notification push dans un workflow](../../automating/using/push-notification-delivery.md)
* [Atteindre des audiences multilingues à l&#39;aide d&#39;un seul workflow](https://helpx.adobe.com/fr/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
