---
title: Tracker les messages
description: Découvrez comment tracker le comportement des destinataires de vos diffusions.
page-status-flag: never-activated
uuid: c3721647-0663-4614-a9c9-3b3a40af328a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 6fa50f0d-3dcf-4a9e-bccc-1ecda2bfb449
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b8c3569fc3965f463a06ae8375a623553037e248

---


# Tracker les messages{#tracking-messages}

## A propos du tracking {#about-tracking}

Grâce à ses fonctionnalités de tracking, Adobe Campaign permet de tracker le comportement des destinataires de vos diffusions. Pour cela, Adobe Campaign utilise des cookies de session et des cookies permanents.

Ainsi, vous pouvez informer les utilisateurs de vos sites soumis au tracking web via une zone de demande de consentement (par exemple en surimpression de la page) proposant une case à cocher pour autoriser l&#39;utilisation de cookies, ou afficher une bannière en haut de la première page visitée, etc. Les fenêtres de type pop-up sont à éviter car elles sont souvent bloquées par les navigateurs.

Tracking information are available for each contact of your database into **[!UICONTROL integrated customer profiles]**. Voir à ce propos [cette section](../../audiences/using/integrated-customer-profile.md).

Adobe Campaign utilise deux types de cookies :

* Un cookie de session (nlid). Il contient l&#39;identifiant de l&#39;email envoyé au contact (broadlogId) et l&#39;identifiant du modèle de message (deliveryId). Il est déposé lorsque le contact clique sur une URL contenue dans un email envoyé par Adobe Campaign et permet de tracker son comportement sur le web. Ce cookie de session est effacé automatiquement à la fermeture du navigateur. Le contact a la possibilité d&#39;en interdire le dépôt en adaptant les paramètres de son navigateur.
* Un cookie partagé entre les solutions Adobe Experience Cloud. Il permet d&#39;identifier un internaute qui interagit avec les solutions Experience Cloud lors de ses visites sur un site web. La description de ce cookie est disponible [ici](https://marketing.adobe.com/resources/help/fr_FR/whitepapers/cookies/cookies_mc.html).

Le suivi avec  Adobe Campaign Standard vous permet d’accéder aux fonctionnalités suivantes :

<table>
<tr>
    <td valign="top">
        <a href="../../administration/using/configuring-email-channel.md#tracking-parameters"><img width="60px" alt="conditions" src="assets/icon_email_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="https://helpx.adobe.com/fr/campaign/kb/push-tracking.html"><img width="60px" alt="conditions" src="assets/icon_push_parameters.png"/></a>
    </td>
    <td valign="top">
        <a href="../../designing/using/links.md#about-tracked-urls"><img width="60px" alt="conditions" src="assets/icon_url.png"/></a>
    </td>
        <td valign="top">
          <a href="../../sending/using/tracking-messages.md#tracking-logs"><img width="60px" alt="conditions" src="assets/icon_log.png"/></a>
    </td>
    </td>
    <td valign="top">
          <a href="../../reporting/using/tracking-indicators.md"><img width="60px" alt="conditions" src="assets/icon_report.png"/></a>
</tr>
<tr>
<td>Email tracking</td>
<td>Suivi Push</td>
<td>Tracked URLs</td>
<td>Tracking logs</td>
<td>Rapport de suivi</td>
</tr>
</table>

## Tracking  {#tracking-logs}

The **[!UICONTROL Tracking logs]** tab lists the tracking history for this delivery. Cet onglet affiche les informations de tracking sur les messages envoyés, soit toutes les URL qui ont fait l&#39;objet d&#39;un tracking par Adobe Campaign. Les informations de tracking de cet onglet sont mises à jour toutes les 10 minutes.

>[!NOTE]
>
>Si le tracking n&#39;est pas activé pour une diffusion, cet onglet n&#39;est pas affiché. Le tracking est uniquement disponible pour les canaux **email** et **notification push**.

![](assets/tracking_logs.png)

Dans l&#39;exemple ci-dessus, le destinataire :

* a ouvert le message.
* a cliqué sur le lien personnalisé « EN SAVOIR PLUS ».
* a cliqué sur le lien de désinscription et sur celui de la page miroir.

Dans la colonne **[!UICONTROL Type]**, les valeurs possibles sont :

* **[!UICONTROL Email click]**: les ont cliqué sur un lien personnalisé.
* **[!UICONTROL Mirror page]**: le a cliqué sur un lien vers le.
* **[!UICONTROL Open]**: le a ouvert le courrier électronique.
* **[!UICONTROL Opt-out]**: le a cliqué sur un lien .

>[!NOTE]
>
>En ce qui concerne le canal **notification push**, seuls les clics des notifications mobiles sont trackés. Dans ce cas, la valeur sera **[!UICONTROL Click on mobile notification]**.

Pour plus d&#39;informations sur l&#39;insertion de liens de tracking, consultez [cette page](../../designing/using/links.md#inserting-a-link).

## URL trackées {#tracked-urls}

The **[!UICONTROL Tracked URLs]** tab regroups the URLs contained in the sent message, including their URL type and their source URL.

![](assets/sending_delivery6.png)

Pour plus d&#39;informations sur les liens de tracking, consultez [cette section](../../designing/using/links.md#about-tracked-urls).
