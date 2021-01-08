---
solution: Campaign Standard
product: campaign
title: Création d'une notification push multilingue
description: Créez des notifications push multilingues pour cibler les utilisateurs dans leur langue et zone géographique préférées.
audience: channels
content-type: reference
topic-tags: push-notifications
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '988'
ht-degree: 100%

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

## Etape 1 : téléchargement d&#39;une variante de contenu multilingue     {#step-1--upload-multilingual-content-variant}

Avant de personnaliser votre notification push multilingue, vous devez télécharger les variantes de contenus dans un modèle de diffusion multilingue et créer la diffusion.

>[!NOTE]
>
>Vous pouvez également ignorer cette étape si vous souhaitez créer manuellement une variante pour chaque variante linguistique.

1. Dans **[!UICONTROL Activités marketing]**, cliquez sur le bouton **[!UICONTROL Créer]**, puis sélectionnez **[!UICONTROL Notification push]**.
1. Sélectionnez le modèle **[!UICONTROL Envoyer des notifications push multilingues aux profils Campaign]** si vous souhaitez cibler les profils Adobe Campaign abonnés à votre application mobile. Choisissez le modèle **[!UICONTROL Envoyer des notifications push multilingues aux abonnés de l&#39;application]** pour envoyer une notification push à tous les utilisateurs ayant accepté de recevoir des notifications de votre application mobile.

   ![](assets/multivariant_push_2.png)

1. Renseignez les propriétés de la notification push et sélectionnez votre application mobile dans le champ **[!UICONTROL Associer une application mobile à une diffusion]**.

   La liste déroulante contiendra les applications des SDK V4 et Adobe Experience Platform.

1. Dans la fenêtre **[!UICONTROL Audiences]**, déposez vos requêtes pour affiner votre audience.

   Les requêtes ajoutées dépendent du modèle sélectionné : si vous avez choisi le modèle **[!UICONTROL Envoyer des notifications push multilingues aux profils Campaign]**, vous pouvez interroger les destinataires connus de votre application mobile. Si vous avez sélectionné en revanche le modèle **[!UICONTROL Envoyer des notifications push multilingues aux abonnés de l&#39;application]**, vous pouvez interroger tous les abonnés d&#39;une application spécifique qui ont accepté de recevoir des notifications.
   >[!NOTE]
   >
   >Si vous ciblez des audiences avec des langues spécifiques, vous devez répertorier toutes les langues ciblées dans votre fichier CSV.

   ![](assets/push_notif_audience.png)

1. Dans la fenêtre **[!UICONTROL Gérez les variantes de contenu]**, déposez votre fichier ou sélectionnez un fichier sur votre ordinateur.

   Le fichier doit être encodé UTF8 et avoir une disposition spécifique que vous pouvez découvrir en cliquant sur l&#39;option **[!UICONTROL Télécharger le fichier d&#39;exemple]**. Vous devez également utiliser la syntaxe adéquate pour les valeurs des paramètres régionaux. Pour plus d&#39;informations sur le format de fichier et les paramètres régionaux pris en charge, consultez cette [technote](https://helpx.adobe.com/fr/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Une fois le fichier téléchargé, les variantes linguistiques sont automatiquement renseignées dans l&#39;onglet **[!UICONTROL Variantes]**. Vous pouvez fournir une **[!UICONTROL Variante par défaut]** dans le fichier qui sera la variante de contenu par défaut si aucune préférence linguistique n&#39;est indiquée pour l&#39;utilisateur ciblé.

   ![](assets/multivariant_push_5.png)

1. L&#39;onglet **[!UICONTROL Choix de la variante]** propose un script permettant de déterminer la préférence linguistique à prendre en compte selon le modèle de diffusion. Il s&#39;agit d&#39;un script d&#39;usine auquel vous n&#39;avez pas à apporter de modifications.
1. Si vous souhaitez ajouter d&#39;autres variantes qui ne sont pas présentes dans le fichier importé, vous pouvez le faire en cliquant sur le bouton **[!UICONTROL Ajouter un élément]** et en ajoutant autant de nouvelles variantes linguistiques que nécessaire.

   Si vous ajoutez d&#39;autres variantes que celles téléchargées depuis le fichier, aucun contenu ne sera associé à cette langue. Vous devrez éditer le contenu directement dans le tableau de bord des diffusions.

   ![](assets/multivariant_push_6.png)

1. Lorsque la configuration est terminée, cliquez sur **[!UICONTROL Créer]**. Vous pouvez toujours retourner dans la fenêtre **[!UICONTROL Variante du contenu]** et apporter quelques modifications depuis le tableau de bord des diffusions.

   ![](assets/multivariant_push_8.png)

Vous pouvez maintenant commencer à personnaliser votre notification push multilingue.

## Etape 2 : aperçu et finalisation d&#39;une notification push à l&#39;aide de variantes de contenus multilingues     {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Après avoir téléchargé le fichier comportant les variantes de contenus, vous pouvez prévisualiser différentes variantes depuis la diffusion de la notification push.

Vous avez également la possibilité de créer et éditer des variantes supplémentaires en plus de celles téléchargées à partir du fichier.

1. Dans la fenêtre **[!UICONTROL Contenu]** du tableau de bord des diffusions, la liste déroulante permet de prévisualiser le contenu de la notification push selon la langue sélectionnée.

   ![](assets/multivariant_push_7.png)

1. Si une variante de contenu n&#39;est pas indiquée pour une langue spécifique, cliquez sur l&#39;icône représentant une cloche sous l&#39;aperçu pour commencer à ajouter du contenu à cette variante linguistique.

   En cliquant sur la fenêtre **[!UICONTROL Contenu]**, la notification push représente le contenu de la langue sélectionnée dans la liste déroulante. Les modifications apportées dans cette fenêtre n&#39;auront une incidence que sur une langue.

1. Vous pouvez également cliquer sur une variante de contenu pour la personnaliser davantage avec des champs de personnalisation par exemple.

   Pour plus d&#39;informations sur la personnalisation d&#39;un message transactionnel, consultez cette [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Cliquez sur la fenêtre **[!UICONTROL Variante du contenu]** si vous souhaitez ajouter ou supprimer des variantes linguistiques.

   Si vous ajoutez une nouvelle langue, vous devez ajouter manuellement du contenu à la notification push associée à la langue ajoutée.

   ![](assets/multivariant_push_10.png)

La diffusion de la notification push multilingue est prête à l&#39;envoi.

## Etape 3 : envoi et analyse de la diffusion de notification push multilingue     {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Les notifications push avec des variantes de contenus multilingues peuvent être maintenant envoyées à vos utilisateurs.

1. Pour commencer à préparer l&#39;envoi, cliquez sur le bouton **[!UICONTROL Préparer]**.
1. Lorsque la préparation est terminée sans avertissement, vous pouvez cliquer sur le bouton **[!UICONTROL Confirmer]** pour commencer à envoyer votre notification push multilingue.

   ![](assets/multivariant_push_12.png)

1. Une fois la notification push envoyée, cliquez sur l&#39;icône **[!UICONTROL Rapports]** puis sur **[!UICONTROL Rapports dynamiques]** pour analyser le succès de votre diffusion.

   ![](assets/multivariant_push_13.png)

1. Sélectionnez **[!UICONTROL Rapport notification push]**.
1. Déposez la dimension **[!UICONTROL Variante]** dans le panneau pour commencer à filtrer vos données.

   ![](assets/multivariant_push_11.png)

Vous pouvez maintenant mesurer l&#39;impact de la diffusion de votre notification push multilingue sur vos destinataires.

**Rubriques connexes :**

* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Envoi d&#39;une notification push dans un workflow](../../automating/using/push-notification-delivery.md)
* [Atteindre des audiences multilingues à l&#39;aide d&#39;un seul workflow](https://helpx.adobe.com/fr/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
