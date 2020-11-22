---
solution: Campaign Standard
product: campaign
title: Configuration d'un processus de double opt-in
description: Suivez ces étapes pour configurer un processus de double opt-in à l'aide de landing pages dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: landing-pages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1232'
ht-degree: 100%

---


# Configuration d&#39;un processus de double opt-in{#setting-up-a-double-opt-in-process}

## A propos du double opt-in {#about-double-opt-in}

Le mécanisme de double opt-in constitue une bonne pratique lors de l’envoi d’emails. Il protège la Plateforme des adresses email erronées ou non valides ainsi que des spammeurs, et empêche les éventuelles plaintes pour spam.

Le principe consiste à envoyer un email pour confirmer l’accord du visiteur avant de le stocker en tant que profil dans votre base de données Adobe Campaign : le visiteur remplit une landing page en ligne, il reçoit ensuite un email et doit cliquer sur le lien de confirmation afin de finaliser son abonnement.

![](assets/optin_mechanism.png)

Pour mettre cela en place, vous devez :

1. Créer et publier une landing page qui permettra aux visiteurs de s&#39;inscrire et de s&#39;abonner. Cette landing page sera disponible à partir du site web. Les visiteurs qui remplissent cette landing page et la valident seront stockés dans la base de données, mais placés en liste bloquée, de façon à ce qu’ils ne reçoivent aucune communication avant validation finale (voir [Gestion de la liste bloquée dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)).
1. Créer et envoyer automatiquement l&#39;email d&#39;opt-in avec un lien de confirmation. Cet email ciblera la population qui a validé la landing page. Il sera basé sur un modèle d&#39;email qui permet de cibler les profils Opt-out.
1. Rediriger les visiteurs vers une landing page de confirmation. Cette dernière landing page comprendra un bouton de confirmation sur lequel les visiteurs devront cliquer. Vous pouvez concevoir un email de bienvenue à envoyer au moment de la confirmation et ajouter, par exemple, une offre spéciale destinée aux nouveaux abonnés.

Ces étapes doivent être réalisées dans Adobe Campaign selon un ordre spécifique afin que tous les paramètres soient correctement activés.

## Etape 1 : création de la landing page de confirmation       {#step-1--create-the-confirmation-landing-page}

Le processus de configuration du mécanisme de double opt-in commence par la création de la landing page de confirmation. Cette page s&#39;affichera lorsque les visiteurs cliqueront sur l&#39;email de confirmation afin de s&#39;inscrire.

Pour créer et configurer cette landing page, vous devez :

1. Concevoir une [landing page](../../channels/using/getting-started-with-landing-pages.md) basée sur le modèle **[!UICONTROL Acquisition de profils (acquisition)]**. Saisir le libellé **CONFIRMATION**.

   Si vous devez faire appel à des [services](../../audiences/using/about-subscriptions.md), vous pouvez également utiliser le modèle **[!UICONTROL Abonnement (abo)]**.

1. Editez les propriétés de la landing page et sous la section **[!UICONTROL Accès &amp; chargement]**, désélectionnez l&#39;option **[!UICONTROL Autoriser les visiteurs non identifiés]** et sélectionnez **[!UICONTROL Précharger les données des visiteurs]** (la sélection de cette option n&#39;est toutefois pas obligatoire).

   ![](assets/optin_confirmlp_param.png)

1. Dans la section **[!UICONTROL Traitement]** > **[!UICONTROL Données additionnelles]**, cliquez sur **[!UICONTROL Ajouter un élément]** et saisissez le chemin du contexte suivant :

   /context/profile/blackList

   Définissez la valeur sur **faux** et cliquez sur **[!UICONTROL Ajouter]**.

   ![](assets/optin_confirmlp_newelement.png)

   Ce contexte retire le champ ‘Sur la liste bloquée’ pour permettre l’envoi d’emails. Nous verrons ultérieurement que la première landing page définissait ce champ sur **vrai** avant confirmation, en vue d&#39;empêcher l&#39;envoi d&#39;emails aux profils non confirmés. Voir à ce propos [Etape 3 : créer la landing page d&#39;acquisition](#step-3--create-the-acquisition-landing-page).

