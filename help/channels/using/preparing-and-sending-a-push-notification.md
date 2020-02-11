---
title: Préparation et envoi d'une notification push
description: Suivez ces étapes pour créer une notification push unique dans Adobe Campaign.
page-status-flag: never-activated
uuid: 01997725-ca0a-420c-9e81-5ea801652f87
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: ec930cd4-6365-4e54-babe-9dc2eed041fc
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07d68b5bf8d800ebd95919f491e98f1b7a015705

---


# Préparation et envoi d&#39;une notification push{#preparing-and-sending-a-push-notification}

## Préparation de la notification {#preparing-the-notification}

Les étapes de création d&#39;une notification push avec Adobe Campaign sont les suivantes :

1. From the **[!UICONTROL Marketing activities]** window, [create a new marketing activity](../../start/using/marketing-activities.md#creating-a-marketing-activity).

   Il est également possible de créer une notification push unique depuis une [campagne](../../start/using/marketing-activities.md#creating-a-marketing-activity) ou à partir de la [page d&#39;accueil](../../start/using/interface-description.md#home-page) Adobe Campaign.

   Vous pouvez également utiliser une activité de diffusion notification push dans un workflow. Cette activité est présentée dans la section [Diffusion d&#39;une notification push](../../automating/using/push-notification-delivery.md).

1. Sélectionner **[!UICONTROL Push notification]**.
1. Choisissez un modèle.

   ![](assets/push_notif_type.png)

   Par défaut, vous avez le choix entre deux modèles :

   * **[!UICONTROL Send push to Campaign profiles]**: utilisez ce modèle pour cibler les profils CRM d’Adobe Campaign qui se sont abonnés à votre application mobile et ont choisi de recevoir des notifications Push. Vous pouvez insérer des champs de [personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field), tels que le prénom du destinataire, dans votre notification push.
   * **[!UICONTROL Send push to app subscribers]**: utilisez ce modèle pour envoyer une notification Push à tous les utilisateurs d’applications mobiles connus et anonymes qui ont choisi de recevoir des notifications de votre application. Vous pouvez personnaliser ces messages avec les données collectées à partir de votre application mobile.
   Vous pouvez également sélectionner des modèles multilingues. Pour plus d&#39;informations, consultez la section [Création d&#39;une notification push multilingue](../../channels/using/creating-a-multilingual-push-notification.md).

   Pour plus d&#39;informations sur les modèles, reportez-vous à la section [Gestion des modèles](../../start/using/marketing-activity-templates.md).

1. Entrez vos propriétés de notification Push et sélectionnez votre application mobile dans le **[!UICONTROL Associate a Mobile App to a delivery]** champ.

   La liste déroulante contiendra les applications des SDK V4 et Experience Platform.

   ![](assets/push_notif_properties.png)

   Vous pouvez associer la notification push à une campagne. Pour cela, sélectionnez celle-ci parmi les campagnes déjà créées.

1. Dans l&#39;écran suivant, vous pouvez spécifier une audience (tous les clients VIP qui se sont abonnés à une application mobile spécifique, par exemple). Voir à ce propos la section [Créer une audience](../../audiences/using/creating-audiences.md).

   Votre audience sera automatiquement filtrée en fonction de l&#39;application mobile sélectionnée à l&#39;étape précédente.

   ![](assets/push_notif_audience.png)

1. Vous pouvez maintenant personnaliser votre notification push. Choisissez tout d’abord le style du message : **[!UICONTROL Alert/Message/Badge]** ou **[!UICONTROL Silent push]**. Les types de notifications push sont présentés dans la section [A propos des notifications push](../../channels/using/about-push-notifications.md).

   Editez le contenu de votre notification push et définissez les options avancées. Voir la section [Personnaliser une notification push](../../channels/using/customizing-a-push-notification.md).

   ![](assets/push_notif_content.png)

   Les options et le contenu de la notification push configurés ici sont transmis à votre application mobile sous la forme d&#39;une payload. La structure détaillée de la payload est présentée dans la technote de [présentation de la structure de la payload des notifications push ACS](https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html).

1. Clics **[!UICONTROL Create]**.

   ![](assets/push_notif_content_2.png)

1. Avant d&#39;envoyer la notification, vous pouvez la tester avec des profils de test puis voir exactement à quoi elle ressemblera avant d&#39;envoyer la diffusion. Select **[!UICONTROL Audiences]** from your delivery summary and click the **[!UICONTROL Test profiles]** tab.

   Pour plus d&#39;informations sur les tests d&#39;envoi, reportez-vous à la section [Profils de test](../../sending/using/sending-proofs.md).

1. Select your test profiles and click **[!UICONTROL Preview]** to display the notification: content is personalized with the test profile data.
1. Vérifiez la présentation de la notification push sur différents appareils : sélectionnez iPhone, téléphone Android, tablette Android ou iPad pour prévisualiser le rendu.

   ![](assets/push_notif_preview.png)

1. Il **[!UICONTROL Estimated Payload Size]** s’agit d’une estimation basée sur les données du profil de test. La taille réelle du contenu peut varier. Chaque message peut aller jusqu&#39;à 4 Ko.

   >[!CAUTION]
   >
   >Si la taille du payload dépasse la limite de 4 Ko, le message n&#39;est pas envoyé. Les données de personnalisation ont un impact sur la taille du message.

## Envoyer la notification {#sending-the-notification}

Il est possible d&#39;envoyer les notifications push à une audience sélectionnée dans Adobe Campaign en définissant les critères de l&#39;audience. Pour l&#39;exemple qui suit, l&#39;audience sélectionnée est composée de 4 abonnés à des applications mobiles ciblés.

1. Click **[!UICONTROL Prepare]** to compute the target and generate the notifications.

   ![](assets/push_send_1.png)

1. Once the preparation has finished successfully, the **[!UICONTROL Deployment]** window presents the following KPIs: **[!UICONTROL Target]** and **[!UICONTROL To deliver]**. Note that the **[!UICONTROL To deliver]** count is lower than the **[!UICONTROL Targeted]** one due to exclusions which can be viewed by clicking ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_2.png)

1. In the **[!UICONTROL Exclusion logs]** tab, you can find the list of all the messages excluded from the target sent and the reason behind this exclusion.

   Ici, nous pouvons constater que l&#39;un de nos abonnés aux applications mobiles a été exclu parce que l&#39;adresse était blacklistée, et que les autres abonnés l&#39;ont été parce que le profil était un doublon.

   ![](assets/push_send_5.png)

1. Click the **[!UICONTROL Exclusion causes]** tab to display the volume of excluded messages.

   ![](assets/push_send_7.png)

1. You can now click **[!UICONTROL Confirm]** to start sending push notifications.
1. Vérifiez le statut de votre diffusion par le biais du tableau de bord du message et des logs. Pour plus d&#39;informations à ce sujet, consultez [Envoi de messages](../../sending/using/confirming-the-send.md) et [Logs de diffusion](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   Dans cet exemple, le tableau de bord du message indique qu&#39;Adobe Campaign a tenté d&#39;envoyer deux notifications push : l&#39;une a été envoyée au périphérique avec succès, mais l&#39;autre a échoué. To know why the delivery has errors, click the ![](assets/lp_link_properties.png) button at the bottom of the **[!UICONTROL Deployment]** window.

   ![](assets/push_send_4.png)

1. From the **[!UICONTROL Deployment]** window, click the **[!UICONTROL Sending logs]** tab to access the list of sent push notifications and their statuses. Pour cette diffusion, une notification push a été envoyée avec succès, tandis que l&#39;autre a échoué en raison d&#39;un token de périphérique erroné. Cet abonné sera alors blacklisté des diffusions ultérieures.

   >[!NOTE]
   >
   >Des défaillances en aval d&#39;Adobe Campaign peuvent en être la cause. Cela peut également être lié à des défaillances des fournisseurs comme apns et fcm. Pour plus d&#39;informations sur les défaillances des fournisseurs, consultez la documentation d&#39;[Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CommunicatingwithAPNs.html) et d&#39;[Android](https://firebase.google.com/docs/cloud-messaging/http-server-ref).

   ![](assets/push_send_6.png)

Vous pouvez maintenant mesurer la portée de la diffusion de votre notification push grâce aux rapports dynamiques.

**Rubriques connexes :**

* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Envoi d&#39;une notification push dans un workflow](../../automating/using/push-notification-delivery.md)

