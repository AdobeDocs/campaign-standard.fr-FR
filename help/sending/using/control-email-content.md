---
title: Contrôle du contenu des courriers électroniques dans Adobe Campaign Standard
description: Découvrez comment améliorer la délivrabilité dans Adobe Campaign Standard lors de la modification du contenu de votre courrier électronique.
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
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# Contrôle du contenu des courriers électroniques{#control-email-content}

Pour améliorer le taux de remise des courriers électroniques et veiller à ce que vos courriers électroniques parviennent à vos destinataires, ces derniers doivent respecter un certain nombre de règles.

* **Nom et adresse** de l'expéditeur : L'adresse doit identifier explicitement l'expéditeur.Le domaine doit être détenu et enregistré par l'expéditeur.Le registre des domaines ne doit pas être privatisé.
* **Objet**: Evitez les majuscules et les mots fréquemment utilisés par les spammeurs ("Win", "Free", etc.).
* **Personnalisez votre adresse électronique**: La personnalisation du courrier électronique augmente les chances d’ouverture du message.
* **Images et texte**: Respectez un rapport texte/image correct (par exemple, 60 % du texte et 40 % des images).
* **Lien de désabonnement et page** d’entrée : Le lien de désabonnement est essentiel.Il doit être visible et valide et le formulaire doit être fonctionnel.
* **Utilisez les outils** proposés par Adobe Campaign pour optimiser le contenu de votre email (analyse de diffusion, analyse anti-spam).

Pour plus d’informations sur la modification du contenu d’un courrier électronique, consultez la présentation [du concepteur de](../../designing/using/designing-content-in-adobe-campaign.md) courrier électronique et les bonnes pratiques [en matière de conception de](../../designing/using/designing-content-in-adobe-campaign.md#content-design-best-practices)message.

## Nom et adresse de l’expéditeur {#sender-name}

Certains FAI vérifient la validité de l'adresse d'expéditeur (From) avant d'accepter les messages. Une adresse erronée peut causer un refus de la part du serveur receveur. Vous devez vous assurer qu’une adresse correcte est donnée au niveau de l’instance ou dans les scénarios les plus fréquemment utilisés. Contactez votre administrateur.

![](assets/delivery_content_edition16.png)

Pour plus d’informations, voir [Personnalisation du nom](../../designing/using/personalization.md#personalizing-the-sender)de l’expéditeur.

## Objet {#subject-line}

Lors de l'édition d'un email, vous pouvez tester différents objets et obtenir une estimation de son taux d'ouverture avant l'envoi. For more on this, see [Testing the subject line of an email](../../sending/using/testing-subject-line-email.md).

![](assets/predictive_subject_line_example.png)

Pour plus d’informations sur la définition de l’objet d’un courrier électronique, voir [cette section](../../designing/using/subject-line.md).

## Optimisation de l'heure d'envoi {#send-time-optimization}

Pour améliorer le taux de succès de vos messages, vous pouvez définir manuellement une heure d'envoi par destinataire. Dans la mesure du possible, chaque profil recevra le message à la date et à l'heure spécifiées.

Pour plus d’informations, voir [Optimisation du temps](../../sending/using/optimizing-the-sending-time.md)d’envoi.

## Lien et formulaire de désinscription {#opt-out}

Par défaut, une règle de typologie vérifie au moment de l'analyse qu'un lien de désinscription est bien présent dans le contenu d'une diffusion et génère un avertissement en cas d'absence.

Il faut vérifier du début à la fin le bon fonctionnement du lien de désinscription avant chaque envoi. Par exemple, lors de l’envoi de la preuve, assurez-vous que le lien est valide, que le formulaire est en ligne et que la validation de ce code change la valeur des cases à cocher Ne plus contacter sont cochées. Cette vérification doit être systématique car on ne peut pas exclure une erreur humaine dans la saisie du lien ou dans la modification du formulaire.

Au cas où un problème empêchant la désinscription ne serait détecté qu'après le démarrage de la diffusion, il sera toutefois possible de désinscrire manuellement (à l'aide d'une mise à jour en masse, par exemple) les destinataires qui ont cliqué sur le lien de désinscription, même s'ils n'ont pas pu ou voulu confirmer ce choix.

Sauf dans des cas particuliers, il ne faut pas tenter de freiner la désinscription en demandant à l'utilisateur de remplir certains champs comme l'email, le nom, etc. La landing page de désinscription ne devra comprendre qu'un seul bouton de validation. Demander une confirmation supplémentaire de l'email n'est pas fiable : il se peut qu'une même personne possède deux adresses email redirigées vers la même boîte (par exemple, prenom.nom@club.fr et prenom.nom@club-internet.fr). Si ce profil ne se souvient que de la première adresse et qu'il souhaite se désinscrire via un message envoyé à la seconde, le formulaire refusera la modification, car l'identifiant crypté et l'email saisi ne correspondent pas.

## Analyse anti-spam {#anti-spam-analysis}

Adobe Campaign's message editor integrates an **Anti-spam analysis** which allows you to score emails to determine whether a message runs the risk of being considered as spam by the anti-spam tools used upon receipt. For more on this, see [Previewing messages](../../sending/using/previewing-messages.md).

Dans l'éditeur de contenus des messages, cliquez sur **[!UICONTROL Prévisualiser]**. Un message vous avertit si l'analyse anti-spam a détecté un risque élevé pour le message. Pour afficher les détails, cliquez sur **Analyse anti-spam[!UICONTROL .]**

![](assets/sending_anti-spam_analysis.png)

## Vérification de la réactivité des messages {#message-responsiveness}

Avant d’envoyer votre message, vous pouvez vérifier à quoi ressemblera votre message sur différents périphériques. Cela permet de s’assurer qu’il sera affiché de manière optimale sur une variété de clients Web, de courriels Web et de périphériques.

Pour vous aider, Adobe Campaign capture le rendu et le rend disponible dans un rapport dédié. Vous pouvez visualiser l'affichage du message envoyé dans les différents contextes de réception.

Voir à ce propos la section [Rendu des emails](../../sending/using/email-rendering.md).

![](assets/inbox_rendering_report_3.png)
