---
title: Configuration des messages transactionnels
description: Découvrez comment configurer les messages transactionnels.
page-status-flag: never-activated
uuid: 4caeadbe-f4a7-43ce-986d-e99fa9ca0d0d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 3f968556-e774-43dc-a0b8-7188d7665fbc
internal: n
snippet: y
translation-type: ht
source-git-commit: 867215b295a7539d8499fa0bb1865605695da020

---


# Configuration des messages transactionnels{#configuring-transactional-messaging}

Pour envoyer un message transactionnel avec Adobe Campaign, vous devez d&#39;abord décrire la structure des données de l&#39;événement.

La configuration d&#39;un événement doit être effectuée par un **administrateur** en suivant les étapes ci-dessous :

La configuration peut varier selon le type de message transactionnel que vous souhaitez envoyer. Pour en savoir plus, consultez [Configurations spécifiques des événements transactionnels](#transactional-event-specific-configurations).

Une fois l&#39;événement publié, le message transactionnel correspondant est automatiquement créé. Pour plus d&#39;informations sur les messages transactionnels, consultez [cette page](../../channels/using/about-transactional-messaging.md).

## Créer un événement  {#creating-an-event}

Commencez par configurer l&#39;événement qui correspond à vos besoins.

1. Cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez**[!UICONTROL  Plans marketing]** > **[!UICONTROL Messages transactionnels]** >**[!UICONTROL  Configuration des événements]**.
1. Cliquez sur le bouton **[!UICONTROL Créer]**.
1. Donnez un **[!UICONTROL Libellé]**et un**[!UICONTROL  Identifiant]** à votre événement. Le champ **[!UICONTROL Identifiant]**est obligatoire et doit commencer par le préfixe &quot;EVT&quot;. Si vous n&#39;utilisez pas ce préfixe, il est automatiquement ajouté lorsque vous cliquez sur**[!UICONTROL  Créer]**.

   ![](assets/message-center_1.png)

   >[!CAUTION]
   >
   >L&#39;identifiant ne doit pas dépasser 64 caractères, le préfixe EVT compris.

1. Sélectionnez le canal qui sera utilisé pour l&#39;envoi des messages transactionnels : **[!UICONTROL Email]**,**[!UICONTROL  Mobile (SMS)]** ou **[!UICONTROL Application mobile]**(notification push).

   >[!NOTE]
   >
   >Un seul canal peut être utilisé pour chaque configuration d&#39;événement. Une fois l&#39;événement créé, vous ne pouvez plus modifier le canal.

1. Sélectionnez la dimension de ciblage qui correspond à la configuration de l&#39;événement souhaitée et cliquez sur **[!UICONTROL Créer]**.

   Les messages transactionnels basés sur un événement ciblent des données contenues dans l&#39;événement lui-même, alors que les messages transactionnels basés sur un profil ciblent des données contenues dans la base de données Adobe Campaign. Pour en savoir plus, consultez [Configurations spécifiques des événements transactionnels](#transactional-event-specific-configurations).

## Définir les attributs d&#39;événement  {#defining-the-event-attributes}

Dans la section **[!UICONTROL Champs]**, définissez les attributs qui seront intégrés au contenu de l&#39;événement et qui pourront être utilisés pour personnaliser le message transactionnel.

Les étapes d&#39;ajout et de modification des champs s&#39;effectuent de la même manière que pour les [ressources personnalisées](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Si vous souhaitez créer un message transactionnel multilingue, définissez un attribut d&#39;événement supplémentaire avec l&#39;identifiant **[!UICONTROL AC_language]**. Cela s&#39;applique uniquement aux messages transactionnels basés sur un événement. Une fois l&#39;événement publié, les étapes nécessaires pour éditer le contenu d&#39;un message transactionnel multilingue sont les mêmes que pour un email standard multilingue. Voir[Créer un email multilingue](../../channels/using/creating-a-multilingual-email.md).

## Définir des collections de données  {#defining-data-collections}

Vous pouvez ajouter une collection d&#39;éléments au contenu de l&#39;événement, chaque élément comprenant lui-même plusieurs attributs.

Cette collection peut être utilisée dans un email transactionnel pour ajouter des listes de produits au contenu du message, par exemple une liste de produits, avec le prix, le numéro de référence, la quantité, etc., pour chaque produit de la liste.

1. Dans la section **[!UICONTROL Collections]**, cliquez sur le bouton**[!UICONTROL  Créer un élément]**.

   ![](assets/message-center_collection_create.png)

1. Ajoutez un libellé et un identifiant pour la collection.
1. Ajoutez tous les champs que vous souhaitez afficher dans le message transactionnel pour chaque produit de la liste.

   Dans cet exemple, nous avons ajouté les champs suivants :

   ![](assets/message-center_collection_fields.png)

Une fois l&#39;événement et le message publiés, vous pouvez utiliser cette collection dans votre message transactionnel.

Voici l&#39;aperçu de l&#39;API pour cet exemple :

![](assets/message-center_collection_api-preview.png)

**Rubriques connexes :**

* [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)
* [Utiliser des listes de produits dans un message transactionnel ](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)

## Enrichir le contenu d&#39;un message transactionnel {#enriching-the-transactional-message-content}

Enrichir le contenu d&#39;un message transactionnel avec des informations de la base de données Adobe Campaign vous permet de personnaliser vos messages. À partir du nom ou de l&#39;identifiant CRM de vos destinataires, vous pouvez par exemple récupérer des données telles que leur adresse, date de naissance ou tout autre champ personnalisé ajouté à la table Profil afin de personnaliser les informations qui leur seront envoyées.

Il est possible d&#39;enrichir le contenu du message transactionnel avec des informations des ressources étendues **[!UICONTROL Profil]**ou**[!UICONTROL  Service]**.

Ces informations peuvent également être stockées dans de nouvelles ressources. Le cas échéant, la ressource doit être liée aux ressources **[!UICONTROL Profil]**ou**[!UICONTROL  Service]** soit directement, soit via une autre table. Par exemple, dans la configuration ci-dessous, il est possible d&#39;enrichir le contenu d&#39;un message transactionnel avec des informations de la ressource **[!UICONTROL Produit]**, telles que la catégorie de produit ou l&#39;identifiant, si la ressource**[!UICONTROL  Produit]** est liée à la ressource **[!UICONTROL Profil]**.

![](assets/message-center_usecaseschema.png)

Pour en savoir plus sur la création et la publication de ressources, consultez [cette page](../../developing/using/key-steps-to-add-a-resource.md).

1. Dans la section **[!UICONTROL Enrichissement]**, cliquez sur le bouton**[!UICONTROL  Créer un élément]**.

   ![](assets/message-center_addenrichment.png)

1. Sélectionnez la ressource à laquelle vous voulez lier votre message. Dans le cas présent, choisissez la ressource **[!UICONTROL Profil]**.

   ![](assets/message-center_new-enrichment.png)

1. Utilisez le bouton **[!UICONTROL Créer un élément]**pour associer un champ de la ressource sélectionnée à l&#39;un des champs que vous avez ajoutés à l&#39;événement (voir[Définir les attributs d&#39;événement](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. Dans cet exemple, nous réconcilions les champs **[!UICONTROL Nom]**et**[!UICONTROL  Prénom]** avec les champs correspondants dans la ressource **[!UICONTROL Profil]**.

   ![](assets/message-center_enrichment-join-fields.png)

   Vous pouvez également enrichir le contenu des messages transactionnels à l&#39;aide de la ressource **[!UICONTROL Service]**. Pour plus d&#39;informations à ce sujet, voir .

1. Dans la section **[!UICONTROL Enrichissement de la cible]**, sélectionnez l&#39;enrichissement qui sera utilisé en tant que cible des messages pendant l&#39;exécution de la diffusion. Dans cet exemple, sélectionnez**[!UICONTROL  Profil]**. Un enrichissement de la cible doit obligatoirement être sélectionné pour les événements basés sur un profil.

   ![](assets/message-center_marketing_targeting_enrichment.png)

Une fois l&#39;événement et le message publiés, le lien avec la ressource **[!UICONTROL Profil]**permettra d&#39;enrichir le contenu du message transactionnel.

**Rubriques connexes :**

* [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event).
* [Personnaliser un message transactionnel](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Prévisualiser et publier l&#39;événement {#previewing-and-publishing-the-event}

Avant de pouvoir utiliser l&#39;événement, vous devez le prévisualiser et le publier.

1. Cliquez sur le bouton **[!UICONTROL Aperçu de l&#39;API]**pour visualiser une simulation de l&#39;API REST, qui sera utilisée par le développeur de votre site web, avant qu&#39;elle ne soit publiée. Une fois l&#39;événement publié, ce bouton permet également d&#39;obtenir un aperçu de l&#39;API en production. Voir[Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >L&#39;API REST varie en fonction du canal sélectionné et de la dimension de ciblage sélectionnée. Pour en savoir plus sur les différentes configurations, consultez [Configurations spécifiques des événements transactionnels](#transactional-event-specific-configurations).

1. Cliquez sur le bouton **[!UICONTROL Publier]**pour lancer la publication.

   ![](assets/message-center_pub.png)

1. Vous pouvez visualiser les logs de publication en sélectionnant l&#39;onglet correspondant.

   ![](assets/message-center_logs.png)

   Vous pouvez également consulter les publications précédentes en sélectionnant l&#39;onglet correspondant.

>[!NOTE]
>
>Chaque fois que vous modifiez l&#39;événement, vous devez à nouveau cliquer sur **[!UICONTROL Publier]**pour générer l&#39;API REST mise à jour qui sera utilisée par le développeur de votre site web.

Une fois la publication effectuée, un message transactionnel associé au nouvel événement est automatiquement créé. Pour que cet événement déclenche l&#39;envoi d&#39;un message transactionnel, vous devez modifier et publier le message qui vient d&#39;être créé. Voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md).

Vous pouvez accéder au message transactionnel qui a été créé directement à partir du lien situé sur la gauche.

![](assets/message-center_messagegeneration.png)

Il vous faut également intégrer le déclenchement de cet événement à votre site web. Voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website).

### Dépublier un événement  {#unpublishing-an-event}

Le bouton **[!UICONTROL Dépublier]**permet d&#39;annuler la publication de l&#39;événement, ce qui supprime de l&#39;API REST la ressource correspondant à l&#39;événement précédemment créé. Désormais, même si l&#39;événement est déclenché via votre site web, les messages correspondants ne sont plus envoyés et ils ne sont pas stockés dans la base de données.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si vous avez déjà publié le message transactionnel correspondant, la publication du message est également annulée. Voir [Dépublier un message transactionnel](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Cliquez sur le bouton **[!UICONTROL Publier]**pour générer une nouvelle API REST.

## Intégrer le déclenchement de l&#39;événement à un site web {#integrating-the-triggering-of-the-event-in-a-website}

Une fois que vous avez créé l&#39;événement de votre choix, il vous faut intégrer le déclenchement de cet événement à votre site web.

Dans l&#39;exemple présenté dans la section [Principe de fonctionnement des messages transactionnels](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle), vous souhaitez qu&#39;un événement de type &quot;Abandon de panier&quot; soit déclenché lorsque l&#39;un de vos clients quitte votre site web avant d&#39;avoir acheté les produits de son panier. Pour ce faire, le développeur web de votre site doit se servir de l&#39;API REST Adobe Campaign Standard.

Consultez la [documentation API REST](../../api/using/managing-transactional-messages.md) .

## Configurations spécifiques des événements transactionnels {#transactional-event-specific-configurations}

La configuration d&#39;un événement transactionnel peut varier en fonction du type de message transactionnel que vous souhaitez envoyer (événement ou profil) et du canal qui sera utilisé.

Les sections suivantes détaillent quelle configuration spécifique devrait être définie en fonction du message transactionnel souhaité. Pour en savoir plus sur les étapes générales à suivre pour configurer un événement, voir  [Créer un événement](#creating-an-event).

### Messages transactionnels basés sur un événement.{#event-based-transactional-messages}

Pour envoyer un message transactionnel basé sur un événement, vous devez d&#39;abord créer et configurer un événement ciblant les données contenues dans l&#39;événement.
Pour plus d&#39;informations, voir [Créer de l&#39;engagement avec des messages transactionnels](https://helpx.adobe.com/fr/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. Lors de la création de la configuration d&#39;un événement, sélectionnez la dimension de ciblage **[!UICONTROL Evénement en temps réel]**(voir[Créer un événement](#creating-an-event)).
1. Ajoutez des champs à l&#39;événement afin de personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).
1. Enrichissez le contenu du message transactionnel si vous souhaitez utiliser des informations supplémentaires de la base de données Adobe Campaign (voir [Enrichir le contenu d&#39;un message transactionnel](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l&#39;événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d&#39;enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign.

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Lors de l&#39;aperçu de l&#39;événement, l&#39;API REST contient un attribut précisant l&#39;adresse email ou le numéro de téléphone portable en fonction du canal sélectionné.

   Une fois la publication effectuée, un message transactionnel associé au nouvel événement est automatiquement créé. Pour que cet événement déclenche l&#39;envoi d&#39;un message transactionnel, vous devez modifier et publier le message qui vient d&#39;être créé, voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md)

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Messages transactionnels basés sur un profil  {#profile-based-transactional-messages}

Pour envoyer un message transactionnel basé sur un profil, vous devez d&#39;abord créer et configurer un événement ciblant les données contenues dans la base de données Adobe Campaign.

1. Lors de la création de la configuration d&#39;un événement, sélectionnez la dimension de ciblage **[!UICONTROL Evénement de profil]**(voir[Créer un événement](#creating-an-event)).
1. Ajoutez des champs à l&#39;événement afin de personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)). Vous devez ajouter au moins un champ pour créer un enrichissement. Vous n&#39;avez pas à créer des champs tels que **Prénom** et **Nom**, car vous pourrez utiliser les champs de personnalisation de la base de données Adobe Campaign.
1. Créez un enrichissement afin de lier l&#39;événement à la ressource **[!UICONTROL Profil]**(voir[Enrichir le contenu d&#39;un message transactionnel](#enriching-the-transactional-message-content)). Lors de l&#39;utilisation d&#39;une dimension de ciblage**[!UICONTROL  Profil]**, la création d&#39;un enrichissement est obligatoire.
1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Lors de l&#39;aperçu de l&#39;événement, l&#39;API REST ne contient pas d&#39;attribut précisant l&#39;adresse email ou le numéro de téléphone portable, car ceux-ci seront récupérés dans la ressource **[!UICONTROL Profil]**.

   Une fois la publication effectuée, un message transactionnel associé au nouvel événement est automatiquement créé. Pour que cet événement déclenche l&#39;envoi d&#39;un message transactionnel, vous devez modifier et publier le message qui vient d&#39;être créé, voir [Envoyer un message transactionnel basé sur un profil](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Notifications push transactionnelles basées sur un événement  {#event-based-transactional-push-notifications}

Pour pouvoir envoyer des notifications push transactionnelles, vous devez configurer Adobe Campaign en conséquence. Voir [Configuration push](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html).

Pour envoyer une notification push transactionnelle anonyme à tous les utilisateurs qui ont accepté de recevoir des notifications de votre application mobile, vous devez d&#39;abord créer et configurer un événement ciblant les données contenues dans l&#39;événement. Les étapes correspondantes sont présentées ci-après.

L&#39;événement doit contenir les trois éléments suivants :

* Un **jeton d&#39;enregistrement** qui est l&#39;identifiant de l&#39;utilisateur pour une application mobile et un appareil. Il peut ne pas correspondre à un profil de la base de données Adobe Campaign.
* Un **nom d&#39;application mobile** (un pour tous les appareils : Android et iOS). Il s&#39;agit de l&#39;identifiant de l&#39;application mobile configuré dans Adobe Campaign qui sera utilisé pour la réception des notifications push sur les appareils des utilisateurs. Voir à ce propos [cette page](https://helpx.adobe.com/fr/campaign/kb/configuring-app-sdkv4.html)
* Une **plate-forme push** (&quot;gcm&quot; pour Android et &quot;apns&quot; pour iOS).

1. Lors de la création de la configuration d&#39;un événement, sélectionnez le canal **[!UICONTROL Application mobile]**et la dimension de ciblage**[!UICONTROL  Evénement en temps réel]** (voir [Créer un événement](#creating-an-event)).
1. Ajoutez des champs à l&#39;événement afin de personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).
1. Enrichissez le contenu du message transactionnel si vous souhaitez utiliser des informations supplémentaires de la base de données Adobe Campaign (voir [Enrichir le contenu d&#39;un message transactionnel](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l&#39;événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d&#39;enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign.

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Lors de l&#39;aperçu de l&#39;événement, l&#39;API REST contient les attributs &quot;registrationToken&quot;, &quot;application&quot; et &quot;pushPlatform&quot; qui seront utilisés pour cibler la diffusion.

   ![](assets/message-center_push_api.png)

   Une fois la publication effectuée, une notification push transactionnelle associée au nouvel événement est automatiquement créée. Pour modifier et publier le message nouvellement créé, voir [Envoyer une notification push transactionnelle ciblant un événement](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-an-event).

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Notifications push transactionnelles basées sur un profil  {#profile-based-transactional-push-notifications}

Pour envoyer une notification push transactionnelle aux profils Adobe Campaign qui se sont inscrits à votre application mobile, vous devez d&#39;abord créer et configurer un événement ciblant la base de données Adobe Campaign.

1. Lors de la création de la configuration d&#39;un événement, sélectionnez le canal **[!UICONTROL Application mobile]**et la dimension de ciblage**[!UICONTROL  Profil]** (voir [Créer un événement](#creating-an-event)).

   La notification push transactionnelle sera envoyée, par défaut, à toutes les applications mobiles auxquelles les destinataires sont inscrits. Pour envoyer la notification push à une application mobile spécifique, sélectionnez-la dans la liste. Les autres applications mobiles seront ciblées par le message, mais seront exclues de l&#39;envoi.

   ![](assets/message-center_push_appfilter.png)

1. Ajoutez des champs à l&#39;événement si vous voulez personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Vous devez ajouter au moins un champ pour créer un enrichissement. Vous n&#39;avez pas à créer des champs tels que **Prénom** et **Nom**, car vous pourrez utiliser les champs de personnalisation de la base de données Adobe Campaign.

1. Créez un enrichissement afin de lier l&#39;événement à la ressource **[!UICONTROL Profil]**(voir[Enrichir le contenu d&#39;un message transactionnel](#enriching-the-transactional-message-content)). Lors de l&#39;utilisation d&#39;une dimension de ciblage**[!UICONTROL  Profil]**, la création d&#39;un enrichissement est obligatoire.
1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Lors de l&#39;aperçu de l&#39;événement, l&#39;API REST ne contient pas d&#39;attribut spécifiant le jeton d&#39;enregistrement, le nom de l&#39;application et la plate-forme push, car ceux-ci seront récupérés dans la ressource **[!UICONTROL Profil]**.

   Une fois la publication effectuée, une notification push transactionnelle associée au nouvel événement est automatiquement créée. Pour modifier et publier le message nouvellement créé, voir [Envoyer une notification push transactionnelle ciblant un profil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Configuration d&#39;un événement pour envoyer un message de relance  {#configuring-an-event-to-send-a-follow-up-message}

Un messages de relance est un modèle de diffusion marketing prédéfini qui peut être utilisé dans un workflow pour envoyer des messages aux destinataires d&#39;un message transactionnel spécifique. Voir à ce propos la section [Messages de relance](../../channels/using/follow-up-messages.md).

1. Utilisez la même configuration d&#39;événement que celle que vous avez créée pour envoyer un message transactionnel basé sur un événement. Voir [Messages transactionnels basés sur un événement](#event-based-transactional-messages).
1. Lors de la configuration de l&#39;événement, cochez la case **[!UICONTROL Créer un modèle de diffusion de relance pour cet événement]**avant de le publier.

   ![](assets/message-center_follow-up-checkbox.png)

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Une fois la publication effectuée, un message transactionnel et un modèle de diffusion de relance associés au nouvel événement sont automatiquement créés. Pour plus d&#39;informations sur l&#39;utilisation des messages de relance, voir [Envoyer un message de relance](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Cas pratique : configuration d&#39;un événement pour envoyer un message transactionnel  {#use-case--configuring-an-event-to-send-a-transactional-message}

Dans cette exemple, nous voulons configurer un événement afin d&#39;envoyer des messages de confirmation après chaque achat sur notre site avec les prérequis suivants :

Puisque nous voulons identifier notre client grâce à son identifiant CRM, assurez-vous d&#39;abord que la ressource **[!UICONTROL Profil]**a été étendue à ce nouveau champ.

De la même manière, une ressource personnalisée correspondant aux achats doit être créée et publiée, et doit être liée à la ressource **[!UICONTROL Profil]**. De cette façon, vous pourrez récupérer les informations de cette ressource pour enrichir le contenu du message.

Pour en savoir plus sur la création et la publication de ressources, consultez [cette page](../../developing/using/key-steps-to-add-a-resource.md).

1. Créez un événement en utilisant le canal **[!UICONTROL Email]**et la dimension de ciblage**[!UICONTROL  Profil]** (voir [Créer un événement](#creating-an-event)).
1. Définissez les attributs qui seront disponibles pour personnaliser le message transactionnel. Dans notre cas, ajoutez les champs &quot;Identifiant CRM&quot; et &quot;Identificateur produit&quot; (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. Pour enrichir le contenu du message avec des informations à propos des précédents achats du client, créez un enrichissement ciblant la ressource **[!UICONTROL Achat]**(voir[Enrichir le contenu d&#39;un message transactionnel](#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Créez une condition de jointure entre le champ &quot;Identificateur produit&quot; ajouté précédemment au message et le champ correspondant dans la ressource **[!UICONTROL Achat]**.

   ![](assets/message-center_usecase3.png)

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).
1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