1. Personnalisez le contenu de la landing page : vous pouvez afficher les données personnalisées et modifier le libellé du bouton de confirmation, par exemple en « Cliquez ici pour confirmer votre inscription ! ».

   ![](assets/optin_confirmlp_design.png)

1. Adaptez le contenu de la page de confirmation pour informer vos abonnés qu&#39;ils sont maintenant inscrits.

   ![](assets/optin_confimlp_page2.png)

1. [Testez et publiez](../../channels/using/testing-publishing-landing-page.md) la landing page.

## Etape 2 : création de l&#39;email de confirmation       {#step-2--create-the-confirmation-email}

Une fois la landing page de confirmation créée, vous pouvez concevoir l&#39;email de confirmation qui sera envoyé automatiquement à chaque visiteur qui valide la landing page d&#39;acquisition. Cette validation est considérée comme un événement, et l&#39;email est un message transactionnel, lié à une règle de typologie spécifique qui permet le ciblage des populations Opt-out.

Les étapes de création de ces éléments sont décrites ci-dessous. Vous devez les suivre avant de créer la landing page d&#39;acquisition car celle-ci fera référence au modèle d&#39;email.

### Création de l&#39;événement       {#create-the-event}

L&#39;email de confirmation est un [message transactionnel](../../channels/using/getting-started-with-transactional-msg.md) car il réagit à un événement : la validation du formulaire. Vous devez commencer par créer l&#39;événement et ensuite le modèle du message transactionnel.

1. Créez un événement, à partir du menu **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]** > **[!UICONTROL Configuration des événements]**, accessible par le biais du logo Adobe Campaign, et saisissez le libellé **CONFIRMER**.
1. Sélectionnez la dimension de ciblage **[!UICONTROL Profil]** et cliquez sur **[!UICONTROL Créer]**.

   ![](assets/optin_eventcreate.png)

1. Dans la section **[!UICONTROL Champs]**, cliquez sur **[!UICONTROL Créer un élément]** et ajoutez l&#39;**[!UICONTROL email]** dans la structure de données de façon à permettre la réconciliation.
1. Dans la section **[!UICONTROL Enrichissement]**, cliquez sur **[!UICONTROL Créer un élément]** et sélectionnez la ressource cible **[!UICONTROL Profils]**. Vous pouvez ensuite créer un mapping sur l&#39;**[!UICONTROL email]** dans la section **[!UICONTROL Définition de la jointure]**, ou sur toute autre clé de réconciliation composite, en fonction de vos besoins.

   ![](assets/optin_eventcreate_join.png)

   Si vous devez utiliser les services, ajoutez la ressource cible **[!UICONTROL Service]** et mappez-la dans le champ **[!UICONTROL serviceName]**. Pour plus d&#39;informations à ce sujet, voir .

1. Sélectionnez **[!UICONTROL profile]** comme **[!UICONTROL Enrichissement de la cible]** dans la liste déroulante.
1. Cliquez sur **[!UICONTROL Publier]** pour publier l&#39;événement.

L&#39;événement est prêt. Vous pouvez maintenant concevoir le modèle d&#39;email. Ce modèle doit inclure un lien vers la landing page **CONFIRMATION** créée préalablement. Voir à ce propos [Concevoir le message de confirmation](#design-the-confirmation-message).

### Création d&#39;une typologie {#create-the-typology-rule}

Vous devez créer une [typologie](../../sending/using/about-typology-rules.md) spécifique, en dupliquant une règle d’usine. Cette typologie vous permettra d&#39;envoyer des messages aux profils qui n’ont pas encore confirmé leur accord et sont encore sur liste bloquée. Par défaut, les typologies excluent les profiles Opt-out (c’est-à-dire sur liste bloquée). Pour créer cette de typologie, procédez comme suit :

