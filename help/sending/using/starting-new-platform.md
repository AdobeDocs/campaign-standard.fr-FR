---
solution: Campaign Standard
product: campaign
title: Démarrage d’une nouvelle Plateforme avec Adobe Campaign Standard
description: Découvrez comment configurer une nouvelle Plateforme tout en conservant la réputation de votre domaine et de votre adresse IP avec Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '448'
ht-degree: 100%

---


# Démarrer une nouvelle Plateforme{#starting-new-platform}

Le contrôle de la réputation de votre domaine et de votre adresse IP est essentiel. Voici quelques conseils pour bien démarrer une nouvelle Plateforme.

Démarrer l&#39;envoi d&#39;emails sur une nouvelle Plateforme est une étape délicate car la Plateforme ne possède aucun historique d&#39;envoi, aucune réputation (dans le cas où les IP d&#39;envoi n&#39;ont jamais été utilisées à des fins d&#39;envoi d&#39;emails). Or rien n&#39;est plus suspect pour un FAI qu&#39;une adresse IP qui n&#39;a jamais envoyé d&#39;emails et qui commence subitement à envoyer des messages en masse. En effet, les spammeurs utilisent généralement des adresses IP « inconnues » (celles qui n’ont jamais été ajoutées sur la liste bloquée) pour envoyer un maximum de messages pendant le laps de temps où ils n’ont pas encore été détectés.

On ne peut donc pas espérer atteindre le régime de croisière en termes de débit dès le début de la mise en production. De surcroît on ne doit pas essayer d&#39;envoyer les premiers messages avec un tel débit, car cela conduirait les FAI à bloquer d&#39;autant plus sévèrement les adresses IP d&#39;envoi et à compromettre gravement la poursuite du démarrage.

Le démarrage d&#39;une Plateforme peut aller de pair avec le premier usage d&#39;une liste d&#39;adresses, c&#39;est-à-dire une liste potentiellement mal qualifiée. Or l&#39;envoi à des adresses invalides ou à des adresses pièges contribue à abaisser la réputation de la Plateforme.
* S’il existe une liste des adresses non valides, la méthode la plus efficace est de l’importer dans la table des quarantaines (**[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Quarantaines]** > **[!UICONTROL Adresses]**) avant de réaliser les premiers envois. Voir à ce propos cette [section](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Si on souhaite malgré tout requalifier les adresses invalides, il est nettement préférable de le faire une fois la réputation de la Plateforme établie et par petites parties afin de &quot;diluer&quot; dans le temps l&#39;usage des mauvaises adresses.

Pour résumer les principes à respecter lors d&#39;un démarrage :
* **Configurez un sous-domaine dédié** pour qu’il fonctionne avec Campaign et qu’il soit spécifique aux campagnes email envoyées depuis Adobe.
* **Importez les adresses non valides/inactives dans la table des quarantaines** (si vous disposez de ces informations).
* **Limitez le débit de diffusion** (réglage technique : limitation du nombre de mtachilds).
* **Augmentez progressivement les volumes d’envoi** : ne pas cibler toute la base de données dès le début, mais à chaque envoi ajouter une fraction de plus par rapport à l&#39;envoi précédent. Cela permet d&#39;augmenter le volume à chaque étape tout en diminuant le taux global d’adresses non valides.
* **Diffusez régulièrement des messages** : dans une certaine mesure, il est préférable de réaliser de petits envois fréquents plutôt que des envois volumineux et sporadiques.
* **Surveillez de près les rapports de diffusion** : un indicateur d&#39;erreur élevé peut signifier qu&#39;un paramétrage technique est mal configuré.
