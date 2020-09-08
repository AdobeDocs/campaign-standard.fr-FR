---
title: Démarrage d’une nouvelle plate-forme avec Adobe Campaign Standard
description: Découvrez comment configurer une nouvelle plate-forme tout en conservant la réputation de votre domaine et de votre adresse IP avec Adobe Campaign Standard.
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
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 94%

---


# Démarrer une nouvelle plate-forme{#starting-new-platform}

Le contrôle de la réputation de votre domaine et de votre adresse IP est essentiel. Voici quelques conseils pour bien démarrer une nouvelle plate-forme.

Démarrer l&#39;envoi d&#39;emails sur une nouvelle plate-forme est une étape délicate car la plate-forme ne possède aucun historique d&#39;envoi, aucune réputation (dans le cas où les IP d&#39;envoi n&#39;ont jamais été utilisées à des fins d&#39;envoi d&#39;emails). Or rien n&#39;est plus suspect pour un FAI qu&#39;une adresse IP qui n&#39;a jamais envoyé d&#39;emails et qui commence subitement à envoyer des messages en masse. En effet, les spammeurs utilisent généralement des adresses IP &quot;inconnues&quot; (adresses qui n&#39;ont jamais été placées sur la liste bloquée) pour envoyer le plus grand nombre possible de messages avant leur détection.

On ne peut donc pas espérer atteindre le régime de croisière en termes de débit dès le début de la mise en production. De surcroît on ne doit pas essayer d&#39;envoyer les premiers messages avec un tel débit, car cela conduirait les FAI à bloquer d&#39;autant plus sévèrement les adresses IP d&#39;envoi et à compromettre gravement la poursuite du démarrage.

Le démarrage d&#39;une plate-forme peut aller de pair avec le premier usage d&#39;une liste d&#39;adresses, c&#39;est-à-dire une liste potentiellement mal qualifiée. Or l&#39;envoi à des adresses invalides ou à des adresses pièges contribue à abaisser la réputation de la plate-forme.
* S’il existe une liste des adresses non valides, la méthode la plus efficace est de l’importer dans la table des quarantaines (**[!UICONTROL Administration]** > **[!UICONTROL Canaux]** > **[!UICONTROL Quarantaines]** > **[!UICONTROL Adresses]**) avant de réaliser les premiers envois. Voir à ce propos cette [section](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Si on souhaite malgré tout requalifier les adresses invalides, il est nettement préférable de le faire une fois la réputation de la plate-forme établie et par petites parties afin de &quot;diluer&quot; dans le temps l&#39;usage des mauvaises adresses.

Pour résumer les principes à respecter lors d&#39;un démarrage :
* **Déléguez un sous-domaine dédié** à Adobe, spécifique des campagnes par e-mail envoyées depuis Adobe.
* **Importez les adresses non valides/inactives dans la table des quarantaines** (si vous disposez de ces informations).
* **Limitez le débit de diffusion** (réglage technique : limitation du nombre de mtachilds).
* **Augmentez progressivement les volumes d’envoi** : ne pas cibler toute la base de données dès le début, mais à chaque envoi ajouter une fraction de plus par rapport à l&#39;envoi précédent. Cela permet d&#39;augmenter le volume à chaque étape tout en diminuant le taux global d’adresses non valides.
* **Diffusez régulièrement des messages** : dans une certaine mesure, il est préférable de réaliser de petits envois fréquents plutôt que des envois volumineux et sporadiques.
* **Surveillez de près les rapports de diffusion** : un indicateur d&#39;erreur élevé peut signifier qu&#39;un paramétrage technique est mal configuré.
