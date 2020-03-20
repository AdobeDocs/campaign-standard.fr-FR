---
title: Tableau de bord des messages
description: Découvrez la composition du tableau de bord d'un message, notamment la barre d'actions et les différents blocs fonctionnels.
page-status-flag: never-activated
uuid: 9bb44ee8-2cf6-43ce-94a4-367f4e469713
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: about-communication-channels
discoiquuid: 90a78742-697f-46da-8c54-108048e57b67
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 80f6a384e99a7cebbe5c570f3273eceb393fd9b0

---


# Tableau de bord des messages{#message-dashboard}

Le tableau de bord d&#39;un message est un espace de travail composé de différentes icônes - regroupées dans une barre d&#39;actions - et de différents blocs fonctionnels vous permettant de définir les paramètres de votre message et d&#39;exécuter son envoi. Ces éléments sont présentés ci-après.

![](assets/delivery_dashboard_2.png)

## Barre grise   {#gray-bar}

La barre grise regroupe différentes icônes en lien avec votre message.

* **[!UICONTROL Summary]**: affiche/masque les informations principales concernant le message.
* **[!UICONTROL Edit properties]**: permet de modifier les paramètres [](../../administration/using/configuring-email-channel.md#list-of-email-properties)avancés du message.
* **[!UICONTROL Reports]**: donne accès aux rapports relatifs au message.

**Rubriques connexes :**

* [Configuration des canaux](../../administration/using/about-channel-configuration.md)
* [Accéder aux rapports](../../reporting/using/about-dynamic-reports.md)

## La barre d&#39;actions {#action-bar}

La barre d&#39;actions contient différentes icônes permettant d&#39;agir sur votre message.

![](assets/delivery_dashboard_4.png)

Selon les paramètres renseignés et l&#39;avancement du processus de création, certaines d&#39;entre elles peuvent ne pas être disponibles.

* **[!UICONTROL Show proofs]**: affiche/masque le  des qui ont été envoyés, le cas échéant. Ce bouton n&#39;est actif que lorsque vous avez envoyé des bons à tirer.

   Pour plus d’informations sur les bons à tirer, voir la section [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).

* **[!UICONTROL Send a test]**: vous permet de sélectionner le mode d’approbation à utiliser : **[!UICONTROL Email rendering]**, **[!UICONTROL Proof]** ou les deux pour un courrier électronique. Pour plus d&#39;informations sur les profils de test, voir la section [Envoyer un bon à tirer](../../sending/using/sending-proofs.md).

   Ce bouton n&#39;est actif que lorsque vous avez défini des profils de test.

   >[!NOTE]
   >
   >For an SMS message, there is no other choice: it is automatically a **[!UICONTROL Proof]**.

* **[!UICONTROL Prepare send]**: pour préparer l&#39;envoi. The **[!UICONTROL Deployment]** block appears and displays the result of the preparation. Ce bouton n&#39;apparaît que lorsque la cible a été renseignée. Vous pouvez arrêter à tout moment la préparation via le bouton correspondant.

   Pour plus d&#39;informations sur la préparation, voir la section [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md).

* **[!UICONTROL Confirm send]**: confirme l&#39;envoi du message. The sending statistics appear in the **[!UICONTROL Deployment]** block. Ce bouton n&#39;apparaît qu&#39;après la préparation de l&#39;envoi. Vous pouvez, à tout moment, arrêter ou mettre en l&#39;envoi à l&#39;aide des boutons **Arrêter l&#39;envoi** et **[!UICONTROL Pause]** Mettre en pause.

   Pour plus d&#39;informations sur la validation d&#39;un envoi, voir la section [Envoyer les messages](../../sending/using/confirming-the-send.md).

## Blocs   {#blocks}

L&#39;écran principal est composé de différents blocs. Cliquez dans un bloc pour accéder à l&#39;écran de paramètres correspondant :

![](assets/delivery_dashboard_3.png)

* **[!UICONTROL Deployment]**: vous permet de suivre la progression de la préparation ou de l’envoi du message. Cliquez sur le bouton situé en bas à droite du bloc pour accéder aux logs d&#39;analyse et d&#39;envoi. Ce bloc n&#39;apparaît qu&#39;après la préparation de l&#39;envoi. Voir à ce propos la section [Confirmer l&#39;envoi](../../sending/using/confirming-the-send.md).
* **[!UICONTROL Audience]**: vous permet d’établir le  principal du message ainsi que le de test. Voir [Créer une audience](../../audiences/using/creating-audiences.md).
* **[!UICONTROL Schedule]**: vous permet de spécifier la date d’envoi du message. See [Scheduling](../../sending/using/about-scheduling-messages.md).
* **[!UICONTROL Content]**: vous permet de définir le contenu du message et de le . Voir [Principales étapes pour envoyer un message](../../channels/using/key-steps-to-send-a-message.md).

## Avertissements {#warnings}

Dans certains cas, un avertissement peut apparaître dans une bannière jaune au-dessus du tableau de bord des messages.

![](assets/delivery_dashboard_warnings.png)

Vous trouverez ci-dessous une liste des messages pouvant être affichés :

* *&quot;L&#39;option de mode test SMTP est activée pour cet email : aucun message ne sera envoyé.&quot;*

   Voir à ce propos [cette section](../../administration/using/configuring-email-channel.md#smtp-test-mode).

* *&quot;Le compte externe de routage a été désactivé.&quot;*

   Pour plus d’informations, voir [Comptes externes](../../administration/using/external-accounts.md).

* *« Les messages ne peuvent pas être envoyés, car l’affinité IP actuelle n’est gérée par aucun processus d’envoi. »*

   Si ce message s’affiche, un problème s’est produit au niveau de la définition de l’affinité IP ou du processus d’envoi. Contactez votre administrateur Adobe.

* *&quot;C&#39;est un  prêt à l&#39;emploi. Si vous souhaitez le modifier, vous devez le  et travailler sur votre copie.&quot;*

   Certains de ces modèles de message transactionnel d’usine sont des modèles de landing page intégrés. Voir à ce propos [cette section](../../channels/using/landing-page-templates.md).

* *&quot;Ce message est un modèle de message transactionnel technique. Vous ne pouvez pas le modifier ni le publier.&quot;*

   Cet avertissement s’affiche dans des modèles de message transactionnel vides ne pouvant pas être modifiés. Pour plus d’informations sur les messages transactionnels, voir [cette section](../../channels/using/about-transactional-messaging.md).
