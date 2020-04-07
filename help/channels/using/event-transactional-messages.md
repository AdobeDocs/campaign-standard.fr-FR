---
title: Messages transactionnels basés sur un événement
description: Découvrez comment créer et publier un message transactionnel basé sur un événement.
page-status-flag: never-activated
uuid: d747feb5-58fb-4e12-a176-404f0eca5391
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 4f6317a1-9dfe-4714-bc1c-393629d855cd
context-tags: deliveryTransactionalTemplate,overview
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: be6751f2f966f99d2b986aeba0b3720d2e8c4599

---


# Messages transactionnels basés sur un événement{#event-transactional-messages}

Vous pouvez envoyer des messages transactionnels d&#39;événement ciblant un événement. Ce type de message transactionnel ne contient pas d&#39;informations de profil : la cible de la diffusion est définie par les données contenues dans l&#39;événement lui-même.

Une fois que vous avez créé et publié l&#39;événement de votre choix (l&#39;abandon de panier, comme expliqué dans [cette section](../../channels/using/about-transactional-messaging.md#transactional-messaging-operating-principle)), le message transactionnel correspondant est automatiquement créé.

Les étapes de configuration sont présentées dans la section [Configurer un événement pour envoyer un message transactionnel](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

Pour que l&#39;événement entraîne l&#39;envoi d&#39;un message transactionnel, vous devez personnaliser le message, le tester et le publier.

>[!NOTE]
>
>To access transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.
>
>Les messages transactionnels basés sur un événement ne contiennent pas d&#39;informations sur les profils. Ils ne sont donc pas compatibles avec les règles de fatigue (même dans le cas d&#39;un enrichissement avec des profils). Voir [Règles de fatigue](../../sending/using/fatigue-rules.md#choosing-the-channel).

## Définir un profil de test dans un message transactionnel    {#defining-a-test-profile-in-a-transactional-message}

Définissez un profil de test adapté, qui vous permettra de prévisualiser votre message et d&#39;envoyer un bon à tirer (BAT) afin de le valider.

### Créer un profil de test dans un message transactionnel    {#creating-a-test-profile-within-the-transactional-----------message}

1. Pour accéder au message que vous avez créé, cliquez sur le **[!UICONTROL Adobe Campaign]** logo, dans le coin supérieur gauche, puis sélectionnez **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.

   ![](assets/message-center_4.png)

1. Créez un profil de test qui sera lié à votre événement.

   ![](assets/message-center_test-profile.png)

1. Spécifiez les informations à envoyer au format JSON dans la **[!UICONTROL Event data used for personalization]** section. C&#39;est le contenu qui sera utilisé lors de la prévisualisation du message et que recevra le profil de test à l&#39;envoi du BAT.

   ![](assets/message-center_event-data.png)

   >[!NOTE]
   >
   >Vous pouvez également saisir les informations associées à la table des profils. Voir [Enrichir le contenu d&#39;un message transactionnel](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).

1. Une fois créé, le profil de test est pré-renseigné dans le message transactionnel. Click the **[!UICONTROL Test profiles]** block of the message to check the target of your proof.

   ![](assets/message-center_5.png)

### Créer un profil de test en dehors du message transactionnel {#creating-a-test-profile-outside-the-transactional-----------message}

You can also create a new test profile or use one that already exists in the **[!UICONTROL Test profiles]** menu.

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]**.
1. In the **[!UICONTROL Event]** section of the page of the test profile that you have chosen, select the event that you have just created. Dans cet exemple, choisissez &quot;Abandon de panier (EVTcartAbandonment)&quot;.
1. Specify the information to send in JSON format in the **[!UICONTROL Event data]** text box.

   ![](assets/message-center_3.png)

1. Enregistrez vos modifications.

Vous pouvez maintenant accéder au message que vous avez créé et sélectionner le profil de test mis à jour.

**Rubriques connexes :**

* [Gestion des profils de test](../../audiences/using/managing-test-profiles.md)
* [Définir les audiences](../../audiences/using/creating-audiences.md)

## Personnaliser un message transactionnel    {#personalizing-a-transactional-message}

Pour configurer la personnalisation dans un message transactionnel, procédez comme suit :

1. Click the **[!UICONTROL Content]** block to modify your message&#39;s subject and content. Dans cet exemple, sélectionnez un modèle contenant des images et du texte. Pour plus d&#39;informations sur les modèles de contenu d&#39;email, voir [Conception à l&#39;aide de modèles](../../designing/using/using-reusable-content.md#designing-templates).

   ![](assets/message-center_6.png)

1. Ajoutez un objet et modifiez le contenu de votre message en fonction de vos besoins.

   >[REMARQUE]
   >
   >Le lien vers le panier abandonné est un lien vers une URL externe qui redirigera la personne sur son panier. Ce paramétrage n&#39;est pas géré dans Adobe Campaign.

1. Dans cet exemple, vous souhaitez ajouter trois champs que vous avez définis lors de la [création de votre événement](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) : prénom, dernier produit consulté, montant total du panier. Pour ce faire, [insérez un champ de personnalisation](../../designing/using/personalization.md#inserting-a-personalization-field) dans le contenu du message.

1. Accédez à ces champs via **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7.png)

1. Pour enrichir le contenu de votre message, ajoutez les champs de votre choix en les sélectionnant dans la table à laquelle vous avez lié votre événement. In our example, select the **[!UICONTROL Title (salutation)]** field in the **[!UICONTROL Profile]** table through **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]**.

   ![](assets/message-center_7-enrichment.png)

