---
title: Utilisation de Campaign Standard et de Microsoft Dynamics 365
description: Découvrez comment travailler avec Campaign Standard et Microsoft Dynamics 365
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
source-git-commit: 03009c47a66aa1a62c05f632e2a60141a98639d8

---


# Utilisation de Campaign Standard et de Microsoft Dynamics 365

Activez vos données de gestion de la relation client lors d’une communication entre  : découvrez comment transmettre des contacts de Microsoft Dynamics 365 à Adobe Campaign et partager les données de performances de la campagne (envoie, ouvre, clique et rebondit) de l&#39; à Microsoft Dynamics 365.

>[!NOTE]
>
>L&#39;intégration de Microsoft Dynamics 365 /  Adobe Campaign Standard prend uniquement en charge l&#39;application **commerciale** Microsoft Dynamics 365.

## Avantages et cas d&#39;utilisation

### Principes

L&#39;intégration de  Adobe Campaign et de Microsoft Dynamics 365 permet la synchronisation de toutes les données de contact disponibles dans le système CRM, rendant toutes les données de contact pertinentes disponibles pour les  de campagne.

Inversement, comme les  au sein de  Adobe Campaign interagissent avec les messages, ces données (p. ex. : envoie, ouvre, clique et rebonds) automatiquement dans Microsoft Dynamics 365 pour conserver les enregistrements Contact complets avec les  de  marketing.

La dernière version de l’intégration ajoute également la prise en charge des entités personnalisées, ce qui permet de synchroniser les entités personnalisées dans Dynamics 365 avec les entités personnalisées correspondantes dans Campaign.

Cette intégration est conçue pour prendre en charge trois principaux cas d’utilisation :

1. Synchronisation des contacts de Dynamics 365 vers Campaign afin qu’ils puissent être ciblés dans les campagnes marketing
1. Envoi de  marketing par courrier électronique (envoie, ouvre, clics, rebonds) de Campaign à Dynamics 365 pour s’afficher dans le référentiel de ventes dans l’interface de Dynamics 365
1. Synchronisation des entités personnalisées de Dynamics 365 vers Campaign afin qu’elles puissent être utilisées pour la segmentation et la personnalisation

Regardez la vidéo de la fonctionnalité d&#39;intégration de Dynamics 365-Campaign Standard [ici](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html).

### Avantages clés

* Messagerie cohérente entre les ventes et le marketing

L&#39;intégration de  Adobe Campaign et de Microsoft Dynamics 365 donne aux deux systèmes un accès à la connaissance du client et au d&#39; de messagerie électronique, ce qui permet à tous les messages adressés au client de partager le même message cohérent.

*  holistique de toutes les données de l&#39;et des clients

En intégrant  Adobe Campaign à Dynamics 365, il est possible de partager et d&#39;accéder aux de  de messagerie sur chaque Contact depuis le système CRM.

* Activation des données Dynamics 365 sur n’importe quel 

Les données de contact étant synchronisées avec  Adobe Campaign, les communications peuvent être envoyées sur n’importe quel en ligne ou hors ligne avec des tels que les notifications Push mobiles, In-App, Courrier électronique ou Courrier direct. Quel que soit le  préféré de chaque contact, Campaign vous a couvert.

>[!CAUTION]
>
>Pour la synchronisation des contacts, cette intégration considère Dynamics 365 comme la source de vérité.  Toute modification des attributs de contact synchronisés doit être effectuée dans Dynamics 365, et non dans Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement remplacées lors de la synchronisation.
