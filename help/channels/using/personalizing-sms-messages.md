---
title: Personnaliser un SMS
seo-title: Personnaliser un SMS
description: Personnaliser un SMS
seo-description: Découvrez la spécificité des options de translittération lors de la personnalisation des SMS.
page-status-flag: never-activated
uuid: 123fe70c-c279-40a3-88b6-6bfb2453ec83
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: 7c64785c-e3c2-4caa-a547-002990aae3f9
delivercontext-tags: deliveryCreation,wizard;delivery,smsContent,back;delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 4084346b537bb483c5519c26d71880d3c57a7e44

---


# Personnaliser un SMS{#personalizing-sms-messages}

Les principes de personnalisation des SMS sont les mêmes que pour les [emails](../../designing/using/personalization.md#inserting-a-personalization-field). Vous devez toutefois être attentif aux options de translittération car elles peuvent faire changer l'encodage et donc le nombre de SMS à envoyer. Voir à ce propos la section [Translittération et longueur des SMS](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

Voici l'exemple d'un SMS contenant des champs de personnalisation qui, selon l'option de translittération choisie, ne générera pas le même nombre d'envois :

**Bonjour &lt;Prénom&gt; &lt;Nom&gt;, de nouveaux produits sont disponibles. Venez les découvrir en magasin !**

* Pour un destinataire nommé 'Jean Dupont', aucun caractère spécial n'étant présent, Adobe Campaign choisira l'encodage GSM qui autorise jusqu'à 160 caractères par SMS. Le message sera donc envoyé en une seule partie.
* Pour un destinataire nommé 'Raphaël Laforêt', les caractères 'ë' et 'ê' ne peuvent pas être encodés en GSM. Selon le paramétrage choisi pour la translittération, Adobe Campaign a le choix entre deux comportements :

   * Si la translittération est autorisée, 'ë' et 'ê' seront remplacés par 'e', ce qui permet d'utiliser l'encodage GSM et autorise 160 caractères dans le SMS. Ce message sera envoyé en un seul SMS, mais il sera légèrement altéré.
   * Si la translittération n'est pas autorisée, Adobe Campaign choisira d'envoyer le message en Unicode et tous les caractères seront envoyés tels quels. Comme les SMS en Unicode sont limités à 70 caractères, Adobe Campaign devra envoyer le message en deux parties.

>[!NOTE]
>
>L'algorithme qui choisit automatiquement le meilleur encodage est effectué indépendamment pour chaque message, au cas par cas. Ainsi, seuls les messages personnalisés nécessitant un encodage Unicode seront envoyés en Unicode ; les autres utiliseront l'encodage GSM.

## Expéditeur des SMS {#sms-sender}

Vous pouvez personnaliser le nom de l'expéditeur du SMS. Pour en savoir plus, consultez la section [Configuration des SMS](../../administration/using/configuring-sms-channel.md#configuring-sms-properties).
