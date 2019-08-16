---
title: Personnaliser une notification push
seo-title: Personnaliser une notification push
description: Personnaliser une notification push
seo-description: Découvrez comment personnaliser vos notifications push à l'aide de diverses options avancées.
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
internal: n
snippet: y
translation-type: ht
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Personnalisation d'une notification push{#customizing-a-push-notification}

Pour parfaire votre notification push, Adobe Campaign vous permet d'accéder à un ensemble d'options avancées lors de sa création.

En tant qu'utilisateur expert, consultez la note technique [Présentation de la structure de la payload des notifications push Campaign Standard](https://helpx.adobe.com/fr/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html) pour configurer des applications mobiles dans Adobe Campaign.

![](assets/push_notif_advanced.png)

**Contenu connexe :**

* [Rapport des notifications push (Push notification)](../../reporting/using/push-notification-report.md)
* [Envoi d'une notification push dans un workflow](../../automating/using/push-notification-delivery.md)

## Jouer un son {#play-a-sound}

La fonction **[!UICONTROL Jouer un son]** permet à l'application d'émettre des sons sur l'appareil lors de la diffusion d'une notification push, lorsqu'elle n'est pas en cours d'exécution.

Un son permet d'avertir l'utilisateur lors de la réception d'une notification push, ce qui lui donne davantage de visibilité. Pour ajouter un son à votre application mobile :

1. Ouvrez la notification push et accédez à la section **[!UICONTROL Options avancées]**.
1. Dans le champ **[!UICONTROL Jouer un son]**, entrez le nom du fichier son, sans l'extension, que doit lancer le terminal mobile à réception de la notification.

   Pour plus d'informations sur les formats multimédias pris en charge, consultez la documentation [Apple](https://support.apple.com/kb/PH16864?locale=fr_FR) et [Android](https://developer.android.com/guide/topics/media/media-formats.html).

   ![](assets/push_notif_advanced_7.png)

1. Le fichier son est lu lors de la diffusion de la notification s'il est défini dans le package de l'application mobile. Sinon, le son par défaut de l'appareil est émis.

L'utilisateur reçoit ensuite la notification push. Le son est émis uniquement si le téléphone n'est pas muet.

## Actualiser la valeur du badge  {#refresh-the-badge-value}

Un badge est utilisé pour afficher le nombre de nouvelles informations non lues directement sur l'icône de l'application. La valeur du badge disparaît dès que l'utilisateur ouvre ou lit le nouveau contenu de l'application.

A la réception d'une notification sur un appareil, la valeur du badge de l'application associée peut être actualisée ou ajoutée. Pour envoyer une valeur de badge du côté serveur :

1. Ouvrez la notification push et accédez à la section **[!UICONTROL Options avancées]**.
1. La valeur du badge doit être un entier et peut être mise à jour de plusieurs manières différentes :

   * Pour actualiser le badge, saisissez 0 dans le champ **[!UICONTROL Valeur du badge]**. Le badge est alors supprimé de l'icône de l'application.
   * Pour ajouter une valeur de badge, saisissez n'importe quel nombre dans le champ **[!UICONTROL Valeur du badge]**. Ce nombre apparaîtra automatiquement dans le badge dès réception de la notification push par l'utilisateur.
   * Si le champ est vide ou s'il ne contient pas d'entier, la valeur du badge ne change pas.
   Dans cet exemple, la valeur 1 a été saisie dans le champ **[!UICONTROL Valeur du badge]** pour indiquer aux utilisateurs que l'application contient une nouvelle information.

   ![](assets/push_notif_advanced_8.png)

1. Une fois le message envoyé, les utilisateurs recevront la notification push. L'application affichera alors automatiquement la nouvelle valeur de badge.

   ![](assets/push_notif_advanced_1.png)

## Ajouter un lien profond  {#add-a-deeplink}

Un lien profond vous permet d'amener directement les utilisateurs à un contenu situé dans l'application (au lieu d'ouvrir une page de navigateur Web).

Un lien profond peut contenir des données de personnalisation permettant d'adapter le contenu à chaque utilisateur. Par exemple, les prénoms des destinataires sont remplis automatiquement sur la page vers laquelle l'application les envoie.

Pour ajouter un lien profond à une notification push :

1. Ouvrez la notification push et accédez à la section **[!UICONTROL Options avancées]**.
1. Saisissez le lien dans le champ **[!UICONTROL Ajouter un lien profond]**.

   ![](assets/push_notif_advanced_3.png)

1. Une fois le message envoyé, les utilisateurs recevront la notification push puis accéderont à la page spécifique de l'application en interagissant avec la notification (en appuyant ou en cliquant sur le bouton d'appel à l'action, par exemple).

   ![](assets/push_notif_advanced_4.png)

## Définir une action  {#define-an-action}

Le cas échéant, vous pouvez ajouter l'identifiant de catégorie de l'application mobile et afficher ensuite des boutons d'action. Ces notifications permettent à l'utilisateur d'effectuer plus rapidement différentes tâches en réponse à celles-ci, sans ouvrir l'application ou la parcourir.

La boîte de dialogue qui s'affiche sur le téléphone de l'utilisateur requiert une prise de décision. Quand l'utilisateur sélectionne l'une des actions, le système notifie l'application afin qu'elle puisse réaliser n'importe quelle tâche associée.

Pour ajouter une catégorie à une notification push :

1. Ouvrez la notification push et accédez à la section **[!UICONTROL Options avancées]**.
1. Entrez un nom de catégorie prédéfinie dans le champ **[!UICONTROL Catégorie]** pour afficher les boutons actifs lorsque la notification push est reçue.

   Le développeur de l'application mobile doit définir l'identifiant de catégorie et le comportement attendu des boutons dans l'application. Consultez à ce sujet la [Documentation développeur Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/SupportingNotificationsinYourApp.html) (section **Configuration des catégories et notifications actives**) ou la [Documentation développeur Android](https://developer.android.com/guide/topics/ui/notifiers/notifications.html).

   ![](assets/push_notif_advanced_9.png)

1. Une fois la notification push envoyée, les utilisateurs la reçoivent et doivent agir à l'aide des boutons actifs configurés auparavant.

   ![](assets/push_notif_actionable_buttons.png)

L'application est ensuite informé de l'action de l'utilisateur afin qu'elle puisse exécuter les tâches associées.

## Ajouter des champ personnalisés  {#add-custom-fields}

Les champs personnalisés vous permettent de transmettre des données personnalisées à la payload sous la forme d’une paire de valeurs de clés. Vous pouvez utiliser cette option pour transmettre des données supplémentaires à l’application en plus des clés prédéfinies.

Pour ce faire :

1. Ouvrez la notification push et accédez à la section **[!UICONTROL Options avancées]**.
1. Dans la catégorie **[!UICONTROL Champs personnalisés]**, cliquez sur le bouton **[!UICONTROL Ajouter un élément]**.
1. Saisissez vos **[!UICONTROL Clés]**, puis les **[!UICONTROL Valeurs]** associées à chacune des clés.

   ![](assets/push_notif_advanced_10.png)

1. La gestion et l’utilisation des champs personnalisés dépendent entièrement de l’application mobile. Dans la notification push ci-dessous, des champs personnalisés ont été utilisés par l’application pour afficher les libellés de boutons pour la notification push.

   ![](assets/push_notif_actionable_buttons.png)

## Ajouter du contenu multimédia {#add-rich-media-content}

Le contenu multimédia permet d'accroître l'engagement des utilisateurs ; ils seront donc plus enclins à ouvrir vos notifications push.

Vous pouvez ajouter un fichier image, gif, audio ou vidéo qui sera lu ou affiché dans la notification. Les utilisateurs de l'application n'ont pas besoin d'ouvrir celle-ci pour le visionner.

Pour insérer du contenu multimédia dans la notification push :

1. Ouvrez la notification push et accédez à la section **[!UICONTROL Options avancées]**.
1. Dans le champ **[!UICONTROL URL du contenu multimédia enrichi]**, saisissez l'URL de votre fichier pour chaque format : iOS et Android.

   A partir d'iOS 10, vous pouvez insérer des fichiers image, gif, audio et vidéo. Pour les versions antérieures d'iOS, la notification push sera affichée sans contenu multimédia. Pour obtenir des étapes détaillées afin d'afficher sur un appareil iOS une image d'une notification push Adobe Campaign, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/display-image-push.html).

   Pour Android, seules des images peuvent être ajoutées.

   ![](assets/push_notif_advanced_6.png)

1. Une fois le message envoyé, l'utilisateur recevra votre notification push et pourra afficher le contenu multimédia.

   ![](assets/push_notif_advanced_2.png)

## Changer le comportement des notifications pour iOS  {#change-the-notification-behavior-for-ios}

![](assets/push_notif_advanced_5.png)

Pour iOS 10 et version ultérieure, deux options supplémentaires sont disponibles dans la section **[!UICONTROL Options avancées]** des notifications push : **[!UICONTROL Contenu mutable]** et **[!UICONTROL Contenu disponible]**.

Lorsque l'option **[!UICONTROL Contenu mutable]** est cochée ou qu'une URL de contenu multimédia est ajoutée, le flag de contenu mutable est envoyé dans la payload push et permet au contenu de la notification push d'être modifié par une extension de l'application de service de notification fournie dans le SDK iOS. Consultez à ce sujet la [Documentation développeur Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/ModifyingNotifications.html).

Vous pouvez ensuite tirer parti des extensions de votre application mobile pour modifier davantage le contenu ou la présentation des notifications push envoyées depuis Adobe Campaign. Par exemple, les utilisateurs peuvent utiliser cette option pour :

* décrypter des données diffusées dans un format crypté ;
* télécharger des images ou d'autres fichiers multimédia et les ajouter sous forme de pièces jointes à une notification ;
* changer le texte du titre ou du corps d'une notification ;
* ajouter un identifiant de thread à une notification.

Lorsque l'option **[!UICONTROL Contenu disponible]** est cochée, le flag de contenu disponible est envoyé dans la payload push pour veiller à ce que l'application sorte de veille à la réception de la notification push et puisse accéder ainsi aux données de la payload. Ce mécanisme fonctionne même si l'application est en cours d'exécution à l'arrière-plan et qu'elle ne nécessite pas l'intervention de l'utilisateur (comme appuyer sur la notification push, par exemple). Toutefois, il ne s'applique pas si l'application n'est pas en cours d'exécution. Consultez à ce sujet la [Documentation développeur Apple](https://developer.apple.com/library/content/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/CreatingtheNotificationPayload.html).

## Changer le comportement des notifications pour Android {#change-the-notification-behavior-for-android}

Pour Android, vous pouvez saisir l'URL de votre fichier dans le champ **URL du contenu multimédia enrichi**. En revanche, pour la version iOS, vous ne pouvez inclure que des images et non des fichiers gif, audio ou vidéo.

La case à cocher **[!UICONTROL Priorité haute]** permet de configurer une priorité haute ou normale pour les notifications push. Pour plus d'informations sur la priorité des messages, consultez la [documentation destinée aux développeurs Google](https://firebase.google.com/docs/cloud-messaging/concept-options#setting-the-priority-of-a-message).

![](assets/push_notif_advanced_11.png)

