---
title: Prise en main de l’intégration de Microsoft Dynamics 365
description: Découvrez comment commencer à utiliser l’intégration de Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 21135f27fd1d8297edd3dd067446d09c39de9f4f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 100%

---


# Prise en main de l’intégration de Microsoft Dynamics 365

>[!IMPORTANT]
>
>Cette intégration est actuellement indisponible. Un nouveau connecteur est en cours de développement et sera disponible ultérieurement. Pour plus d’informations, veuillez contacter votre représentant commercial Adobe.

Activez vos données CRM lors d’une communication cross-canal : découvrez comment transférer des contacts de Microsoft Dynamics 365 à Adobe Campaign et partager les données de performances de la campagne (envois, ouvertures, clics et bounces) d’Adobe Campaign vers Microsoft Dynamics 365.

>[!NOTE]
>
>L&#39;intégration Microsoft Dynamics 365 / Adobe Campaign Standard prend uniquement en charge l&#39;application **Microsoft Dynamics 365 Sales**.

## Principes

L&#39;intégration Adobe Campaign et Microsoft Dynamics 365 permet la synchronisation de toutes les données de contact disponibles dans le système CRM, rendant ainsi toutes celles appropriées disponibles pour les activités de campagne.

Inversement, comme les profils au sein d’Adobe Campaign interagissent avec les messages, ces données (p. ex. : envois, ouvertures, clics et bounces) se déplacent automatiquement vers Microsoft Dynamics 365 pour conserver les enregistrements Contact complets avec les activités de marketing.

La dernière version de l’intégration ajoute également la prise en charge des entités personnalisées, ce qui permet de synchroniser les entités personnalisées dans Dynamics 365 avec les entités personnalisées correspondantes dans Campaign.

Cette intégration est conçue pour prendre en charge trois principaux cas pratiques :

1. Synchronisation des contacts de Dynamics 365 vers Campaign afin qu’ils puissent être ciblés dans les campagnes marketing
1. Envoi d’événements de marketing par e-mail (envois, ouvertures, clics, bounces) de Campaign vers Dynamics 365 pour s’afficher dans le référentiel de ventes dans l’interface de Dynamics 365
1. Synchronisation des entités personnalisées de Dynamics 365 vers Campaign afin qu’elles puissent être utilisées pour la segmentation et la personnalisation

## Principaux avantages

* Messagerie cohérente entre les ventes et le marketing

L&#39;intégration d’Adobe Campaign et de Microsoft Dynamics 365 donne aux deux systèmes un accès à l’insight du client et à l’historique marketing e-mail, ce qui permet à tous les messages adressés au client de partager le même message cohérent.

*  Affichage holistique de toutes les données client et prospect

En intégrant Adobe Campaign à Dynamics 365, il est possible de partager et d&#39;accéder à l’historique marketing email de chaque contact depuis le système CRM.

* Activation des données Dynamics 365 sur n’importe quel canal

Les données de contact étant synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris des notifications Push mobiles, In-App, des e-mails ou du mailing direct. Quel que soit le canal préféré de chaque contact, Campaign s’occupe de tout.

>[!CAUTION]
>
>Pour la synchronisation des contacts, cette intégration considère Dynamics 365 comme la source de vérité.  Toute modification des attributs de contact synchronisés doit être effectuée dans Dynamics 365, et non dans Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées lors de la synchronisation.
