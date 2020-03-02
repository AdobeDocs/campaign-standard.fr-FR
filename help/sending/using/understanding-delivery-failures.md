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
translation-type: ht
source-git-commit: 3c45cbbb261f18252689d0fc4f332b9f45137c85

---


# Comprendre les diffusions en échec{#understanding-delivery-failures}

## A propos des diffusions en échec {#about-delivery-failures}

Lorsqu&#39;une diffusion ne peut pas être envoyée à un profil, le serveur distant envoie automatiquement un message d&#39;erreur, qui est relevé par la plateforme Adobe Campaign et qualifié afin de déterminer si l&#39;adresse email ou le numéro de téléphone doit être mis ou non en quarantaine Voir [Qualification des emails bounce](#bounce-mail-qualification).

>[!NOTE]
>
>Les messages d&#39;erreur de type **Email** (ou &quot;bounces&quot;) sont qualifiés par le processus inMail. Les messages d&#39;erreur de type **SMS** (ou &quot;SR&quot; pour &quot;Status Report&quot;) sont qualifiés par le processus MTA.

Les messages peuvent être également exclus pendant la préparation de la diffusion si une adresse est mise en quarantaine ou un profil blacklisté. Les messages exclus sont répertoriés dans l&#39;onglet **[!UICONTROL Exclus]** du tableau de bord des diffusions (voir [cette section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)).

![](assets/exclusion_logs.png)

**Rubriques connexes :**

* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Gestion du blacklistage dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

## Identifier les diffusions en échec pour un message  {#identifying-delivery-failures-for-a-message}

Une fois une diffusion envoyée, l&#39;onglet **[!UICONTROL Envois]** (voir [cette section](../../sending/using/monitoring-a-delivery.md#sending-logs)) permet de consulter le statut de la diffusion pour chaque profil ainsi que le type d&#39;échec et la raison associés (voir [Types de diffusion en échec et raisons](#delivery-failure-types-and-reasons)).

![](assets/sending_logs.png)

Un rapport d&#39;usine dédié est également disponible. Ce rapport présente l&#39;ensemble des statistiques d&#39;erreurs hard et soft survenues lors des diffusions ainsi que le traitement automatique des retours. Voir à ce propos [cette section](../../reporting/using/bounce-summary.md).

## Types de diffusion en échec et raisons  {#delivery-failure-types-and-reasons}

Trois types d&#39;erreur sont liés à une diffusion en échec :

* **Hard** : une erreur de type &quot;hard&quot; indique une adresse invalide. Il s&#39;agit d&#39;un message d&#39;erreur indiquant explicitement que l&#39;adresse est invalide, par exemple : &quot;Utilisateur inconnu&quot;.
* **Soft** : il s&#39;agit d&#39;une erreur qui peut être temporaire, ou qui n&#39;a pas pu être qualifiée, par exemple : &quot;Domaine invalide&quot; ou &quot;Boîte pleine&quot;.
* **Ignoré** : il s&#39;agit d&#39;une erreur que l&#39;on sait temporaire, par exemple &quot;Out of office&quot;, ou d&#39;une erreur technique, par exemple si l&#39;expéditeur est de type &quot;postmaster&quot;.

Les motifs possibles d&#39;une diffusion en échec sont les suivants :

* **[!UICONTROL Utilisateur inconnu]** (type Hard) : l&#39;adresse n&#39;existe pas. Aucune autre diffusion ne sera envoyée pour ce profil.
* **[!UICONTROL Adresse en quarantaine]** (type Hard) : l&#39;adresse a été mise en quarantaine.
* **[!UICONTROL Inatteignable]** (type Soft/Hard) : une erreur s&#39;est produite dans la chaîne de distribution du message. Il peut s&#39;agir d&#39;un incident sur le relais SMTP, d&#39;un domaine temporairement inatteignable, etc. Selon l&#39;erreur renvoyée par le fournisseur, l&#39;adresse sera directement mise en quarantaine ou la diffusion sera envoyée à nouveau jusqu&#39;à ce que Campaign reçoive une erreur justifiant le statut Quarantaine ou que le nombre d&#39;erreurs atteigne 5.
* **[!UICONTROL Adresse non renseignée]** (type Hard) : l&#39;adresse n&#39;est pas définie.
* **[!UICONTROL Boîte pleine]** (type Soft) : la boîte de messagerie du destinataire est pleine et ne peut pas accepter d&#39;autres messages. Cette adresse peut éventuellement être retirée de la liste des quarantaines pour faire une nouvelle tentative, et l&#39;est automatiquement au bout de 30 jours.

   Pour que l&#39;adresse soit automatiquement retirée de la liste des adresses en quarantaine, le workflow technique **[!UICONTROL Nettoyage de la base]** doit être démarré.

