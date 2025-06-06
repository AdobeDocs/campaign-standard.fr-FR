---
title: Prise en main du test et de l’envoi
description: Préparez, testez, planifiez, envoyez et surveillez vos messages.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '578'
ht-degree: 100%

---

# Prise en main du test et de l&#39;envoi {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Préparation et test</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Envoi, surveillance et tracking</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Indications relatives à la délivrabilité</a></p></td></tr>
</table>

Une fois la cible définie et le contenu d’un message créé, vous devez préparer et tester le contenu, la personnalisation, le rendu et la configuration de vos diffusions. Vous pouvez ainsi vous assurer que tout est correct avant d’envoyer le message à la cible principale. Pour ce faire, un certain nombre de fonctionnalités sont disponibles, notamment les aperçus, les BAT, les tests de l’objet d’un email et le rendu des emails.

Une fois les campagnes marketing exécutées et les différents messages envoyés, surveillez-les à l’aide de logs pour vérifier le succès de votre opération et récupérez les informations de tracking des destinataires.

Enfin, appuyez-vous sur les indications et les outils relatifs à la délivrabilité de Campaign Standard pour améliorer le nombre de messages diffusés et assurer le succès des campagnes marketing.

![](assets/do-not-localize/how-to-video.png) [Découvrez comment envoyer un email de test, préparer et envoyer une diffusion email en vidéo](#video)

## Préparation et test {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

La **préparation des messages** de Campaign Standard analyse la cible, la personnalisation et la validité de ceux-ci. Les erreurs détectées pendant cette étape doivent être corrigées avant de poursuivre.

**Prévisualisation et test** de vos messages à l’aide de différentes fonctionnalités : envoyez des BAT aux profils de test ou à des profils ciblés, testez l’objet de vos e-mails et vérifiez le rendu de vos messages pour garantir qu’ils s’afficheront de manière optimale sur différents clients web, e-mails et appareils.

Utilisez les fonctionnalités de planification de Campaign pour définir quand vos messages seront envoyés. Vous pouvez, par exemple, adapter l’envoi au fuseau horaire du destinataire, optimiser l’heure d’envoi ou calculer la date d’envoi.

Utilisez des **typologies** pour vérifier, au cours de la préparation, si votre message est valide et répond à vos critères de qualité par le biais de règles de fatigue, de contrôle et de ciblage. Vous pouvez, par exemple, vérifier que vos emails contiennent toujours un objet ou exclure les destinataires du message qui se sont désabonnés.

En savoir plus :

* [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md)
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Envoi d&#39;un bon à tirer](../../sending/using/sending-proofs.md)
* [Rendu des e-mails](../../sending/using/email-rendering.md)
* [Planification de l&#39;envoi des messages](../../sending/using/about-scheduling-messages.md)
* [À propos des typologies et des règles de typologie](../../sending/using/about-typology-rules.md)

## Envoi, surveillance et tracking {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Une fois votre message prêt, vous pouvez vérifier les logs et les rapports d’envoi et d’accès pour **surveiller la diffusion** et mesurer le succès de votre campagne. Adobe Campaign met également à votre disposition un système d’alerte par email pour tracker les succès ou les échecs de diffusion, ainsi que des fonctionnalités de gestion des quarantaines.

**Trackez le comportement** des destinataires des messages en utilisant des cookies de session et permanents. Vous pourrez ainsi récupérer les informations de tracking (URL cliquées, pages miroir, messages ouverts...).

Vous pouvez aussi paramétrer Adobe Campaign pour **conserver une copie des emails** envoyés depuis votre plateforme via Email BCC. Activez cette fonctionnalité notamment si votre entreprise doit archiver tous les emails sortants à des fins de conformité.

En savoir plus :

* [Confirmer l&#39;envoi](../../sending/using/confirming-the-send.md)
* [Tracker les messages](../../sending/using/tracking-messages.md)
* [Archivage avec e-mail Cci](../../sending/using/archiving.md)
* [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md)
* [Comprendre les échecs de diffusion](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)

## Indications relatives à la délivrabilité {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

La délivrabilité permet de mesurer le succès des campagnes atteignant la boîte de réception de vos destinataires sans bounces ou sans être marqués comme spam.

Campaign Standard met à votre disposition plusieurs **outils de délivrabilité** pour améliorer le nombre de messages correctement diffusés : rapports de débit de diffusion, optimisation de l’heure d’envoi, prévisualisation des messages, rendu des emails, gestion des quarantaines, etc.

En savoir plus :

* [À propos de la délivrabilité](../../sending/using/about-deliverability.md)
* [Surveillance de la délivrabilité](../../sending/using/monitor-deliverability.md)
* [Guide des bonnes pratiques relatives à la délivrabilité](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=fr)
* [Contrôle du débit des diffusions](../../reporting/using/delivery-throughput.md)

## Ressources supplémentaires

* [Conception d’emails de test A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Prise en main des messages](../../channels/using/key-steps-to-send-a-message.md)
* [Bonnes pratiques relatives à la diffusion](../../sending/using/delivery-best-practices.md)
* [Ajouter une population témoin](../../sending/using/control-group.md)

## Tutoriel vidéo {#video}

Cette vidéo montre comment envoyer un email de test, préparer puis envoyer une diffusion email avec Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/30236?captions=fre_fr)

D’autres vidéos pratiques sur Campaign Standard sont disponibles [ici](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=fr).
