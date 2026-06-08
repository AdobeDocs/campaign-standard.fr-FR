---
title: Diffusion d’anniversaire
description: Cet exemple représente un workflow d'anniversaire. Un email est envoyé chaque jour aux profils dont l'anniversaire a lieu le jour même.
audience: automating
content-type: reference
topic-tags: channel-activities
context-tags: delivery,workflow,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 535ddbce-d8ba-4578-9e37-10604291c95d
TQID: https://experienceleague.adobe.com/LXiYfz5VXaY7j0pOHWUCGJzp5F4bCsSCmFzEqsQG18E
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 174
ht-degree: 100%

---

# Diffusion d’anniversaire {#birthday-delivery}

![](assets/wkf_delivery_example_1.png)

Cet exemple représente un workflow d&#39;anniversaire. Un email est envoyé chaque jour aux profils dont l&#39;anniversaire a lieu le jour même.

Pour créer le workflow, procédez comme suit :

* Le [Planificateur](../../automating/using/scheduler.md) permet de lancer le workflow chaque jour à 8h00.

  ![](assets/wkf_delivery_example_2.png)

* La [Requête](../../automating/using/query.md) permet de calculer à chaque exécution du workflow les profils dont c&#39;est l&#39;anniversaire et dont l&#39;adresse email est renseignée. Le calcul de l&#39;anniversaire est réalisé grâce à un filtre prédéfini disponible dans la palette de l&#39;outil d&#39;édition de requêtes.

  ![](assets/wkf_delivery_example_3.png)

* La [Diffusion Email](../../automating/using/email-delivery.md) est de type récurrent. Les envois sont agrégés par mois. Ainsi, tous les emails envoyés dans un mois sont agrégés dans une seule vue. En un an, 365 diffusions sont donc exécutées mais sont regroupées dans 12 vues (aussi appelés **exécutions récurrentes**) dans l&#39;interface d&#39;Adobe Campaign. Le détail des historiques et des rapports est ainsi affiché sur une base mensuelle et non pour chaque envoi.

  ![](assets/wkf_delivery_example_4.png)
