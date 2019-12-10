---
title: Résolution des problèmes de délivrabilité dans Adobe Campaign Standard
description: Découvrez ce que vous devez faire lorsque vous rencontrez des problèmes de délivrabilité avec Adobe Campaign Standard.
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
source-git-commit: b2df5ca4d38e35f57815924ffbe0313dc1a22b29

---


# Résolution des problèmes{#troubleshooting}

Vous rencontrez un problème de délivrabilité ? Vous trouverez peut-être la solution ici...

**Pourquoi est-ce que je reçois toujours le même message d'erreur pour un FAI particulier ?**

Si vous obtenez toujours le même message d’erreur pour un FAI, votre adresse électronique ou votre adresse IP a peut-être été détectée comme défectueuse par le FAI. Effectuez les recommandations suivantes :
* Vérifiez si vous recevez un pourcentage élevé d’échecs liés à des adresses électroniques inexistantes (échecs inconnus **de l’** utilisateur).
* Mettez à jour vos formulaires d’abonnement pour détecter toute erreur dans les noms de domaine saisis (par exemple : gmaul.com ou yaho.com).
* Si vous constatez des erreurs indiquant que vos messages sont déclarés comme des messages indésirables ou que vos messages sont constamment bloqués, essayez d'exclure les destinataires qui n'ont pas ouvert ou cliqué sur l'un de vos messages au cours des 12 derniers mois depuis la cible.

Si le problème persiste, contactez les services commerciaux ou de délivrabilité, ou le support technique d’Adobe Campaign.

**Quelle est la différence entre une adresse de courriel mise sur liste noire et une adresse de courriel mise en quarantaine ?**

L’état **[!UICONTROL Liste]** noire est le résultat d’une boucle de rétroaction (lorsqu’une personne signale un message comme indésirable).

Le statut **[!UICONTROL Quarantined]** est le résultat d’un rebond doux ou dur.

**Que signifient les différentes raisons d'erreur de quarantaine ?**

Voici 10 raisons possibles : non défini, utilisateur inconnu, domaine non valide, adresse sur liste noire, refusé, erreur ignorée, inaccessible, compte désactivé, boîte aux lettres pleine, non connectée.

Pour plus d’informations, voir [Présentation de la gestion](../../sending/using/understanding-quarantine-management.md)de la quarantaine.

**Un de mes destinataires a été mis sur liste noire par erreur. Comment puis-je les démettre de la liste noire pour pouvoir recommencer à leur envoyer des messages ?**

* Accédez à **[!UICONTROL Administration &gt; Canaux &gt; Quarantines &gt; Adresses]**.
* Dans les détails de l’enregistrement correspondant, définissez la valeur du champ **[!UICONTROL État]** sur **[!UICONTROL Valide]**.
* Enregistrez l'enregistrement.

**Comment puis-je savoir si l’une de mes adresses IP est sur liste noire ? Comment annuler la liste noire de mes adresses IP ?**

Pour vérifier si votre adresse IP est sur liste noire, vous pouvez utiliser divers sites Web pour la vérifier :
* http://mxtoolbox.com/
* http://whatismyipaddress.com/blacklist-check
* http://www.blacklistalert.org/

En règle générale, le résultat de la vérification de l'adresse IP retournera une liste qui contient les détails de la liste noire ainsi que le nom du site Web qui a mis l'adresse IP sur liste noire.

En cliquant sur le lien, vous pouvez accéder aux détails du site Web.

Ensuite, vous pouvez demander que votre site Web soit retiré du site Web qui a mis l’adresse IP sur liste noire.

Le processus de radiation peut varier selon le site Web. Certains sites vous obligent à créer un compte, tandis que d'autres ont simplement besoin que vous fournissiez l'adresse IP.
