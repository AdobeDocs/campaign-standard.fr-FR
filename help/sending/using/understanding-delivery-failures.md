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
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 96%

---


# Comprendre les diffusions en échec{#understanding-delivery-failures}

## A propos des diffusions en échec {#about-delivery-failures}

Lorsqu’une diffusion ne peut pas être envoyée à un profil, le serveur distant envoie automatiquement un message d’erreur, qui est relevé par la plateforme Adobe Campaign et qualifié afin de déterminer si l’adresse email ou le numéro de téléphone doit être mis ou non en quarantaine Voir [Qualification des emails bounce](#bounce-mail-qualification).

>[!NOTE]
>
>Les messages d’erreur **email** (ou « bounces ») sont qualifiés par le MTA amélioré (bounces synchrones) ou par le traitement inMail (bounces asynchrones).
>
>Les messages d’erreur de type **SMS** (ou &quot;SR&quot; pour &quot;Status Report&quot;) sont qualifiés par le processus MTA.

Les messages peuvent également être exclus pendant la préparation de la diffusion si une adresse est mise en quarantaine ou si un profil est placé sur la liste bloquée. Les messages exclus sont répertoriés dans l’onglet **[!UICONTROL Exclus]** du tableau de bord des diffusions (voir [cette section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Rubriques connexes :**

* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Les processus d’inscription et de désinscription dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifier les diffusions en échec pour un message     {#identifying-delivery-failures-for-a-message}

Une fois une diffusion envoyée, l’onglet **[!UICONTROL Envois]** (voir [cette section](../../sending/using/monitoring-a-delivery.md#sending-logs)) permet de consulter le statut de la diffusion pour chaque profil ainsi que le type d’échec et la raison associés (voir [Types de diffusion en échec et raisons](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Un rapport d’usine dédié est également disponible. Ce rapport présente l’ensemble des statistiques d’erreurs hard et soft survenues lors des diffusions ainsi que le traitement automatique des retours. Voir à ce propos [cette section](../../reporting/using/bounce-summary.md).

## Types de diffusion en échec et raisons     {#delivery-failure-types-and-reasons}

Trois types d’erreur sont liés à une diffusion en échec :

* **Hard** : une erreur de type &quot;hard&quot; indique une adresse invalide. Il s’agit d’un message d’erreur indiquant explicitement que l’adresse est invalide, par exemple : &quot;Utilisateur inconnu&quot;.
* **Soft** : il s’agit d’une erreur qui peut être temporaire, ou qui n’a pas pu être qualifiée, par exemple : &quot;Domaine invalide&quot; ou &quot;Boîte pleine&quot;.
* **Ignoré** : il s’agit d’une erreur que l’on sait temporaire, par exemple &quot;Out of office&quot;, ou d’une erreur technique, par exemple si l’expéditeur est de type &quot;postmaster&quot;.

Les motifs possibles d’une diffusion en échec sont les suivants :

| Libellé de l&#39;erreur | Type d&#39;erreur | Description |
---------|----------|---------
| **[!UICONTROL Utilisateur inconnu]** | Hard | L&#39;adresse n&#39;existe pas. Aucune autre diffusion ne sera envoyée pour ce profil. |
| **[!UICONTROL Adresse en quarantaine]** | Hard | L&#39;adresse a été mise en quarantaine. |
| **[!UICONTROL Inatteignable]** | Soft/Hard | Une erreur s’est produite dans la chaîne de distribution du message (domaine temporairement inatteignable, par exemple). Selon l’erreur renvoyée par le fournisseur, l’adresse sera directement mise en quarantaine ou la diffusion sera envoyée à nouveau jusqu’à ce que Campaign reçoive une erreur justifiant le statut Quarantaine ou que le nombre d’erreurs atteigne 5. |
| **[!UICONTROL Adresse vide]** | Hard | L’adresse n’est pas définie. |
| **[!UICONTROL Boîte pleine]** | Soft | La boîte aux lettres de cet utilisateur est pleine et ne peut pas accepter d’autres messages. Cette adresse peut éventuellement être retirée de la liste des quarantaines pour faire une nouvelle tentative, et l’est automatiquement au bout de 30 jours. Pour que l’adresse soit automatiquement retirée de la liste des adresses en quarantaine, le workflow technique **[!UICONTROL Nettoyage de la base]** doit être démarré. |
| **[!UICONTROL Refusés]** | Soft/Hard | L’adresse a été mise en quarantaine en raison d’un retour de sécurité signalant du spam. Selon l’erreur renvoyée par le fournisseur, l’adresse sera directement mise en quarantaine ou la diffusion sera envoyée à nouveau jusqu’à ce que Campaign reçoive une erreur justifiant le statut Quarantaine ou que le nombre d’erreurs atteigne 5. |
| **[!UICONTROL Doublon]** | Ignoré | L’adresse a déjà été détectée dans la segmentation. |
| **[!UICONTROL Non définie]** | Soft | L’adresse est en cours de qualification parce que les erreurs n’ont pas encore été incrémentées. Ce type d’erreur apparaît lorsqu’un nouveau message d’erreur est envoyé par le serveur : il peut s’agir d’une erreur isolée, mais si elle se répète, le compteur d’erreur augmente, ce qui permet d’alerter les équipes techniques. |
| **[!UICONTROL Erreur ignorée]** | Ignoré | L&#39;adresse est placée sur la liste autorisée et un e-mail lui sera envoyé en tout cas. |
| **[!UICONTROL Adresse placée sur la liste bloquée]** | Hard | L&#39;adresse a été ajoutée à la liste bloquée au moment de l&#39;envoi. |
| **[!UICONTROL Compte désactivé]** | Soft/Hard | Lorsque le Fournisseur d’Accès Internet (FAI) détecte une inactivité prolongée, il peut fermer le compte de l’utilisateur, ce qui rend les diffusions vers son adresse impossibles. Le type d’erreur Soft ou Hard dépend du type d’erreur reçu : si le compte est temporairement désactivé en raison d’une inactivité de 6 mois et qu’il peut toujours être activé, le statut **[!UICONTROL En erreur]** sera affecté et la diffusion sera de nouveau envoyée. Si l’erreur a reçu des signaux indiquant que le compte est définitivement désactivé, il sera mis directement en quarantaine. |
| **[!UICONTROL Non connecté]** | Ignoré | Le téléphone portable du profil est éteint ou n’est pas connecté au réseau au moment de l’envoi du message. |
| **[!UICONTROL Domaine invalide]** | Soft | Le domaine de l&#39;adresse email est erroné ou n&#39;existe plus. Ce profil sera ciblé de nouveau jusqu&#39;à ce que le nombre d&#39;erreurs atteigne 5. Une fois ce chiffre atteint, l&#39;enregistrement sera défini sur le statut Quarantaine et aucune autre reprise ne sera effectuée. |
| **[!UICONTROL Texte trop long]** | Ignoré | Le nombre de caractères du SMS dépasse la limite autorisée. Voir à ce propos la section [Encodage, longueur et translittération des SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration). |
| **[!UICONTROL Caractère non pris en charge par le codage]** | Ignoré | Le message SMS contient un ou plusieurs caractères qui ne sont pas pris en charge par le codage. Voir à ce propos la section [Table des caractères - Norme GSM](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard). |

## Reprises après une diffusion temporairement en échec     {#retries-after-a-delivery-temporary-failure}

Si un message est en échec en raison d’une erreur temporaire du type **Ignoré**, les reprises seront effectuées pendant la durée de la diffusion. Pour plus d’informations sur les types d’erreurs, voir [Types de diffusion en échec et raisons](#delivery-failure-types-and-reasons).

Le nombre de reprises (le nombre de reprises à exécuter le jour suivant le démarrage de l’envoi) et le délai minimal entre traitements sont désormais gérés par le MTA amélioré d’Adobe, en fonction de la performance historique et actuelle d’une IP sur un domaine donné. Les paramètres de **Reprises** dans Campaign sont ignorés.

Pour modifier la durée d’une diffusion, accédez aux paramètres avancés de la diffusion ou du modèle de diffusion, puis modifiez le champ **[!UICONTROL Durée de diffusion]** de la section [Période de validité](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!IMPORTANT]
>
>**Le paramètre**[!UICONTROL  Durée de diffusion ]**dans vos diffusions Campaign n’est désormais utilisé que s’il est défini sur 3,5 jours ou moins.** Si vous définissez une valeur supérieure à 3,5 jours, elle ne sera pas prise en compte car elle est désormais gérée par le MTA amélioré d’Adobe Campaign.

Si, par exemple, vous souhaitez que les reprises pour une diffusion s’arrêtent après une journée, vous pouvez définir la durée de diffusion sur **1d**, et le MTA amélioré respectera ce paramètre en supprimant les messages dans la file d’attente des nouvelles reprises après une journée.

>[!NOTE]
>
>Une fois qu’un message figure dans la file d’attente du MTA amélioré depuis 3,5 jours et qu’il n’a pas été diffusé, il expire et son état est mis à jour de **[!UICONTROL Envoi]** à **[!UICONTROL Échec]** dans les [logs de diffusion](../../sending/using/monitoring-a-delivery.md#delivery-logs).

<!--The default configuration allows five retries at one-hour intervals, followed by one retry per day for four days. The number of retries can be changed globally (contact your Adobe technical administrator) or for each delivery or delivery template (see [this section](../../administration/using/configuring-email-channel.md#sending-parameters)).-->

## Erreurs synchrones et asynchrones     {#synchronous-and-asynchronous-errors}

Une diffusion peut échouer immédiatement (erreur synchrone) ou plus tard, après sont envoi (erreur asynchrone).

* **Erreur synchrone** : le serveur distant contacté par le serveur de diffusion Adobe Campaign a retourné immédiatement un message d&#39;erreur. L&#39;envoi de la diffusion au serveur du profil n&#39;est pas autorisé.
* **Erreur asynchrone** : un email bounce ou un SR a été renvoyé plus tard par le serveur de réception. Les erreurs asynchrones peuvent se produire jusqu’à une semaine après l’envoi d’une diffusion.

## Qualification des emails bounce     {#bounce-mail-qualification}

Pour les messages d’erreur d’échec de diffusion synchrone, le MTA amélioré détermine le type et la qualification du bounce et renvoie ces informations à Campaign.

Les bounces asynchrones sont toujours qualifiés par le processus inMail via les règles **[!UICONTROL Mail entrant]**. Pour accéder à ces règles, cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, sélectionnez **[!UICONTROL Administration > Canaux > Email > Règles de gestion des emails]**, puis **[!UICONTROL Emails bounce]**. Pour plus d’informations sur cette règle, voir cette [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!NOTE]
>
>La qualification des emails bounce est maintenant gérée par le MTA amélioré d’Adobe Campaign. Les qualifications bounce figurant dans le tableau **[!UICONTROL Qualification des messages]** de Campaign ne sont plus utilisées.

<!--Bounces can have the following qualification statuses:

* **[!UICONTROL To qualify]**: the bounce mail needs to be qualified. Qualification must be done by the Deliverability team to ensure that the platform deliverability functions correctly. As long as it is not qualified, the bounce mail is not used to enrich the list of email processing rules.
* **[!UICONTROL Keep]**: the bounce mail was qualified and will be used by the **Update for deliverability** workflow to be compared to existing email processing rules and enrich the list.
* **[!UICONTROL Ignore]**: the bounce mail was qualified but will not be used by the **Update for deliverability** workflow. So it will not be sent to the client instances.

To list the various bounces and their associated error types et reasons, click the **[!UICONTROL Adobe Campaign]** logo, in the top left, then select **[!UICONTROL Administration > Channels > Quarantines > Message qualification]**.

![](assets/qualification.png)-->

## Optimiser la délivrabilité des emails avec le mécanisme de double opt-in {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Le mécanisme de double opt-in constitue une bonne pratique lors de l’envoi d’emails. Il protège la plate-forme des adresses email erronées ou non valides ainsi que des spammeurs, et empêche les éventuelles plaintes pour spam.

Le principe consiste à envoyer un email pour confirmer l’accord du visiteur avant de le stocker en tant que profil dans votre base de données Adobe Campaign : le visiteur remplit une landing page en ligne, il reçoit ensuite un email et doit cliquer sur le lien de confirmation afin de finaliser son abonnement.

Voir à ce propos [cette section](../../channels/using/setting-up-a-double-opt-in-process.md).
