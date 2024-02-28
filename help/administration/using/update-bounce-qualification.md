---
title: Mettre à jour la qualification des rebonds après une panne d’un FAI
description: Découvrez comment mettre à jour la qualification des rebonds après une panne d’un fournisseur d’accès à Internet.
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: f81b8a3b076a6e29b697f21ea4d99fa7d5b6788c
workflow-type: ht
source-wordcount: '444'
ht-degree: 100%

---

# Mettre à jour la qualification des rebonds après une panne d’un FAI{#update-bounce-qualification.md}

## Contexte

En cas de panne d’un fournisseur d’accès à Internet, les emails envoyés par la biais de Campaign ne peuvent pas être correctement envoyés à leur destinataire : ils seront incorrectement marqués comme mails rebonds.

En décembre 2020, un problème mondial qui a affecté Gmail a entraîné des rebonds définitifs incorrects lors de l’envoi d’e-mails à des adresses Gmail valides. Les serveurs Gmail les ont incorrectement rejetés pour cause d’adresses e-mail non valides avec la réponse suivante : *« 550-5.1.1 Le compte de messagerie que vous avez tenté d’atteindre n’existe pas. »*

Google a déclaré que les pannes et interruptions de Gmail qui ont causé ce problème ont commencé le 14 décembre à 6h55 et se sont terminées à 18h09 EST le 15 décembre. Notre analyse de données a également montré un pic très court des rebonds Gmail à 2h06 EST le 16 décembre, la majorité s’étant produits le 15 décembre entre 14h00 HNE et 18h30 EST.

>[!NOTE]
>
>Vous pouvez vérifier le tableau de bord d’état de Google Workspace sur [cette page](https://www.google.com/appsstatus#hl=fr&amp;v=status).


Selon la logique standard de gestion des rebonds, Adobe Campaign a automatiquement ajouté ces destinataires à la liste de quarantaine avec un paramètre **[!UICONTROL Statut]** de **[!UICONTROL Quarantaine]**. Pour corriger ce problème, vous devez mettre à jour votre table de quarantaines dans Campaign en recherchant et en supprimant ces destinataires ou en basculant leur **[!UICONTROL Statut]** sur **[!UICONTROL Valide]** afin que le processus de nettoyage de nuit les supprime.

Pour trouver les destinataires qui ont été affectés par ce problème Gmail, ou au cas où cela se reproduirait avec un autre FAI, référez-vous aux instructions ci-dessous.

## Processus de mise à jour

Vous devrez exécuter une requête sur votre table de quarantaine pour filtrer tous les destinataires Gmail (ou autres FAI) qui ont été potentiellement affectés par la panne afin qu’ils puissent être supprimés de la liste de quarantaine et inclus dans les futures diffusions d’emails de Campaign.

En fonction du calendrier de l’incident, voici les instructions recommandées pour cette requête.

>[!IMPORTANT]
>
>Ces dates/heures sont basées sur le fuseau horaire standard de l&#39;Est (EST). Configurez le fuseau horaire de votre instance.

Pour les instances Campaign contenant des informations de réponse de rebond SMTP dans le champ **[!UICONTROL Texte d’erreur]** de la liste de quarantaine :

* **Texte d’erreur (texte de la quarantaine)** contenant « 550-5.1.1 Le compte de messagerie que vous avez tenté d’atteindre n’existe pas » ET **Texte d’erreur (texte de la quarantaine)** contenant « support.google.com » **
* **Mise à jour du statut (@lastModified)** le ou après le 14/12/2020 à 6:55:00
* **État de la mise à jour (@lastModified)** le ou avant le 16/12/2020 6:00:00

Une fois que vous disposez de la liste des destinataires concernés, vous pouvez soit leur attribuer l’état **[!UICONTROL Valide]** afin qu’ils soient supprimés de la liste de quarantaine par le processus de **[!UICONTROL nettoyage de la base de données]**, soit simplement les supprimer de la table.

**Rubriques connexes :**
* [Présentation des diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Qualification des e-mails rejetés](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
