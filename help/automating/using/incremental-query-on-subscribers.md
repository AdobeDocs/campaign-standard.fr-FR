---
title: Requête incrémentale sur les abonnés à un service
description: L’exemple suivant montre comment configurer une activité de Requête incrémentale pour filtrer les abonnés à un service.
page-status-flag: never-activated
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 81%

---


# Incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

L&#39;exemple suivant illustre le paramétrage d&#39;une activité de **[!UICONTROL Requête incrémentale]** visant à filtrer les profils de la base Adobe Campaign qui sont abonnés au service **Newsletter Running**, afin de leur envoyer un email de bienvenue contenant un code promotion.

Le workflow est construit de la manière suivante :

![](assets/incremental_query_example1.png)

* Un [Planificateur](../../automating/using/scheduler.md), afin que le workflow s&#39;exécute chaque lundi à 6h.

   ![](assets/incremental_query_example2.png)

* Une [Requête incrémentale](../../automating/using/incremental-query.md), permettant de cibler tous les abonnés actuels lors de la première exécution, puis uniquement les nouveaux abonnés de la semaine lors des exécutions suivantes.

   ![](assets/incremental_query_example3.png)

* Une [Diffusion Email](../../automating/using/email-delivery.md). Le workflow est exécuté une fois par semaine, mais vous pouvez agréger les emails envoyés ainsi que les résultats par mois, par exemple pour générer des rapports portant sur un mois entier et non une seule semaine.

   Pour cela, choisissez ici de créer un **[!UICONTROL Email récurrent]** regroupant les emails et les résultats **[!UICONTROL Par mois]**.

   Définissez le contenu de votre email, en insérant le code promotion de bienvenue. Pour plus d&#39;informations sur ce sujet, reportez-vous aux sections [Définition du contenu](../../designing/using/personalization.md) des courriels.

Lancez alors l&#39;exécution du workflow. Chaque semaine les nouveaux abonnés recevront l&#39;email de bienvenue avec le code promotion.