* **[!UICONTROL Refusé]** (type Soft/Hard) : l&#39;adresse a été mise en quarantaine en raison d&#39;un retour de sécurité signalant du spam. Selon l&#39;erreur renvoyée par le fournisseur, l&#39;adresse sera directement mise en quarantaine ou la diffusion sera envoyée à nouveau jusqu&#39;à ce que Campaign reçoive une erreur justifiant le statut Quarantaine ou que le nombre d&#39;erreurs atteigne 5.
* **[!UICONTROL Doublon]** : l&#39;adresse a déjà été détectée dans la segmentation.
* **[!UICONTROL Non définie]** (type Soft) : l&#39;adresse est en cours de qualification, car les erreurs n&#39;ont pas encore été incrémentées.

   Ce type d&#39;erreur apparaît lorsqu&#39;un nouveau message d&#39;erreur est envoyé par le serveur : il peut s&#39;agir d&#39;une erreur isolée, mais si elle se répète, le compteur d&#39;erreur augmente, ce qui permet d&#39;alerter les équipes techniques.

* **[!UICONTROL Erreur ignorée]** : l&#39;adresse est en whiteliste et un email lui sera envoyé dans tous les cas.
* **[!UICONTROL Adresse en blackliste]** : l&#39;adresse était en blackliste au moment de l&#39;envoi.
* **[!UICONTROL Compte désactivé]** : (type Soft/Hard) : lorsque le Fournisseur d&#39;Accès Internet (FAI) détecte une inactivité prolongée, il peut fermer le compte de l&#39;utilisateur, ce qui rend les diffusions vers son adresse impossibles. Le type d&#39;erreur Soft ou Hard dépend du type d&#39;erreur reçu : si le compte est temporairement désactivé en raison d&#39;une inactivité de 6 mois et qu&#39;il peut toujours être activé, le statut **[!UICONTROL En erreur]** sera affecté et la diffusion sera de nouveau envoyée. Si l&#39;erreur a reçu des signaux indiquant que le compte est définitivement désactivé, il sera mis directement en quarantaine.
* **[!UICONTROL Non connecté]** : le téléphone portable du profil est éteint ou n&#39;est pas connecté au réseau au moment de l&#39;envoi du message.
* **[!UICONTROL Domaine invalide]** (type Soft) : le domaine de l&#39;adresse email est erroné ou n&#39;existe plus. Ce profil sera ciblé de nouveau jusqu&#39;à ce que le nombre d&#39;erreurs atteigne 5. Ensuite, l&#39;enregistrement sera défini sur le statut Quarantaine et aucune autre reprise ne sera effectuée.
* **[!UICONTROL Texte trop long]** : le nombre de caractères du SMS dépasse la limite autorisée. Voir à ce propos la section [Encodage, longueur et translittération des SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).
* **[!UICONTROL Caractère non supporté par l&#39;encodage]** : le SMS contient un ou plusieurs caractères qui ne sont pas supportés par l&#39;encodage. Voir à ce propos la section [Table des caractères - Norme GSM](../../administration/using/configuring-sms-channel.md#table-of-characters---gsm-standard).

## Reprises après une diffusion temporairement en échec  {#retries-after-a-delivery-temporary-failure}

Si un message est en échec en raison d&#39;une erreur temporaire du type **Ignoré**, les reprises seront effectuées pendant la durée de la diffusion. Pour plus d&#39;informations sur les types d&#39;erreurs, voir [Types de diffusion en échec et raisons](#delivery-failure-types-and-reasons).

Pour modifier la durée d&#39;une diffusion, accédez aux paramètres avancés de la diffusion ou du modèle de diffusion et indiquez la durée souhaitée dans le champ correspondant. Les propriétés avancées des diffusions sont présentées dans [cette section](../../administration/using/configuring-email-channel.md#validity-period-parameters).

La configuration par défaut permet cinq reprises à des intervalles d&#39;une heure chacune, puis une reprise par jour pendant quatre jours. Le nombre de reprises peut être changé de manière globale (contactez l&#39;administrateur technique Adobe) ou pour chaque diffusion ou modèle de diffusion (voir [cette section](../../administration/using/configuring-email-channel.md#sending-parameters)).

## Erreurs synchrones et asynchrones  {#synchronous-and-asynchronous-errors}

Une diffusion peut échouer immédiatement (erreur synchrone) ou plus tard, après sont envoi (erreur asynchrone).

* **Erreur synchrone** : le serveur distant contacté par le serveur de diffusion Adobe Campaign a retourné immédiatement un message d&#39;erreur. L&#39;envoi de la diffusion au serveur du profil n&#39;est pas autorisé.
* **Erreur asynchrone** : un email bounce ou un SR a été renvoyé plus tard par le serveur de réception. Les erreurs asynchrones peuvent se produire jusqu&#39;à une semaine après l&#39;envoi d&#39;une diffusion.

## Qualification des emails bounce  {#bounce-mail-qualification}

Les messages d’erreur relatifs aux échecs de diffusion (ou « réponses de bounce SMTP ») sont sélectionnés par la plateforme Adobe Campaign, puis traités et qualifiés comme **Hard**, **Soft** ou **Ignoré** à l’aide de la base de données de **[!UICONTROL qualification du log de diffusion]**.

<!--Delivery failure error messages (or "bounces") are picked up by the Adobe Campaign platform and qualified by the inMail process to enrich the list of email management rules.(applies to asynchronous (out-of-band) bounces)-->

Cette liste est disponible pour les administrateurs uniquement. Elle contient toutes les règles utilisées par Adobe Campaign pour qualifier les diffusions en échec.

Pour accéder à cette liste, cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Administration > Canaux > Email > Règles de gestion des emails]**.

