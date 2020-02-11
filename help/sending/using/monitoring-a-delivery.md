---
title: Surveillance d’une diffusion dans Adobe Campaign Standard
description: Découvrez comment surveiller une diffusion dans Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 7772c607-debd-40fd-8322-4d49119979b4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: monitoring-messages
discoiquuid: eb9fa216-4568-423a-9396-8f7b82181ae9
context-tags: delivery,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 54612511de07edc3e6f3eea34ef095c26b35f4af

---


# Contrôler une diffusion{#monitoring-a-delivery}

Plusieurs méthodes permettent de contrôler une diffusion et de mesurer son impact :

* **Logs des messages** : ces logs sont accessibles depuis le tableau de bord des messages. Ils indiquent le détail de l&#39;envoi, la cible exclue et les raisons de l&#39;exclusion et fournissent des informations de tracking telles que les ouvertures et les clics.

   To view the message logs, click the icon at the bottom right of the **[!UICONTROL Deployment]** block.

   Plusieurs onglets contiennent des informations (le cas échéant) concernant le **[!UICONTROL Sending logs]**, **[!UICONTROL Exclusion logs]**, **[!UICONTROL Exclusion causes]**, **[!UICONTROL Tracking logs]** et **[!UICONTROL Tracked URLs]**. Voir [Logs de diffusion](#delivery-logs).

   ![](assets/sending_delivery1.png)

   Le journal contient tous les messages relatifs à la diffusion et aux bons à tirer (BAT). Des icônes spécifiques permettent de repérer les erreurs ou avertissements. Voir à ce propos la section [Valider les messages](../../sending/using/previewing-messages.md).

   You can export the log by clicking the **[!UICONTROL Export list]** button.

   ![](assets/sending_delivery2.png)

* **Alertes de diffusion** : pour tracker les performances des diffusions, Adobe Campaign propose un système d&#39;alerte par email qui envoie des notifications afin d&#39;avertir les utilisateurs des activités système importantes.
* **Rapports** : depuis le tableau de bord d&#39;un message, vous pouvez accéder à plusieurs rapports relatifs à ce message spécifique. You also have a **[!UICONTROL Reports]** menu that allows you to access a complete list of built-in or custom reports that you can use to outline specific metrics related to your message or campaign.
* Un administrateur peut également exporter des logs dans un fichier distinct qui peut être traité dans vos outils de reporting ou de Business Intelligence. Voir à ce propos la section [Exporter des logs](../../automating/using/exporting-logs.md).

**Rubriques connexes :**

* [Recevoir des alertes en cas d&#39;échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapports](../../reporting/using/about-dynamic-reports.md)

## Logs de diffusion {#delivery-logs}

### Envois {#sending-logs}

The **[!UICONTROL Sending logs]** tab offers a history of every occurrence of this delivery. Y est répertoriée la liste des messages envoyés et leur statut. Il permet de visualiser l&#39;état de la diffusion pour chaque destinataire.

For each profile with a **[!UICONTROL Sent]** status, the **[!UICONTROL Date]** column shows when the message was sent.

![](assets/sending_delivery3.png)

Pour accéder aux détails d&#39;un journal d&#39;envoi spécifique, cliquez sur l&#39;icône représentant un crayon à droite de la ligne correspondante.

![](assets/sending_access-sending-log.png)

Tous les détails du journal d’envoi sont en lecture seule. Vous pouvez également afficher un aperçu de la page miroir.

![](assets/sending_sending-log.png)

>[!NOTE]
>
>Pour afficher le rendu de la page miroir dans l’interface utilisateur de Campaign, l’URL du serveur de pages miroir doit être sécurisée. Dans ce cas, utilisez https:// plutôt que http:// pour configurer cette URL lors de la [configuration de votre marque](../../administration/using/branding.md#configuring-and-using-brands).

### Exclus {#exclusion-logs}

The **[!UICONTROL Exclusion logs]** tab lists all the messages that have been excluded from the target sent and specifies the reason for the send failure.

![](assets/sending_delivery4.png)

### Exclusions appliquées {#exclusion-causes}

The **[!UICONTROL Exclusion causes]** tab displays the volume (in number of messages) of messages that were excluded from the target send.

![](assets/sending_delivery5.png)
