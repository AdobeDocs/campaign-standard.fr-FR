---
title: Comprendre les diffusions en échec
description: Découvrez comment gérer les diffusions en échec dans Campaign.
page-status-flag: never-activated
uuid: 2735aa05-7b6f-47c9-98c4-a15cc33be39d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: 38452841-4cd4-4f92-a5c3-1dfdd54ff6f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: bee7ea0f1728da2a96c1f225b91b13a7903be660

---


# Comprendre les diffusions en échec{#understanding-delivery-failures}

## A propos des diffusions en échec {#about-delivery-failures}

Lorsqu&#39;une diffusion ne peut pas être envoyée à un profil, le serveur distant envoie automatiquement un message d&#39;erreur, qui est relevé par la plateforme Adobe Campaign et qualifié afin de déterminer si l&#39;adresse email ou le numéro de téléphone doit être mis ou non en quarantaine Voir [Qualification des emails bounce](#bounce-mail-qualification).

>[!NOTE]
>
>Les messages d&#39;erreur de type **Email** (ou &quot;bounces&quot;) sont qualifiés par le processus inMail. Les messages d&#39;erreur de type **SMS** (ou &quot;SR&quot; pour &quot;Status Report&quot;) sont qualifiés par le processus MTA.

Les messages peuvent être également exclus pendant la préparation de la diffusion si une adresse est mise en quarantaine ou un profil blacklisté. Excluded messages are listed in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Rubriques connexes :**

* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Gestion du blacklistage dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifier les diffusions en échec pour un message  {#identifying-delivery-failures-for-a-message}

Once a delivery is sent, the **[!UICONTROL Sending logs]** tab (see [this section](../../sending/using/monitoring-a-delivery.md#sending-logs)) allows you to view the delivery status for each profile and the associated failure type and reason (see [Delivery failure types and reasons](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Un rapport d&#39;usine dédié est également disponible. Ce rapport présente l&#39;ensemble des statistiques d&#39;erreurs hard et soft survenues lors des diffusions ainsi que le traitement automatique des retours. Voir à ce propos [cette section](../../reporting/using/bounce-summary.md).

## Types de diffusion en échec et raisons  {#delivery-failure-types-and-reasons}

Trois types d&#39;erreur sont liés à une diffusion en échec :

* **Hard** : une erreur de type &quot;hard&quot; indique une adresse invalide. Il s&#39;agit d&#39;un message d&#39;erreur indiquant explicitement que l&#39;adresse est invalide, par exemple : &quot;Utilisateur inconnu&quot;.
* **Soft** : il s&#39;agit d&#39;une erreur qui peut être temporaire, ou qui n&#39;a pas pu être qualifiée, par exemple : &quot;Domaine invalide&quot; ou &quot;Boîte pleine&quot;.
* **Ignoré** : il s&#39;agit d&#39;une erreur que l&#39;on sait temporaire, par exemple &quot;Out of office&quot;, ou d&#39;une erreur technique, par exemple si l&#39;expéditeur est de type &quot;postmaster&quot;.

Les motifs possibles d&#39;une diffusion en échec sont les suivants :

* **[!UICONTROL User unknown]** (Type dur) : l&#39;adresse n&#39;existe pas. Aucune autre diffusion ne sera envoyée pour ce profil.
* **[!UICONTROL Quarantined address]** (Type dur) : l&#39;adresse a été placée en .
* **[!UICONTROL Unreachable]** (Type souple/net) : une erreur s&#39;est produite dans la chaîne de de messages (par exemple, domaine temporairement -----). Selon l&#39;erreur renvoyée par le fournisseur, l&#39;adresse sera directement mise en quarantaine ou la diffusion sera envoyée à nouveau jusqu&#39;à ce que Campaign reçoive une erreur justifiant le statut Quarantaine ou que le nombre d&#39;erreurs atteigne 5.
* **[!UICONTROL Address empty]** (Type dur) : l&#39;adresse n&#39;est pas définie.
* **[!UICONTROL Mailbox full]** (Type souple) : la boîte aux lettres de cet utilisateur est pleine et ne peut pas accepter plus de messages. Cette adresse peut éventuellement être retirée de la liste des quarantaines pour faire une nouvelle tentative, et l&#39;est automatiquement au bout de 30 jours.

   In order for the address to be automatically removed from the list of quarantined addresses, the **[!UICONTROL Database cleanup]** technical workflow must be started.

* **[!UICONTROL Refused]** (Type souple/net) : l&#39;adresse a été placée dans le en raison d&#39;un commentaire de sécurité en tant que rapport de spam. Selon l&#39;erreur renvoyée par le fournisseur, l&#39;adresse sera directement mise en quarantaine ou la diffusion sera envoyée à nouveau jusqu&#39;à ce que Campaign reçoive une erreur justifiant le statut Quarantaine ou que le nombre d&#39;erreurs atteigne 5.
* **[!UICONTROL Duplicate]**: l&#39;adresse a déjà été détectée dans la segmentation.
* **[!UICONTROL Not defined]** (Type souple) : l&#39; adresse est en réserve, car les erreurs n&#39; ont pas encore été incrémentées.

   Ce type d&#39;erreur apparaît lorsqu&#39;un nouveau message d&#39;erreur est envoyé par le serveur : il peut s&#39;agir d&#39;une erreur isolée, mais si elle se répète, le compteur d&#39;erreur augmente, ce qui permet d&#39;alerter les équipes techniques.

* **[!UICONTROL Error ignored]**: l&#39;adresse figure sur la liste blanche et un courriel lui sera envoyé dans tous les cas.
* **[!UICONTROL Blacklisted address]**: l&#39;adresse était au moment de l&#39;envoi.
* **[!UICONTROL Account disabled]** (Type souple/net) : lorsque le fournisseur d’accès Internet (IAP) détecte une longue période d’inactivité, il peut fermer le compte de l’utilisateur : Il sera alors impossible d’ à l’adresse de l’utilisateur. The Soft or Hard type depends upon the type of error received: if the account is temporarily disabled due to six months of inactivity and can still be activated, the status **[!UICONTROL Erroneous]** will be assigned and the delivery will be tried again. Si l&#39;erreur a reçu des signaux indiquant que le compte est définitivement désactivé, il sera mis directement en quarantaine.
* **[!UICONTROL Not connected]**: le  téléphone mobile est éteint ou n&#39;est pas connecté au réseau lors de l&#39;envoi du message.
* **[!UICONTROL Invalid domain]** (Type souple) : le domaine de l’adresse électronique est incorrect ou n’existe plus. Ce profil sera ciblé de nouveau jusqu&#39;à ce que le nombre d&#39;erreurs atteigne 5. Ensuite, l&#39;enregistrement sera défini sur le statut Quarantaine et aucune autre reprise ne sera effectuée.
* **[!UICONTROL Text too long]**: le nombre de caractères dans le message SMS dépasse la limite. Voir à ce propos la section [Encodage, longueur et translittération des SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Character not supported by encoding]**: le message SMS contient un ou plusieurs caractères qui ne sont pas pris en charge par le codage. Voir à ce propos la section [Table des caractères - Norme GSM](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Reprises après une diffusion temporairement en échec  {#retries-after-a-delivery-temporary-failure}

Si un message est en échec en raison d&#39;une erreur temporaire du type **Ignoré**, les reprises seront effectuées pendant la durée de la diffusion. Pour plus d&#39;informations sur les types d&#39;erreurs, voir [Types de diffusion en échec et raisons](#delivery-failure-types-and-reasons).

Pour modifier la durée d&#39;une diffusion, accédez aux paramètres avancés de la diffusion ou du modèle de diffusion et indiquez la durée souhaitée dans le champ correspondant. Les propriétés avancées des diffusions sont présentées dans [cette section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

La configuration par défaut permet cinq reprises à des intervalles d&#39;une heure chacune, puis une reprise par jour pendant quatre jours. Le nombre de reprises peut être changé de manière globale (contactez l&#39;administrateur technique Adobe) ou pour chaque diffusion ou modèle de diffusion (voir [cette section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Erreurs synchrones et asynchrones  {#synchronous-and-asynchronous-errors}

Une diffusion peut échouer immédiatement (erreur synchrone) ou plus tard, après sont envoi (erreur asynchrone).

* **Erreur synchrone** : le serveur distant contacté par le serveur de diffusion Adobe Campaign a retourné immédiatement un message d&#39;erreur. L&#39;envoi de la diffusion au serveur du profil n&#39;est pas autorisé.
* **Erreur asynchrone** : un email bounce ou un SR a été renvoyé plus tard par le serveur de réception. Les erreurs asynchrones peuvent se produire jusqu&#39;à une semaine après l&#39;envoi d&#39;une diffusion.

## Qualification des emails bounce  {#bounce-mail-qualification}

<!--Delivery failure error messages (or "SMTP bounce responses") are picked up by the Adobe Campaign platform and then processed and qualified as **Hard**, **Soft**, or **Ignored** using the **[!UICONTROL Delivery log qualification]** database.

//Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)

This list is available to administrators only and contains all the rules used by Adobe Campaign to qualify delivery failures.-->

>[!IMPORTANT]
>
>Once upgraded to the Enhanced MTA, the bounce qualifications in the Campaign **[!UICONTROL Message qualification]** table are no longer used.

Pour les messages d’erreur d’échec de diffusion synchrone, le MTA amélioré détermine le type et la qualification du bounce et renvoie ces informations à Campaign. Pour plus d’informations sur le MTA amélioré d&#39;Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Les rebonds asynchrones sont toujours qualifiés par le processus inMail via les **[!UICONTROL Inbound email]** règles. Pour accéder à ces règles, cliquez sur le **[!UICONTROL Adobe Campaign]** logo, en haut à gauche, puis sélectionnez **[!UICONTROL Administration > Channels > Email > Email processing rules]** et **[!UICONTROL Bounce mails]**. For more on this rule, refer to this [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimiser la délivrabilité des emails avec le mécanisme de double opt-in {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Le mécanisme de double opt-in constitue une bonne pratique lors de l&#39;envoi d&#39;emails. Il protège la plate-forme des adresses email erronées ou non valides ainsi que des spammeurs, et empêche les éventuelles plaintes pour spam.

Le principe consiste à envoyer un email pour confirmer l&#39;accord du visiteur avant de le stocker en tant que profil dans votre base de données Adobe Campaign : le visiteur remplit une landing page en ligne, il reçoit ensuite un email et doit cliquer sur le lien de confirmation afin de finaliser son abonnement.

Voir à ce propos [cette section](../../channels/using/setting-up-a-double-opt-in-process.md).
