---
title: Segmentation en fonction des tranches d’âge
description: Cette page présente une segmentation de profils de la base de données en fonction de leur tranche d’âge. Le but du workflow est d'envoyer un email distinct pour chaque tranche d'âge.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: dab7ef86-4776-48f4-be9a-37de316e0dd9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '208'
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

   * un filtrage sur l&#39;âge permettant de définir la tranche d&#39;âge du segment

     ![](assets/wkf_segment_new_segment.png)

   * une limitation de type **[!UICONTROL Tirage aléatoire]** associé à une limite de **[!UICONTROL Taille maximale]** avec pour valeur 100.

     ![](assets/wkf_segment_example_1.png)

* Une activité [Diffusion email](../../automating/using/email-delivery.md) par segment.
