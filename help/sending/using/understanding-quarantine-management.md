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
source-git-commit: f7e361d10d039718c421a3684c518347af2be951

---


# Comprendre la gestion des quarantaines{#understanding-quarantine-management}

## A propos des quarantaines {#about-quarantines}

Une adresse email ou un numéro de téléphone peut être mis en quarantaine, par exemple, lorsque la boîte de messagerie est pleine ou si l&#39;adresse n&#39;existe pas.

Dans tous les cas, la mise en quarantaine répond à des règles précises qui sont décrites dans cette [section](#conditions-for-sending-an-address-to-quarantine).

### Optimiser votre diffusion par le biais des mises en quarantaine {#optimizing-your-delivery-through-quarantines}

Les profils dont l&#39;adresse email ou le numéro de téléphone est en quarantaine sont exclus automatiquement lors de la préparation des messages (voir [Identifier les adresses en quarantaine pour une diffusion](#identifying-quarantined-addresses-for-a-delivery)). Le taux d&#39;erreur ayant une incidence importante sur la vitesse de diffusion, les envois sont ainsi accélérés.

Certains fournisseurs d&#39;accès Internet considèrent automatiquement les emails comme du spam si le taux d&#39;adresses invalides est trop élevé. Les mises en quarantaine permettent donc d&#39;éviter des blacklistages de la part de ces fournisseurs.

De plus, elles réduisent les coûts d&#39;envoi des SMS en excluant les numéros de téléphone erronés des diffusions.

Pour plus d&#39;informations sur les bonnes pratiques en matière de sécurisation et d&#39;optimisation de vos diffusions, consultez [cette page](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).

### Mise en quarantaine et blacklistage {#quarantine-vs-blacklisting}

La **mise en quarantaine** concerne uniquement une adresse, pas le profil lui-même. Cela signifie que si deux profils utilisent la même adresse email, en cas de mise en quarantaine de l&#39;adresse, les deux profils seront impactés.

De même, un profil, dont l&#39;adresse email est en quarantaine qui met à jour son profil et enregistre une nouvelle adresse pourra de nouveau être ciblé par des actions de diffusions.

En revanche, en cas de **blacklistage**, c&#39;est le profil qui ne sera plus ciblé par aucune diffusion, par exemple après une désinscription (opt-out). Pour plus d&#39;informations sur le blacklistage, consultez la section [Gestion du blacklistage dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

>[!NOTE]
>
>Lorsqu&#39;un utilisateur répond à un SMS avec un mot-clé tel que &quot;STOP&quot; pour se désinscrire des diffusions SMS, son profil n&#39;est pas blacklisté comme c&#39;est le cas pour la désinscription des emails. The profile phone number is sent to quarantine with the **[!UICONTROL Blacklisted]** status. Ce statut se rapporte uniquement au numéro de téléphone. Le profil n&#39;est pas blacklisté afin que l&#39;utilisateur puisse continuer à recevoir des emails. Voir à ce propos [cette section](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

## Identifier les adresses en quarantaine {#identifying-quarantined-addresses}

Les adresses en quarantaine peuvent être répertoriées pour une diffusion spécifique ou l&#39;ensemble de la plateforme.

>[!NOTE]
>
>Si vous souhaitez sortir une adresse de quarantaine, contactez votre administrateur technique.

### Identifier les adresses en quarantaine pour une diffusion {#identifying-quarantined-addresses-for-a-delivery}

Quarantined addresses for a specific delivery are listed during the delivery preparation phase, in the **[!UICONTROL Exclusion logs]** tab of the delivery dashboard (see [this section](../../sending/using/monitoring-a-delivery.md#exclusion-logs)). Pour plus d&#39;informations sur la préparation des diffusions, consultez [cette section](../../sending/using/preparing-the-send.md).

![](assets/exclusion_logs.png)

### Identifier les adresses en quarantaine pour l&#39;ensemble de la plateforme {#identifying-quarantined-addresses-for-the-entire-platform}

Administrators can list the addresses in quarantine for the entire platform from the **[!UICONTROL Administration > Channels > Quarantines > Addresses]** menu.

>[!NOTE]
>
>Ce menu répertorie les éléments en quarantaine pour les canaux **email**, **SMS** et **notification push**.

![](assets/quarantines1.png)

>[!NOTE]
>
>L&#39;augmentation du nombre de quarantaines est un phénomène normal, lié à &quot;l&#39;usure&quot; de la base de données. Par exemple, si l&#39;on considère que la durée de vie d&#39;une adresse email est de trois ans et que la table des destinataires augmente de 50 % tous les ans, l&#39;augmentation des quarantaines peut être calculée comme suit : Fin de l&#39;année 1 : (1*0,33)/(1+0,5)=22 %. Fin de l&#39;année 2 : ((1,22*0,33)+0,33)/(1,5+0,75)=32,5 %.

## Conditions de mise en quarantaine d&#39;une adresse {#conditions-for-sending-an-address-to-quarantine}

Adobe Campaign gère les quarantaines selon le type de diffusion en échec et la raison affectée pendant la qualification des messages d&#39;erreur (voir [Types de diffusion en échec et raisons](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) et [Qualification des emails bounce](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)).

* **Erreur de type Ignoré** : les erreurs de type Ignoré ne mettent pas une adresse en quarantaine.
* **Erreur de type Hard** : l&#39;adresse email correspondante est mise immédiatement en quarantaine.
* **Erreur** douce : les erreurs douces n’envoient pas immédiatement une adresse à l’, mais elles incrémentent un compteur d’erreurs. Lorsque le compteur d’erreurs atteint le seuil limite, l’adresse est placée dans le  du. Dans la configuration par défaut, le seuil est défini sur cinq erreurs, où deux erreurs sont importantes si elles se produisent au moins à 24 heures d’intervalle. L&#39;adresse est placée en  à la cinquième erreur. Le seuil du compteur d&#39;erreurs peut être modifié. Voir à ce propos [cette page](../../administration/using/configuring-email-channel.md#email-channel-parameters).

   Lorsqu&#39;une diffusion aboutit après une nouvelle tentative, le compteur d&#39;erreurs de l&#39;adresse précédemment en quarantaine est réinitialisé. The address status changes to **[!UICONTROL Valid]** and it is deleted from the list of quarantines after two days by the **[!UICONTROL Database cleanup]** workflow.

Si un utilisateur qualifie un email comme du spam (**système de gestion des plaintes (feedback loop)**), le message est automatiquement redirigé vers une boîte email technique gérée par Campaign. The user&#39;s email address is then automatically sent to quarantine with the **[!UICONTROL Blacklisted]** status. Ce statut ne concerne que l&#39;adresse. Le profil n&#39;est pas blacklisté afin que l&#39;utilisateur puisse continuer à recevoir des SMS et des notification push.

>[!NOTE]
La quarantaine dans Adobe Campaign respecte la casse. Veillez à importer les adresses email en minuscules, de telle sorte qu&#39;elles ne soient pas reciblées ultérieurement.

In the list of quarantined addresses (see [Identifying quarantined addresses for the entire platform](#identifying-quarantined-addresses-for-the-entire-platform)), the **[!UICONTROL Error reason]** field indicates why the selected address was placed in quarantine.

![](assets/quarantines2.png)