1. Insérez tous les champs nécessaires.

   ![](assets/message-center_8.png)

1. Prévisualisez votre message en sélectionnant le profil que vous avez défini pour cet événement.

   Les étapes de prévisualisation d&#39;un message sont présentées dans la section [Prévisualiser le message](../../sending/using/previewing-messages.md).

   ![](assets/message-center_9.png)

   Vous constatez que les champs de personnalisation correspondent bien aux informations saisies dans le profil de test. Pour plus d&#39;informations à ce propos, voirVoir à ce sujet [Définir un profil de test dans un message transactionnel](#defining-a-test-profile-in-a-transactional-message).

## Utiliser des listes de produits dans un message transactionnel    {#using-product-listings-in-a-transactional-message}

Vous pouvez créer des listes de produits référençant une ou plusieurs collections de données dans un email transactionnel. Par exemple, dans un email d&#39;abandon de panier, vous pouvez inclure la liste de tous les produits figurant dans le panier de l&#39;utilisateur au moment où il a quitté le site web, avec une image, le prix et un lien vers chaque produit.

>[!IMPORTANT]
>
>Les listes de produits ne sont disponibles que lorsque vous éditez des emails transactionnels via l&#39;interface du [Concepteur d&#39;email](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-interface).

Pour ajouter une liste de produits abandonnés dans un message transactionnel, suivez les étapes ci-dessous.

Vous pouvez également regarder une série de vidéos expliquant les étapes nécessaires à la configuration de listes de produits dans un email transactionnel. Voir à ce propos [cette page](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html).

>[!NOTE]
>
>Adobe Campaign ne prend pas en charge les listes de produits imbriquées, ce qui signifie que vous ne pouvez pas inclure une liste de produits dans une autre.

### Définir une liste de produits    {#defining-a-product-listing}