1. Depuis le logo Adobe Campaign, sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Typologies]** et cliquez sur **[!UICONTROL Typologies]**.
1. Dupliquez la typologie d&#39;usine **[!UICONTROL Message transactionnel sur le profil (mcTypologyProfile)]**.
1. Après confirmation de la duplication, éditez la nouvelle typologie et saisissez le libellé **TYPOLOGIE_PROFIL**.
1. Supprimez la règle **Adresse sur la liste bloquée**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Cette typologie peut maintenant être associée à l&#39;email de confirmation.

### Conception du message de confirmation       {#design-the-confirmation-message}

L&#39;email de confirmation est un message transactionnel basé sur l&#39;événement créé préalablement. Suivez les étapes ci-dessous pour créer ce message :

1. Depuis le logo Adobe Campaign, sélectionnez **[!UICONTROL Plans marketing]** > **[!UICONTROL Messages transactionnels]** et cliquez sur **[!UICONTROL Messages transactionnels]**.
1. Personnalisez le modèle d&#39;email **CONFIRMER.** Vous pouvez charger du contenu existant ou utiliser un modèle d&#39;usine.
1. Ajoutez un lien vers la landing page **CONFIRMATION** et cliquez sur **[!UICONTROL Valider]** pour enregistrer les modifications.

   ![](assets/optin_email_selectlp.png)

1. Editez les propriétés du modèle d&#39;email. Dans la section **[!UICONTROL Paramètres avancés]** > **[!UICONTROL Préparation]**, sélectionnez la typologie **TYPOLOGIE_PROFIL** créée préalablement.
1. Enregistrez le message transactionnel et publiez-le.

## Etape 3 : création de la landing page d&#39;acquisition       {#step-3--create-the-acquisition-landing-page}

Vous devez créer la landing page d&#39;acquisition initiale. Ce formulaire d&#39;opt-in sera publié sur votre site web.

Pour créer et configurer cette landing page, vous devez :

1. Concevoir une [landing page](../../channels/using/getting-started-with-landing-pages.md) basée sur le modèle **[!UICONTROL Acquisition de profils (acquisition)]**. Saisir le libellé **ACQUISITION**.
1. Editez les propriétés de la landing page, dans la section **[!UICONTROL Traitement]** > **[!UICONTROL Données additionnelles]**, cliquez sur **[!UICONTROL Ajouter un élément]** et saisissez le chemin du contexte suivant :

   /context/profile/blackList

   puis définissez la valeur sur **vrai**.

   Cela est obligatoire pour forcer la mise en liste bloquée et éviter d’envoyer des messages aux visiteurs qui n’ont pas confirmé qu’ils donnaient leur accord. La validation de la landing page CONFIRMATION définira ce champ sur **faux** après confirmation. Voir à ce propos [Etape 1 : créer la landing page de confirmation](#step-1--create-the-confirmation-landing-page).

1. Dans la section **[!UICONTROL Traitement]** > **[!UICONTROL Actions spécifiques]**, sélectionnez l&#39;option **[!UICONTROL Déclencher l&#39;envoi d&#39;un message]**.
1. Dans la liste déroulante associée, sélectionnez le modèle de message transactionnel **CONFIRMER** que vous avez créé.

   ![](assets/optin_acquisition_startoption.png)

1. Personnalisez le contenu de la landing page, selon votre marque et les données qu&#39;il vous faut acquérir. Vous pouvez afficher les données personnalisées et modifier le libellé du bouton de confirmation, par exemple en **Cliquez ici pour confirmer votre inscription !**.

   ![](assets/optin_acquisition_page1.png)

1. Personnalisez la page de confirmation afin d&#39;informer le nouvel abonné qu&#39;il doit valider son inscription.

   ![](assets/optin_acquisition_page2.png)

1. [Testez et publiez](../../channels/using/testing-publishing-landing-page.md) la landing page.

Le mécanisme de double opt-in est maintenant configuré. Vous pouvez exécuter et tester la procédure de bout en bout, en commençant par l&#39;URL publique de cette landing page **[!UICONTROL ACQUISITION]**. Cette URL est affichée dans le tableau de bord de la landing page.
