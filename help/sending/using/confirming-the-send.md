---
title: Confirmer l'envoi
description: Découvrez comment finaliser la préparation des messages.
page-status-flag: never-activated
uuid: 1eaecb32-ffd2-45d0-a8b4-f97bee59a1bd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
discoiquuid: 8bb160b1-7de9-4c1f-bb89-b2e5fdafed41
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 100%

---


# Confirmer l&#39;envoi{#confirming-the-send}

Une fois que la préparation de vos messages est terminée et que les étapes de validation ont été réalisées, vous pouvez démarrer l&#39;envoi. Pour plus d&#39;informations sur la préparation des messages, consultez la section [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md).

Seuls les utilisateurs qui détiennent le rôle **[!UICONTROL Démarrer des diffusions]** peuvent confirmer l&#39;envoi. Voir à ce propos la section [Liste des rôles](../../administration/using/list-of-roles.md).

Le message suivant s&#39;affiche pour les utilisateurs qui ne possèdent pas ce rôle :

![](assets/confirm_delivery_2.png)

Pour envoyer votre diffusion, cliquez sur le bouton **[!UICONTROL Confirmer l&#39;envoi]** dans la barre d&#39;actions du message.

![](assets/confirm_delivery.png)

Validez l&#39;envoi en cliquant sur **[!UICONTROL OK]**.

![](assets/confirm_delivery1.png)

Le message est en cours d&#39;envoi.

>[!NOTE]
>
>Si le message est planifié, il sera envoyé à l&#39;heure d&#39;envoi. Pour plus d&#39;informations sur la planification des messages, consultez [cette section](../../sending/using/about-scheduling-messages.md).

Si vous utilisez une diffusion récurrente sans période d&#39;agrégation, vous pouvez demander confirmation avant l&#39;envoi de la diffusion. Pour ce faire, ouvrez la zone **[!UICONTROL Planning]** du tableau de bord de diffusion, puis activez l&#39;option dédiée.

![](assets/confirmation_recurring_deliveries.png)

La zone **[!UICONTROL Déploiement]** affiche la progression de l&#39;envoi.

Lorsque le message est envoyé aux contacts, la zone **[!UICONTROL Déploiement]** affiche vos données d&#39;indicateurs de performance clés (KPI) avec :

* le nombre de messages à envoyer,
* le nombre de messages envoyés,
* le pourcentage de messages délivrés,
* le pourcentage de bounces et d&#39;erreurs,
* le pourcentage de messages ouverts,
* le pourcentage de clics dans les messages (pour les emails).

   >[!NOTE]
   >
   >Le **[!UICONTROL Taux d&#39;ouverture]** et le **[!UICONTROL Taux de clics]** sont mis à jour toutes les heures.

![](assets/sending_delivery.png)

Si les indicateurs de performance clés sont trop longs à se mettre à jour ou ne prennent pas en compte les résultats à partir des envois, cliquez sur le bouton **[!UICONTROL Calculer les statistiques]** dans la fenêtre **[!UICONTROL Déploiement]**.

![](assets/sending_delivery7.png)

Le message peut être visualisé dans l&#39;historique d&#39;un des profils clients faisant partie de l&#39;audience. Voir à ce sujet la section [Profil client intégré](../../audiences/using/integrated-customer-profile.md).

Une fois un message envoyé, vous pouvez suivre le comportement des destinataires et le surveiller afin de mesurer son impact. Voir à ce propos les sections suivantes :

* [Tracker les messages](../../sending/using/tracking-messages.md)
* [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md)

