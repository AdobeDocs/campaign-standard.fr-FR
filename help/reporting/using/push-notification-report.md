---
title: Rapport des notifications push
description: Grâce au rapport d'usine des notifications push, découvrez les performances de vos notifications push.
audience: reporting
content-type: reference
topic-tags: list-of-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: acfe0b9c-77a4-46ad-8151-7bf9c21fa4b0
TQID: 'https://experienceleague.adobe.com/Z7fXMSiDxpF6LXWMV2aYc71UvOYWlUzyOv8TS6ogS7k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c309ee4e-82e4-4f7e-b608-ef345678c34e
    internal-label: Dynamic reporting
subfeature_v2:
  - id: b3a4149f-2b3a-44d1-894e-e3ac4c77fb47
    internal-label: Reporting interface
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 100%
---
# Rapport des notifications push{#push-notification-report}

>[!CAUTION]
>
>Vous devez faire glisser les mesures **[!UICONTROL Type de message]** dans vos tableaux pour fractionner vos données en fonction de vos types de diffusion, dans ce cas des diffusions Notification push.

Le rapport **notification push** fournit des informations détaillées sur les performances marketing des notifications push dans Adobe Campaign. Ce rapport d’usine permet de comprendre comment les utilisateurs interagissent avec les notifications push, les applications mobiles et les diffusions.

Une configuration est nécessaire dans l&#39;application mobile pour mettre en œuvre le tracking des notifications push. Pour obtenir les étapes détaillées, consultez cette [page](../../administration/using/push-tracking.md).

![](assets/dynamic_report_push.png)

Chaque tableau est représenté par des nombres et des graphiques de synthèse. Les paramètres de visualisation des détails vous permettent de modifier leur affichage.

Le premier tableau **Résumé de l&#39;engagement des notifications push** est divisé en trois catégories : par jour, par application mobile et par diffusion. Il contient les données disponibles sur la réactivité du destinataire face à la diffusion :

* **[!UICONTROL Traités/envoyés]** : nombre total de notifications push envoyées.
* **[!UICONTROL Délivrés]** : nombre de notifications push envoyées avec succès, par rapport au nombre total de notifications push envoyées.
* **[!UICONTROL Impressions]** : nombre de fois qu&#39;une notification push a été diffusée sur l&#39;appareil et laissée intacte dans le centre de notification. Dans la plupart des cas, le nombre d&#39;impressions doit être similaire au nombre délivrés. Cela garantit que l&#39;appareil reçoit le message et transmet cette information au serveur.
* **[!UICONTROL Impressions uniques]** : nombre d&#39;impressions par destinataire.
* **[!UICONTROL Taux de clics]** : pourcentage d&#39;utilisateurs ayant interagi avec la notification push.
* **[!UICONTROL Taux d&#39;ouverture]** : pourcentage de notifications push ouvertes.

![](assets/dynamic_report_push_2.png)

Le deuxième tableau **Clics et ouvertures des notifications push** est divisé en trois catégories : par jour, par application mobile et par diffusion. Il contient les données disponibles sur le comportement du destinataire par diffusion :

* **[!UICONTROL Impressions]** : nombre total de notifications push vues par les destinataires.
* **[!UICONTROL Impressions uniques]** : nombre d&#39;impressions par destinataire.
* **[!UICONTROL Clic]** : nombre de fois qu&#39;une notification push a été diffusée sur l&#39;appareil et a fait l&#39;objet d&#39;un clic par l&#39;utilisateur. L&#39;utilisateur souhaitait afficher la notification, qui sera déplacée vers le tracking Ouverture push, ou l&#39;ignorer.
* **[!UICONTROL Clics uniques]** : nombre de fois où un utilisateur unique interagit avec la notification push, par exemple clics sur la notification ou le bouton.
* **[!UICONTROL Ouverture]** : nombre total de notifications push diffusées sur l&#39;appareil et ayant fait l&#39;objet d&#39;un clic par les utilisateurs ouvrant l&#39;application. Cette mesure est similaire au Clic push, sauf qu’une Ouverture push ne sera pas déclenchée si la notification a été ignorée.
* **[!UICONTROL Ouvertures uniques]** : nombre de destinataires ayant ouvert la diffusion.
