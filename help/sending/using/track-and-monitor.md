---
solution: Campaign Standard
product: campaign
title: Tracking et surveillance des messages
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: ht
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: ht
source-wordcount: '410'
ht-degree: 100%

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

Pour mieux connaître le comportement de vos profils ciblés, vous pouvez suivre leur réaction à une diffusion : réception, ouverture, clics sur des liens, désabonnements, etc. Reportez-vous à l&#39;onglet **Logs de tracking** de la diffusion.

**Conseil** : Le tracking des messages est activé par défaut. Pour paramétrer les URL, sélectionnez l&#39;option Afficher les URL, située dans la section inférieure de l’assistant de diffusion. Pour chaque URL du message, vous pouvez choisir d&#39;activer ou non le tracking.

Pour plus d&#39;informations, reportez-vous à la section [Messages de tracking](../../sending/using/tracking-messages.md) et à la description des [Indicateurs de tracking](../../reporting/using/tracking-indicators.md).

## Rapports dynamiques {#dyn-reports}

Les rapports dynamiques vous permettent de créer des rapports en temps réel entièrement personnalisables afin de contrôler vos campagnes. Les dimensions, les mesures et les visualisations vous permettent de mesurer l’impact et les performances de vos campagnes sur leurs destinataires.

**Conseil** : les rapports natifs sont disponibles pour contrôler vos campagnes, mais vous pouvez également les personnaliser en plaçant des mesures ou des dimensions dans votre rapport par glisser-déposer.

Voir à ce propos le guide [Reporting](../../reporting/using/about-dynamic-reports.md).

## Hot clicks

Le rapport Hot clicks présente le contenu du message (HTML et/ou texte) avec, sur chaque lien, le pourcentage de clics sur ce lien. En affichant le pourcentage de clics sur chaque contenu dynamique, vous pouvez identifier les contenus les plus attrayants pour les destinataires.

Pour plus d&#39;informations à ce sujet, consultez la section [Rapport Hot clicks](../../reporting/using/hot-clicks.md).

## Conseils sur les performances des diffusions {#performance-tips}

* Ne gardez pas les diffusions en échec sur l&#39;instance, car cela conserve les tables temporaires et a un impact sur les performances.

* Supprimez les diffusions qui ne sont plus nécessaires et les destinataires inactifs de la base pour conserver la qualité des adresses.

* N&#39;essayez pas de planifier des diffusions volumineuses ensemble. 5 à 10 minutes sont nécessaires pour répartir la charge uniformément sur le système.

**Rubriques connexes :**

* [Recevoir des alertes en cas d&#39;échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapports](../../reporting/using/about-dynamic-reports.md)
