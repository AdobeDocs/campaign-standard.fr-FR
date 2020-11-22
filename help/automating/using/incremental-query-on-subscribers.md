---
solution: Campaign Standard
product: campaign
title: Requête incrémentale sur les abonnés à un service
description: L’exemple ci-après montre comment configurer une activité de requête incrémentale pour filtrer les abonnés à un service.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 100%

---


# Requête incrémentale sur les abonnés à un service {#example--incremental-query-on-subscribers-to-a-service}

L’exemple ci-après illustre le paramétrage d’une activité de **[!UICONTROL Requête incrémentale]** visant à filtrer les profils de la base Adobe Campaign qui sont abonnés au service **Newsletter Running**, afin de leur envoyer un email de bienvenue contenant un code promotion.

Le workflow est construit de la manière suivante :

![](assets/incremental_query_example1.png)

* Un [Planificateur](../../automating/using/scheduler.md), afin que le workflow s’exécute chaque lundi à 6h.

   ![](assets/incremental_query_example2.png)

* Une [Requête incrémentale](../../automating/using/incremental-query.md), permettant de cibler tous les abonnés actuels lors de la première exécution, puis uniquement les nouveaux abonnés de la semaine lors des exécutions suivantes.

   ![](assets/incremental_query_example3.png)

* Une [Diffusion Email](../../automating/using/email-delivery.md). Le workflow est exécuté une fois par semaine, mais vous pouvez agréger les emails envoyés ainsi que les résultats par mois, par exemple pour générer des rapports portant sur un mois entier et non une seule semaine.

   Pour cela, choisissez ici de créer un **[!UICONTROL Email récurrent]** regroupant les emails et les résultats **[!UICONTROL Par mois]**.

   Définissez le contenu de votre email, en insérant le code promotion de bienvenue. Pour plus d’informations à ce sujet, voir les sections [Définition du contenu des emails](../../designing/using/personalization.md).

Lancez alors l’exécution du workflow. Chaque semaine les nouveaux abonnés recevront l&#39;email de bienvenue avec le code promotion.
