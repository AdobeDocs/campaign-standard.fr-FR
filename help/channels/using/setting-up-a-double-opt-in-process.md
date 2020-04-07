---
title: Configuration d'un processus de double opt-in
description: Suivez ces étapes pour configurer un processus de double opt-in à l'aide de landing pages dans Adobe Campaign.
page-status-flag: never-activated
uuid: 23e6c4c2-e2c7-472f-b616-36a95225ac1d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: 1a24504e-7f9d-4297-b39e-c5f085b0f388
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3b40a9bba79d04f1635b7522cfc99f9e7566c3c0

---


# Configuration d&#39;un processus de double opt-in{#setting-up-a-double-opt-in-process}

## A propos du double opt-in {#about-double-opt-in}

Le mécanisme de double opt-in constitue une bonne pratique lors de l&#39;envoi d&#39;emails. Il protège la plate-forme des adresses email erronées ou non valides ainsi que des spammeurs, et empêche les éventuelles plaintes pour spam.

Le principe consiste à envoyer un email pour confirmer l&#39;accord du visiteur avant de le stocker en tant que profil dans votre base de données Adobe Campaign : le visiteur remplit une landing page en ligne, il reçoit ensuite un email et doit cliquer sur le lien de confirmation afin de finaliser son abonnement.

![](assets/optin_mechanism.png)

Pour mettre cela en place, vous devez :

1. Créer et publier une landing page qui permettra aux visiteurs de s&#39;inscrire et de s&#39;abonner. Cette landing page sera disponible à partir du site web. Les visiteurs qui remplissent cette landing page et la valident seront stockés dans la base de données, mais blacklistés, de façon à ce qu&#39;ils ne reçoivent aucune communication avant validation finale (voir [Gestion du blacklistage dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Créer et envoyer automatiquement l&#39;email d&#39;opt-in avec un lien de confirmation. Cet email ciblera la population qui a validé la landing page. Il sera basé sur un modèle d&#39;email qui permet de cibler les profils Opt-out.
1. Rediriger les visiteurs vers une landing page de confirmation. Cette dernière landing page comprendra un bouton de confirmation sur lequel les visiteurs devront cliquer. Vous pouvez concevoir un email de bienvenue à envoyer au moment de la confirmation et ajouter, par exemple, une offre spéciale destinée aux nouveaux abonnés.

Ces étapes doivent être réalisées dans Adobe Campaign selon un ordre spécifique afin que tous les paramètres soient correctement activés.

## Etape 1 : création de la landing page de confirmation  {#step-1--create-the-confirmation-landing-page}

Le processus de configuration du mécanisme de double opt-in commence par la création de la landing page de confirmation. Cette page s&#39;affichera lorsque les visiteurs cliqueront sur l&#39;email de confirmation afin de s&#39;inscrire.

Pour créer et configurer cette landing page, vous devez :

1. Design a [new landing page](../../channels/using/getting-started-with-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Saisir le libellé **CONFIRMATION**.

   If you need to use [services](../../audiences/using/about-subscriptions.md), you can also use the **[!UICONTROL Subscription (sub)]** template.

1. Modifiez les propriétés  du et, sous la **[!UICONTROL Access and loading]** section, désélectionnez l’option **[!UICONTROL Authorize unidentified visitors]**, sélectionnez **[!UICONTROL Preload visitor data]** (celle-ci n’est pas obligatoire).

   ![](assets/optin_confirmlp_param.png)

1. Dans la section **[!UICONTROL Job]** > **[!UICONTROL Additional data]** , cliquez **[!UICONTROL Add an element]** et saisissez le chemin de contexte suivant :

   /context/profile/blackList

   Set the value to **false** and click **[!UICONTROL Add]**.

   ![](assets/optin_confirmlp_newelement.png)

   Ce contexte retire le champ de blackliste pour permettre l&#39;envoi d&#39;emails. Nous verrons ultérieurement que la première landing page définissait ce champ sur **vrai** avant confirmation, en vue d&#39;empêcher l&#39;envoi d&#39;emails aux profils non confirmés. Voir à ce propos [Etape 3 : créer la landing page d&#39;acquisition](#step-3--create-the-acquisition-landing-page).

1. Personnalisez le contenu de la landing page : vous pouvez afficher les données personnalisées et modifier le libellé du bouton de confirmation, par exemple en « Cliquez ici pour confirmer votre inscription ! ».

   ![](assets/optin_confirmlp_design.png)

1. Adaptez le contenu de la page de confirmation pour informer vos abonnés qu&#39;ils sont maintenant inscrits.

   ![](assets/optin_confimlp_page2.png)

1. [Testez et publiez](../../channels/using/testing-publishing-landing-page.md) la landing page.

## Etape 2 : création de l&#39;email de confirmation  {#step-2--create-the-confirmation-email}

Une fois la landing page de confirmation créée, vous pouvez concevoir l&#39;email de confirmation qui sera envoyé automatiquement à chaque visiteur qui valide la landing page d&#39;acquisition. Cette validation est considérée comme un événement, et l&#39;email est un message transactionnel, lié à une règle de typologie spécifique qui permet le ciblage des populations Opt-out.

Les étapes de création de ces éléments sont décrites ci-dessous. Vous devez les suivre avant de créer la landing page d&#39;acquisition car celle-ci fera référence au modèle d&#39;email.

### Création de l&#39;événement  {#create-the-event}

L&#39;email de confirmation est un [message transactionnel](../../channels/using/about-transactional-messaging.md) car il réagit à un événement : la validation du formulaire. Vous devez commencer par créer l&#39;événement et ensuite le modèle du message transactionnel.

1. Créez un , à partir du menu **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Event configuration]** , accessible à partir du logo , puis saisissez l’étiquette &quot;**CONFIRMER**&quot;.
1. Sélectionnez le **[!UICONTROL Profile]** de et cliquez sur **[!UICONTROL Create]**.

   ![](assets/optin_eventcreate.png)

