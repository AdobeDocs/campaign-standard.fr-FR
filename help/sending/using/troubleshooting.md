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
translation-type: ht
source-git-commit: 331769e7f1c1c30e3b7ff340252052c5aaa2eac9
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---


# Résolution des problèmes{#troubleshooting}

Vous rencontrez un problème de délivrabilité ? La solution se trouve peut-être ici.

## Même message d’erreur pour un FAI {#same-error-for-an-isp}

**Pourquoi ai-je toujours le même message d’erreur pour un FAI particulier ?**

Si vous recevez toujours le même message d’erreur pour un FAI, il se peut que vous rencontriez des problèmes de réputation liés à votre adresse IP ou votre adresse d’expéditeur. Appliquez les recommandations suivantes :
* Vérifiez si vous recevez un fort pourcentage d’échecs liés à des adresses email inexistantes (échecs de type **Utilisateur inconnu**)
* Mettez à jour vos formulaires d’abonnement pour détecter d’éventuelles erreurs sur la saisie des noms de domaine (par exemple, gmaul.com ou yaho.com)
* Si vous constatez des erreurs indiquant que vos messages sont déclarés en spam, ou que vos messages sont constamment bloqués, essayez d’exclure de la cible les destinataires qui n’ont pas ouvert ou cliqué dans l’un de vos messages dans les 12 mois précédents.

Si le problème persiste, contactez les services commerciaux, délivrabilité ou support d’Adobe Campaign.

## Liste bloquée et quarantaine {#denylist-versus-quarantine}

* **Quelle est la différence entre une adresse email en liste bloquée et une adresse email en quarantaine ?**

   * Le statut **[!UICONTROL Sur la liste bloquée]** signifie que l’un de vos destinataires a déclaré un message comme étant un spam.

   * L’application du statut **[!UICONTROL Quarantaine]** est entraînée par un échec soft ou hard.
   Voir à ce propos cette [section](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **A quoi correspondent les différentes raisons de mise en quarantaine ?**

   Il existe dix raisons de mise en quarantaine : non définie, utilisateur inconnu, domaine invalide, adresse en liste bloquée, refusé, erreur ignorée, inatteignable, compte désactivé, boîte pleine, non connecté.

   Pour plus d’informations, voir [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md).

## Retrait de la liste bloquée {#removing-from-denylist}

* **Un de mes destinataires a été ajouté par erreur à la liste bloquée. Comment puis-je le retirer de la liste bloquée pour pouvoir lui envoyer à nouveau des messages ?**

   * Accédez à **[!UICONTROL Administration > Canaux > Quarantaines > Adresses]**.
   * Dans l’écran de détails de l’enregistrement correspondant, changez la valeur du champ **[!UICONTROL Statut]** à **[!UICONTROL Valide]**.
   * Sauvegardez l’enregistrement.

* **Comment puis-je savoir si l’une de mes adresses IP est sur la liste bloquée ? Comment supprimer mes adresses IP d’une liste bloquée ?**

   Pour vérifier si votre adresse IP se trouve dans une liste bloquée, vous pouvez utiliser différents sites web, tels que :
   * [MX Toolbox](https://mxtoolbox.com/)
   * [Quelle est mon adresse IP ?](https://whatismyipaddress.com)

   En général, la vérification d’une adresse IP renvoie une liste contenant les détails de la liste bloquée et le nom du site web qui a bloqué l’adresse IP.

   En cliquant sur le lien correspondant, accédez aux détails du site web.

   Vous pouvez ensuite demander que votre adresse IP soit supprimée du site web qui l’a mise en liste bloquée.

   >[!NOTE]
   >
   >Le processus peut varier selon le site web. Certains sites requièrent la création d’un compte alors que d’autres demandent uniquement que vous fournissiez l’adresse IP.