Avant de pouvoir utiliser une liste de produits dans un message transactionnel, vous devez définir au niveau de l&#39;événement la liste des produits et les champs de chaque produit de la liste que vous souhaitez afficher. Voir à ce propos la section [Définir des collections de données](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. In the transactional message, click the **[!UICONTROL Content]** block to modify the email content.
1. Placez un composant de structure dans l&#39;espace de travail. Voir à ce propos la section [Editer la structure de l&#39;email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

   Par exemple, sélectionnez un composant de structure à une colonne et ajoutez un composant de texte, un composant d&#39;image et un composant de bouton. Voir à ce propos la section [Ajouter des fragments et des composants de contenu](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Select the structure component you just created and click the **[!UICONTROL Enable product listing]** icon from the contextual toolbar.

   ![](assets/message-center_loop_create.png)

   The structure component is highlighted with an orange frame and the **[!UICONTROL Product listing]** settings are displayed in the left palette.

   ![](assets/message-center_loop_palette.png)

1. Sélectionnez l&#39;affichage des éléments de la collection :

   * **[!UICONTROL Row]**: horizontalement, c’est-à-dire chaque élément d’une ligne sous l’autre.
   * **[!UICONTROL Column]**: verticalement, c’est-à-dire que chaque élément se trouve à côté de l’autre sur la même ligne.
   >[!NOTE]
   >
   >L’ **[!UICONTROL Column]** option n’est disponible que lors de l’utilisation d’un composant de structure à plusieurs colonnes ( **[!UICONTROL 2:2 column]**, **[!UICONTROL 3:3 column]** et **[!UICONTROL 4:4 column]** ). Lors de l&#39;édition de la liste de produits, ne remplissez que la première colonne. Les autres colonnes ne seront pas prises en compte. Pour plus d&#39;informations sur la sélection de composants de structure, consultez la section [Editer la structure de l&#39;email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

1. Sélectionnez la collection de données que vous avez créée lors de la configuration de l&#39;événement associé au message transactionnel. Vous pouvez le trouver sous le noeud **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** .

   ![](assets/message-center_loop_selection.png)

   Pour plus d&#39;informations sur la configuration de l&#39;événement, consultez la section [Définir des collections de données](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Use the **[!UICONTROL First item]** drop-down list to select which element will start the list displayed in the email.

   Par exemple, si vous sélectionnez 2, le premier élément de la collection ne sera pas affiché dans l&#39;email. La liste de produits commencera sur le deuxième élément.

1. Sélectionnez le nombre maximal d&#39;éléments à afficher dans la liste.

   >[!NOTE]
   >
   >If you want the elements of your list to be displayed vertically ( **[!UICONTROL Column]** ), the maximum number of items is limited according to the selected structure component (2, 3 or 4 columns). Pour plus d&#39;informations sur la sélection de composants de structure, consultez la section [Editer la structure de l&#39;email](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

### Remplir la liste de produits    {#populating-the-product-listing}

Pour afficher une liste des produits provenant de l&#39;événement associé à l&#39;email transactionnel, suivez les étapes ci-dessous.

Pour plus d&#39;informations sur la création d&#39;une collection et de champs associés lors de la configuration de l&#39;événement, consultez la section [Définir des collections de données](../../administration/using/configuring-transactional-messaging.md#defining-data-collections).

1. Select the image component you inserted, select **[!UICONTROL Enable personalization]** and click the pencil in the Settings pane.

   ![](assets/message-center_loop_image.png)

1. Sélectionnez **[!UICONTROL Add personalization field]** dans la **[!UICONTROL Image source URL]** fenêtre qui s’ouvre.

   Dans le noeud **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** , ouvrez le noeud correspondant à la collection que vous avez créée (ici **[!UICONTROL Product list]** ) et sélectionnez le champ d’image que vous avez défini (ici **[!UICONTROL Product image]** ). Clics **[!UICONTROL Save]**.

   ![](assets/message-center_loop_product-image.png)

   Le champ de personnalisation que vous avez sélectionné est maintenant affiché dans le volet Paramètres.

1. A l’emplacement souhaité, sélectionnez **[!UICONTROL Insert personalization field]** dans la barre d’outils contextuelle.

   ![](assets/message-center_loop_product.png)

