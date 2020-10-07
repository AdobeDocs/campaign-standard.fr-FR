---
title: Optimiser la diffusion des messages
seo-title: Optimiser la diffusion des messages
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 84%

---


# Optimiser votre diffusion {#optimize-delivery}

Avant même de commencer à créer des diffusions, vous pouvez prendre des mesures pour sécuriser et optimiser le processus d&#39;envoi en amont.

La section suivante présente les bonnes pratiques et les procédures recommandées pour optimiser la configuration d&#39;Adobe Campaign. L&#39;application de ces pratiques permettra de limiter les problèmes que vous risquez de rencontrer en aval.

## Performances de la plate-forme

Plusieurs facteurs peuvent avoir une incidence directe sur les performances du serveur et ralentir la plate-forme :

* Nombre et type d’éléments de personnalisation : dans les emails, la personnalisation extrait les données de la base de données pour chaque destinataire. Si les éléments de personnalisation sont nombreux, la quantité de données nécessaire pour préparer la diffusion augmente.  Learn more about email personalization in [this section](../../designing/using/personalization.md)

* Chargement du serveur : lorsque Campaign gère plusieurs tâches différentes en même temps, il peut ralentir les performances. Le serveur doit coordonner toutes les données entrantes et sortantes pour l’ensemble des diffusions afin de s’assurer que les données sont correctes et disponibles à temps.

   **CONSEIL** : pour éviter cette situation, coordonnez la planification des diffusions avec les autres membres de votre équipe afin d’assurer les meilleures performances.

* The [workflow execution](../../automating/using/about-workflow-execution.md): monitoring your workflows is essential to avoid platform performance issues. Follow the guidelines listed [in this page](../../automating/using/monitoring-workflow-execution.md). Pour en savoir plus, consultez la section Meilleures pratiques [du](../../automating/using/best-practices-workflows.md) flux de travail.

* You can leverage [Campaign Contol Panel capabilities](https://docs.adobe.com/content/help/fr-FR/control-panel/using/discover-control-panel/key-features.html) to monitor your platform, using [performance monitoring](https://docs.adobe.com/content/help/fr-FR/control-panel/using/performance-monitoring/about-performance-monitoring.html) functionalities.

## Vérifier la configuration du réseau {#network-config}

Pour optimiser une diffusion lors d&#39;un envoi en masse et éviter d&#39;être pris pour un spammeur, vérifiez que vous disposez d&#39;une configuration réseau correcte qui ne cherche pas à cacher des informations.

**Conseil** : utilisez une adresse d’expéditeur transparente qui correspond au site web de votre marque. Par exemple, la société TravelAgency gère la chaîne d&#39;hôtels Valentino. Elle possède le domaine valentino.com pour son site web. Pour promouvoir l’hôtel Valentino à Paris, elle utilise le sous-domaine paris.valentino.com. Une adresse d’expéditeur pertinente peut donc être hotel@paris.valentino.com.

## Gestion de la délivrabilité {#deliverability-management}

Pour que vos messages arrivent dans la boîte de réception de vos destinataires sans rebond et sans être marqués comme spam, vous devez en améliorer la délivrabilité.

* Qu’est-ce que la délivrabilité ?

   * La délivrabilité désigne les facteurs qui déterminent la capacité d’un email à être accepté par le serveur d’un destinataire. Les fournisseurs d’accès à Internet (FAI) filtrent les emails qu’ils identifient comme spam ou bloquent le téléchargement des images. S’ils déterminent qu’un domaine donné envoie un trop grand nombre d’emails, ils fixent une limite au nombre d’emails qu’ils acceptent de cet expéditeur.

   * Lorsque vous vérifiez la délivrabilité de votre email, vous devez vous concentrer sur quatre catégories principales : qualité des données, message et contenu, infrastructure d’envoi et réputation. Pour une étude plus approfondie de ce sujet, consultez [cette section](../../sending/using/about-deliverability.md).

* Lors du démarrage d’une nouvelle plateforme, appliquez les recommandations détaillées [dans cette page](../../sending/using/starting-new-platform.md).

* Contactez votre représentant Adobe pour obtenir de l&#39;aide.

## Gestion des quarantaines {#quarantine-management}

Vous avez tout intérêt à mettre en place et à conserver de bons processus de gestion des quarantaines.

Lorsque vous commencez à envoyer des emails sur une nouvelle plate-forme, vous pouvez utiliser une liste d’adresses qui ne sont pas entièrement qualifiées. Or l’envoi à des adresses non valides ou à des adresses pièges (boîtes mails créées dans le but de piéger les spammeurs) contribue à abaisser la réputation de la plate-forme. De bons processus de gestion des quarantaines aident à : maintenez la qualité de l&#39;adresse, évitez la liste bloquée des fournisseurs d&#39;accès internet et réduisez votre taux d&#39;erreur, accélérant les diffusions et le débit.

**Conseils**

* Les destinataires dont l’adresse est en quarantaine sont par défaut exclus lors de l’analyse d’une diffusion : ils ne seront pas ciblés. Le taux d’erreur ayant une incidence importante sur la vitesse de diffusion, les envois sont ainsi accélérés. Une adresse email peut être mise en quarantaine par exemple lorsque la boîte de messagerie est pleine ou si l’adresse n’existe pas. [En savoir plus](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Le mode de gestion des adresses en erreur par Adobe Campaign dépend du type d’erreur retourné. Voir à ce propos [cette section](../../sending/using/understanding-quarantine-management.md).

* Certains fournisseurs d’accès Internet considèrent automatiquement les emails comme du spam si le taux d’adresses invalides est trop élevé. La quarantaine permet donc d’éviter d’être ajouté à une liste bloquée par ces fournisseurs.

* La gestion des quarantaines réduit également les coûts d’envoi des SMS en excluant les numéros de téléphone erronés des diffusions.

## Mécanisme de double opt-in {#double-opt-in}

Pour éviter d&#39;envoyer des messages à des adresses invalides, limiter les communications abusives et améliorer la réputation de l&#39;expéditeur, Adobe recommande de mettre en place un mécanisme de double opt-in pour une confirmation après inscription. Cela vous permet de vous assurer que le destinataire est bien à l&#39;origine de l&#39;abonnement.

Les détails de la mise en œuvre de ce mécanisme sont décrits dans [cette section](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Pour en savoir plus, consultez [Prise en main des profils et des audiences](../../audiences/using/get-started-profiles-and-audiences.md).
