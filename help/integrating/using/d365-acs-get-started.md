---
title: Prise en main de l’intégration de Microsoft Dynamics 365
description: Découvrez comment commencer à utiliser l’intégration de Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '854'
ht-degree: 100%

---


# Prise en main de l’intégration de Microsoft Dynamics 365

Activez vos données CRM lors d’une communication cross-canal : découvrez comment transférer des contacts de Microsoft Dynamics 365 à Adobe Campaign et partager les données de performances de la campagne (envois, ouvertures, clics et bounces) d’Adobe Campaign vers Microsoft Dynamics 365.

Cette intégration requiert les versions de logiciels suivantes :

* Microsoft Dynamics 365 pour Sales Online uniquement, dernière version

* Adobe Campaign Standard, dernière version

>[!CAUTION]
>
>Cette fonctionnalité ne fait pas partie des paramètres d’usine du produit. La mise en œuvre nécessite l’implication d’Adobe Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.


## Principes

L’intégration Adobe Campaign Standard et Microsoft Dynamics 365 permet la synchronisation de toutes les données de contact disponibles dans le système CRM, rendant ainsi toutes celles appropriées disponibles pour les activités de campagne.

Inversement, comme les profils au sein d’Adobe Campaign Standard interagissent avec les messages, ces données (p. ex. : envois, ouvertures, clics et bounces) se déplacent automatiquement vers Microsoft Dynamics 365 pour conserver les enregistrements Contact complets avec les activités de marketing.

L’intégration prend également en charge les [entités personnalisées](../../integrating/using/d365-acs-self-service-app-settings.md) dans Dynamics 365 pour qu&#39;elles soient synchronisées avec les **ressources personnalisées** correspondantes dans Campaign.

Cette intégration est conçue pour prendre en charge quatre principaux cas pratiques :

1. Synchronisation des contacts de Dynamics 365 vers Campaign afin qu’ils puissent être ciblés dans les campagnes marketing
1. Synchronisation des entités personnalisées de Dynamics 365 vers Campaign afin qu’elles puissent être utilisées pour la segmentation et la personnalisation
1. Envoi d’événements de marketing par email (envois, ouvertures, clics, bounces) de Campaign vers Dynamics 365 pour s’afficher dans le référentiel de ventes dans l’interface de Dynamics 365
1. Synchronisation des statuts de désinscription (par exemple, ne pas envoyer d’email) entre Dynamics 365 et Campaign afin de conserver les préférences de confidentialité des clients.

Les principaux avantages sont les suivants :

* Messages cohérents entre les ventes et le marketing : l’intégration Adobe Campaign Standard et Microsoft Dynamics 365 donne aux deux systèmes un accès aux informations du client et à l’historique marketing email, ce qui permet à tous les messages adressés au client de partager le même message cohérent.

* Affichage holistique de toutes les données de prospect et de clients : en intégrant Adobe Campaign Standard à Dynamics 365, il est possible de partager et d&#39;accéder à l&#39;historique marketing par email de chaque contact depuis le système CRM.

* Activation des données Dynamics 365 sur n&#39;importe quel canal : les données de contact étant synchronisées avec Adobe Campaign, les communications peuvent être envoyées sur n’importe quel canal en ligne ou hors ligne avec Campaign, y compris des notifications push mobiles, In-App, des emails ou du mailing direct. Campaign « vous couvre » quel que soit le canal préféré de chaque contact.

>[!CAUTION]
>
>Cette intégration considère Dynamics 365 comme la source de vérité pour la synchronisation des contacts et des entités personnalisées.  Toute modification des attributs synchronisés doit être effectuée dans Dynamics 365, et non dans Adobe Campaign Standard.  Si des modifications sont effectuées dans Campaign, elles peuvent être éventuellement écrasées lors de la synchronisation.


## Étapes clés de la mise en œuvre de l&#39;intégration Microsoft Dynamics 365{#request-and-implement-this-integration}

Pour configurer cette intégration, vous devez suivre les étapes ci-dessous.

Veuillez suivre l’organigramme et ses détails ci-dessous pour demander et configurer l’intégration.

![](assets/provisioning-wf.png)

Détails de l’organigramme (mise en correspondance avec les étapes ci-dessus) :

* **Étape 1** - Il est supposé que vous disposez déjà, ou êtes en cours d’achat, d’une licence pour Microsoft Dynamics 365 for Sales et pour Adobe Campaign Standard.
* **Étape 2** - L’offre d’intégration standard est gratuite pour tous les clients, toutefois, des coûts supplémentaires peuvent s’appliquer en fonction de vos besoins. En savoir plus sur [les bonnes pratiques et limitations](../../integrating/using/d365-acs-notices-and-recommendations.md). Une nouvelle commande client (SO) devra être signée afin de tirer parti de l&#39;intégration si elle n&#39;était pas incluse dans la commande client originale.
* **Étape 3** - Exécuter les étapes préalables à l’intégration pour Dynamics 365 et Campaign. Voir [Configurer cette intégration](#configure-this-integration).
* **Étape 4** - L’équipe d’intégration d’Adobe vous donnera accès à l’interface utilisateur (IU) de l’application d’intégration.
* **Étape 5** - Vous pourrez configurer vos mappings de données, vos remplacements, vos filtres, etc. et tester votre intégration depuis l’interface utilisateur de l’application d’intégration.

   >[!IMPORTANT]
   >
   > Si vous avez besoin de la configuration de désinscription bidirectionnelle ou de Campaign vers Dynamics 365, vous devrez adresser la demande à votre contact technique Adobe pour que les workflows de désinscription soient configurés sur votre instance Campaign. [En savoir plus](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configurer cette intégration {#configure-this-integration}

Trois systèmes doivent être approvisionnés et configurés pour cette intégration :

* **Dans Adobe Campaign Standard** : vous devez configurer l’accès à l’API et configurer une nouvelle intégration pour l’outil d’intégration. Pour ce faire, reportez-vous à [cet article](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Dans Microsoft 365** : vous devez créer une nouvelle inscription d’application et permettre à un utilisateur d’utiliser l’intégration.  Pour configurer Microsoft Dynamics 365 pour cette intégration, reportez-vous à [cet article](../../integrating/using/d365-acs-configure-d365.md).
* **Application en libre-service d&#39;intégration Adobe Campaign Standard et Microsoft Dynamics 365** : vous devrez suivre les étapes de [cet article](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Pour chaque système, ces étapes doivent être exécutées par un **administrateur**.
>
>Les étapes de cette documentation vous guideront tout au long de la création d’intégrations/inscriptions impliquant l’attribution de permissions et/ou d’accès administrateur.  Vous êtes tenu de vous assurer que ces étapes sont conformes aux politiques de votre entreprise avant de les exécuter, et de les exécuter avec précaution.


### Demande d’assistance

Les demandes d’assistance peuvent être effectuées auprès de l&#39;Assistance clientèle d&#39;Adobe.

Pour tout problème lié aux flux de données d’intégration, veillez à inclure la suite de rapports dans la description du problème ainsi que les informations suivantes :

* **Propriétaire du processus** : architectes d’ingénierie
* **Identifiant du processus ES** : fourni pendant le processus d’intégration
* **Titre du processus** : intégration Microsoft Dynamics 365 / Adobe Campaign Standard
* **Description du problème** : description du problème

La couverture d’assistance pour l’intégration est actuellement de 24h/24, 5j/7 (disponible du lundi au vendredi, à l’exception des jours fériés et des temps de pause).
