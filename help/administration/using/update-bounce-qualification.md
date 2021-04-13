---
solution: Campaign Standard
product: campaign
title: Mettre à jour la qualification des bounces après une panne de FAI
description: Découvrez comment mettre à jour la qualification des bounces après une panne de FAI.
audience: delivery
content-type: reference
topic-tags: monitoring-deliveries
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
translation-type: ht
source-git-commit: f58a6d067a562e5e157e249e6b97c02669caf3a5
workflow-type: ht
source-wordcount: '456'
ht-degree: 100%

---

# Mettre à jour la qualification des bounces après une panne de FAI {#update-bounce-qualification.md}

Si vous N&#39;exécutez PAS la dernière version de Campaign, cette section peut s&#39;appliquer à vous. Vérifiez avec votre représentant Adobe Campaign.

## Contexte

En cas de panne d&#39;un FAI, les emails envoyés via Campaign ne peuvent pas être correctement délivrés à leur destinataire : ces emails seront incorrectement marqués comme bounces.

En décembre 2020, un problème mondial lié à Gmail a entraîné l&#39;envoi d&#39;emails à des adresses email Gmail valides, caractérisées incorrectement d&#39;adresses non valides par les serveurs Gmail avec la réponse bounce suivante : *« 550-5.1.1 Le compte de messagerie que vous avez tenté d&#39;atteindre n&#39;existe pas. »*

Google a déclaré que les pannes et interruptions de Gmail qui ont causé ce problème ont commencé le 14 décembre à 6 h 55 et se sont terminées à 18 h 09 EST le 15 décembre. Notre analyse de données a également montré un pic très court des bounces Gmail à 2 h 06 EST le 16 décembre, la majorité se produisant le 15 décembre entre 14 h 00 EST et 18 h 30 EST.

>[!NOTE]
>
>Vous pouvez vérifier le Tableau de bord de statut de Google Workspace sur [cette page](https://www.google.com/appsstatus#hl=fr&amp;v=status).


Selon la logique standard de gestion des bounces, Adobe Campaign a automatiquement ajouté ces destinataires à la liste de quarantaine avec un **[!UICONTROL Statut]** de **[!UICONTROL Quarantaine]**. Pour corriger ce problème, vous devez mettre à jour votre table de quarantaine dans Campaign en recherchant et en supprimant ces destinataires ou en modifiant leur **[!UICONTROL Statut]** en **[!UICONTROL Valide]** afin que le workflow de nettoyage de nuit les supprime.

Pour trouver les destinataires qui ont été touchés par ce problème de Gmail, ou au cas où cela se reproduirait avec un autre FAI, veuillez consulter les instructions ci-dessous.

## Processus de mise à jour

Vous devrez exécuter une requête sur votre table de quarantaine pour filtrer tous les destinataires Gmail (ou autres FAI) qui ont été potentiellement touchés par la panne afin qu&#39;ils puissent être supprimés de la liste de quarantaine et inclus dans les futures diffusions email de Campaign.

En fonction du calendrier de l&#39;incident, voici les lignes directrices recommandées pour cette requête.

>[!IMPORTANT]
>
>Ces dates/heures sont basées sur le fuseau de l&#39;Heure normale de l&#39;Est américain (EST). Veuillez ajuster le fuseau horaire de votre instance.

Pour les instances Campaign contenant des informations de réponse de bounce SMTP dans le champ **[!UICONTROL Texte de l&#39;erreur]** de la liste de quarantaine :

* **Le texte de l&#39;erreur (texte de la quarantaine)** contient « 550-5.1.1 Le compte de messagerie que vous avez tenté d’atteindre n’existe pas » ET le **texte de l&#39;erreur (texte de la quarantaine)** contient « support.google.com » **
* **Statut de la mise à jour (@lastModified)** le ou après le 14/12/2020 6:55:00
* **Statut de la mise à jour (@lastModified)** le ou avant le 16/12/2020 6:00:00

Une fois que vous disposez de la liste des destinataires concernés, vous pouvez soit les définir sur le statut **[!UICONTROL Valide]** afin qu&#39;ils soient supprimés de la liste de quarantaine par le workflow de **[!UICONTROL nettoyage de la base]**, soit simplement les supprimer de la table.

**Rubriques connexes :**
* [Comprendre les diffusions en échec](../../sending/using/understanding-delivery-failures.md)
* [Qualification des emails bounce](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
