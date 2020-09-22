---
title: Tracking et surveillance des messages
seo-title: Tracking et surveillance des messages
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 469d2a8b3f8026087929583affd2c294e2a954bb
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 68%

---


# Tracker et suivre vos diffusions {#track-and-monitor}

Vous avez cliqué sur le bouton Envoyer ? Voyons maintenant ce qui se passe. Une fois la diffusion envoyée, Adobe Campaign vous permet de conserver une trace des messages envoyés et de découvrir la réaction des destinataires face à votre diffusion. Vous pourrez ainsi améliorer les prochains envois et optimiser vos campagnes suivantes.

## Surveillance des diffusions {#monitoring-deliveries}

Pour contrôler vos campagnes, vous devez vérifier que le message a bien été délivré à vos destinataires.

**Conseils**

* Vous pouvez également contrôler le statut des messages dans les logs de diffusion.

* Pour suivre les performances des diffusions, Adobe Campaign propose un système d&#39;alerte par email qui envoie des notifications afin d&#39;avertir les utilisateurs des activités système importantes.

* Depuis le tableau de bord d&#39;un message, vous pouvez accéder à plusieurs rapports relatifs à ce message spécifique.

Voir à ce propos la section [Suivre une diffusion](../../sending/using/monitoring-a-delivery.md).

## Tracking {#tracking-deliveries}

Pour mieux connaître le comportement de vos profils ciblés, vous pouvez suivre leur réaction à une diffusion : réception, ouverture, clics sur des liens, désinscriptions, etc. Reportez-vous à l&#39;onglet **Logs de tracking** de la diffusion.

**Conseil** : Le tracking des messages est activé par défaut. Pour paramétrer les URL, sélectionnez l&#39;option Afficher les URL, située dans la section inférieure de l’assistant de diffusion. Pour chaque URL du message, vous pouvez choisir d&#39;activer ou non le tracking.

For more on this, refer to the [Tracking messages](../../sending/using/tracking-messages.md) section and the [Tracking indicators](../../reporting/using/tracking-indicators.md) description.

## Rapports dynamiques {#dyn-reports}

Les rapports dynamiques vous permettent de créer des rapports en temps réel entièrement personnalisables afin de contrôler vos campagnes. Les dimensions, les mesures et les visualisations vous permettent de mesurer l’impact et les performances de vos campagnes sur leurs destinataires.

**Conseil** - Des rapports intégrés vous permettent de surveiller vos campagnes, mais vous pouvez également personnaliser ces rapports en les faisant glisser et en les déposant sur votre rapport.

Voir à ce propos le guide [Reporting](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

Le rapport Clics rapides présente le contenu du message (HTML et/ou texte) avec le pourcentage de clics sur chaque lien. En affichant le pourcentage de clics sur chaque contenu dynamique, vous pouvez mesurer le contenu qui attire le plus les destinataires.

For more on this, refer to the [Hot click report](../../reporting/using/hot-clicks.md).

## Conseils sur les performances des diffusions {#performance-tips}

* Ne gardez pas les diffusions en échec sur l&#39;instance, car cela conserve les tables temporaires et a un impact sur les performances.

* Supprimez les diffusions qui ne sont plus nécessaires et les destinataires inactifs de la base pour conserver la qualité des adresses.

* N&#39;essayez pas de planifier des diffusions volumineuses ensemble. 5 à 10 minutes sont nécessaires pour répartir la charge uniformément sur le système.

**Rubriques connexes :**

* [Recevoir des alertes en cas d&#39;échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapports](../../reporting/using/about-dynamic-reports.md)
