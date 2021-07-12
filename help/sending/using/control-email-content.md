---
solution: Campaign Standard
product: campaign
title: Contrôle du contenu des emails dans Adobe Campaign Standard
description: Découvrez comment améliorer la délivrabilité dans Adobe Campaign Standard en modifiant le contenu de vos emails.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Délivrabilité
role: User
level: Intermediate
exl-id: debbc70d-4094-44c0-b7cb-c999effda1a6
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '798'
ht-degree: 100%

---

# Contrôle du contenu des e-mails{#control-email-content}

<!--TO KEEP because specific to Campaign-->

Pour que vos emails atteignent vos destinataires et améliorer ainsi leur taux de délivrabilité, assurez-vous qu’ils respectent un certain nombre de règles. Dans le cas contraire, le contenu de certains messages peut être détecté comme du spam. Adobe Campaign fournit plusieurs outils vous permettant de vérifier que votre contenu respecte ces règles.

Suivez les principes ci-dessous lors de la conception du contenu de votre message :

* [Nom et adresse de l’expéditeur](#sender-name) : l’adresse doit identifier explicitement l’expéditeur, lequel doit être propriétaire du domaine et l’avoir enregistré. Le registre du domaine ne doit pas être privatisé.

   <!--**Subject**: Avoid excessive capitalization and punctuation, and words that are frequently used by spammers ("Win", "Free", etc.).-->
* [Personnalisation et optimisation de l’heure d’envoi](#perso-send-time-optimization) : la personnalisation du contenu et la définition d’une heure d’envoi par destinataire augmentent les chances d’ouverture de votre message.
* Images et texte : respectez un ratio texte/images correct (par exemple, 60 % de texte et 40 % d’images).
* [Lien de désinscription](#opt-out) et landing page correspondante : le lien de désinscription est indispensable. Il doit être visible et valide. En outre, le formulaire doit être fonctionnel.
* Prévisualisation : utilisez les outils fournis par Adobe Campaign pour vérifier et optimiser le contenu de votre email ([Analyse anti-spam](#anti-spam-analysis), [Rendu des emails](#message-responsiveness)).

Pour obtenir des conseils supplémentaires sur l’optimisation de la délivrabilité lors de la conception du contenu, consultez le [Guide des bonnes pratiques relatives à la délivrabilité d’Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/content-best-practices-for-optimal-delivery.html?lang=fr).

>[!NOTE]
>
>Pour plus d’informations sur la modification du contenu des emails, consultez la [Présentation du concepteur d’email](../../designing/using/designing-content-in-adobe-campaign.md) et les [Bonnes pratiques de conception de messages](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices).

## Nom et adresse de l’expéditeur {#sender-name}

Certains FAI vérifient la validité de l’adresse de l’expéditeur (**[!UICONTROL De]**) avant d’accepter les messages. Une adresse mal formée peut entraîner son rejet par le serveur de réception.

![](assets/delivery_content_edition16.png)

Assurez-vous qu’une adresse correcte est bien renseignée au niveau de l’instance ou dans les scénarios les plus couramment utilisés. Pour ce faire, contactez votre administrateur.

Pour plus d’informations à ce sujet, consultez la section [Définition de l’expéditeur d’un email](../../designing/using/subject-line.md#email-sender).

## Personnalisation et optimisation de l’heure d’envoi {#perso-send-time-optimization}

Pour améliorer l’expérience de vos destinataires et les inciter à ouvrir votre email, Adobe Campaign vous permet de personnaliser vos messages. Pour plus d’informations à ce sujet, consultez [cette section](../../designing/using/personalization.md).

Pour améliorer le taux d’ouverture de vos messages, vous pouvez également définir manuellement une heure d’envoi par destinataire. Dans la mesure du possible, chaque profil recevra le message à la date et à l’heure spécifiées. Voir à ce propos la section [Optimiser l&#39;heure d&#39;envoi](../../sending/using/optimizing-the-sending-time.md).

## Lien et formulaire d’exclusion {#opt-out}

Par défaut, une règle de typologie vérifie au moment de l&#39;analyse qu&#39;un lien de désinscription est bien présent dans le contenu d&#39;une diffusion et génère un avertissement en cas d&#39;absence. Pour plus d’informations sur la gestion des liens, consultez [cette section](../../designing/using/links.md).

Vous devez vérifier le bon fonctionnement du lien de désinscription avant chaque envoi. Par exemple, lors de l’[envoi du BAT](../../sending/using/sending-proofs.md), assurez-vous que le lien est valide, que le formulaire est en ligne et que sa validation active bien les cases **[!UICONTROL Ne plus contacter]**. Cette vérification doit être systématique, car on ne peut pas exclure une erreur humaine dans la saisie du lien ou dans la modification du formulaire. Pour plus d’informations sur la gestion de l’opt-in et de l’opt-out, consultez [cette section](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md).

![](assets/optin_landingpage_3.png)

Au cas où un problème empêchant la désinscription ne serait détecté qu’après le démarrage de la diffusion, il sera toutefois possible de désinscrire manuellement (à l’aide d’une mise à jour en masse, par exemple) les destinataires qui ont cliqué sur le lien de désinscription, même s’ils n’ont pas pu confirmer ce choix.

De manière générale, n’essayez pas de faire obstacle aux destinataires qui souhaitent se désinscrire en leur demandant de remplir des champs tels que leur adresse email ou leur nom, par exemple. La landing page de désinscription ne doit comporter qu’un seul bouton de validation.

Demander une confirmation supplémentaire n’est pas fiable, car un utilisateur peut disposer de deux adresses email redirigées vers la même boîte (par exemple : prénom.nom@club.com et prénom.nom@internet-club.com). Si le profil est capable de se souvenir uniquement de la première adresse et souhaite se désinscrire via un message envoyé à l’autre, le formulaire refusera cette adresse car l’identifiant chiffré et l’adresse email saisie ne correspondront pas.

## Analyse anti-spam {#anti-spam-analysis}

L&#39;éditeur de messages d&#39;Adobe Campaign intègre une **Analyse anti-spam** qui permet d&#39;attribuer un score aux emails afin de déterminer si un message risque d&#39;être considéré comme indésirable par les outils anti-spam utilisés à sa réception. Voir à ce propos la section [Prévisualiser un message](../../sending/using/previewing-messages.md).

Dans l&#39;éditeur de contenus des messages, cliquez sur **[!UICONTROL Prévisualiser]**. Un message vous avertit si l&#39;analyse anti-spam a détecté un risque élevé pour le message. Pour afficher les détails, cliquez sur **[!UICONTROL Analyse anti-spam]**.

![](assets/sending_anti-spam_analysis.png)

## Rendu des e-mails {#message-responsiveness}

Avant d’envoyer votre message, vous pouvez tester sa réactivité en vérifiant son apparence sur différents appareils. Vous vous assurez ainsi que son affichage sera optimal sur divers clients web, webmails et appareils.

![](assets/inbox_rendering_report_3.png)

Pour vous aider, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez visualiser l&#39;affichage du message envoyé dans les différents contextes de réception.

Voir à ce propos la section [Rendu des emails](../../sending/using/email-rendering.md).
