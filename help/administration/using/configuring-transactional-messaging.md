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
translation-type: tm+mt
source-git-commit: 34f4bbf7b7913cfb1833379c963b590961f7de73

---


# Configuration des messages transactionnels{#configuring-transactional-messaging}

Pour envoyer un message transactionnel avec Adobe Campaign, vous devez d&#39;abord décrire la structure des données de l&#39;événement.

La configuration d&#39;un événement doit être effectuée par un **administrateur** en suivant les étapes ci-dessous :

La configuration peut varier selon le type de message transactionnel que vous souhaitez envoyer. Pour en savoir plus, consultez [Configurations spécifiques des événements transactionnels](#transactional-event-specific-configurations).

Une fois l&#39;événement publié, le message transactionnel correspondant est automatiquement créé. Pour plus d&#39;informations sur les messages transactionnels, consultez [cette page](../../channels/using/about-transactional-messaging.md).

## Créer un événement   {#creating-an-event}

Commencez par configurer l&#39;événement qui correspond à vos besoins.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Cliquez sur le **[!UICONTROL Create]** bouton.
1. Give a **[!UICONTROL Label]** and an **[!UICONTROL ID]** to the event. The **[!UICONTROL ID]** field is mandatory and should begin with the prefix &quot;EVT&quot;. If you do not use this prefix, it is automatically added once you click **[!UICONTROL Create]**.

   ![](assets/message-center_1.png)

   >[!IMPORTANT]
   >
   >L’identifiant ne doit pas dépasser 64 caractères, le préfixe EVT compris.

1. Select the channel that will be used to send your transactional messages **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** or **[!UICONTROL Mobile application]** (push notification).

   >[!NOTE]
   >
   >Un seul canal peut être utilisé pour chaque configuration d&#39;événement. Une fois l&#39;événement créé, vous ne pouvez plus modifier le canal.

1. Select the targeting dimension corresponding to the desired event configuration and click **[!UICONTROL Create]**.

   Les messages transactionnels basés sur un événement ciblent des données contenues dans l&#39;événement lui-même, alors que les messages transactionnels basés sur un profil ciblent des données contenues dans la base de données Adobe Campaign. Pour en savoir plus, consultez [Configurations spécifiques des événements transactionnels](#transactional-event-specific-configurations).

## Définir les attributs d&#39;événement   {#defining-the-event-attributes}

In the **[!UICONTROL Fields]** section, define the attributes that will be integrated into the event content and will then be able to be used to personalize the transactional message.

Les étapes d&#39;ajout et de modification des champs s&#39;effectuent de la même manière que pour les [ressources personnalisées](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource).

![](assets/message-center_2.png)

>[!NOTE]
>
>Si vous souhaitez créer un message transactionnel multilingue, définissez un attribut d&#39;événement supplémentaire avec l&#39;identifiant **[!UICONTROL AC_language]**. Cela s&#39;applique uniquement aux messages transactionnels basés sur un événement. Une fois l&#39;événement publié, les étapes nécessaires pour éditer le contenu d&#39;un message transactionnel multilingue sont les mêmes que pour un email standard multilingue. Voir [Créer un email multilingue](../../channels/using/creating-a-multilingual-email.md).

## Définir des collections de données   {#defining-data-collections}

Vous pouvez ajouter une collection d&#39;éléments au contenu de l&#39;événement, chaque élément comprenant lui-même plusieurs attributs.

Cette collection peut être utilisée dans un email transactionnel pour ajouter des listes de produits au contenu du message, par exemple une liste de produits, avec le prix, le numéro de référence, la quantité, etc., pour chaque produit de la liste.

1. Dans la **[!UICONTROL Collections]** section, cliquez sur le **[!UICONTROL Create element]** bouton.

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

It is possible to enrich the transactional message content with information from extended **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources.

Ces informations peuvent également être stockées dans de nouvelles ressources. In that case, the resource must be linked to the **[!UICONTROL Profile]** or **[!UICONTROL Service]** resources either directly, or via another table. For example, in the configuration below, it is possible to enrich the transactional message content with information from the **[!UICONTROL Product]** resource like the product category or ID, if the **[!UICONTROL Product]** resource is linked to the **[!UICONTROL Profile]** resource.

![](assets/message-center_usecaseschema.png)

Pour en savoir plus sur la création et la publication de ressources, consultez [cette page](../../developing/using/key-steps-to-add-a-resource.md).

1. Dans la **[!UICONTROL Enrichment]** section, cliquez sur le **[!UICONTROL Create element]** bouton.

   ![](assets/message-center_addenrichment.png)

1. Sélectionnez la ressource à laquelle vous voulez lier votre message. In this case, choose the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_new-enrichment.png)

