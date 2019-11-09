---
title: Personnalisation d'un message in-app
description: Découvrez comment personnaliser vos messages in-app à l'aide de diverses options.
page-status-flag: never-activated
uuid: 1d9c08ed-4de5-440d-bf51-4a437eec67d5
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: in-app-messaging
discoiquuid: c9c3e033-e319-447b-8d87-ff7dd4941876
context-tags: delivery,inAppContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Personnalisation d'un message in-app{#customizing-an-in-app-message}

Pour parfaire votre message in-app, Adobe Campaign vous permet d'accéder à un ensemble d'options avancées lors de sa création.

L'éditeur de contenu in-app vous permet de choisir entre deux modes de message in-app :

* [Modèle de message](#customizing-with-a-message-template) : ce modèle permet de personnaliser entièrement votre message in-app avec des images ou des vidéos et des boutons d'action.
* [Message personnalisé](#customizing-with-a-custom-html-message) : ce modèle permet d'importer du code HTML personnalisé.

![](assets/inapp_customize_1.png)

**Rubriques connexes :**

* [Envoi de votre message in-app](../../channels/using/preparing-and-sending-an-in-app-message.md#sending-your-in-app-message)
* [Reporting in-app](../../reporting/using/in-app-report.md)
* [Implémentation du tracking des notifications locales](https://helpx.adobe.com/campaign/kb/local-notification-tracking.html)

## Personnalisation à l'aide d'un modèle de message {#customizing-with-a-message-template}

### Disposition {#layout}

La liste déroulante **[!UICONTROL Disposition]** propose quatre options différentes en fonction de vos besoins en matière de messages :

* **[!UICONTROL Pleine page]** : ce type de disposition couvre tout l'écran des appareils de votre audience.

   Elle prend en charge des composants multimédia (image, vidéo), texte et bouton.

* **[!UICONTROL Grand modal]** : cette disposition apparaît dans une grande fenêtre de style alerte. Votre application est toujours visible en arrière-plan.

   Elle prend en charge des composants multimédia (image, vidéo), texte et bouton.

* **[!UICONTROL Petit modal]** : cette disposition apparaît dans une petite fenêtre de style alerte. Votre application est toujours visible en arrière-plan.

   Elle prend en charge des composants multimédia (image, vidéo), texte et bouton.

* **[!UICONTROL Alerte]** : ce type de disposition apparaît comme message d'alerte du système d'exploitation natif.

   Il ne peut prendre en charge que les composants texte et bouton.

* **[!UICONTROL Notification locale]** : ce type de disposition apparaît en tant que message de bannière.

   Il prend uniquement en charge le son, le texte et la destination. Pour plus d'informations sur la notification locale, consultez [Personnaliser un type de message de notification locale](#customizing-a-local-notification-message-type).

Chaque type de disposition peut être prévisualisé sur différents appareils tels que téléphone, tablette, plate-forme (Android ou iOS, par exemple) et orientation (paysage ou portrait) dans la fenêtre de droite de l'éditeur de contenu.

![](assets/inapp_customize_4.png)

### Média   {#media}

La liste déroulante **[!UICONTROL Médias]** permet d'ajouter des médias à votre message in-app afin de créer une expérience utilisateur unique.

1. Sélectionnez le **[!UICONTROL Type de média]** : image ou vidéo.
1. Pour le type de média **[!UICONTROL Image]**, saisissez l'URL dans le champ **[!UICONTROL URL médias]** en respectant les formats pris en charge.

   En cas de besoin, vous pouvez également saisir le chemin d'accès à une **[!UICONTROL Image groupée]** pouvant être utilisée si l'appareil est déconnecté.

   ![](assets/inapp_customize_5.png)

1. Pour le type de média **[!UICONTROL Vidéo]**, saisissez l'URL dans le champ **[!UICONTROL URL médias]**.

   Ensuite, saisissez le **[!UICONTROL Poster de vidéo]** à utiliser pendant le téléchargement de la vidéo sur les appareils de l'audience ou jusqu'à ce que les utilisateurs appuient sur le bouton de lecture.

   ![](assets/inapp_customize_6.png)

### Texte {#text}

En cas de besoin, vous pouvez également ajouter un titre et un contenu à votre message in-app. Pour mieux personnaliser votre message in-app, vous pouvez ajouter différents champs de personnalisation, des blocs de contenu et du texte dynamique à votre contenu.

1. Dans la liste déroulante **[!UICONTROL Texte]**, ajoutez un titre dans le champ **[!UICONTROL Titre du message]**.

   ![](assets/inapp_customize_9.png)

1. Ajoutez votre contenu dans le champ **[!UICONTROL Contenu du message]**.
1. Pour personnaliser davantage votre texte, cliquez sur l'icône ![](assets/edit_darkgrey-24px.png) pour ajouter des champs de personnalisation.

   ![](assets/inapp_customize_8.png)

1. Saisissez le contenu de votre message et ajoutez vos champs de personnalisation en cas de besoin.

   Pour plus d'informations sur les champs de personnalisation, consultez cette [section](../../designing/using/personalization.md#inserting-a-personalization-field).

   ![](assets/inapp_customize_10.png)

1. Vérifiez le contenu de votre message dans la fenêtre de prévisualisation.

   ![](assets/inapp_customize_11.png)

### Boutons   {#buttons}

Vous pouvez ajouter jusqu'à deux boutons à votre message In-App.

1. Dans la liste déroulante **[!UICONTROL Boutons]**, saisissez le texte du premier bouton dans la catégorie **[!UICONTROL Primaire]**.

   ![](assets/inapp_customize_12.png)

1. Parmi les actions **[!UICONTROL Ignorer]** et **[!UICONTROL Rediriger]**, choisissez celle qui sera affectée au bouton principal.
1. Dans la catégorie **[!UICONTROL Secondaire]**, ajoutez un second bouton à votre message in-app en saisissant votre texte.
1. Sélectionnez l'action associée au second bouton.
1. Si vous choisissez l'action **[!UICONTROL Rediriger]**, saisissez l'URL web ou le lien profond dans le champ **[!UICONTROL URL destination]**.

   ![](assets/inapp_customize_13.png)

1. Saisissez l'URL web ou le lien profond dans le champ **[!UICONTROL URL destination]**, si vous avez choisi l'action **[!UICONTROL Rediriger]**.
1. Vérifiez le contenu de votre message dans la fenêtre de prévisualisation ou en cliquant sur le bouton Aperçu.

   Consultez la page [Prévisualisation du message in-app](#previewing-the-in-app-message).

   ![](assets/inapp_customize_11.png)

### Paramètres   {#settings}

1. Dans la catégorie **[!UICONTROL Paramètres]**, sélectionnez votre couleur de fond entre une couleur claire et foncée.
1. A l'aide de l'option **[!UICONTROL Afficher le bouton Fermer]**, choisissez d'afficher ou non un bouton de fermeture afin que les utilisateurs puissent ignorer le message in-app.
1. A l'aide de l'option **[!UICONTROL Alignement des boutons]**, choisissez si l'alignement de votre bouton sera horizontal ou vertical.
1. Choisissez si votre message in-app peut être ignoré automatiquement après quelques secondes.

   ![](assets/inapp_customize_7.png)

## Personnaliser un type de message de notification locale   {#customizing-a-local-notification-message-type}

Les notifications locales peuvent uniquement être déclenchées par une application à une heure spécifique et en fonction d'un événement. Elles alerteront les utilisateurs sur le fait que quelque chose se passe dans leur application, même sans accès à Internet.
Pour découvrir comment tracker les notifications locales, reportez-vous à cette [page](https://helpx.adobe.com/campaign/kb/local-notification-tracking.html).

Pour personnaliser une notification locale :

1. Sur votre page **[!UICONTROL Contenu]**, sélectionnez **[!UICONTROL Notification locale]** dans la catégorie **[!UICONTROL Disposition]**.

   ![](assets/inapp_customize_17.png)

1. Sous la catégorie **[!UICONTROL Texte]**, saisissez le **[!UICONTROL Titre du message]** et **[!UICONTROL Contenu du message]**.

   ![](assets/inapp_customize_18.png)

1. Sous la catégorie **[!UICONTROL Option avancée]**, dans le champ **[!UICONTROL Attendre pour afficher]**, choisissez la durée (en secondes) pendant laquelle votre notification locale apparaîtra à l'écran une fois votre événement déclenché.
1. Dans le champ **[!UICONTROL Son]**, entrez le nom du fichier son, avec l'extension, que doit lancer l'appareil mobile à réception de la notification.

   Le fichier son est lu lors de la diffusion de la notification s'il est défini dans le package de l'application mobile. Sinon, le son par défaut de l'appareil est émis.

   ![](assets/inapp_customize_19.png)

1. Spécifiez une destination vers laquelle rediriger vos utilisateurs lorsqu'ils interagissent avec votre notification locale dans le champ **[!UICONTROL URL de lien profond]**.
1. Pour transmettre des données personnalisées dans la payload sous la forme d'une paire de valeurs de clés, vous pouvez ajouter des champs personnalisés à votre notification locale. Dans la catégorie **[!UICONTROL Champs personnalisés]**, cliquez sur le bouton **[!UICONTROL Créer un élément]**.
1. Saisissez vos **[!UICONTROL Clés]**, puis les **[!UICONTROL Valeurs]** associées à chacune des clés.

   Notez que la finalité des champs personnalisés et leur gestion dépend entièrement de l'application mobile.

1. Dans la catégorie **[!UICONTROL Options Apple]**, remplissez les champs **[!UICONTROL Catégorie]** afin d'ajouter un ID de catégorie pour les actions personnalisées si elles sont disponibles dans votre application mobile Apple.

## Personnalisation à l'aide d'un message HTML personnalisé {#customizing-with-a-custom-html-message}

>[!NOTE]
>
>Un message HTML personnalisé ne prend pas en charge la personnalisation du contenu.

Le mode **[!UICONTROL Message personnalisé]** permet d'importer directement l'un de vos messages HTML préconfigurés.

Pour cela, il vous suffit d'effectuer un glisser-déposer ou de sélectionner votre fichier depuis l'ordinateur.

Le fichier doit avoir une disposition spécifique que vous pouvez découvrir en cliquant sur l'option **Télécharger le fichier d'exemple**.

![](assets/inapp_customize_16.png)

Vous pouvez également trouver une liste des exigences liées au code HTML personnalisé pour réussir l'import dans Adobe Campaign.

![](assets/inapp_customize_3.png)

Une fois le code HTML importé, vous pouvez trouver un aperçu de votre fichier sur différents appareils dans la fenêtre de prévisualisation.

## Prévisualisation du message in-app {#previewing-the-in-app-message}

Avant d'envoyer votre message in-app, vous pouvez le tester avec vos profils de test pour vérifier ce que l'audience cible verra lorsqu'elle recevra la diffusion.

1. Cliquez sur le bouton **[!UICONTROL Aperçu]**.

   ![](assets/inapp_sending_2.png)

1. Cliquez sur le bouton **[!UICONTROL Sélectionner un profil de test]** et sélectionnez un de vos profils de test pour commencer à prévisualiser votre diffusion. Pour plus d'informations sur les profils de test, consultez cette [section](../../sending/using/managing-test-profiles-and-sending-proofs.md).
1. Vérifiez votre message sur différents appareils tels que des appareils Android, des téléphones iPhone et même des tablettes. Vous pouvez également contrôler si les champs de personnalisation récupèrent les données adéquates.

   ![](assets/inapp_sending_3.png)

1. Vous pouvez maintenant envoyer votre message et mesurer son impact à l'aide des rapports de diffusion. Pour plus d'informations sur le reporting, consultez [cette section](../../reporting/using/in-app-report.md).

