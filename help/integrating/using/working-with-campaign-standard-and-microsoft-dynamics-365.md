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
source-git-commit: 3590fd42e4692df6bba21ac721568ae60dfcdd65
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 46%

---


# Prise en main de l’intégration de Microsoft Dynamics 365

Activez vos données CRM lors d’une communication cross-canal : découvrez comment transférer des contacts de Microsoft Dynamics 365 à Adobe Campaign et partager les données de performances de la campagne (envois, ouvertures, clics et bounces) d’Adobe Campaign vers Microsoft Dynamics 365.

Les versions prises en charge sont répertoriées [dans cette section](#support-software-versions).

>[!CAUTION]
>
>Cette fonctionnalité n&#39;est pas disponible en standard dans le cadre du produit. La mise en oeuvre nécessite l’engagement de Adobes Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.

## Principes

L&#39;intégration Adobe Campaign et Microsoft Dynamics 365 permet la synchronisation de toutes les données de contact disponibles dans le système de gestion de la relation client, rendant toutes les données de contact pertinentes disponibles pour les activités de campagne.

Inversement, lorsque les profils de Adobe Campaign interagissent avec des messages, ces données (p. ex. : envoie, ouvre, clics et rebonds) automatiquement dans Microsoft Dynamics 365 pour conserver les enregistrements de contact complets avec l&#39;activité marketing.

L&#39;intégration prend également en charge les entités personnalisées, ce qui permet aux entités [](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) personnalisées dans Dynamics 365 d&#39;être synchronisées avec les entités personnalisées correspondantes dans Campaign.

Cette intégration est conçue pour prendre en charge quatre principaux cas d’utilisation :

1. Synchronisation des contacts de Dynamics 365 vers Campaign afin qu&#39;ils puissent être ciblés dans les campagnes marketing
1. Synchronisation des entités personnalisées de Dynamics 365 vers Campaign afin qu’elles puissent être utilisées pour la segmentation et la personnalisation
1. Envoi d’événements de marketing par e-mail (envois, ouvertures, clics, bounces) de Campaign vers Dynamics 365 pour s’afficher dans le référentiel de ventes dans l’interface de Dynamics 365
1. Synchronisation des états d&#39;exclusion (par exemple, ne pas envoyer de courrier électronique) entre Dynamics 365 et ACS afin de conserver les préférences de confidentialité des clients.

## Principaux avantages

* Messagerie cohérente entre les ventes et le marketing

L&#39;intégration d’Adobe Campaign et de Microsoft Dynamics 365 donne aux deux systèmes un accès à l’insight du client et à l’historique marketing e-mail, ce qui permet à tous les messages adressés au client de partager le même message cohérent.

*  Affichage holistique de toutes les données client et prospect

En intégrant Adobe Campaign à Dynamics 365, il est possible de partager et d&#39;accéder à l&#39;historique marketing de courriel de chaque contact depuis le système de gestion de la relation client.

* Activation des données Dynamics 365 sur n’importe quel canal

Les données de contact étant synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris des notifications Push mobiles, In-App, des e-mails ou du mailing direct. Quel que soit le canal préféré de chacun des contacts, Campaign vous a couvert.

>[!CAUTION]
>
>Pour la synchronisation des contacts et des entités personnalisées, cette intégration considère Dynamics 365 comme la source de vérité.  Toute modification des attributs de synchronisés doit être effectuée dans Dynamics 365, et non dans Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées lors de la synchronisation.

## Prise en charge des versions des logiciels {#support-software-versions}

Cette intégration requiert les versions logicielles suivantes :

* Microsoft Dynamics 365 pour Sales Online uniquement, dernière version

* adobe campaign standard, dernière version
