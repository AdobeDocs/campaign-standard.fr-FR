---
title: Requête incrémentale sur les abonnés à un service
description: L’exemple ci-après montre comment configurer une activité de requête incrémentale pour filtrer les abonnés à un service.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: incremental,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: c80ed1f6-ad8a-4448-a6df-b9881327228a
TQID: 'https://experienceleague.adobe.com/MHB1ETCecN9gQq51bSii-keTyFaYof0JtAyckFSCKQE'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 100%
---
# Requête incrémentale sur les abonnés à un service {#example--incremental-query-on-subscribers-to-a-service}

L’exemple ci-après illustre la configuration d’une activité **[!UICONTROL Requête incrémentale]** qui filtre les profils de la base de données Adobe Campaign qui sont abonnés au service **Newsletter Running**, afin de leur envoyer un e-mail de bienvenue contenant un code promotionnel.

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
