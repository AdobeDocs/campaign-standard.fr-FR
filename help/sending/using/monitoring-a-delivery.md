---
title: Contrôler une diffusion
seo-title: Contrôler une diffusion
description: Contrôler une diffusion
seo-description: Découvrez comment contrôler une diffusion.
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
translation-type: ht
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Contrôler une diffusion{#monitoring-a-delivery}

Plusieurs méthodes permettent de contrôler une diffusion et de mesurer son impact :

* **Logs des messages** : ces logs sont accessibles depuis le tableau de bord des messages. Ils indiquent le détail de l'envoi, la cible exclue et les raisons de l'exclusion et fournissent des informations de tracking telles que les ouvertures et les clics.

   Pour visualiser les logs des messages, cliquez sur l'icône située en bas à droite du bloc **[!UICONTROL Déploiement]**.

   Plusieurs onglets contiennent les informations (si elles existent) relatives aux **[!UICONTROL Envois]**, aux **[!UICONTROL Exclus]**, aux **[!UICONTROL Causes d'exclusion]**, aux **[!UICONTROL Logs de tracking]** et **[!UICONTROL URL trackées]**. Voir [Logs de diffusion](../../sending/using/monitoring-a-delivery.md#delivery-logs).

   ![](assets/sending_delivery1.png)

   Le journal contient tous les messages relatifs à la diffusion et aux bons à tirer (BAT). Des icônes spécifiques permettent de repérer les erreurs ou avertissements. Voir à ce propos la section [Valider les messages](../../sending/using/previewing-messages.md).

   Vous pouvez exporter le journal en cliquant sur le bouton **[!UICONTROL Exporter la liste]**.

   ![](assets/sending_delivery2.png)

* **Alertes de diffusion** : pour tracker les performances des diffusions, Adobe Campaign propose un système d'alerte par email qui envoie des notifications afin d'avertir les utilisateurs des activités système importantes.
* **Rapports** : depuis le tableau de bord d'un message, vous pouvez accéder à plusieurs rapports relatifs à ce message spécifique. Un menu **[!UICONTROL Rapports]** vous permet également d'accéder à la liste complète des rapports intégrés ou personnalisés que vous pouvez utiliser pour mettre en avant des mesures spécifiques relatives à votre message ou campagne.
* Un administrateur peut également exporter des logs dans un fichier distinct qui peut être traité dans vos outils de reporting ou de Business Intelligence. Voir à ce propos la section [Exporter des logs](../../automating/using/exporting-logs.md).

**Rubriques connexes :**

* [Recevoir des alertes en cas d'échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapports](../../reporting/using/about-dynamic-reports.md)

## Logs de diffusion  {#delivery-logs}

### Envois {#sending-logs}

L'onglet **[!UICONTROL Envois]** propose un historique des occurrences de cette diffusion. Y est répertoriée la liste des messages envoyés et leur statut. Il permet de visualiser l'état de la diffusion pour chaque destinataire.

Pour chaque profil dont l'état est **[!UICONTROL Envoyé]**, la colonne **[!UICONTROL Date]** indique quand le message a été envoyé.

![](assets/sending_delivery3.png)

### Exclus {#exclusion-logs}

L'onglet **[!UICONTROL Exclus]** liste tous les messages qui ont été exclus de l'envoi à la cible et indique la raison de l'échec de l'envoi.

![](assets/sending_delivery4.png)

### Exclusions appliquées {#exclusion-causes}

L'onglet **[!UICONTROL Exclusions appliquées]** indique le volume (en nombre de messages) des messages qui ont été exclus de l'envoi à la cible.

![](assets/sending_delivery5.png)