1. Dans le noeud **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** , ouvrez le noeud correspondant à la collection que vous avez créée (ici **[!UICONTROL Product list]** ) et sélectionnez le champ que vous avez créé (ici **[!UICONTROL Product name]** ). Clics **[!UICONTROL Confirm]**.

   ![](assets/message-center_loop_product_node.png)

   Le champ de personnalisation que vous avez sélectionné est maintenant affiché à l&#39;emplacement voulu dans le contenu de l&#39;email.

1. Procédez de la même manière pour insérer le prix.
1. Select some text and select **[!UICONTROL Insert link]** from the contextual toolbar.

   ![](assets/message-center_loop_link_insert.png)

1. Sélectionnez **[!UICONTROL Add personalization field]** dans la **[!UICONTROL Insert link]** fenêtre qui s’ouvre.

   Dans le noeud **[!UICONTROL Context]** > **[!UICONTROL Real-time event]** > **[!UICONTROL Event context]** , ouvrez le noeud correspondant à la collection que vous avez créée (ici **[!UICONTROL Product list]** ) et sélectionnez le champ URL que vous avez créé (ici **[!UICONTROL Product URL]** ). Clics **[!UICONTROL Save]**.

   >[!IMPORTANT]
   >
   >Pour des raisons de sécurité, veillez à insérer le champ de personnalisation dans un lien commençant par un nom de domaine statique approprié.

   ![](assets/message-center_loop_link_select.png)

   Le champ de personnalisation que vous avez sélectionné est maintenant affiché dans le volet Paramètres.

1. Select the structure component on which the product listing is applied and select **[!UICONTROL Show fallback]** to define a default content.

   ![](assets/message-center_loop_fallback_show.png)

1. Faites glisser un ou plusieurs composants de contenu et éditez-les si nécessaire.

   ![](assets/message-center_loop_fallback.png)

   Le contenu de remplacement sera affiché si la collection est vide lorsque l&#39;événement est déclenché, par exemple lorsqu&#39;un client ne possède aucun produit dans son panier.

