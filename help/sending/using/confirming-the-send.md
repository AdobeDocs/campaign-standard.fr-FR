---
solution: Campaign Standard
product: campaign
title: Confirmer l'envoi
description: Découvrez comment finaliser la préparation des messages.
audience: sending
content-type: reference
topic-tags: sending-and-tracking-messages
context-tags: delivery,deployment,back
translation-type: tm+mt
source-git-commit: 8c636ec7a35e9c34210bbb04b1b13aaa6a431345
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 100%

---


# Confirmer l&#39;envoi{#confirming-the-send}

Une fois que la préparation de vos messages est terminée et que les étapes de validation ont été réalisées, vous pouvez démarrer l&#39;envoi. Pour plus d&#39;informations sur la préparation des messages, consultez la section [Préparer l&#39;envoi](../../sending/using/preparing-the-send.md).

Seuls les utilisateurs qui détiennent le rôle **[!UICONTROL Démarrer des diffusions]** peuvent confirmer l&#39;envoi. Voir à ce propos la section [Liste des rôles](../../administration/using/list-of-roles.md).

<!--Users without this role will see the following message: 

![](assets/confirm_delivery_2.png)-->

## Envoyer le message {#sending-message}

Une fois la préparation terminée, suivez les étapes ci-dessous pour envoyer votre message.

