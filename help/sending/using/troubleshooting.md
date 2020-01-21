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
source-git-commit: fc9c6371732aa0eba9e675d2709cd62c25b27b96

---


# Résolution des problèmes{#troubleshooting}

Vous rencontrez un problème de délivrabilité ? La solution se trouve peut-être ici...

**Pourquoi ai-je toujours le même message d&#39;erreur pour un FAI particulier ?**

Si vous recevez toujours le même message d&#39;erreur pour un FAI, il se peut que vous rencontriez des problèmes de réputation liés à votre adresse IP ou votre adresse d&#39;expéditeur. Appliquez les recommandations suivantes :
* Vérifiez si vous recevez un fort pourcentage d&#39;échecs liés à des adresses email inexistantes (échecs de type **Utilisateur inconnu**)
* Mettez à jour vos formulaires d&#39;abonnement pour détecter d&#39;éventuelles erreurs sur la saisie des noms de domaine (par exemple, gmaul.com ou yaho.com)
* Si vous constatez des erreurs indiquant que vos messages sont déclarés en spam, ou que vos messages sont constamment bloqués, essayez d&#39;exclure de la cible les destinataires qui n&#39;ont pas ouvert ou cliqué dans l&#39;un de vos messages dans les 12 mois précédents.

Si le problème persiste, contactez les services commerciaux, délivrabilité ou support d&#39;Adobe Campaign.

**Quelle est la différence entre une adresse email blacklistée et en quarantaine ?**

Le statut **[!UICONTROL En blackliste]**signifie que l&#39;un de vos destinataires a déclaré un message comme étant un spam.

L&#39;application du statut **[!UICONTROL Quarantaine]**est entraînée par un échec soft ou hard.

**A quoi correspondent les différentes raisons de mise en quarantaine ?**

Il existent dix raisons de mise en quarantaine : non définie, utilisateur inconnu, domaine invalide, adresse en blackliste, refusé, erreur ignorée, inatteignable, compte désactivé, boîte pleine, non connecté.

Pour plus d’informations, voir [Comprendre la gestion des quarantaines](../../sending/using/understanding-quarantine-management.md).

**Un de mes destinataires est passé par erreur en statut &quot;En blackliste&quot;. Que puis-je faire lui envoyer à nouveau des emails ?**

* Accédez à **[!UICONTROL Administration > Canaux > Quarantaines > Adresses]**.
* Dans l&#39;écran de détails de l&#39;enregistrement correspondant, changez la valeur du champ **[!UICONTROL Statut]**à**[!UICONTROL  Valide]**.
* Sauvegardez l&#39;enregistrement.

**Comment puis-je savoir si l&#39;une de mes IP est backlistée ? Comment débloquer mon ou mes IP ?**

Pour vérifier si votre adresse IP est blacklistée, vous pouvez consulter l&#39;un des sites web ci-dessous :
* https://mxtoolbox.com/
* https://whatismyipaddress.com/blacklist-check
* http://www.blacklistalert.org/

En général, la vérification d&#39;adresse IP renvoie une liste contenant les détails du blacklistage et le nom du site web qui a blacklisté l&#39;adresse IP.

Un lien est disponible pour accéder aux détails du site web.

Vous pouvez ensuite demander que votre adresse IP soit supprimée du site web qui l&#39;a blacklistée.

Le processus peut varier selon le site web. Certains sites requièrent la création d&#39;un compte alors que d&#39;autres demandent uniquement que vous fournissiez l&#39;adresse IP.