1. Dans le volet Paramètres, éditez les styles de la liste de produits. Voir à ce propos la section [Editer les styles d&#39;un email](../../designing/using/styles.md).
1. Prévisualisez l&#39;email en utilisant un profil de test associé à l&#39;événement transactionnel adéquat et pour lequel vous avez défini des données de collection. For example, add the following information in the **[!UICONTROL Event data]** section for the test profile you want to use:

   ![](assets/message-center_loop_test-profile_payload.png)

   Pour plus d&#39;informations sur la définition d&#39;un profil de test dans un message transactionnel, consultez [cette section](#defining-a-test-profile-in-a-transactional-message).

## Tester un message transactionnel {#testing-a-transactional-message}

Après avoir enregistré votre message transactionnel, vous pouvez envoyer un bon à tirer (BAT) pour le tester.

![](assets/message-center_10.png)

Les étapes d&#39;envoi d&#39;un BAT sont présentées dans la section [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).

## Publier un message transactionnel    {#publishing-a-transactional-message}

Une fois que vous avez validé le message transactionnel, vous pouvez le publier.

![](assets/message-center_12.png)

A présent, dès que l&#39;événement &quot;Abandon de panier&quot; est déclenché, il entraîne automatiquement l&#39;envoi d&#39;un message contenant la civilité et le nom du destinataire, l&#39;URL du panier, le dernier produit consulté ou la liste des produits si vous avez défini une liste de produits et le montant total du panier.

To access reports concerning your transactional message, use the **[!UICONTROL Reports]** button. Voir [Rapports](../../reporting/using/about-dynamic-reports.md).

![](assets/message-center_13.png)

## Suspendre la publication d&#39;un message transactionnel    {#suspending-a-transactional-message-publication}

Vous pouvez suspendre la publication de votre message transactionnel en utilisant le bouton **[!UICONTROL Pause]** Mettre en , , afin de modifier les données contenues dans le message par exemple. Les événements ne sont alors plus traités, mais ils sont conservés dans une file d&#39;attente, dans la base de données Adobe Campaign.

Les événements placés dans la file d&#39;attente sont conservés pendant une période définie dans l&#39;API REST (voir la [documentation sur l&#39;API REST](../../api/using/about-campaign-standard-apis.md)) ou dans l&#39;événement trigger si vous utilisez le core service Triggers (voir [Utilisation de Campaign et des Triggers Experience Cloud](../../integrating/using/about-adobe-experience-cloud-triggers.md)).

![](assets/message-center_pause.png)

When clicking **[!UICONTROL Resume]**, all of the queued events (provided that they are not expired) are processed. Ils contiennent alors les modifications effectuées tant que la publication du modèle était suspendue.

## Dépublier un message transactionnel    {#unpublishing-a-transactional-message}

Clicking **[!UICONTROL Unpublish]** allows you to cancel the transactional message publication, but also the publication of the corresponding event, which deletes from the REST API the resource corresponding to the event that you previously created.

![](assets/message-center_unpublish-template.png)

Désormais, même si l&#39;événement est déclenché via votre site web, les messages correspondants ne sont plus envoyés et ils ne sont pas stockés dans la base de données.

>[!NOTE]
>
>Pour publier de nouveau le message, revenez d&#39;abord à la configuration de l&#39;événement correspondant et publiez-le. Vous pouvez alors republier votre message. Voir à ce propos la section [Publier un message transactionnel](#publishing-a-transactional-message).

Si vous dépubliez un message transactionnel mis en pause, vous devrez attendre jusqu&#39;à 24 heures avant de pouvoir le republier. This is to let the **[!UICONTROL Database cleanup]** workflow clean all the events that were sent to the queue.

Les étapes de mise en pause d&#39;un message sont présentées dans la section [Suspendre la publication d&#39;un message transactionnel](#suspending-a-transactional-message-publication).

Le **[!UICONTROL Database cleanup]** flux de travaux, qui s’exécute tous les jours à 4 heures du matin, est accessible par **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]**.

## Supprimer un message transactionnel {#deleting-a-transactional-message}

Une fois qu’un  a été annulé ou qu’un  de n’a pas encore été publié, vous pouvez le supprimer dude la  de l’. Pour cela :

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Transactional messages]**.
1. Passez la souris sur le message de votre choix.
1. Cliquez sur le **[!UICONTROL Delete element]** bouton.

![](assets/message-center_delete-template.png)

La suppression d&#39;un message transactionnel ne peut toutefois être effectuée que sous certaines conditions :

