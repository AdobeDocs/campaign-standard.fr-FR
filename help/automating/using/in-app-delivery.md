---
solution: Campaign Standard
product: campaign
title: Diffusion In-App
description: L'activité Diffusion In-App permet de paramétrer l'envoi d'un message in-app dans un workflow.
audience: automating
content-type: reference
topic-tags: channel-activities
feature: Workflows
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 99%

---


# Diffusion In-App{#in-app-delivery}

## Description {#description}

![](assets/wkf_in_app_1.png)

L&#39;activité **Diffusion In-App** permet de paramétrer l&#39;envoi d&#39;un message in-app dans un workflow. La messagerie in-app permet d&#39;afficher un message lorsque l&#39;utilisateur est actif dans l&#39;application. Pour plus d&#39;informations sur la diffusion In-App, consultez cette [section](../../channels/using/about-in-app-messaging.md).

## Contexte d&#39;utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Diffusion In-App]** est généralement utilisée afin d&#39;automatiser l&#39;envoi d&#39;un message In-App à une audience cible calculée dans le même workflow.

Les destinataires sont définis en amont de l&#39;activité dans le même workflow, grâce à des activités de ciblage telles que requêtes, intersections, etc.

La préparation du message est déclenchée selon les paramètres d&#39;exécution du workflow. Depuis le tableau de bord du message, vous pouvez choisir de demander ou non une confirmation manuelle pour envoyer le message (requise par défaut). Vous pouvez lancer manuellement le workflow ou bien placer une activité de planification afin d&#39;en automatiser l&#39;exécution.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Requête]** dans votre workflow. La dimension de ciblage de l&#39;activité **[!UICONTROL Requête]** dans l&#39;onglet **[!UICONTROL Propriétés]** doit être mise à jour selon le modèle sélectionné à l&#39;étape 4 :

   * La dimension de ciblage doit être définie sur **[!UICONTROL mobileApp (mobileAppV5)]** pour le modèle **[!UICONTROL Cibler tous les utilisateurs d&#39;une application mobile (inAppBroadcast)]**.
   * La dimension de ciblage doit être définie sur **[!UICONTROL Profil (profile)]** pour le modèle **[!UICONTROL Cibler les utilisateurs en fonction de leur profil Campaign (inAppProfile)]**.
   * La dimension de ciblage doit être définie sur **[!UICONTROL abonnements à une application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** pour le modèle **[!UICONTROL Cibler les utilisateurs en fonction de leur profil Mobile (inApp)]**.

1. Placez une activité **[!UICONTROL Diffusion In-App]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.

   >[!NOTE]
   >
   >Les propriétés générales et les options avancées de l&#39;activité (et non de la diffusion elle-même) sont disponibles à l&#39;aide du bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité.

   ![](assets/wkf_in_app_3.png)

1. Sélectionnez le type de message in-app. Celui-ci dépendra des données ciblées dans votre activité **[!UICONTROL Requête]**.

   * **[!UICONTROL Cibler les utilisateurs en fonction de leur profil Campaign (inAppProfile)]** : ce type de message permet de cibler les profils Adobe Campaign abonnés à votre application mobile et de personnaliser les messages In-App avec les attributs de profil disponibles dans Campaign.
   * **[!UICONTROL Cibler tous les utilisateurs d&#39;une application mobile (inAppBroadcast)]** : ce type de message permet d&#39;envoyer un message à tous les utilisateurs de votre application mobile, même s&#39;ils ne possèdent pas de profil dans Campaign.
   * **[!UICONTROL Cibler les utilisateurs en fonction de leur profil Mobile (inApp)]** : ce type de message permet de cibler tous les utilisateurs d&#39;une application mobile ayant un profil mobile dans Campaign, qu&#39;ils soient connus ou non, et de personnaliser les messages in-app avec tous les attributs de profil obtenus à partir de l&#39;appareil mobile.

   ![](assets/wkf_in_app_4.png)

1. Renseignez les propriétés du message in-app et sélectionnez votre application mobile dans le champ **[!UICONTROL Associer une application mobile à une diffusion]**.
1. Dans l&#39;onglet **[!UICONTROL Triggers]**, placez l&#39;événement qui déclenchera votre message. Trois catégories d&#39;événements sont disponibles :
1. Définissez le contenu du message in-app. Consultez la section concernant la [personnalisation des messages in-app](../../channels/using/customizing-an-in-app-message.md).
1. Par défaut, l&#39;activité **[!UICONTROL Diffusion In-App]** ne possède aucune transition sortante. Si vous souhaitez ajouter une transition sortante à votre activité **[!UICONTROL Diffusion In-App]**, accédez à l&#39;onglet **[!UICONTROL Général]** des options avancées de l&#39;activité (bouton ![](assets/dlv_activity_params-24px.png), disponible dans les actions rapides de l&#39;activité) puis cochez l&#39;une des options suivantes :

   * **[!UICONTROL Ajouter une transition sortante sans la population]** : permet de générer une transition sortante contenant la même population que la transition entrante.
   * **[!UICONTROL Ajouter une transition sortante avec la population]** : permet de générer une transition sortante contenant la population à qui le message a été envoyé. Les membres de la cible exclus pendant la préparation de la diffusion sont exclus de cette transition.

   ![](assets/wkf_in_app_5.png)

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Lorsque vous ouvrez à nouveau l&#39;activité par la suite, vous accédez au tableau de bord du message in-app. Seul son contenu reste modifiable.

Par défaut, le démarrage d&#39;un workflow de diffusion déclenche uniquement la préparation des messages. L&#39;envoi des messages créés depuis un workflow doit toujours être confirmé après le démarrage du workflow. Dans le tableau de bord des messages, vous pouvez toutefois désactiver l&#39;option **[!UICONTROL Demander confirmation avant d&#39;envoyer les messages]** si les messages ont été créés depuis un workflow. Lorsque cette option est décochée, les messages sont envoyés sans autre préavis une fois la préparation terminée.

## Remarques        {#remarks}

Les diffusions créées à partir d&#39;un workflow sont accessibles dans la liste des activités marketing de l&#39;application. Vous pouvez visualiser l&#39;état d&#39;exécution du workflow depuis le tableau de bord. Des liens dans le volet de résumé de la notification push vous permettent d&#39;accéder directement aux éléments liés (workflow, campagne, etc.).

Depuis les diffusions parentes, accessibles depuis la liste des activités marketing, vous pouvez visualiser l&#39;ensemble des envois ayant été réalisés (en fonction de la période d&#39;agrégation définie lors du paramétrage de l&#39;activité **[!UICONTROL Diffusion In-App]**.) Pour cela, accédez au détail du bloc **[!UICONTROL Déploiement]** de la diffusion parente en sélectionnant![](assets/wkf_dlv_detail_button.png) .
