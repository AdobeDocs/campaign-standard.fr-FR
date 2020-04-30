---
title: Prise en main de l'intégration de Microsoft Dynamics 365
description: Découvrez comment commencer avec l'intégration de Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# Prise en main de l&#39;intégration de Microsoft Dynamics 365

Activez vos données de gestion de la relation client lors de la communication entre canaux : découvrez comment transmettre des contacts de Microsoft Dynamics 365 à Adobe Campaign et partager des données de performances de campagne (envoie, ouvre, clics et rebonds) de Adobe Campaign vers Microsoft Dynamics 365.

>[!NOTE]
>
>L&#39;intégration Microsoft Dynamics 365 / Adobe Campaign Standard ne prend en charge que l&#39;application **commerciale** Microsoft Dynamics 365.

## Avantages et cas d&#39;utilisation

### Principes

L&#39;intégration Adobe Campaign et Microsoft Dynamics 365 permet la synchronisation de toutes les données de contact disponibles dans le système de gestion de la relation client, rendant toutes les données de contact pertinentes disponibles pour les activités de campagne.

Inversement, lorsque les profils de Adobe Campaign interagissent avec des messages, ces données (p. ex. : envoie, ouvre, clics et rebonds) s&#39;enchaînent automatiquement dans Microsoft Dynamics 365 afin de conserver les enregistrements Contact complets avec l&#39;activité marketing.

La dernière version de l&#39;intégration ajoute également la prise en charge des entités personnalisées, ce qui permet de synchroniser les entités personnalisées dans Dynamics 365 avec les entités personnalisées correspondantes dans Campaign.

Cette intégration est conçue pour prendre en charge trois principaux cas d’utilisation :

1. Synchronisation des contacts de Dynamics 365 vers Campaign afin qu&#39;ils puissent être ciblés dans les campagnes marketing
1. Envoi de événements de marketing par courriel (envoie, ouvre, clics, rebonds) de Campaign à Dynamics 365 pour s&#39;afficher dans le référentiel de ventes dans l&#39;interface Dynamics 365
1. Synchronisation d&#39;entités personnalisées entre Dynamics 365 et Campaign afin qu&#39;elles puissent être utilisées pour la segmentation et la personnalisation

Regardez la vidéo de la fonctionnalité d&#39;intégration de Dynamics 365-Campaign Standard [ici](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html).

### Avantages clés

* Messagerie cohérente entre les ventes et le marketing

L&#39;intégration Adobe Campaign et Microsoft Dynamics 365 permet aux deux systèmes d&#39;accéder aux informations client et à l&#39;historique marketing électronique permettant à tous les messages envoyés au client de partager le même message cohérent.

* vue holistique de toutes les données de prospect et de client

En intégrant Adobe Campaign à Dynamics 365, il est possible de partager et d&#39;accéder à l&#39;historique marketing de courriel de chaque Contact depuis le système de gestion de la relation client.

* Activer les données Dynamics 365 sur n&#39;importe quel canal

Les données de contact étant synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris les notifications Push mobiles, in-app, e-mail ou publipostage direct. Quel que soit le canal préféré de chacun des Contacts, Campaign a couvert votre demande.

>[!CAUTION]
>
>Pour la synchronisation des contacts, cette intégration considère Dynamics 365 comme la source de vérité.  Toute modification des attributs de contact synchronisés doit être effectuée dans Dynamics 365, et non dans Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent éventuellement être remplacées lors de la synchronisation.
