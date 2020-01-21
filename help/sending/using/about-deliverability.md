---
title: !binary |-
woHDgCBwcm9wb3MgZGUgbGEgZMOpbGl2cmFiaWxpdMOpIGRhbnMgQWRvYmXCoENhbXBhaWduwqBTdGFuZGFyZA=
description: 'Découvrez les concepts et bonnes pratiques liés à la délivrabilité, ainsi que les outils proposés par Adobe Campaign Standard pour optimiser l''envoi de vos diffusions.'
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
translation-type: ht
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# A propos de la délivrabilité{#about-deliverability}

La délivrabilité ou comment mesurer le succès de vos campagnes atteignant la boîte de réception de vos destinataires sans rebonds ou sans être marqués comme spam.

Adobe Campaign Deliverability est un service payant qui est proposé dans le cadre de plusieurs offres. Pour en savoir plus, contactez le service commercial ou de délivrabilité.

Le taux de délivrabilité dépend de nombreux facteurs et notamment :

* le bon paramétrage de vos instances
* la réputation de vos adresses IP
* la qualité des adresses ciblées
* le faible taux de plaintes
* le contenu de vos messages
* l&#39;authentification des messages (SPF, DKIM, DMARC)
* la réputation de l&#39;expéditeur

## Points clés à vérifier {#deliverability-key-points}

Afin d&#39;optimiser la délivrabilité de vos emails Adobe Campaign, nous vous recommandons de suivre les bonnes pratiques listées ci-dessous. Les problèmes de délivrabilité sont généralement liés à des mesures de protection contre les spams mises en place par les fournisseurs d&#39;accès à internet et les administrateurs de serveurs de mail.

La délivrabilité des emails désigne l&#39;ensemble des caractéristiques qui déterminent la capacité d&#39;un message à atteindre sa destination, via une adresse email personnelle, en peu de temps, et avec la qualité attendue en termes de contenu et de format. Ces caractéristiques se divisent en quatre catégories principales : qualité des données, message et contenu, infrastructure d&#39;envoi et réputation. Ensemble, elles forment la base d&#39;un programme performant de délivrabilité des emails.

Le taux de délivrabilité est le nombre d&#39;emails envoyés qui ont été délivrés avec succès aux destinataires.
Voici une liste de points clés à vérifier pour assurer une bonne délivrabilité.

## Outils de délivrabilité {#deliverability-tools}

Tout d&#39;abord, consultez la documentation sur les outils de délivrabilité fournis par Adobe Campaign :
* [Bonnes pratiques de diffusion](https://helpx.adobe.com/fr/campaign/kb/delivery-best-practices.html)
* [Personnaliser le nom de l&#39;expéditeur](../../designing/using/personalization.md#personalizing-the-sender)
* [Test de l&#39;objet d&#39;un email](../../sending/using/testing-subject-line-email.md)
* [Optimiser l&#39;heure d&#39;envoi](../../sending/using/optimizing-the-sending-time.md)
* [Prévisualiser un message](../../sending/using/previewing-messages.md)
* [Rendu des emails](../../sending/using/email-rendering.md)
* [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md)
* [Recevoir des alertes en cas d&#39;échec](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md)
* [Mise en quarantaine et blacklistage](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [Rapports dynamiques](../../reporting/using/about-dynamic-reports.md)

## Vérifier la configuration du réseau {#network-configuration}

Les spammeurs cherchent à cacher leur véritable identité et par conséquent rendent leurs serveurs d&#39;envoi difficilement identifiables. Une configuration réseau correcte, qui ne cherche pas à cacher d&#39;information, est un préalable à tout envoi en masse.

## Envoi à des adresses valides {#valid-addresses}

Les spammeurs utilisent parfois des générateurs d&#39;adresses basés sur des listes de prénoms et de noms fréquents ; d&#39;autre part, ils traitent rarement les notifications techniques renvoyées par les serveurs de messagerie. Un taux d&#39;adresses invalides élevé dans une diffusion est souvent interprété comme la marque d&#39;un spammeur. Une inscription par double opt-in et une gestion rigoureuse des rebonds techniques permet d&#39;éviter cela.

## Réduction du taux de plaintes {#reduce-complaint-rate}

Les FAI ont systématisé la mise à disposition d&#39;une fonction &quot;Ceci est un spam&quot; pour permettre aux utilisateurs de rapporter les emails non sollicités et en déduire les envoyeurs. Une gestion honnête des demandes, une diffusion régulière sur sa liste, la vérification des inscriptions par double opt-in, la facilité de désinscription et son temps de prise en compte et surtout la mise en place de boucles de rétro-action ou &quot;feedback loop&quot; permettent de diminuer les taux de plaintes.

## Envoi à des adresses pièges {#honeypot-addresses}

Les FAI et d&#39;autres organisations (voir le site https://www.projecthoneypot.org/) créent des boîtes mails ne correspondant à aucune personne physique dans le but de piéger les spammeurs. Ces adresses piège ou &quot;honey pots&quot; sont publiées sur le web dans le but qu&#39;elles soient trouvées par les robots collecteurs d&#39;adresses des spammeurs et pour ainsi en déduire les expéditeurs illégitimes. Un mécanisme de double opt-in empêche totalement l&#39;ajout de ce genre d&#39;adresses. Quand on utilise une liste fournie par un tiers, il faut être sûr des méthodes employées par ce dernier.

## Adaptation du contenu des messages {#adapt-message-content}

Dans une moindre mesure, le contenu des messages peut amener certains filtres à détecter un spam. L&#39;emploi de certains mots, l&#39;usage de points d&#39;exclamation dans le corps ou le sujet du message doit être mesuré. Une parade temporaire des spammeurs a consisté à remplacer le texte interdit par des images dont le texte ne peut pas être examiné automatiquement par les filtres anti-spam. En réponse à cela, un message (au format HTML) contenant une trop forte proportion d&#39;images peut désormais être bloqué, de même qu&#39;un message embarquant les images en pièces-jointes.

## Envois réguliers {#regular-deliveries}

Les spammeurs font des envois ponctuels pour maintenir leur réputation dans le temps. Il est parfois nécessaire d&#39;adapter son plan marketing pour répondre aux exigences des bonnes pratiques imposées par les FAI et donc, après la phase de montée en réputation (ram-up), paramétrer des envois réguliers.
