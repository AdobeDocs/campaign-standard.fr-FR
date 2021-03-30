---
solution: Campaign Standard
product: campaign
title: À propos de la délivrabilité dans Adobe Campaign Standard
description: Découvrez les concepts et bonnes pratiques liés à la délivrabilité, ainsi que les outils proposés par Adobe Campaign Standard pour optimiser l'envoi de vos diffusions.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Délivrabilité
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: fb9a6218bb754f803affde1fdf6c6fc01570126f
workflow-type: tm+mt
source-wordcount: '749'
ht-degree: 19%

---


# Qu&#39;est-ce que la délivrabilité{#about-deliverability}

La délivrabilité permet de mesurer le succès des campagnes atteignant la boîte de réception de vos destinataires sans bounces ou sans être marqués comme spam. [Découvrez pourquoi la délivrabilité est importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html#why-deliverability-matters).

Plus précisément, la délivrabilité des e-mails se rapporte à l&#39;ensemble des caractéristiques qui déterminent la capacité d&#39;un message à atteindre sa destination, par l&#39;intermédiaire d&#39;une adresse e-mail personnelle, dans un laps de temps court, et avec la qualité attendue en termes de contenu et de format. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Pour en savoir plus sur ce qu&#39;est la délivrabilité et pour en savoir plus sur les termes, concepts et approches clés de la délivrabilité, consultez le [Guide des meilleures pratiques en matière de délivrabilité des Adobes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr-FR).

## Comment améliorer la délivrabilité {#deliverability-key-points}

Les problèmes de délivrabilité sont généralement liés aux mesures de protection contre le spam mises en oeuvre par les prestataires Internet et les administrateurs de serveurs de messagerie.

* Pour obtenir des recommandations générales sur la manière de concevoir des campagnes de marketing par courriel réussies, consultez la [Stratégie et définition de la délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html).

* Pour des recommandations plus spécifiques sur la façon d&#39;optimiser la délivrabilité de vos courriels Adobe Campaign, nous vous recommandons d&#39;utiliser les meilleures pratiques répertoriées dans cette section.

>[!NOTE]
>
>Les FAI étant obligés de développer continuellement de nouvelles techniques de filtrage sophistiquées pour protéger leurs clients contre les spammeurs, la délivrabilité des courriels se caractérise par des critères et des règles en constante évolution. Consultez le [Guide des meilleures pratiques en matière de délivrabilité des Adobes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html) régulièrement mis à jour.

### Taux de délivrabilité

Le taux de délivrabilité est le nombre de messages qui ont atteint les boîtes de réception des destinataires par rapport au nombre de messages qui ont été remis. Pour améliorer la délivrabilité, vous pouvez augmenter ce taux.

Avec Adobe Campaign, le taux de délivrabilité dépend de nombreux facteurs, notamment :

* Configuration correcte de vos instances : contactez votre représentant d&#39;Adobe pour obtenir de l&#39;aide.
* Configuration réseau légitime : voir [cette section](../../sending/using/optimize-delivery.md#network-config) et [Configuration et stratégie du domaine](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#domain-setup-and-strategy).
* Votre réputation d&#39;adresse IP : voir [Stratégie IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#ip-strategy).
* Qualité des adresses ciblées : voir [Gestion des Quarantaines](../../sending/using/optimize-delivery.md#quarantine-management).
* Faibles taux de [plaintes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html) et de [rebond](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html#hard-bounces).
* Contenu de votre message : voir [Contrôle du contenu du courrier électronique](../../sending/using/control-email-content.md).
* Authentification des messages (SPF, DKIM, DMARC) : voir [cette section](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html#authentication).
* Connaissance de l&#39;expéditeur : pour savoir comment les principaux FAI évaluent la réputation d&#39;un expéditeur, voir [cette section](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html).

## Outils de délivrabilité de Campaign {#deliverability-tools}

Adobe Campaign fournit un certain nombre d’outils permettant de suivre et d’améliorer les performances de délivrabilité de votre plate-forme. Cette page met également en évidence les principaux principes que vous devez garder à l&#39;esprit pour optimiser la délivrabilité lors de l&#39;utilisation de Campaign.

### Créez soigneusement votre message

Lors de la configuration, de la conception et du test de votre message, veillez à respecter les meilleures pratiques mentionnées dans les sections ci-dessous. L&#39;exploitation de toutes les fonctionnalités fournies par Adobe Campaign vous aidera à améliorer la délivrabilité.

* [Bonnes pratiques relatives à la diffusion](../../sending/using/delivery-best-practices.md)
* [Contrôle du contenu des emails](../../sending/using/control-email-content.md)
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Envoyer un bon à tirer](../../sending/using/sending-proofs.md)

### Vérifier le consentement au moyen de l&#39;inclusion de doublon {#double-opt-in}

Pour éviter d&#39;envoyer des messages à des adresses incorrectes, limiter les communications incorrectes et améliorer la réputation de l&#39;expéditeur, l&#39;Adobe recommande la mise en oeuvre d&#39;un mécanisme d&#39;inclusion doublon. Cela vous permet de vous assurer que vos destinataires se sont abonnés intentionnellement.

Pour plus d’informations à ce sujet, voir [A propos de l’inclusion et de l’exclusion dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Pour plus d&#39;informations sur les meilleures pratiques lors de la collecte de données auprès de vos clients, consultez le [Guide des meilleures pratiques en matière de délivrabilité des Adobes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html#data-quality-and-hygiene).

### Exploitation de la gestion des quarantaines

Adobe Campaign gère une liste qui recueille les plaintes contre le spam, les rebonds durs et les rebonds doux qui se produisent de manière cohérente.

Pour protéger votre délivrabilité, les destinataires dont les adresses se trouvent sur cette liste sont exclus par défaut de toutes les diffusions futures, car envoyer à ces contacts pourrait nuire à votre réputation d&#39;envoi.

Certains fournisseurs d&#39;accès Internet considèrent automatiquement les emails comme du spam si le taux d&#39;adresses invalides est trop élevé. La quarantaine permet donc d&#39;éviter d&#39;être ajouté à une liste bloquée par ces fournisseurs.

Voir à ce propos les sections suivantes :

* [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Quarantaine et liste bloquée](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Utilisation des outils de surveillance et de rapports

Utilisez les fonctionnalités offertes par Adobe Campaign pour surveiller votre délivrabilité.

Adobe Campaign vous permet de vérifier les performances de vos diffusions à l’aide d’un ensemble d’indicateurs intégrés en temps réel. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Vous pouvez également créer des rapports entièrement personnalisables et en temps réel pour mieux comprendre vos diffusions.

Voir à ce propos les sections suivantes :

* [Contrôle de la délivrabilité](../../sending/using/monitor-deliverability.md)

   <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Recevoir des alertes en cas d’échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Rapports dynamiques](../../reporting/using/about-dynamic-reports.md)

<!--## General recommendations

NOT SURE TO KEEP

Here are a few additional recommendations when it comes to deliverability.

### Send to valid addresses {#valid-addresses}

Spammers often use address generators based on lists of frequent names and first names; in addition, they rarely process technical notifications sent back by mail servers. A high rate of invalid addresses is often interpreted as a sign of spam.

Double opt-in mechanisms and effective handling of technical bounce messages make it possible to avoid this.

### Reduce complaint rate {#reduce-complaint-rate}

ISPs usually have a prominent means of reporting a received message as spam. This makes it possible to identify unreliable sources. By rapidly honoring opt-out requests, making regular use of a given list, verifying consent through a double opt-in system, and implementing feedback loops, you can reduce complaint rates.

<!--Sending to honeypot addresses {#honeypot-addresses}
ISPs and other organizations (refer to https://www.projecthoneypot.org/) make use of mailboxes that do not correspond to physical persons but are created simply to trick spammers. These so-called "honey pot" addresses are published on the Web in order to be collected by spambots and thus catch illegitimate senders. The use of a double opt-in mechanism precludes this sort of address being added to a list. When using a third-party list, you must be sure of the methods employed by its maintainer.-->

<!--## Sending on a regular basis {#regular-deliveries}

Spammers make programmed deliveries to maintain their reputation over time. They sometimes need to adapt their marketing plan to meet the best practices imposed by the ISPs and so, after a peak in reputation (ramp-up), they configure regular deliveries.-->
