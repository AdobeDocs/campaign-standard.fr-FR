---
title: A propos de la délivrabilité dans Adobe Campaign Standard
description: Découvrez les concepts et les bonnes pratiques liés à la délivrabilité ainsi que les outils proposés par Adobe Campaign Standard pour optimiser l’envoi de vos livraisons.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# A propos de la délivrabilité{#about-deliverability}

La délivrabilité ou la manière de mesurer le succès de vos campagnes dans la boîte de réception des destinataires sans rebondir ou être marquée comme indésirable.

La délivrabilité d’Adobe Campaign est un service payant disponible dans différentes offres. Communiquez avec la délivrabilité ou le service commercial.

Le taux de délivrabilité dépend de nombreux facteurs, notamment :

* Configuration correcte de vos instances
* Votre réputation d'adresse IP
* Qualité des adresses ciblées
* Faibles taux de plaintes et de rebonds brutaux
* Votre contenu de message
* Authentification des messages (SPF, DKIM, DMARC)
* Connaissance de l'expéditeur

## Points clés à vérifier {#deliverability-key-points}

Pour optimiser la délivrabilité de vos courriers électroniques Adobe Campaign, nous vous recommandons d’utiliser les meilleures pratiques répertoriées ci-dessous. Les problèmes de délivrabilité sont généralement liés aux mesures de protection contre le spam mises en oeuvre par les fournisseurs de services Internet et les administrateurs de serveurs de messagerie.

La délivrabilité des courriers électroniques désigne l'ensemble des caractéristiques qui déterminent la capacité d'un message à atteindre sa destination, par l'intermédiaire d'une adresse électronique personnelle, dans un délai court, et avec la qualité attendue en termes de contenu et de format. Ces caractéristiques se répartissent en quatre catégories principales : qualité des données, message et contenu, infrastructure d’envoi et réputation. Ensemble, ils forment la base d'un programme de livraison de courriels réussi.

Le taux de délivrabilité est le nombre de courriers électroniques envoyés qui ont été remis avec succès à ses destinataires.
Voici une liste des points clés à vérifier pour assurer une bonne livraison.

## Outils de délivrabilité {#deliverability-tools}

Commencez par consulter la documentation sur les outils de délivrabilité fournis avec Campaign Standard :
* [Meilleures pratiques de livraison](https://helpx.adobe.com/campaign/kb/delivery-best-practices.html)
* [Personnalisation du nom de l’expéditeur](../../designing/using/personalization.md#personalizing-the-sender)
* [Test de l'objet d'un email](../../sending/using/testing-subject-line-email.md)
* [Optimiser l'heure d'envoi](../../sending/using/optimizing-the-sending-time.md)
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Rendu des emails](../../sending/using/email-rendering.md)
* [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md)
* [Recevoir des alertes en cas d'échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Mise en quarantaine et blacklistage](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [Rapports dynamiques](../../reporting/using/about-dynamic-reports.md)

## Vérification de la configuration du réseau {#network-configuration}

Les spammeurs essaient de dissimuler leur véritable identité et par conséquent rendent leurs serveurs difficiles à identifier. Une configuration réseau légitime qui n'essaie pas de masquer l'identité du serveur est essentielle pour envoyer des courriers électroniques en gros volumes.

## Envoi à des adresses valides {#valid-addresses}

Les spammeurs utilisent souvent des générateurs d'adresses basés sur des listes de noms fréquents et de prénoms; en outre, ils traitent rarement les notifications techniques envoyées par les serveurs de messagerie. Un taux élevé d'adresses non valides est souvent interprété comme un signe de spam. Les mécanismes de double inclusion et la gestion efficace des messages techniques de rebond permettent d’éviter ce problème.

## Réduction du taux de plaintes {#reduce-complaint-rate}

Les FAI ont généralement un moyen important de signaler un message reçu comme indésirable. Cela permet d'identifier les sources non fiables. En répondant rapidement aux demandes d’exclusion, en utilisant régulièrement une liste donnée, en vérifiant le consentement par le biais d’un système de double inclusion et en mettant en oeuvre des boucles de rétroaction, vous pouvez réduire les taux de plaintes.

## Envoi aux adresses de miel {#honeypot-addresses}

Les FAI et autres organisations (voir http://www.projecthoneypot.org/) utilisent des boîtes aux lettres qui ne correspondent pas à des personnes physiques mais qui sont simplement créées pour tromper les spammeurs. Ces adresses dites de "miel pot" sont publiées sur le Web afin d'être collectées par des robots spammeurs et ainsi attraper des expéditeurs illégitimes. L'utilisation d'un mécanisme d'inclusion double empêche l'ajout de ce type d'adresse à une liste. Lorsque vous utilisez une liste tierce, vous devez être sûr des méthodes utilisées par son responsable.

## Adaptation du contenu des messages {#adapt-message-content}

Dans une moindre mesure, le contenu de certains messages peut amener certains filtres à le détecter comme indésirable. L'utilisation de certains mots, l'utilisation de points d'exclamation dans la ligne objet et dans les messages sont lus comme des signes révélateurs de spam. Les spammeurs sont également connus pour remplacer le texte par des images afin d’empêcher l’analyse automatique du texte par des filtres anti-spam. En réponse à cela, un message (au format HTML) avec une forte proportion d’images, ou des images en tant que pièces jointes, peut se retrouver bloqué.

## Envoi régulier {#regular-deliveries}

Les spammeurs font des livraisons programmées pour maintenir leur réputation au fil du temps. Il leur faut parfois adapter leur plan marketing pour répondre aux meilleures pratiques imposées par les FAI, et ainsi, après un pic de réputation (montée en puissance), ils configurent des livraisons régulières.
