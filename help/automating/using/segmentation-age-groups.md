---
title: Segmentation en fonction des tranches d’âge
description: Cette page présente une segmentation de profils de la base de données en fonction de leur tranche d’âge. Le but du workflow est d'envoyer un email distinct pour chaque tranche d'âge.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
TQID: https://experienceleague.adobe.com/LkH1qmElMwEn6JGmUaWj7Qpv7arSvLAZixbfJYTi2NQ
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 210
ht-degree: 100%

---

# Segmentation en fonction des tranches d&#39;âge {#segmentation-age-groups}

L&#39;exemple suivant illustre une segmentation de profils de la base de données en fonction de leur tranche d&#39;âge.

Le but du workflow est d&#39;envoyer un email distinct pour chaque tranche d&#39;âge. En considérant que ce workflow fait partie d&#39;une campagne de test, chaque segment ne pourra contenir qu&#39;un maximum de 100 profils, sélectionnés aléatoirement, afin d&#39;utiliser des audiences à la fois limitées et représentatives.

![](assets/wkf_segment_example_4.png)

Le workflow est constitué des éléments suivants :

* Une [activité Planificateur](../../automating/using/segmentation.md) permettant de définir la date d&#39;exécution du workflow.
* Une activité [Requête](../../automating/using/query.md) permettant de cibler les profils de personnes dont la date de naissance et l&#39;adresse email sont renseignées.
* Une activité [Segmentation](../../automating/using/segmentation.md) permettant de créer trois segments répartis dans des transitions sortantes différentes : 18 - 25 ans, 26 - 32 ans et plus de 32 ans. Les segments sont définis selon les paramètres suivants :

  ![](assets/wkf_segment_example_3.png)

   * un filtre sur l’âge permettant de définir la tranche d’âge du segment ;

     ![](assets/wkf_segment_new_segment.png)

   * une limitation de type **[!UICONTROL Échantillonnage aléatoire]** associé à une limite de **[!UICONTROL Taille maximale]** avec pour valeur 100.

     ![](assets/wkf_segment_example_1.png)

* Une activité [Diffusion email](../../automating/using/email-delivery.md) par segment.