1. In the **[!UICONTROL Fields]** section, click **[!UICONTROL Create element]** and add the **[!UICONTROL email]** in the data structure to enable reconciliation.
1. Dans la **[!UICONTROL Enrichment]** section, cliquez sur **[!UICONTROL Create element]** et sélectionnez la ressource de  **[!UICONTROL Profile]** . You can then map on the **[!UICONTROL email]** field in the **[!UICONTROL Join definition]** section, or any other composite reconciliation key, depending on your needs.

   ![](assets/optin_eventcreate_join.png)

   Si vous devez utiliser les services, ajoutez la ressource cible **[!UICONTROL Service]** et mappez-la dans le champ **[!UICONTROL serviceName]**. Pour plus d&#39;informations à ce sujet, voir .

1. Sélectionnez **[!UICONTROL Profile]** comme valeur **[!UICONTROL Targeting enrichment]** dans le  de la liste déroulante.
1. Click **[!UICONTROL Publish]** to publish the event.

L&#39;événement est prêt. Vous pouvez maintenant concevoir le modèle d&#39;email. Ce modèle doit inclure un lien vers la landing page **CONFIRMATION** créée préalablement. Voir à ce propos [Concevoir le message de confirmation](#design-the-confirmation-message).

### Create the typology {#create-the-typology-rule}

You need to create a specific [typology](../../sending/using/about-typology-rules.md), by duplicating an out-of-box one. La typologie permettra d&#39;envoyer des messages à des qui n&#39;ont pas encore confirmé leur accord et qui sont encore. Par défaut, les typologies excluent les  d’exclusion (c.-à-d.). Pour créer cette typologie, procédez comme suit :

1. From the Adobe Campaign logo, select **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Typologies]** and click **[!UICONTROL Typologies]**.
1.  la typologie prête à l’emploi **[!UICONTROL Transactional message on profile (mcTypologyProfile)]**.
1. Après confirmation de la duplication, éditez la nouvelle typologie et saisissez le libellé **TYPOLOGIE_PROFIL**.
1. Supprimez la règle des **adresses blacklistées**.
1. Clics **[!UICONTROL Save]**.

Cette typologie peut maintenant être associée à l&#39;email de confirmation.

### Conception du message de confirmation  {#design-the-confirmation-message}

L&#39;email de confirmation est un message transactionnel basé sur l&#39;événement créé préalablement. Suivez les étapes ci-dessous pour créer ce message :

1. From the Adobe Campaign logo, select **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** and click **[!UICONTROL Transactional messages]**.
1. Personnalisez le modèle d&#39;email **CONFIRMER**. Vous pouvez charger du contenu existant ou utiliser un modèle d&#39;usine.
1. Add a link to the **CONFIRMATION** landing page, and click **[!UICONTROL Confirm]** to save modifications.

   ![](assets/optin_email_selectlp.png)

1. Editez les propriétés du modèle d&#39;email. In the **[!UICONTROL Advanced parameters]** > **[!UICONTROL Preparation]** section, select the **TYPOLOGY_PROFILE** typology created before.
1. Enregistrez le message transactionnel et publiez-le.

## Etape 3 : création de la landing page d&#39;acquisition  {#step-3--create-the-acquisition-landing-page}

Vous devez créer la landing page d&#39;acquisition initiale. Ce formulaire d&#39;opt-in sera publié sur votre site web.

Pour créer et configurer cette landing page, vous devez :

1. Design a [new landing page](../../channels/using/getting-started-with-landing-pages.md) based on the **[!UICONTROL Profile acquisition (acquisition)]** template. Saisir le libellé **ACQUISITION**.
1. Modifiez les propriétés  du : dans la section **[!UICONTROL Job]** > **[!UICONTROL Additional data]** , cliquez **[!UICONTROL Add an element]** et saisissez le chemin de contexte suivant :

   /context/profile/blackList

   puis définissez la valeur sur **vrai**.

   Cela est obligatoire pour forcer le blacklistage et éviter d&#39;envoyer des messages aux visiteurs qui n&#39;ont pas confirmé qu&#39;ils donnaient leur accord. La validation de la landing page CONFIRMATION définira ce champ sur **faux** après confirmation. Voir à ce propos [Etape 1 : créer la landing page de confirmation](#step-1--create-the-confirmation-landing-page).

1. Dans la section **[!UICONTROL Job]** > **[!UICONTROL Specific actions]** , sélectionnez l’option **[!UICONTROL Start sending messages]**.
1. Dans la liste déroulante associée, sélectionnez le modèle de message transactionnel **CONFIRMER** que vous avez créé.

   ![](assets/optin_acquisition_startoption.png)

1. Personnalisez le contenu de la landing page, selon votre marque et les données qu&#39;il vous faut acquérir. Vous pouvez afficher les données personnalisées et modifier le libellé du bouton de confirmation, par exemple en **Cliquez ici pour confirmer votre inscription !**.

   ![](assets/optin_acquisition_page1.png)

1. Personnalisez la page de confirmation afin d&#39;informer le nouvel abonné qu&#39;il doit valider son inscription.

   ![](assets/optin_acquisition_page2.png)

1. [Testez et publiez](../../channels/using/testing-publishing-landing-page.md) la landing page.

Le mécanisme de double opt-in est maintenant configuré. Vous pouvez exécuter et tester la procédure de bout en bout, en commençant par l&#39;URL publique de cette landing page **[!UICONTROL ACQUISITION]**. Cette URL est affichée dans le tableau de bord de la landing page.
