---
title: Contrôle de la délivrabilité dans Adobe Campaign Standard
description: Utilisez les outils proposés par Adobe Campaign Standard pour surveiller la délivrabilité de votre plateforme.
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
source-git-commit: 1d5bb21ab16df87e268b9eabe92965be1b052556

---


# Contrôle de la délivrabilité{#monitor-deliverability}

Vous trouverez ci-dessous des informations détaillées sur le rapport **[!UICONTROL de débit]** de livraison ainsi que sur les différents outils de surveillance proposés par Adobe Campaign. Voici quelques directives supplémentaires sur le suivi de la délivrabilité :
* Vérifiez régulièrement le débit de livraison pour l'ensemble de la plate-forme pour vérifier s'il est conforme à la configuration initiale.
* Vérifiez que les tentatives sont correctement configurées (30 minutes pour la période de nouvelle tentative et plus de 20 tentatives) dans les modèles de remise.
* Vérifiez régulièrement que la boîte aux lettres de rebond est accessible et que le compte n’est pas sur le point d’expirer.
* Vérifiez chaque débit de remise pour vous assurer qu’il est cohérent avec la validité du contenu de remise (ex. Les "ventes Flash" doivent être livrées en quelques minutes et non en quelques jours).
* Lors de l’utilisation d’ondes, vérifiez que chaque onde dispose de suffisamment de temps pour se terminer avant que la prochaine ne soit déclenchée.
* Vérifiez que le nombre d’erreurs et de nouvelles mises en quarantaine est cohérent avec les autres livraisons.
* Consultez attentivement les journaux de livraison en détail pour vérifier le type d'erreurs surlignées (liste grise ou noire, problèmes DNS, règles anti-spam, etc...).

## Débit des diffusions (Delivery throughput){#delivery-throughput}

Ce rapport contient des informations sur le débit de remise de l’ensemble de la plate-forme pendant une période donnée afin de mesurer la vitesse de remise des messages.

Pour plus d’informations sur ce sujet, reportez-vous à la section [Débit de livraison](../../reporting/using/delivery-throughput.md).

![](assets/delivery_reports_1.png)

Vous pouvez configurer les valeurs affichées en modifiant l’échelle de temps.

D’autres rapports sont disponibles, tels que le résumé **[!UICONTROL de la]** livraison ou les **[!UICONTROL résultats non livrables et les rebonds]**. Pour plus d’informations, voir Rapports [](../../reporting/using/about-dynamic-reports.md)dynamiques.

## Surveillance des livraisons {#monitoring-deliveries}

Le tableau de bord des messages vous donne accès aux journaux de diffusion : **[!UICONTROL Envoi de journaux]**, de journaux **** d’exclusion, de causes **[!UICONTROL d’exclusion, de journaux de]****[!UICONTROL suivi et d’URLsuivies.]****** Ils indiquent les détails de l’envoi, la cible qui a été exclue et la raison pour laquelle, ainsi que les informations de suivi telles que les ouvertures et les clics.

Pour plus d’informations à ce sujet, voir [Surveillance d’une diffusion](../../sending/using/monitoring-a-delivery.md).

![](assets/sending_delivery1.png)

## Recevoir des alertes {#receiving-alerts}

La fonctionnalité **[!UICONTROL Alertes de diffusion]est un système de gestion des alertes qui permet à un groupe d'utilisateurs de recevoir automatiquement des notifications contenant des informations sur l'exécution de leurs diffusions.**

Pour plus d’informations, voir [Réception d’alertes en cas](../../sending/using/receiving-alerts-when-failures-happen.md)d’échec.

## Signal indésirable {#signal-spam}

Signal Spam est un service français qui offre des rapports anonymisés en boucle de rétroaction pour les FAI français (Orange, SFR).

Ce service vous permet de suivre la réputation des FAI français et de suivre l'évolution de l'activité des clients.

Signal Spam fournit également des plaintes directes aux utilisateurs finaux qui se connectent via une interface dédiée. Ces plaintes sont ensuite mises en quarantaine à partir de la base de données des adresses électroniques.

## 250ok {#solution-250ok}

250ok est une solution de surveillance qui fournit des indicateurs de propriété intellectuelle, de liste noire des domaines et de réputation.

Les informations fournies sont en temps réel, ce qui permet une assistance proactive. 250ok offre une solution complémentaire aux outils internes de délivrabilité d’Adobe.