Voir à ce propos cette [section](../../administration/using/configuring-email-channel.md#email-processing-rules).

>[!IMPORTANT]
>
>Une fois effectuée la mise à niveau vers le serveur de diffusion MTA amélioré, les qualifications des rebonds dans le tableau **[!UICONTROL Qualification des messages]** ne sont plus utilisées. Pour les messages d’erreur d’échec de diffusion synchrone, le serveur MTA amélioré détermine le type et la qualification du rebond et renvoie ces informations à Campaign. Les rebonds asynchrones restent qualifiés par le processus inMail.
>
>Pour plus d’informations sur le serveur de diffusion MTA amélioré d&#39;Adobe Campaign, reportez-vous à ce [document](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html).

Les statuts de qualification des bounces sont les suivants :

* **[!UICONTROL A qualifier]** : le mail bounce n&#39;a pas pu être qualifié. La qualification doit être confiée à l&#39;équipe Délivrabilité afin de garantir le bon fonctionnement de la délivrabilité de la plateforme. Tant qu&#39;il n&#39;est pas qualifié, le mail bounce n&#39;est pas utilisé pour enrichir la liste des règles de gestion des emails.
* **[!UICONTROL Conserver]** : le mail bounce a été qualifié et sera utilisé par le workflow **Mise à jour pour la délivrabilité** pour être comparé aux règles de gestion des emails existantes et en enrichir la liste.
* **[!UICONTROL Ignorer]** : le mail rebond a été qualifié mais ne sera pas utilisé par le workflow **Mise à jour pour la délivrabilité**. Il ne sera donc pas envoyé vers les instances clientes.

Pour répertorier les différents bounces et les types d&#39;erreur et raisons associés, cliquez sur le logo **[!UICONTROL Adobe Campaign]**, en haut à gauche, puis sélectionnez **[!UICONTROL Administration > Canaux > Quarantaines > Qualification des messages]**.

![](assets/qualification.png)

## Optimiser la délivrabilité des emails avec le mécanisme de double opt-in {#optimizing-mail-deliverability-with-double-opt-in-mechanism}

Le mécanisme de double opt-in constitue une bonne pratique lors de l&#39;envoi d&#39;emails. Il protège la plate-forme des adresses email erronées ou non valides ainsi que des spammeurs, et empêche les éventuelles plaintes pour spam.

Le principe consiste à envoyer un email pour confirmer l&#39;accord du visiteur avant de le stocker en tant que profil dans votre base de données Adobe Campaign : le visiteur remplit une landing page en ligne, il reçoit ensuite un email et doit cliquer sur le lien de confirmation afin de finaliser son abonnement.

Voir à ce propos [cette section](../../channels/using/setting-up-a-double-opt-in-process.md).
