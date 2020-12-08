---
solution: Campaign Standard
product: campaign
title: Tracker les messages
description: Découvrez comment tracker le comportement des destinataires de vos diffusions.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
translation-type: tm+mt
source-git-commit: 79e172d08557bfeebd088d8a0e8756c5965318cb
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 98%

---


# Tracker les messages{#tracking-messages}

## A propos du tracking {#about-tracking}

Grâce à ses fonctionnalités de tracking, Adobe Campaign permet de tracker le comportement des destinataires de vos diffusions. Pour cela, Adobe Campaign utilise des cookies de session et des cookies permanents.

Ainsi, vous pouvez informer les utilisateurs de vos sites soumis au tracking web via une zone de demande de consentement (par exemple en surimpression de la page) proposant une case à cocher pour autoriser l&#39;utilisation de cookies, ou afficher une bannière en haut de la première page visitée, etc. Les fenêtres de type pop-up sont à éviter car elles sont souvent bloquées par les navigateurs.

Les informations de tracking sont disponibles pour chaque contact de votre base de données dans des **[!UICONTROL profils client intégrés]**. Voir à ce propos [cette section](../../audiences/using/integrated-customer-profile.md).

Adobe Campaign utilise deux types de cookies :

* Un cookie de session (nlid). Il contient l’identifiant de l’email envoyé au contact (broadlogId) et l’identifiant du modèle de message (deliveryId). Il est déposé lorsque le contact clique sur une URL contenue dans un email envoyé par Adobe Campaign et permet de tracker son comportement sur le web. Ce cookie de session est effacé automatiquement à la fermeture du navigateur. Le contact a la possibilité d&#39;en interdire le dépôt en adaptant les paramètres de son navigateur.
* Un cookie partagé entre les solutions Adobe Experience Cloud. Il permet d’identifier un internaute qui interagit avec les solutions Experience Cloud lors de ses visites sur un site web. La description de ce cookie est disponible [ici](https://docs.adobe.com/content/help/fr-FR/core-services/interface/ec-cookies/cookies-mc.html).

Le tracking avec Adobe Campaign Standard vous permet d’accéder aux fonctionnalités suivantes :

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
<td>Tracking email</td>
<td>Tracking Push</td>
<td>Tracked URLs</td>
<td>Logs de tracking</td>
<td>Rapport de tracking</td>
</tr>
</table>

## Logs de tracking   {#tracking-logs}

L&#39;onglet **[!UICONTROL Tracking]** liste l&#39;historique du tracking pour cette diffusion. Cet onglet affiche les informations de tracking sur les messages envoyés, soit toutes les URL qui ont fait l&#39;objet d&#39;un tracking par Adobe Campaign. Les informations de tracking de cet onglet sont mises à jour toutes les 10 minutes.

>[!NOTE]
>
>Si le tracking n&#39;est pas activé pour une diffusion, cet onglet n&#39;est pas affiché. Le tracking est uniquement disponible pour les canaux **email** et **notification push**.

![](assets/tracking_logs.png)

Dans l&#39;exemple ci-dessus, le destinataire :

* a ouvert le message.
* Cliquez sur le lien de la page miroir.
* a cliqué sur le lien personnalisé « EN SAVOIR PLUS ».

Dans la colonne **[!UICONTROL Type]**, les valeurs possibles sont :

* **[!UICONTROL Clic email]** : le destinataire a cliqué sur un lien personnalisé.
* **[!UICONTROL Page miroir]** : le destinataire a cliqué sur un lien vers la page miroir.
* **[!UICONTROL Ouverture]** : le destinataire a ouvert l&#39;email.
* **[!UICONTROL Désabonnement]** : le destinataire a cliqué sur un lien de désabonnement.

>[!NOTE]
>
>En ce qui concerne le canal **notification push**, seuls les clics des notifications mobiles sont trackés. Dans ce cas, la valeur sera **[!UICONTROL Clic sur notification mobile]**.

Pour plus d&#39;informations sur l&#39;insertion de liens de tracking, consultez [cette page](../../designing/using/links.md#inserting-a-link).

Le rapport **[!UICONTROL Indicateurs de tracking]** contient les indicateurs clés de tracking du comportement une fois les emails reçus. Pour plus d’informations à ce propos, consultez cette [page](../../reporting/using/tracking-indicators.md).

## URL trackées {#tracked-urls}

L&#39;onglet **[!UICONTROL URL trackées]** regroupe les URL contenues dans le message envoyé, leur type et leur URL source.

![](assets/sending_delivery6.png)

Pour plus d&#39;informations sur les liens de tracking, consultez [cette section](../../designing/using/links.md#about-tracked-urls).