1. Use the **[!UICONTROL Create element]** button to link a field from the selected resource to one of the fields you previously added to the event (see [Defining the event attributes](#defining-the-event-attributes)).

   ![](assets/message-center_enrichment-join.png)

1. In this example, we reconcile the **[!UICONTROL Last name]** and the **[!UICONTROL First name]** fields with the corresponding fields in the **[!UICONTROL Profile]** resource.

   ![](assets/message-center_enrichment-join-fields.png)

   Vous pouvez également enrichir le contenu des messages transactionnels à l&#39;aide de la ressource **[!UICONTROL Service]**. For more on services, see this [section](../../audiences/using/creating-a-service.md).

1. Si vous créez ou modifiez un  de basé sur , dans la **[!UICONTROL Targeting enrichment]** section, sélectionnez le, le decontenu qui sera utilisé comme de message lors de l’exécution de la programmation.

   ![](assets/message-center_marketing_targeting_enrichment.png)

   >[!NOTE]
   >
   >La sélection d’un  de ciblage   en fonction de la **[!UICONTROL Profile]** ressource est obligatoire pour lesbasés sur les .

Une fois le  et le message publiés, ce lien vous permettra d&#39;enrichir le contenu de la  de.

**Rubriques connexes :**

* [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event).
* [Personnaliser un message transactionnel](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

## Prévisualiser et publier l&#39;événement {#previewing-and-publishing-the-event}

Avant de pouvoir utiliser l&#39;événement, vous devez le prévisualiser et le publier.

1. Click the **[!UICONTROL API preview]** button to see a simulation of the REST API that will be used by your website developer before it is published. Une fois l&#39;événement publié, ce bouton permet également d&#39;obtenir un aperçu de l&#39;API en production. Voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website).

   ![](assets/message-center_api_preview.png)

   >[!NOTE]
   >
   >L&#39;API REST varie en fonction du canal sélectionné et de la dimension de ciblage sélectionnée. Pour en savoir plus sur les différentes configurations, consultez [Configurations spécifiques des événements transactionnels](#transactional-event-specific-configurations).

1. Click **[!UICONTROL Publish]** to start publication.

   ![](assets/message-center_pub.png)

1. Vous pouvez  les journaux de publication dans l’onglet correspondant.

   ![](assets/message-center_logs.png)

   >[!IMPORTANT]
   >
   >Each time you modify the event, you must click **[!UICONTROL Publish]** again to generate the updated REST API that will be used by your website developer.

   Une fois la publication effectuée, un message transactionnel associé au nouvel événement est automatiquement créé.

1. Vous pouvez accéder directement à ce par le lien situé dans la zone de gauche.

   ![](assets/message-center_messagegeneration.png)

In order for the event to trigger sending a transactional message, you must modify and publish the message that was just created. See [Event transactional messages](../../channels/using/event-transactional-messages.md).

Il vous faut également intégrer le déclenchement de cet événement à votre site web. Voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website).

Une fois  Adobe Campaign de réception de **[!UICONTROL Latest transactional events]** l&#39;lié à cette configuration de l&#39; **[!UICONTROL History]** annuaire, le lien sous la section vous permet d&#39;accéder au dernier envoyé par votre service tiers et traité par le.

![](assets/message-center_latest-events.png)

Les  de (au format JSON) sont répertoriés du plus récent au plus ancien. Ce  vous permet de vérifier des données telles que le contenu ou l’état d’un  de, à des fins de contrôle et de débogage.

### Dépublier un événement   {#unpublishing-an-event}

The **[!UICONTROL Unpublish]** button lets you cancel the publication of the event, which deletes from the REST API the resource corresponding to the event that you previously created. Désormais, même si l&#39;événement est déclenché via votre site web, les messages correspondants ne sont plus envoyés et ils ne sont pas stockés dans la base de données.

![](assets/message-center_unpublish.png)

>[!NOTE]
>
>Si vous avez déjà publié le message transactionnel correspondant, la publication du message est également annulée. Voir [Dépublier un message transactionnel](../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message).

Click the **[!UICONTROL Publish]** button to generate a new REST API.

### Suppression d’un  de {#deleting-an-event}

Une fois qu’un  a été annulé ou qu’un  de n’a pas encore été publié, vous pouvez le supprimer de l’de configuration de l’. Pour cela :

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]**.
1. Passez la souris sur la configuration  du de votre choix et sélectionnez le **[!UICONTROL Delete element]** bouton.

   ![](assets/message-center_delete-button.png)

   >[!NOTE]
   >
   >Assurez-vous que la configuration  a l’ **[!UICONTROL Draft]** état, sinon vous ne pourrez pas la supprimer. L’ **[!UICONTROL Draft]** état s’applique à un qui n’a pas encore été publié ou qui a été [annulé](#unpublishing-an-event).

1. Cliquez sur le **[!UICONTROL Confirm]** bouton.

   ![](assets/message-center_delete-confirm.png)

>[!IMPORTANT]
>
>La suppression d’une configuration de  de qui a été publiée et déjà utilisée supprimera également le ou les (s)(s) correspondant(s), ainsi que ses (s) d’envoi et ses(s) d’envoi.

## Intégrer le déclenchement de l&#39;événement à un site web {#integrating-the-triggering-of-the-event-in-a-website}

Une fois que vous avez créé l’événement de votre choix, il vous faut intégrer le déclenchement de cet événement à votre site web.

Dans l&#39;exemple présenté dans la section [Principe de fonctionnement des messages transactionnels](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle), vous souhaitez qu&#39;un événement de type &quot;Abandon de panier&quot; soit déclenché lorsque l&#39;un de vos clients quitte votre site web avant d&#39;avoir acheté les produits de son panier. Pour ce faire, le développeur web de votre site doit se servir de l&#39;API REST Adobe Campaign Standard.

Consultez la [documentation API REST](../../api/using/managing-transactional-messages.md) .

## Configurations spécifiques des événements transactionnels {#transactional-event-specific-configurations}

La configuration d&#39;un événement transactionnel peut varier en fonction du type de message transactionnel que vous souhaitez envoyer (événement ou profil) et du canal qui sera utilisé.

Les sections suivantes détaillent quelle configuration spécifique devrait être définie en fonction du message transactionnel souhaité. Pour en savoir plus sur les étapes générales à suivre pour configurer un événement, voir   [Créer un événement](#creating-an-event).

### Messages transactionnels basés sur un événement.{#event-based-transactional-messages}

Pour envoyer un message transactionnel basé sur un événement, vous devez d&#39;abord créer et configurer un événement ciblant les données contenues dans l&#39;événement.
Pour plus d&#39;informations, voir [Créer de l&#39;engagement avec des messages transactionnels](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences).

1. When creating the event configuration, select the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](#creating-an-event)).
1. Ajoutez des champs à l&#39;événement afin de personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).
1. Enrichissez le contenu du message transactionnel si vous souhaitez utiliser des informations supplémentaires de la base de données Adobe Campaign (voir [Enrichir le contenu d&#39;un message transactionnel](#enriching-the-transactional-message-content)).

   >[!NOTE]
   >
   >Les messages transactionnels basés sur un événement sont censés utiliser uniquement les données figurant dans l&#39;événement envoyé pour définir le destinataire et la personnalisation du contenu du message. Il est toutefois possible d&#39;enrichir le contenu de votre message transactionnel en utilisant des informations de la base de données Adobe Campaign.

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Lors de l&#39;aperçu de l&#39;événement, l&#39;API REST contient un attribut précisant l&#39;adresse email ou le numéro de téléphone portable en fonction du canal sélectionné.

   Une fois la publication effectuée, un message transactionnel associé au nouvel événement est automatiquement créé. Pour que cet événement déclenche l&#39;envoi d&#39;un message transactionnel, vous devez modifier et publier le message qui vient d&#39;être créé, voir [Messages transactionnels basés sur un événement](../../channels/using/event-transactional-messages.md)

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Messages transactionnels basés sur un profil   {#profile-based-transactional-messages}

Pour envoyer un message transactionnel basé sur un profil, vous devez d&#39;abord créer et configurer un événement ciblant les données contenues dans la base de données Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Profile event]** targeting dimension (see [Creating an event](#creating-an-event)).
1. Ajoutez des champs à l&#39;événement afin de personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)). Vous devez ajouter au moins un champ pour créer un enrichissement. Vous n&#39;avez pas à créer des champs tels que **Prénom** et **Nom**, car vous pourrez utiliser les champs de personnalisation de la base de données Adobe Campaign.
1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the email address or the mobile phone as it will be retrieved from the **[!UICONTROL Profile]** resource.

   Une fois la publication effectuée, un message transactionnel associé au nouvel événement est automatiquement créé. Pour que cet événement déclenche l&#39;envoi d&#39;un message transactionnel, vous devez modifier et publier le message qui vient d&#39;être créé, voir [Envoyer un message transactionnel basé sur un profil](../../channels/using/profile-transactional-messages.md#sending-a-profile-transactional-message)

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Notifications push transactionnelles basées sur un événement   {#event-based-transactional-push-notifications}

Pour pouvoir envoyer des notifications push transactionnelles, vous devez configurer Adobe Campaign en conséquence. Voir [Configuration push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

Pour envoyer une notification push transactionnelle anonyme à tous les utilisateurs qui ont accepté de recevoir des notifications de votre application mobile, vous devez d&#39;abord créer et configurer un événement ciblant les données contenues dans l&#39;événement. Les étapes correspondantes sont présentées ci-après.

L&#39;événement doit contenir les trois éléments suivants :

* Un **jeton d&#39;enregistrement** qui est l&#39;identifiant de l&#39;utilisateur pour une application mobile et un appareil. Il peut ne pas correspondre à un profil de la base de données Adobe Campaign.
* Un **nom d&#39;application mobile** (un pour tous les appareils : Android et iOS). Il s&#39;agit de l&#39;identifiant de l&#39;application mobile configuré dans Adobe Campaign qui sera utilisé pour la réception des notifications push sur les appareils des utilisateurs. Voir à ce propos [cette page](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)
* Une **plate-forme push** (&quot;gcm&quot; pour Android et &quot;apns&quot; pour iOS).

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Real-time event]** targeting dimension (see [Creating an event](#creating-an-event)).
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

### Notifications push transactionnelles basées sur un profil   {#profile-based-transactional-push-notifications}

Pour envoyer une notification push transactionnelle aux profils Adobe Campaign qui se sont inscrits à votre application mobile, vous devez d&#39;abord créer et configurer un événement ciblant la base de données Adobe Campaign.

1. When creating the event configuration, select the **[!UICONTROL Mobile application]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](#creating-an-event)).

   La notification push transactionnelle sera envoyée, par défaut, à toutes les applications mobiles auxquelles les destinataires sont inscrits. Pour envoyer la notification push à une application mobile spécifique, sélectionnez-la dans la liste. Les autres applications mobiles seront ciblées par le message, mais seront exclues de l&#39;envoi.

   ![](assets/message-center_push_appfilter.png)

1. Ajoutez des champs à l&#39;événement si vous voulez personnaliser le message transactionnel (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).

   >[!NOTE]
   >
   >Vous devez ajouter au moins un champ pour créer un enrichissement. Vous n&#39;avez pas à créer des champs tels que **Prénom** et **Nom**, car vous pourrez utiliser les champs de personnalisation de la base de données Adobe Campaign.

1. Create an enrichment in order to link the event to the **[!UICONTROL Profile]** resource (see [Enriching the transactional message content](#enriching-the-transactional-message-content)). Creating an enrichment is mandatory when using a **[!UICONTROL Profile]** targeting dimension.
1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   When previewing the event, the REST API does not contain an attribute specifying the registration token, the application name and the push platform as they will be retrieved from the **[!UICONTROL Profile]** resource.

   Une fois la publication effectuée, une notification push transactionnelle associée au nouvel événement est automatiquement créée. Pour modifier et publier le message nouvellement créé, voir [Envoyer une notification push transactionnelle ciblant un profil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile).

1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

### Configuration d&#39;un événement pour envoyer un message de relance   {#configuring-an-event-to-send-a-follow-up-message}

Un messages de relance est un modèle de diffusion marketing prédéfini qui peut être utilisé dans un workflow pour envoyer des messages aux destinataires d&#39;un message transactionnel spécifique. Voir à ce propos la section [Messages de relance](../../channels/using/follow-up-messages.md).

1. Utilisez la même configuration d&#39;événement que celle que vous avez créée pour envoyer un message transactionnel basé sur un événement. Voir [Messages transactionnels basés sur un événement](#event-based-transactional-messages).
1. Lors de la configuration de votre  de, cochez la **[!UICONTROL Create follow-up delivery template for this event]** case avant de publier le  de.

   ![](assets/message-center_follow-up-checkbox.png)

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).

   Une fois la publication effectuée, un message transactionnel et un modèle de diffusion de relance associés au nouvel événement sont automatiquement créés. Pour plus d&#39;informations sur l&#39;utilisation des messages de relance, voir [Envoyer un message de relance](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).

## Cas pratique : configuration d&#39;un événement pour envoyer un message transactionnel   {#use-case--configuring-an-event-to-send-a-transactional-message}

Dans cette exemple, nous voulons configurer un événement afin d&#39;envoyer des messages de confirmation après chaque achat sur notre site avec les prérequis suivants :

As we want to identify our client via his CRM ID, first make sure that the **[!UICONTROL Profile]** resource has been extended with this new field.

In the same way, a custom resource corresponding to purchases must have been created and published, and must be linked to the **[!UICONTROL Profile]** resource. De cette façon, vous pourrez récupérer les informations de cette ressource pour enrichir le contenu du message.

Pour en savoir plus sur la création et la publication de ressources, consultez [cette page](../../developing/using/key-steps-to-add-a-resource.md).

1. Create a new event using the **[!UICONTROL Email]** channel and the **[!UICONTROL Profile]** targeting dimension (see [Creating an event](#creating-an-event)).
1. Définissez les attributs qui seront disponibles pour personnaliser le message transactionnel. Dans notre cas, ajoutez les champs &quot;Identifiant CRM&quot; et &quot;Identificateur produit&quot; (voir [Définir les attributs d&#39;événement](#defining-the-event-attributes)).

   ![](assets/message-center_usecase1.png)

1. To enrich the message content with information regarding the client&#39;s previous purchases, create an enrichment targeting the **[!UICONTROL Purchase]** resource (see [Enriching the transactional message content](#enriching-the-transactional-message-content)).

   ![](assets/message-center_usecase2.png)

1. Create a join condition between the &quot;Product identifier&quot; field that was previously added to the message, and the corresponding field from the **[!UICONTROL Purchase]** resource.

   ![](assets/message-center_usecase3.png)

1. Prévisualisez et publiez l&#39;événement (voir [Prévisualiser et publier l&#39;événement](#previewing-and-publishing-the-event)).
1. Intégrez l&#39;événement à votre site web (voir [Intégrer le déclenchement de l&#39;événement à un site web](#integrating-the-triggering-of-the-event-in-a-website)).

