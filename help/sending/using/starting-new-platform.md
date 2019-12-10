---
title: Démarrage d’une nouvelle plateforme avec Adobe Campaign Standard
description: Découvrez comment configurer une nouvelle plateforme tout en conservant la réputation de votre domaine et de votre adresse IP avec Adobe Campaign Standard.
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
source-git-commit: 89965d859986b9176de6b6bf96df1fbbb89b5b8f

---


# Démarrage d’une nouvelle plateforme{#starting-new-platform}

Le maintien de la réputation de votre domaine et de votre adresse IP est essentiel. Voici quelques conseils pour configurer une nouvelle plateforme.

Le démarrage de l'envoi de courriels sur une nouvelle plateforme est une étape délicate car la plateforme n'a aucun historique d'utilisation et aucune réputation (lorsque les adresses IP d'envoi n'ont jamais été utilisées à cette fin). Les FAI se méfient naturellement des adresses IP qui n'ont jamais été utilisées pour envoyer des courriels et qui commencent soudainement à envoyer de gros volumes de trafic de courriels. En effet, les spammeurs utilisent généralement des adresses IP "inconnues" (c’est-à-dire des adresses qui n’ont jamais été mises sur liste noire) pour envoyer le plus grand nombre possible de messages avant leur détection.

On ne peut pas s'attendre à atteindre la vitesse opérationnelle en termes de production au tout début de la phase de production. De plus, vous ne devriez pas tenter d'envoyer des messages à ce rythme, car cela pourrait conduire les FAI à bloquer les adresses d'envoi et à compromettre sérieusement le reste de la phase de démarrage.

Le démarrage d’une plate-forme se produit souvent lors de l’utilisation initiale d’une liste d’adresses qui ne sont peut-être pas entièrement qualifiées. Si vous envoyez à des adresses non valides ou à des adresses de miel, cela contribue à diminuer la réputation de la plateforme. Si vous disposez d’une liste d’adresses non valides, il est dans votre intérêt de l’importer dans la table de quarantaine (**[!UICONTROL Administration]** &gt; **[!UICONTROL Canaux]** &gt; **[!UICONTROL Quarantines]** &gt; **[!UICONTROL Adresses) avant de procéder à l’envoi pour la première fois.]** Si vous souhaitez tout de même requalifier les adresses non valides, il est de loin préférable de le faire une fois la réputation de la plate-forme établie et bit par bit afin de "diluer" l'utilisation des mauvaises adresses au fil du temps.

Pour résumer les principes à suivre au démarrage:
* **Déléguer un sous-domaine** dédié à Adobe spécifique aux campagnes par courrier électronique envoyées par Adobe
* **Importer des adresses incorrectes/inactives dans la table** de quarantaine (si vous disposez de ces informations)
* **Limiter le débit** de livraison (paramètre technique : limitation du nombre d’enfants mineurs)
* **Augmentez progressivement les volumes envoyés**: ne ciblez pas l'ensemble de la base de données dès le début, mais ajoutez une fraction supplémentaire de la liste chaque fois que vous envoyez ; cela devrait vous permettre d'augmenter le volume à chaque étape tout en réduisant le taux global d'adresses non valides
* **Envoyer des messages régulièrement**: Dans une certaine mesure, il est préférable d'envoyer régulièrement des petits plans plutôt que des campagnes volumineuses de manière sporadique.
* **Surveillez attentivement les rapports** de remise : des indicateurs d'erreur élevés peuvent signifier qu'un paramètre technique est mal configuré.
