---
title: Résolution des problèmes de délivrabilité dans Adobe Campaign Standard
description: Découvrez ce que vous devez faire lorsque vous rencontrez des problèmes de délivrabilité avec Adobe Campaign Standard.
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
source-git-commit: 331769e7f1c1c30e3b7ff340252052c5aaa2eac9
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 60%

---


# Résolution des problèmes{#troubleshooting}

Vous rencontrez un problème de délivrabilité ? La solution se trouve peut-être ici.

## Même message d&#39;erreur pour un FAI {#same-error-for-an-isp}

**Pourquoi ai-je toujours le même message d&#39;erreur pour un FAI particulier ?**

Si vous recevez toujours le même message d&#39;erreur pour un FAI, il se peut que vous rencontriez des problèmes de réputation liés à votre adresse IP ou votre adresse d&#39;expéditeur. Appliquez les recommandations suivantes :
* Vérifiez si vous recevez un fort pourcentage d&#39;échecs liés à des adresses email inexistantes (échecs de type **Utilisateur inconnu**)
* Mettez à jour vos formulaires d&#39;abonnement pour détecter d&#39;éventuelles erreurs sur la saisie des noms de domaine (par exemple, gmaul.com ou yaho.com)
* Si vous constatez des erreurs indiquant que vos messages sont déclarés en spam, ou que vos messages sont constamment bloqués, essayez d&#39;exclure de la cible les destinataires qui n&#39;ont pas ouvert ou cliqué dans l&#39;un de vos messages dans les 12 mois précédents.

Si le problème persiste, contactez les services commerciaux, délivrabilité ou support d&#39;Adobe Campaign.

## Liste bloquée contre quarantaine {#denylist-versus-quarantine}

* **Quelle est la différence entre une adresse électronique sur la liste bloquée et une adresse électronique mise en quarantaine ?**

   * The status **[!UICONTROL On denylist]** is a result of a feedback loop (when a person reports a message as spam).

   * L&#39;application du statut **[!UICONTROL Quarantaine]** est entraînée par un échec soft ou hard.
   Voir à ce propos cette [section](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **A quoi correspondent les différentes raisons de mise en quarantaine ?**

   Voici 10 raisons possibles : non défini, utilisateur inconnu, domaine invalide, adresse à la liste bloquée, refusé, erreur ignorée, inatteignable, compte désactivé, boîte aux lettres pleine, non connectée.

   Pour plus d’informations, voir [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md).

## Suppression de la liste bloquée {#removing-from-denylist}

* **Un de mes destinataires a été ajouté à la liste bloquée par erreur. How do I remove them from the denylist so that I can start sending them messages again?**

   * Accédez à **[!UICONTROL Administration > Canaux > Quarantaines > Adresses]**.
   * Dans l&#39;écran de détails de l&#39;enregistrement correspondant, changez la valeur du champ **[!UICONTROL Statut]** à **[!UICONTROL Valide]**.
   * Sauvegardez l&#39;enregistrement.

* **Comment puis-je savoir si une de mes adresses IP est en liste bloquée ? How do I remove my IP(s) from a denylist?**

   Pour vérifier si votre adresse IP est en liste bloquée, vous pouvez utiliser divers sites Web pour la vérifier, par exemple :
   * [MX Toolbox](https://mxtoolbox.com/)
   * [Quelle est mon adresse IP ?](https://whatismyipaddress.com)

   En règle générale, le résultat de la vérification de l’adresse IP renvoie une liste qui contient les détails de la liste bloquée ainsi que le nom du site Web qui a bloqué l’adresse IP.

   En cliquant sur le lien correspondant, accédez aux détails du site web.

   Ensuite, vous pouvez demander que votre site Web soit radié du site Web qui a ajouté l’adresse IP à sa liste bloquée.

   >[!NOTE]
   >
   >Le processus peut varier selon le site web. Certains sites requièrent la création d&#39;un compte alors que d&#39;autres demandent uniquement que vous fournissiez l&#39;adresse IP.
