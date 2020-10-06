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
translation-type: ht
source-git-commit: 3590fd42e4692df6bba21ac721568ae60dfcdd65
workflow-type: ht
source-wordcount: '431'
ht-degree: 100%

---


# Prise en main de l’intégration de Microsoft Dynamics 365

Activez vos données CRM lors d’une communication cross-canal : découvrez comment transférer des contacts de Microsoft Dynamics 365 à Adobe Campaign et partager les données de performances de la campagne (envois, ouvertures, clics et bounces) d’Adobe Campaign vers Microsoft Dynamics 365.

Les versions prises en charge sont répertoriées [dans cette section](#support-software-versions).

>[!CAUTION]
>
>Cette fonctionnalité ne fait pas partie des paramètres d’usine du produit. La mise en œuvre nécessite l’implication d’Adobe Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.

## Principes

L’intégration Adobe Campaign et Microsoft Dynamics 365 permet la synchronisation de toutes les données de contact disponibles dans le système CRM, rendant ainsi toutes celles appropriées disponibles pour les activités de campagne.

Inversement, comme les profils au sein d’Adobe Campaign interagissent avec les messages, ces données (p. ex. : envois, ouvertures, clics et bounces) se déplacent automatiquement vers Microsoft Dynamics 365 pour conserver les enregistrements Contact complets avec les activités de marketing.

L’intégration prend également en charge les entités personnalisées, ce qui permet aux [entités personnalisées](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md) de Dynamics 365 d’être synchronisées avec les entités personnalisées correspondantes dans Campaign.

Cette intégration est conçue pour prendre en charge quatre principaux cas pratiques :

1. Synchronisation des contacts de Dynamics 365 vers Campaign afin qu’ils puissent être ciblés dans les campagnes marketing
1. Synchronisation des entités personnalisées de Dynamics 365 vers Campaign afin qu’elles puissent être utilisées pour la segmentation et la personnalisation
1. Envoi d’événements de marketing par email (envois, ouvertures, clics, bounces) de Campaign vers Dynamics 365 pour s’afficher dans le référentiel de ventes dans l’interface de Dynamics 365
1. Synchronisation des statuts de désinscription (par exemple, ne pas envoyer d’email) entre Dynamics 365 et ACS afin de conserver les préférences de confidentialité des clients.

## Principaux avantages

* Messagerie cohérente entre les ventes et le marketing

L’intégration d’Adobe Campaign et de Microsoft Dynamics 365 donne aux deux systèmes un accès à l’insight du client et à l’historique marketing e-mail, ce qui permet à tous les messages adressés au client de partager le même message cohérent.

*  Affichage holistique de toutes les données client et prospect

En intégrant Adobe Campaign à Dynamics 365, il est possible de partager et d’accéder à l’historique marketing email de chaque contact depuis le système CRM.

* Activation des données Dynamics 365 sur n’importe quel canal

Les données de contact étant synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris des notifications Push mobiles, In-App, des e-mails ou du mailing direct. Quel que soit le canal préféré de chaque contact, Campaign s’occupe de tout.

>[!CAUTION]
>
>En ce qui concerne la synchronisation des contacts et des entités personnalisées, cette intégration considère Dynamics 365 comme la source de la vérité.  Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365, et non dans Campaign.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées lors de la synchronisation.

## Prise en charge des versions de logiciels {#support-software-versions}

Cette intégration requiert les versions de logiciels suivantes :

* Microsoft Dynamics 365 pour Sales Online uniquement, dernière version

* Adobe Campaign Standard, dernière version