* Assurez-vous que le  a le **[!UICONTROL Draft]** statut, sinon vous ne pourrez pas le supprimer. L’ **[!UICONTROL Draft]** état s’applique à un message qui n’a pas encore été publié ou qui a été [annulé](#unpublishing-a-transactional-message) (et non [suspendu](#suspending-a-transactional-message-publication)).

* ****: A moins qu’un autre  de ne soit lié à l’ de correspondante, si l’ de la version non publiée est annulée, la configuration de l’doit également être annulée pour que la suppression de votre soit réussie. Pour plus d’informations, voir [Annulation de la publication d’un](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).

   >[!IMPORTANT]
   >
   >La suppression d&#39;un message transactionnel ayant déjà envoyé des notifications entraîne celle de ses logs d&#39;envoi et du tracking.

* **à partir d’un modèle de  de prêt à l’emploi ( interne)**: Si un interne est le seul associé au interne correspondant, il ne peut pas être supprimé. Vous devez d’abord créer un autre en le dupliquant ou via le menu **[!UICONTROL Resources]** > **[!UICONTROL Templates]** > **[!UICONTROL Transactional message templates]** .

## Processus de reprise d&#39;un message transactionnel    {#transactional-message-retry-process}

Un message transactionnel temporairement non diffusé fait l&#39;objet de reprises automatiques jusqu&#39;à l&#39;expiration de la diffusion. Pour plus d&#39;informations sur la durée de diffusion, voir [Paramètres de période de validité](../../administration/using/configuring-email-channel.md#validity-period-parameters).

En cas d&#39;échec de l&#39;envoi d&#39;un message transactionnel, il existe deux systèmes de reprise :

* Au niveau des messages transactionnels, un message transactionnel peut échouer avant que l&#39;événement ne soit assigné à une diffusion d&#39;exécution, c&#39;est-à-dire entre la réception de l&#39;événement et la préparation de la diffusion. Voir [Processus de reprise du traitement d&#39;un événement](#event-processing-retry-process).
* Au niveau du processus d&#39;envoi, une fois l&#39;événement assigné à une diffusion d&#39;exécution, le message transactionnel peut échouer en raison d&#39;une erreur temporaire. Voir [Processus de reprise de l&#39;envoi d&#39;un message](#message-sending-retry-process).

### Processus de reprise du traitement d&#39;un événement    {#event-processing-retry-process}

Si l&#39;événement ne peut pas être assigné à une diffusion d&#39;exécution, son traitement est reporté. Des reprises sont ensuite effectuées jusqu&#39;à ce qu&#39;il soit assigné à une nouvelle diffusion d&#39;exécution.

>[!NOTE]
>
>Un événement reporté n&#39;apparaît pas dans les logs d&#39;envoi de messages transactionnels, car il n&#39;est pas encore assigné à une diffusion d&#39;exécution.

Par exemple, l&#39;événement ne pourrait pas être assigné à une diffusion d&#39;exécution, en raison d&#39;un contenu incorrect, d&#39;un problème de droits d&#39;accès ou de branding, d&#39;une erreur détectée lors de l&#39;application des règles de typologie, etc. Dans ce cas, vous pouvez mettre le message en pause, l&#39;éditer pour résoudre le problème et le publier à nouveau. Le système de reprise l&#39;assignera ensuite à une nouvelle diffusion d&#39;exécution.

### Processus de reprise de l&#39;envoi d&#39;un message    {#message-sending-retry-process}

Une fois que l&#39;événement a été assigné à une diffusion d&#39;exécution, le message transactionnel peut échouer en raison d&#39;une erreur temporaire, par exemple si la boîte du destinataire est pleine. Voir à ce propos [Reprises après un échec temporaire de diffusion](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

>[!NOTE]
>
>Lorsqu&#39;un événement est assigné à une diffusion d&#39;exécution, il apparaît dans les logs d&#39;envoi de cette diffusion d&#39;exécution, et uniquement à ce moment. The failed deliveries are displayed in the **[!UICONTROL Execution list]** tab of the transactional message.

### Limitations {#limitations}

**Mise à jour des logs d&#39;envoi**

Dans le processus de reprise, les logs d&#39;envoi de la nouvelle diffusion d&#39;exécution ne sont pas immédiatement mis à jour (la mise à jour est réalisée via un workflow planifié). It means that the message could be in **[!UICONTROL Pending]** status even if the transactional event has been processed by the new execution delivery.

**Diffusion d&#39;exécution en échec**

Vous ne pouvez pas arrêter une diffusion d&#39;exécution. Cependant, si la diffusion d&#39;exécution actuelle échoue, une nouvelle est créée dès qu&#39;un nouvel événement est reçu, et tous les nouveaux événements sont traités par cette nouvelle diffusion d&#39;exécution. Aucun nouvel événement n&#39;est traité par la diffusion d&#39;exécution en échec.

Si certains événements déjà assignés à une diffusion d&#39;exécution ont été reportés et si cette diffusion d&#39;exécution échoue, le système de reprise n&#39;assigne pas les événements reportés à la nouvelle diffusion d&#39;exécution, ce qui signifie que ces événements sont perdus.
