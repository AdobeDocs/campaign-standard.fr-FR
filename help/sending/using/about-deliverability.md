---
title: À propos de la délivrabilité dans Adobe Campaign Standard
description: Découvrez les concepts et bonnes pratiques liés à la délivrabilité, ainsi que les outils proposés par Adobe Campaign Standard pour optimiser l'envoi de vos diffusions.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 5e523519-7192-4031-9d96-559af23074d9
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: ht
source-wordcount: '676'
ht-degree: 100%

---

# Qu’est-ce que la délivrabilité ?{#about-deliverability}

La délivrabilité permet de mesurer le succès des campagnes atteignant la boîte de réception de vos destinataires, et ce, sans bounces et sans être marquées comme spam. [Découvrez pourquoi la délivrabilité est importante](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=fr#why-deliverability-matters).

Plus précisément, la délivrabilité des emails désigne l’ensemble des caractéristiques qui déterminent la capacité d’un message à atteindre sa destination, par l’intermédiaire d’une adresse email personnelle, dans un délai court, et avec la qualité attendue en termes de contenu et de format. <!--These characteristics fall into four main categories: data quality, message and content, sending infrastructure, and reputation. Together, they form the foundation of a successful email deliverability program.-->

Pour en apprendre davantage sur la délivrabilité et en savoir plus sur les termes, concepts et approches clés qui s’y rapportent, consultez le [Guide des bonnes pratiques relatives à la délivrabilité d’Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr).

## Procédure d&#39;amélioration de la délivrabilité {#deliverability-key-points}

En règle générale, les problèmes de délivrabilité sont liés aux mesures de protection contre le spam implémentées par les prestataires Internet et les administrateurs de serveurs de messagerie.

* Pour obtenir des recommandations générales sur la manière de concevoir des campagnes de marketing par email réussies, consultez la section [Stratégie et définition de la délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/deliverability-strategy-and-definition.html?lang=fr).

* Pour bénéficier de recommandations plus spécifiques quant à la manière d’optimiser la délivrabilité de vos emails Adobe Campaign, nous vous recommandons de suivre les bonnes pratiques répertoriées dans cette section.

>[!NOTE]
>
>Les FAI sont sans cesse obligés de développer de nouvelles techniques de filtrage sophistiquées afin de protéger leurs clients contre les spammeurs. Par conséquent, les critères et les règles qui caractérisent la délivrabilité des emails sont en constante évolution. Prenez soin de consulter le [Guide des bonnes pratiques relatives à la délivrabilité d&#39;Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr), qui est mis à jour régulièrement.

### Taux de délivrabilité

Le taux de délivrabilité correspond au nombre de messages qui ont atteint les boîtes de réception des destinataires comparé au nombre de messages délivrés. Pour améliorer la délivrabilité, vous pouvez faire en sorte d&#39;augmenter ce taux.

Avec Adobe Campaign, le taux de délivrabilité dépend de nombreux facteurs, parmi lesquels :

* Configuration correcte de vos instances : contactez votre représentant Adobe pour obtenir de l&#39;aide.
* Configuration réseau légitime : consultez [cette section](../../sending/using/optimize-delivery.md#network-config) ainsi que la section [Configuration et stratégie du domaine](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#domain-setup-and-strategy).
* Votre réputation d’adresse IP : consultez la section [Stratégie IP](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#ip-strategy).
* Qualité des adresses ciblées : consultez la section [Gestion des quarantaines](../../sending/using/optimize-delivery.md#quarantine-management).
* Le faible taux de [plaintes](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/complaints.html?lang=fr) et de [rebonds définitifs](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/metrics-for-deliverability/bounces.html?lang=fr#hard-bounces).
* Le contenu de votre message : consultez la section [Contrôle du contenu des emails](../../sending/using/control-email-content.md).
* Authentification des messages (SPF, DKIM, DMARC) : consultez [cette section](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=fr#authentication).
* Réputation de l&#39;expéditeur : pour savoir comment les principaux FAI évaluent la réputation d&#39;un expéditeur, consultez [cette section](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/internet-service-provider-specifics/overview.html?lang=fr).

## Outils de délivrabilité de Campaign {#deliverability-tools}

Adobe Campaign fournit un ensemble d’outils pour suivre et améliorer les performances de délivrabilité de votre plateforme. Cette page met également en avant les principes clés à garder en tête pour optimiser la délivrabilité lors de l’utilisation de Campaign.

### Création minutieuse de votre message

Lors de la configuration, de la conception et du test de votre message, assurez-vous de suivre les bonnes pratiques mentionnées dans les sections ci-dessous. Tirer parti de toutes les fonctionnalités d&#39;Adobe Campaign contribue à améliorer la délivrabilité.

* [Bonnes pratiques relatives à la diffusion](../../sending/using/delivery-best-practices.md)
* [Contrôle du contenu des e-mails](../../sending/using/control-email-content.md)
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Envoi d&#39;un bon à tirer](../../sending/using/sending-proofs.md)

### Vérification du consentement par le biais du double opt-in {#double-opt-in}

Pour éviter d’envoyer des messages à des adresses non valides, limiter les communications abusives et améliorer la réputation de l’expéditeur, Adobe recommande de mettre en place un mécanisme de double opt-in. Cela vous permet de vous assurer que vos destinataires se sont abonnés intentionnellement.

Pour plus d’informations à ce sujet, consultez la section [À propos des opt-in et opt-out dans Campaign](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md).

Pour plus d’informations sur les bonnes pratiques à appliquer lors de la collecte de données auprès de vos clients, consultez le [Guide des bonnes pratiques relatives à la délivrabilité d’Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/first-impressions/address-collection-and-list-growth.html?lang=fr#data-quality-and-hygiene).

### Utilisation de la gestion des quarantaines

Adobe Campaign gère une liste qui rassemble les plaintes contre le spam, les rebonds définitifs et les rebonds temporaires qui surviennent de manière systématique.

Pour protéger votre délivrabilité, les destinataires dont les adresses se trouvent sur cette liste sont exclus par défaut de toute diffusion future. En effet, un envoi à ces contacts pourrait nuire à votre réputation d&#39;envoi.

Certains fournisseurs d&#39;accès Internet considèrent automatiquement les emails comme du spam si le taux d&#39;adresses invalides est trop élevé. La quarantaine permet donc d&#39;éviter d&#39;être ajouté à une liste bloquée par ces fournisseurs.

Voir à ce propos les sections suivantes :

* [Comprendre les échecs de diffusion](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Quarantaine et liste bloquée](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

### Utilisation des outils de surveillance et de reporting

Utilisez les outils proposés par Adobe Campaign pour surveiller votre délivrabilité.

Adobe Campaign vous permet de vérifier les performances de vos diffusions à l’aide d’un ensemble d’indicateurs natifs, et ce, en temps réel. <!--For example, you can check the number of messages that are successfully executed, sent and delivered. You can also verify the number of messages that have been opened and the number of messages/links that have been clicked.-->Vous pouvez également créer des rapports en temps réel entièrement personnalisables pour obtenir davantage d’informations sur vos diffusions.

Voir à ce propos les sections suivantes :

* [Surveillance de la délivrabilité](../../sending/using/monitor-deliverability.md)
  <!--[Monitoring a delivery](../../sending/using/monitoring-a-delivery.md)-->
* [Recevoir des alertes en cas d&#39;échec](../../sending/using/receiving-alerts-when-failures-happen.md)
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
