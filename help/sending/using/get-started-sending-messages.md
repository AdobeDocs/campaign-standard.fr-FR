---
title: Commencer avec les tests et l’envoi
description: Découvrez les différentes étapes pour tester et envoyer un message.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c1b7d2210647a87693d93e325a4c888cb23e5f3a

---


# Commencer avec les tests et l’envoi {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Préparation et test</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Envoi, surveillance et suivi</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Lignes directrices sur la délivrabilité</a></p></td></tr>
</table>

Une fois que vous avez défini la cible et créé le contenu d’un message, vous devez préparer et tester le contenu, la personnalisation, le rendu et la configuration de vos diffusions. Cela vous permet de vous assurer que tout est correct avant d&#39;envoyer le message à la cible principale. Pour ce faire, plusieurs fonctionnalités sont disponibles, telles que la prévisualisation, les BAT, le test de l’objet du courrier électronique ou le rendu du courrier électronique.

Une fois les campagnes marketing exécutées et les différents messages envoyés, surveillez-les à l’aide de journaux afin de vérifier la réussite de votre campagne et récupérez les informations de suivi sur les destinataires.

Enfin, vous pouvez tirer parti des directives et outils de délivrabilité disponibles à Campaign Standard pour augmenter le nombre de messages diffusés et garantir la réussite des campagnes marketing.

## Préparation et test {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **message preparation** analyzes the target, the personalization and the validity of the message. Les erreurs détectées pendant cette étape doivent être corrigées avant de poursuivre.

**Prévisualisation et test** de vos messages à l&#39;aide de différentes fonctionnalités : envoyez des BAT pour tester des profils ou des profils ciblés, testez l&#39;objet de vos courriels et vérifiez le rendu de vos messages afin de vous assurer qu&#39;ils s&#39;afficheront de manière optimale sur divers clients Web, courriels Web et périphériques.

Utilisez les fonctionnalités de planification de Campaign$$ pour définir quand vos messages seront envoyés. Par exemple, vous pouvez adapter l’envoi à la zone de temps du destinataire, optimiser l’heure d’envoi ou calculer la date d’envoi.

Utilisez **des typologies** pour vérifier pendant la préparation si votre message est valide et répond à vos critères de qualité par le biais de règles de fatigue, de contrôle et de ciblage. Par exemple, pour vérifier que vos courriels contiennent toujours un objet ou pour exclure les abonnés des destinataires de message.

En savoir plus:

* [Préparer l’envoi](../../sending/using/preparing-the-send.md)
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Envoyer un bon à tirer](../../sending/using/sending-proofs.md)
* [Rendu des emails](../../sending/using/email-rendering.md)
* [Planification de l’envoi des messages](../../sending/using/about-scheduling-messages.md)
* [A propos des typologies et des règles de typologie](../../sending/using/about-typology-rules.md)

## Envoi, surveillance et suivi {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Une fois votre message prêt, vous pouvez vérifier les journaux d’envoi et d’accès et les rapports pour **surveiller la diffusion** et mesurer la réussite de votre campagne. Adobe Campaign fournit également un système d’alerte par courrier électronique pour suivre les réussites ou les échecs de diffusion, ainsi que les fonctionnalités de gestion des quarantaines.

**Suivez le comportement** des destinataires de messages en utilisant des cookies de session et permanents pour récupérer les informations de suivi (URL, pages miroir, messages ouverts sur un clic..).

Finally, you can configure Adobe Campaign to **keep a copy of emails** sent from your platform through Email BCC. Activez cette fonctionnalité notamment si votre entreprise doit archiver tous les emails sortants à des fins de conformité.

En savoir plus:

* [Confirmer l’envoi](../../sending/using/confirming-the-send.md)
* [Tracker les messages](../../sending/using/tracking-messages.md)
* [Archivage avec Email BCC](../../sending/using/archiving.md)
* [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md)
* [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)

## Lignes directrices sur la délivrabilité {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

La délivrabilité permet de mesurer le succès des campagnes atteignant la boîte de réception de vos destinataires sans bounces ou sans être marqués comme spam.

Campaign Standard fournit plusieurs outils **de** délivrabilité pour vous aider à améliorer le nombre de messages correctement diffusés : rapports de pensée de diffusion, optimisation du temps d’envoi, prévisualisation des messages, rendu des courriels, gestion des quarantaines, etc.

En savoir plus:

* [A propos de la délivrabilité](../../sending/using/about-deliverability.md)
* [Contrôle de la délivrabilité](../../sending/using/monitor-deliverability.md)
* [Amélioration de votre réputation](../../sending/using/improving-reputation.md)
* [Recommandations techniques](../../sending/using/technical-recommendations.md)
* [Contrôle du débit des Diffusions](../../reporting/using/delivery-throughput.md)

## Autres ressources

* [Conception de courriers électroniques de test A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Envoyer un test, préparer et envoyer un message électronique (vidéo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/sending-test-preparing-sending-email.html)
* [Vérification d’une diffusion de messagerie et de rapports (vidéo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/reviewing-personalized-email-delivery-and-reports.html)
* [Prise en main des courriers électroniques](https://helpx.adobe.com/fr/campaign/kb/acs-get-started-with-emails.html)
* [Bonnes pratiques de diffusion](https://helpx.adobe.com/fr/campaign/kb/delivery-best-practices.html)