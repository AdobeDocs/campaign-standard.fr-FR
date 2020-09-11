---
title: Demande et configuration de l'intégration Microsoft Dynamics 365
description: Découvrez comment demander et configurer l’intégration de Microsoft Dynamics 365 avec Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0ce73bf7e250c5e88bbb525854e81ef27662ab06
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 35%

---


# Demande et configuration de l&#39;intégration Microsoft Dynamics 365

Pour configurer cette intégration, vous devez suivre les étapes ci-dessous.

Veuillez suivre l’organigramme et ses détails ci-dessous pour demander et configurer l’intégration.

![](assets/provisioning-wf.png)

Détails de l’organigramme (mise en correspondance avec les étapes ci-dessus) :

* **Étape 1** - Il est supposé que vous disposez déjà, ou êtes en train d&#39;acheter, d&#39;une licence pour Microsoft Dynamics 365 pour Sales et pour Adobe Campaign Standard.

* **Étape 2** - L&#39;offre d&#39;intégration standard est gratuite pour tous les clients ; toutefois, des coûts supplémentaires peuvent s’appliquer en fonction de vos besoins (voir Gardiens et limites [d’](../../integrating/using/ms-dynamics-365-integration-guardrails.md)intégration). Une nouvelle commande client devra être signée pour tirer parti de l&#39;intégration.

* **Étape 3** - Suivez les étapes de préintégration pour Dynamics 365 et Campaign. Voir [Configuration de cette intégration](#configure-this-integration).

* **Étapes 4-7** - L&#39;équipe d&#39;intégration d&#39;Adobes travaillera avec vous tout au long du processus d&#39;intégration.

## Configurer cette intégration {#configure-this-integration}

Trois systèmes doivent être configurés et configurés pour cette intégration : adobe campaign standard, Microsoft Dynamics 365 for Sales et l&#39;outil d&#39;intégration. Les liens vers les articles de configuration se trouvent ci-dessous.

>[!CAUTION]
>
>Pour chaque système, ces étapes doivent être exécutées par un administrateur.
>
>Les étapes des articles ci-dessous vous guideront tout au long de la création d’intégrations/inscriptions impliquant l’attribution de permissions et/ou d’accès administrateur.  Vous êtes tenu de vous assurer que ces étapes sont conformes aux politiques de votre entreprise avant de les exécuter, et de les exécuter avec précaution.

En ADOBE CAMPAIGN, vous devez configurer l’accès à l’API et configurer une nouvelle intégration pour l’outil d’intégration. Pour ce faire, reportez-vous à [cet article](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

Dans Microsoft Dynamics 365, vous devez créer une nouvelle inscription d’application et permettre à un utilisateur d’utiliser l’intégration.  Pour configurer Microsoft Dynamics 365 pour cette intégration, reportez-vous à [cet article](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Vous devez travailler avec l’équipe d’intégration d’Adobes pour configurer la configuration des flux de données d’entrée, d’entrée et d’exclusion.


## Demande de support

Les tickets d&#39;assistance peuvent être enregistrés avec l&#39;assistance personnalisée Adobe, comme d&#39;habitude ; Le service à la clientèle fera appel au personnel d’assistance, si nécessaire.

Pour tout problème lié aux flux de données d’intégration, veillez à inclure la suite de rapports dans la description du problème ainsi que les informations suivantes :

* **Propriétaire** du processus : Architectes d&#39;ingénierie

* **ID** de processus ES : Fourni pendant le processus d&#39;intégration

* **Titre** du processus : Intégration Dynamics 365 / Adobe Campaign Standard

* **Description** de la publication : Description du problème

La couverture du support d&#39;intégration est actuellement de 24h/24 et 5j/7 (disponible du lundi au vendredi, à l&#39;exclusion des jours fériés et des périodes de pause).