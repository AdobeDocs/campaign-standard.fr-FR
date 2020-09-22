---
title: Comprendre la gestion des quarantaines
description: Découvrez comment optimiser la délivrabilité avec la gestion des quarantaines.
page-status-flag: never-activated
uuid: 3c287865-1ada-4351-b205-51807ff9f7ed
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: de3a50b6-ea8f-4521-996b-c49cc1f3c946
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b1fb4a0dc0f7881e24e10f8ac171feab2ac8cba
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Comprendre la gestion des quarantaines{#understanding-quarantine-management}

## À propos des quarantaines {#about-quarantines}

Une adresse email ou un numéro de téléphone peut être mis en quarantaine, par exemple, lorsque la boîte de messagerie est pleine ou si l’adresse n’existe pas.

Dans tous les cas, la mise en quarantaine répond à des règles précises qui sont décrites dans cette [section](#conditions-for-sending-an-address-to-quarantine).

### Optimiser votre diffusion par le biais des mises en quarantaine   {#optimizing-your-delivery-through-quarantines}

Les profils dont l’adresse email ou le numéro de téléphone est en quarantaine sont exclus automatiquement lors de la préparation des messages (voir [Identifier les adresses en quarantaine pour une diffusion](#identifying-quarantined-addresses-for-a-delivery)). Le taux d’erreur ayant une incidence importante sur la vitesse de diffusion, les envois sont ainsi accélérés.

Certains fournisseurs d&#39;accès Internet considèrent automatiquement les emails comme du spam si le taux d&#39;adresses invalides est trop élevé. La quarantaine vous permet donc d&#39;éviter d&#39;être ajouté à la liste bloquée par ces fournisseurs.

De plus, elles réduisent les coûts d’envoi des SMS en excluant les numéros de téléphone erronés des diffusions.

Pour plus d’informations sur les bonnes pratiques en matière de sécurisation et d’optimisation de vos diffusions, consultez [cette page](https://docs.campaign.adobe.com/doc/standard/getting_started/fr/ACS_DeliveryBestPractices.html).

### Quarantaine / Liste bloquée {#quarantine-vs-denylist}

La **mise en quarantaine** concerne uniquement une adresse, pas le profil lui-même. Cela signifie que si deux profils utilisent la même adresse email, en cas de mise en quarantaine de l’adresse, les deux profils seront impactés.

De même, un profil, dont l’adresse email est en quarantaine qui met à jour son profil et enregistre une nouvelle adresse pourra de nouveau être ciblé par des actions de diffusions.

Being on the **Denylist**, on the other hand, will result in the profile no longer being targeted by any delivery, for example after an unsubscription (opt-out). For more on the denylist process, refer to [About opt-in and opt-out in Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Lorsqu&#39;un utilisateur répond à un message SMS avec un mot-clé tel que &quot;STOP&quot; afin de s&#39;exclure des diffusions SMS, son profil n&#39;est pas en liste bloquée comme dans le processus d&#39;exclusion par courriel. The profile phone number is sent to quarantine with the **[!UICONTROL On denylist]** status. Cet état se rapporte uniquement au numéro de téléphone, le profil n’est pas en liste bloquée, de sorte que l’utilisateur continue à recevoir des messages électroniques. Voir à ce propos [cette section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifier les adresses en quarantaine   {#identifying-quarantined-addresses}

Les adresses en quarantaine peuvent être répertoriées pour une diffusion spécifique ou l’ensemble de la plateforme.

>[!NOTE]
>
>Si vous souhaitez sortir une adresse de quarantaine, contactez votre administrateur technique.

### Identifier les adresses en quarantaine pour une diffusion   {#identifying-quarantined-addresses-for-a-delivery}

Les adresses en quarantaine pour une diffusion spécifique sont répertoriées pendant la phase de préparation de la diffusion, dans l’onglet **[!UICONTROL Exclus]** du tableau de bord des diffusions (voir [cette section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Pour plus d’informations sur la préparation des diffusions, consultez [cette section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifier les adresses en quarantaine pour l’ensemble de la plateforme   {#identifying-quarantined-addresses-for-the-entire-platform}

Les administrateurs peuvent répertorier les adresses en quarantaine pour l’ensemble de la plateforme depuis le menu **[!UICONTROL Administration > Canaux > Quarantaines > Adresses]**.

>[!NOTE]
>
>Ce menu répertorie les éléments en quarantaine pour les canaux **email**, **SMS** et **notification push**.

![](assets/quarantines1.png)

>[!NOTE]
>
>L’augmentation du nombre de quarantaines est un phénomène normal, lié à &quot;l’usure&quot; de la base de données. Par exemple, si l’on considère que la durée de vie d’une adresse email est de trois ans et que la table des destinataires augmente de 50 % tous les ans, l’augmentation des quarantaines peut être calculée comme suit : Fin de l’année 1 : (1*0,33)/(1+0,5)=22 %. Fin de l’année 2 : ((1,22*0,33)+0,33)/(1,5+0,75)=32,5 %.

## Conditions de mise en quarantaine d’une adresse   {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign gère les quarantaines selon le type de diffusion en échec et la raison affectée pendant la qualification des messages d’erreur (voir [Types de diffusion en échec et raisons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) et [Qualification des emails bounce](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Erreur de type Ignoré** : les erreurs de type Ignoré ne mettent pas une adresse en quarantaine.
* **Erreur de type Hard** : l’adresse email correspondante est mise immédiatement en quarantaine.
* **Erreur de type Soft** : les erreurs de type Soft ne provoquent pas de mise en quarantaine immédiate mais incrémentent un compteur d’erreurs. Quand le compteur d’erreurs atteint le seuil limite, l’adresse est mise en quarantaine. Dans les paramétrages par défaut, le seuil est de cinq erreurs : deux erreurs sont significatives si elles sont séparées d’au moins 24 h. L’adresse est mise en quarantaine à la cinquième erreur. Le seuil du compteur d’erreurs peut être modifié. Voir à ce propos [cette page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Lorsqu’une diffusion aboutit après une nouvelle tentative, le compteur d’erreurs de l’adresse précédemment en quarantaine est réinitialisé. Le statut de l’adresse passe en **[!UICONTROL Valide]** et est supprimé de la liste des quarantaines après deux jours grâce au workflow **[!UICONTROL Nettoyage de la base]**.

Si un utilisateur qualifie un email comme du spam (**système de gestion des plaintes (feedback loop)**), le message est automatiquement redirigé vers une boîte email technique gérée par Campaign. The user&#39;s email address is then automatically sent to quarantine with the **[!UICONTROL On denylist]** status. Cet état se rapporte uniquement à l’adresse, le profil n’est pas sur la liste bloquée, de sorte que l’utilisateur continue à recevoir des messages SMS et des notifications Push.

>[!NOTE]
La quarantaine dans Adobe Campaign respecte la casse. Veillez à importer les adresses email en minuscules, de telle sorte qu’elles ne soient pas reciblées ultérieurement.

Dans la liste des adresses mises en quarantaine (voir [Identifier les adresses mises en quarantaine pour l’ensemble de la plateforme](#identifying-quarantined-addresses-for-the-entire-platform)), le champ **[!UICONTROL Raison de l’erreur]** indique pourquoi l’adresse sélectionnée a été mise en quarantaine.

![](assets/quarantines2.png)

