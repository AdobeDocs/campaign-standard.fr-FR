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
source-git-commit: b4ba56e5cd639c547a7060be9c60985f5564160d

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

## Liste noire contre {#blacklisting-versus-quarantine}

* **Quelle est la différence entre une adresse email blacklistée et en quarantaine ?**

   * The status **[!UICONTROL Blacklisted]** is a result of a feedback loop (when a person reports a message as spam).

   * The status **[!UICONTROL Quarantined]** is a result of a soft or hard bounce. For more on this, see this [section](../../sending/using/understanding-quarantine-management.md).

* **A quoi correspondent les différentes raisons de mise en quarantaine ?**

   Il existent dix raisons de mise en quarantaine : non définie, utilisateur inconnu, domaine invalide, adresse en blackliste, refusé, erreur ignorée, inatteignable, compte désactivé, boîte pleine, non connecté.

   Pour plus d’informations, voir [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md).

## Annulation de la liste noire {#unblacklisting}

* **Un de mes destinataires est passé par erreur en statut &quot;En blackliste&quot;. Que puis-je faire lui envoyer à nouveau des emails ?**

   * Go to **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * In the details of the corresponding record, set the value of the **[!UICONTROL Status]** field to **[!UICONTROL Valid]**.
   * Sauvegardez l&#39;enregistrement.

* **Comment puis-je savoir si l&#39;une de mes IP est backlistée ? Comment débloquer mon ou mes IP ?**

   Pour vérifier si votre adresse IP est blacklistée, vous pouvez consulter l&#39;un des sites web ci-dessous :
   * https://mxtoolbox.com/
   * https://whatismyipaddress.com/blacklist-check
   * https://www.blacklistalert.org/
   En général, la vérification d&#39;adresse IP renvoie une liste contenant les détails du blacklistage et le nom du site web qui a blacklisté l&#39;adresse IP.

   En cliquant sur le lien correspondant, vous pouvez accéder aux détails du site Web.

   Vous pouvez ensuite demander que votre adresse IP soit supprimée du site web qui l&#39;a blacklistée.

   >[!NOTE]
   >
   >Le processus peut varier selon le site web. Certains sites requièrent la création d&#39;un compte alors que d&#39;autres demandent uniquement que vous fournissiez l&#39;adresse IP.