1. Cliquez sur le bouton **[!UICONTROL Confirmer l&#39;envoi]** situé dans la barre d&#39;actions du message.

   ![](assets/confirm_delivery.png)

1. Finalisez l’envoi en cliquant sur le bouton **[!UICONTROL OK]**.

   ![](assets/confirm_delivery1.png)

1. Patientez pendant l’envoi du message. La zone **[!UICONTROL Déploiement]** affiche la progression de l&#39;envoi.

>[!NOTE]
>
>Si le message est planifié, il sera envoyé à l&#39;heure d&#39;envoi. Pour plus d&#39;informations sur la planification des messages, consultez [cette section](../../sending/using/about-scheduling-messages.md).

Si vous utilisez une diffusion récurrente sans période d&#39;agrégation, vous pouvez demander confirmation avant l&#39;envoi de la diffusion. Pour ce faire, pendant la configuration de votre message, ouvrez la zone **[!UICONTROL Planning]** du tableau de bord de diffusion, puis activez l&#39;option dédiée.

![](assets/confirmation_recurring_deliveries.png)

## Comprendre les indicateurs de message {#message-indicators}

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

Si les KPI sont trop longs à se mettre à jour ou ne prennent pas en compte les résultats à partir des logs d&#39;envoi, cliquez sur le bouton **[!UICONTROL Calculer les statistiques]** dans la fenêtre **[!UICONTROL Déploiement]**.

![](assets/sending_delivery7.png)

Le message peut être affiché dans l’historique de l’un des profils ciblés. Voir à ce sujet la section [Profil client intégré](../../audiences/using/integrated-customer-profile.md).

Une fois un message envoyé, vous pouvez suivre le comportement des destinataires et le surveiller pour mesurer son impact. Voir à ce propos les sections suivantes :

* [Tracker les messages](../../sending/using/tracking-messages.md)
* [Contrôler une diffusion](../../sending/using/monitoring-a-delivery.md)

### Rapports de réussite de diffusion {#delivered-status-report}

>[!NOTE]
>
>Cette section s’applique uniquement au canal email.

Dans la vue **[!UICONTROL Résumé]** de chaque email, le pourcentage de **[!UICONTROL Diffusion]** débute à 100 %, puis diminue progressivement tout au long de la [période de validité](../../administration/using/configuring-email-channel.md#validity-period-parameters) de la diffusion, à mesure que les bounces soft et hard sont rapportés<!--from the Enhanced MTA to Campaign-->.

En effet, tous les messages s&#39;affichent sous la forme **[!UICONTROL Envoyé]** dans les [logs d&#39;envoi](../../sending/using/monitoring-a-delivery.md#sending-logs) dès qu&#39;ils sont correctement relayés de Campaign vers le MTA (Message Transfer Agent) amélioré. Ils restent dans ce statut à moins ou jusqu’à ce qu’un [bounce](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons) pour ce message soit communiqué de nouveau de la MTA améliorée à Campaign.

Lorsque les messages hard bounce sont renvoyés à partir du MTA amélioré, leur état passe de **[!UICONTROL Envoyé]** à **[!UICONTROL Échec]** et le pourcentage **[!UICONTROL Diffusé]** est réduit en conséquence.

Lorsque les messages soft bounces sont renvoyés à partir du MTA amélioré, ils apparaissent toujours sous la forme **[!UICONTROL Envoyé]** et le pourcentage **[!UICONTROL Diffusé]** n’est pas encore mis à jour. L&#39;envoi des messages soft bounces est ensuite [réessayé](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure) tout au long de la période de validité de la diffusion :

* Si une nouvelle tentative a réussi avant la fin de la période de validité, l’état du message reste **[!UICONTROL Envoyé]** et le pourcentage **[!UICONTROL Diffusé]** reste inchangé.

* Dans le cas contraire, l’état devient **[!UICONTROL Échec]** et le pourcentage **[!UICONTROL Diffusé]** est réduit en conséquence.

Par conséquent, vous devez attendre la fin de la période de validité pour voir le pourcentage final **[!UICONTROL Diffusé]** et le nombre final de messages réellement **[!UICONTROL Envoyés]** et en **[!UICONTROL Échec]**.

### Service de commentaires par email (bêta) {#email-feedback-service}

Grâce à la fonctionnalité de service de commentaires par email (EFS), l’état de chaque email est rapporté avec précision, car les commentaires sont capturés directement à partir de l’agent du MTA amélioré.

>[!IMPORTANT]
>
>Le service de commentaires par email est actuellement disponible en version bêta.

Une fois la diffusion lancée, le pourcentage **[!UICONTROL Diffusé]** n’est plus modifié lorsque le message est relayé de Campaign vers le MTA amélioré.

![](assets/efs-sending.png)

Les logs de diffusion affichent le statut **[!UICONTROL En attente]** pour chaque adresse ciblée.

![](assets/efs-pending.png)

Lorsque le message est effectivement diffusé aux profils ciblés et que ces informations sont rapportées en temps réel à partir du MTA amélioré, les logs de diffusion affichent l’état **[!UICONTROL Envoyé]** pour chaque adresse qui a reçu le message avec succès. Le pourcentage **[!UICONTROL Diffusé]** est augmenté en conséquence à chaque diffusion réussie.

Lorsque les messages hard bounces sont renvoyés du MTA amélioré, leur état de log passe de **[!UICONTROL En attente]** à **[!UICONTROL Échec]** et le pourcentage **[!UICONTROL Bounces + erreurs]** est augmenté en conséquence.

Lorsque les messages soft bounces à l’écran sont renvoyés du MTA amélioré, leur état de log passe également de **[!UICONTROL En attente]** à **[!UICONTROL Échec]** et le pourcentage **[!UICONTROL Bounces + erreurs]** est augmenté en conséquence. Le pourcentage **[!UICONTROL Diffusé]** reste inchangé. L&#39;envoi des messages soft bounces est ensuite réessayé tout au long de la [période de validité](../../administration/using/configuring-email-channel.md#validity-period-parameters) de la diffusion :

* Si une nouvelle tentative a réussi avant la fin de la période de validité, l’état du message passe à **[!UICONTROL Envoyé]** et le pourcentage **[!UICONTROL Diffusé]** est augmenté en conséquence.

* Sinon, l’état reste **[!UICONTROL Échec]**. Les pourcentages **[!UICONTROL Diffusé]** et **[!UICONTROL Bounces + erreurs]** restent inchangés.

>[!NOTE]
>
>Pour plus d’informations sur les bounces hard et soft, voir [cette section](../../sending/using/understanding-delivery-failures.md#delivery-failure-types-and-reasons).
>
>Pour plus d’informations sur les reprises après une défaillance temporaire d’une diffusion, voir [cette section](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure).

<!--Soft-bouncing messages increment an error counter. When the error counter reaches the limit threshold or when the validity period is over, the address goes into quarantine and the status remains as **[!UICONTROL Failed]**. For more on conditions for sending an address to quarantine, see [this section](../../help/sending/using/understanding-quarantine-management.md#conditions-for-sending-an-address-to-quarantine).-->

### Modifications introduites par EFS {#changes-introduced-by-efs}

Le tableau ci-dessous présente les modifications des KPI clés et de l’état des logs d&#39;envoi introduites par la fonctionnalité EFS.

| Étape du <br>processus d’envoi | Résumé des KPI<br>SANS EFS | État des logs d&#39;envoi<br>SANS EFS | Résumé des KPI<br>AVEC EFS | État des logs d&#39;envoi<br>AVEC EFS |
|--- |--- |--- | --- | --- |
| Le message est relayé avec succès de Campaign vers le MTA amélioré | <ul><li>Le pourcentage **[!UICONTROL Diffusés]** commence à 100 %</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** commence à 0 %</li></ul> | Envoyés | <ul><li>Le pourcentage **[!UICONTROL Diffusés]** commence à 0 %</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** commence à 0 %</li></ul> | En attente |
| Les rapports sur les messages hard bounces sont renvoyés à partir du MTA amélioré. | <ul><li>Le pourcentage **[!UICONTROL Diffusés]** est diminué en conséquence.</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** est augmenté en conséquence</li></ul> | En échec | <ul><li>Aucun changement dans le pourcentage **[!UICONTROL Diffusés]**</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** est augmenté en conséquence</li></ul> | En échec |
| Les messages soft bounces sont renvoyés à partir du MTA amélioré. | <ul><li>Aucun changement dans le pourcentage **[!UICONTROL Diffusés]**</li><li>Aucun changement dans le pourcentage **[!UICONTROL Bounces + erreurs]**</li></ul> | Envoyés | <ul><li>Aucun changement dans le pourcentage **[!UICONTROL Diffusés]**</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** est augmenté en conséquence</li></ul> | En échec |
| Les reprises de messages soft bounces réussissent | <ul><li>Aucun changement dans le pourcentage **[!UICONTROL Diffusés]**</li><li>Aucun changement dans le pourcentage **[!UICONTROL Bounces + erreurs]**</li></ul> | Envoyés | <ul><li>Le pourcentage **[!UICONTROL Diffusés]** est augmenté en conséquence.</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** est diminué en conséquence.</li></ul> | Envoyés |
| Échec des reprises de messages soft bounces | <ul><li>Le pourcentage **[!UICONTROL Diffusés]** est diminué en conséquence.</li><li>Le pourcentage **[!UICONTROL Bounces + erreurs]** est augmenté en conséquence</li></ul> | En échec | <ul><li> Aucun changement dans le pourcentage **[!UICONTROL Diffusés]** </li><li> Aucun changement dans le pourcentage **[!UICONTROL Bounces + erreurs]** </li></ul> | En échec |
