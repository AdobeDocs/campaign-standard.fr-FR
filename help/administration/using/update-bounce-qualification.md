---
solution: Campaign Standard
product: campaign
title: Mettre à jour la qualification des rebonds après une panne de fournisseur de services Internet
description: Découvrez comment mettre à jour la qualification de rebond après une panne de fournisseur de services Internet.
audience: delivery
content-type: reference
topic-tags: monitoring-deliveries
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
translation-type: tm+mt
source-git-commit: f58a6d067a562e5e157e249e6b97c02669caf3a5
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 1%

---

# Mettre à jour la qualification de rebond après une panne de fournisseur de services Internet {#update-bounce-qualification.md}

Si vous n&#39;exécutez PAS la dernière version de Campaign, cette section peut s&#39;appliquer à vous. Vérifiez avec votre représentant Adobe Campaign.

## Contexte

En cas de panne d&#39;un fournisseur de services Internet, les courriers électroniques envoyés via Campaign ne peuvent pas être correctement envoyés à leur destinataire : ces courriels seront incorrectement marqués comme rebonds.

En décembre 2020, un problème mondial à Gmail a entraîné l&#39;envoi incorrect de messages électroniques à des adresses de messagerie Gmail valides, rebondissant de manière irréversible en tant qu&#39;adresses de messagerie non valides par les serveurs Gmail avec le rebond suivant la réponse : *&quot;550-5.1.1 Le compte de messagerie que vous avez tenté d&#39;atteindre n&#39;existe pas.&quot;*

Google a déclaré que les pannes et interruptions de Gmail qui ont causé ce problème ont commencé le 14 décembre à 6h55 et se sont terminées à 18h09 HNE le 15 décembre. Notre analyse de données a également montré un pic très court des rebonds Gmail à 2h06 HNE le 16 décembre, la majorité se produisant le 15 décembre entre 14h00 HNE et 18h30 HNE.

>[!NOTE]
>
>Vous pouvez vérifier le Tableau de bord d’état de Google Workspace sur [cette page](https://www.google.com/appsstatus#hl=en&amp;v=status).


Selon la logique standard de gestion des rebonds, Adobe Campaign a automatiquement ajouté ces destinataires à la liste de quarantaine avec un paramètre **[!UICONTROL Status]** de **[!UICONTROL Quarantaine]**. Pour corriger ce problème, vous devez mettre à jour votre table de quarantaines dans Campaign en recherchant et en supprimant ces destinataires ou en modifiant leur **[!UICONTROL État]** en **[!UICONTROL Valide]** afin que le processus de nettoyage de nuit les supprime.

Pour trouver les destinataires qui ont été affectés par ce problème Gmail, ou au cas où cela se reproduirait avec un autre FAI, veuillez voir les instructions ci-dessous.

## Processus de mise à jour

Vous devrez exécuter une requête sur votre table de quarantaine pour filtrer tous les destinataires Gmail (ou autres FAI) qui ont été potentiellement affectés par la panne afin qu&#39;ils puissent être supprimés de la liste de quarantaine et inclus dans les futures diffusions de messagerie Campaign.

En fonction du calendrier de l&#39;incident, voici les lignes directrices recommandées pour cette requête.

>[!IMPORTANT]
>
>Ces dates/heures sont basées sur le fuseau horaire standard de l’Est (EST). Veuillez ajuster le fuseau horaire de votre instance.

Pour les instances Campaign contenant des informations de réponse de rebond SMTP dans le champ **[!UICONTROL Texte d’erreur]** de la liste de quarantaine :

* **Le texte d’erreur (texte de la quarantaine)** contient &quot;550-5.1.1 Le compte de messagerie que vous avez tenté d’atteindre n’existe pas&quot; ET le texte d’ **erreur (texte de la quarantaine)** contient &quot;support.google.com&quot; **
* **Etat de la mise à jour (@lastModified)** le ou après le 14/12/2020 6:55:00
* **Etat de la mise à jour (@lastModified)** le ou avant le 16/12/2020 6:00:00

Une fois que vous disposez de la liste des destinataires concernés, vous pouvez soit les définir sur l&#39;état **[!UICONTROL Valid]** afin qu&#39;ils soient supprimés de la liste de quarantaine par le processus de nettoyage de la base de données ****, soit simplement les supprimer de la table.

**Rubriques connexes :**
* [Comprendre les échecs de Diffusion](../../sending/using/understanding-delivery-failures.md)
* [Qualification des emails bounce  ](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
