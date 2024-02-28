---
title: Optimisation de la diffusion des messages
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Découvrez comment sécuriser et optimiser le processus d’envoi en amont.
feature: Deliverability
role: User
level: Intermediate
exl-id: 28b0cf6d-c1f1-4d55-b9bc-0d6bfb063471
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: ht
source-wordcount: '727'
ht-degree: 100%

---

# Optimisation de votre diffusion {#optimize-delivery}

Avant même de commencer à créer des diffusions, vous pouvez prendre des mesures pour sécuriser et optimiser le processus d&#39;envoi en amont.

La section suivante présente les bonnes pratiques et les procédures recommandées pour optimiser la configuration d&#39;Adobe Campaign. L&#39;application de ces pratiques permettra de limiter les problèmes que vous risquez de rencontrer en aval.

## Performances de la plateforme

Plusieurs facteurs peuvent avoir une incidence directe sur les performances du serveur et ralentir la plateforme :

* Nombre et type d’éléments de personnalisation : dans les emails, la personnalisation extrait les données de la base de données pour chaque destinataire. Si les éléments de personnalisation sont nombreux, la quantité de données nécessaire pour préparer la diffusion augmente.  En savoir plus sur la personnalisation des emails dans [cette section](../../designing/using/personalization.md)

* Charge du serveur : lorsque Campaign gère simultanément trop de tâches différentes en même temps, cela peut ralentir les performances. Le serveur doit coordonner toutes les données entrantes et sortantes pour l’ensemble des diffusions afin de s’assurer que les données sont correctes et disponibles à temps.

  **CONSEIL** : pour éviter cette situation, coordonnez la planification des diffusions avec les autres membres de votre équipe afin d’assurer les meilleures performances.

* [Exécution du workflow](../../automating/using/about-workflow-execution.md) : la surveillance de vos workflows est essentielle pour éviter tout problème de performances de la plateforme. Suivez les directives répertoriées [dans cette page](../../automating/using/monitoring-workflow-execution.md). Pour en savoir plus, consultez la section [bonnes pratiques relatives aux workflows](../../automating/using/best-practices-workflows.md).

* Vous pouvez tirer parti des [fonctionnalités du Panneau de contrôle de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/discover-control-panel/key-features.html?lang=fr) pour surveiller votre plateforme à l&#39;aide des fonctionnalités de [surveillance des performances](https://experienceleague.adobe.com/docs/control-panel/using/performance-monitoring/about-performance-monitoring.html?lang=fr).

## Vérifier la configuration du réseau {#network-config}

Pour optimiser une diffusion lors d&#39;un envoi en masse et éviter d&#39;être pris pour un spammeur, vérifiez que vous disposez d&#39;une configuration réseau correcte qui ne cherche pas à cacher des informations.

**Conseil** : utilisez une adresse d’expéditeur transparente qui correspond au site web de votre marque. Par exemple, la société TravelAgency gère la chaîne d&#39;hôtels Valentino. Elle possède le domaine valentino.com pour son site web. Pour promouvoir l’hôtel Valentino à Paris, elle utilise le sous-domaine paris.valentino.com. Une adresse d’expéditeur pertinente peut donc être hotel@paris.valentino.com.

## Gestion de la délivrabilité {#deliverability-management}

Pour que vos messages arrivent dans la boîte de réception de vos destinataires sans rebond et sans être marqués comme spam, vous devez en améliorer la délivrabilité.

* Qu’est-ce que la délivrabilité ?

   * La délivrabilité désigne les facteurs qui déterminent la capacité d’un email à être accepté par le serveur d’un destinataire. Les fournisseurs d’accès à Internet (FAI) filtrent les emails qu’ils identifient comme spam ou bloquent le téléchargement des images. S’ils déterminent qu’un domaine donné envoie un trop grand nombre d’emails, ils fixent une limite au nombre d’emails qu’ils acceptent de cet expéditeur.

   * Lorsque vous vérifiez la délivrabilité de votre email, vous devez vous concentrer sur quatre catégories principales : qualité des données, message et contenu, infrastructure d’envoi et réputation. Pour une étude plus approfondie de ce sujet, consultez [cette section](../../sending/using/about-deliverability.md).

* Lors du démarrage d’une nouvelle plateforme, appliquez les recommandations présentées sur [cette page](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/switching-email-platforms.html?lang=fr#transition-process).

* Contactez votre représentant Adobe pour obtenir de l&#39;aide.

## Gestion des quarantaines {#quarantine-management}

Vous avez tout intérêt à mettre en place et à conserver de bons processus de gestion des quarantaines.

Lorsque vous commencez à envoyer des emails sur une nouvelle plateforme, vous pouvez utiliser une liste d’adresses qui ne sont pas entièrement qualifiées. Or l’envoi à des adresses non valides ou à des adresses pièges (boîtes mails créées dans le but de piéger les spammeurs) contribue à abaisser la réputation de la plateforme. De bons processus de gestion des quarantaines permettent de conserver la qualité des adresses, d&#39;éviter la mise sur liste bloquée de la part des FAI et de réduire le taux d&#39;erreur, tout en augmentant la vitesse des diffusions et le débit.

**Conseils**

* Les destinataires dont l’adresse est en quarantaine sont par défaut exclus lors de l’analyse d’une diffusion : ils ne seront pas ciblés. Le taux d’erreur ayant une incidence importante sur la vitesse de diffusion, les envois sont ainsi accélérés. Une adresse email peut être mise en quarantaine par exemple lorsque la boîte de messagerie est pleine ou si l’adresse n’existe pas. [En savoir plus](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses)

* Le mode de gestion des adresses en erreur par Adobe Campaign dépend du type d’erreur retourné. Pour plus d’informations, consultez [cette section](../../sending/using/understanding-quarantine-management.md).

* Certains fournisseurs d&#39;accès Internet considèrent automatiquement les emails comme du spam si le taux d&#39;adresses invalides est trop élevé. La quarantaine permet donc d&#39;éviter d&#39;être ajouté à une liste bloquée par ces fournisseurs.

* La gestion des quarantaines réduit également les coûts d’envoi des SMS en excluant les numéros de téléphone erronés des diffusions.

## Mécanisme de double opt-in {#double-opt-in}

Pour éviter d&#39;envoyer des messages à des adresses invalides, limiter les communications abusives et améliorer la réputation de l&#39;expéditeur, Adobe recommande de mettre en place un mécanisme de double opt-in pour une confirmation après inscription. Cela vous permet de vous assurer que le destinataire est bien à l&#39;origine de l&#39;abonnement.

Les détails de la mise en œuvre de ce mécanisme sont décrits dans [cette section](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Pour en savoir plus, consultez [Prise en main des profils et des audiences](../../audiences/using/get-started-profiles-and-audiences.md).
