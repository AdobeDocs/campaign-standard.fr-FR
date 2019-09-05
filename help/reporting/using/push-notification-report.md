---
title: Rapport des notifications push (Push notification)
seo-title: Rapport des notifications push (Push notification)
description: Rapport des notifications push (Push notification)
seo-description: Grâce au rapport d'usine Notification push (Push notification), découvrez les performances de vos notifications push.
page-status-flag: never-activated
uuid: 5b121a37-1c09-4749-a409-6989978ddc4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: list-of-reports
discoiquuid: a425cd59-edfd-42c5-a6bd-38773c353ff0
internal: n
snippet: y
translation-type: ht
source-git-commit: 7102ed308f94985f8924a13aab2583e50b6c68e4

---


# Rapport des notifications push (Push notification){#push-notification-report}

>[!CAUTION]
>
>Vous devez faire glisser les mesures **[!UICONTROL Type de message]** dans vos tableaux pour fractionner vos données en fonction de vos types de diffusion, dans ce cas des diffusions Notification push.

Le rapport **notification push** (Push notification) fournit des informations détaillées sur les performances marketing des notifications push dans Adobe Campaign. Ce rapport d'usine permet de comprendre comment les utilisateurs interagissent avec les notifications push, les applications mobiles et les diffusions.

Une configuration est nécessaire dans l'application mobile pour mettre en œuvre le tracking des notifications push. Pour obtenir les étapes détaillées, consultez cette [page](https://helpx.adobe.com/fr/campaign/kb/push-tracking.html).

![](assets/dynamic_report_push.png)

Chaque tableau est représenté par des nombres et des graphiques de synthèse. Les paramètres de visualisation des détails vous permettent de modifier leur affichage.

Le premier tableau **Résumé d'engagement des notifications push** (Push notification Engagement Summary) est divisé en trois catégories : par jour, par application mobile et par diffusion. Il contient les données disponibles sur la réactivité du destinataire face à la diffusion :

* **[!UICONTROL Traités/envoyés]** : nombre total de notifications push envoyées.
* **[!UICONTROL Délivrés]** : nombre de notifications push envoyées avec succès, par rapport au nombre total de notifications push envoyées.
* **[!UICONTROL Impressions]** : nombre de fois qu'une notification push a été diffusée sur l'appareil et laissée intacte dans le centre de notification. Dans la plupart des cas, le nombre d'impressions doit être similaire au nombre délivrés. Cela garantit que l'appareil reçoit le message et transmet cette information au serveur.
* **[!UICONTROL Impressions uniques]** : nombre d'impressions par destinataire.
* **[!UICONTROL Taux de clics]** : pourcentage d'utilisateurs ayant interagi avec la notification push.
* **[!UICONTROL Taux d'ouverture]** : pourcentage de notifications push ouvertes.

![](assets/dynamic_report_push_2.png)

Le deuxième tableau **Clics et ouvertures des notifications push** (Push notification Clicks &amp; opens) est divisé en trois catégories : par jour, par application mobile et par diffusion. Il contient les données disponibles sur le comportement du destinataire par diffusion :

* **[!UICONTROL Impressions]** : nombre total de notifications push vues par les destinataires.
* **[!UICONTROL Impressions uniques]** : nombre d'impressions par destinataire.
* **[!UICONTROL Clic]** : nombre de fois qu'une notification push a été diffusée sur l'appareil et a fait l'objet d'un clic par l'utilisateur. L'utilisateur souhaitait afficher la notification, qui sera déplacée vers le tracking Ouverture push, ou l'ignorer.
* **[!UICONTROL Clics uniques]** : nombre de fois où un utilisateur unique interagit avec la notification push, par exemple clics sur la notification ou le bouton.
* **[!UICONTROL Ouverture]** : nombre total de notifications push diffusées sur l'appareil et ayant fait l'objet d'un clic par les utilisateurs ouvrant l'application. Cette mesure est similaire au Clic push, sauf qu'une Ouverture push ne sera pas déclenchée si la notification a été ignorée.
* **[!UICONTROL Ouvertures uniques]** : nombre de destinataires ayant ouvert la diffusion.

