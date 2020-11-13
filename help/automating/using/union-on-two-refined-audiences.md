---
title: Union sur deux audiences affinées
description: Ce cas pratique montre l’union de deux activités Lecture d’audience.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '157'
ht-degree: 100%

---


# Union sur deux audiences affinées {#example--union-on-two-refined-audiences}

Le workflow défini dans cet exemple montre l&#39;union de deux activités **[!UICONTROL Lecture d&#39;audience]**. L&#39;objectif de ce workflow est d&#39;envoyer un email aux membres Gold ou Silver qui ont entre 18 et 30 ans. Des audiences spécifiques sont déjà créées dans le système pour tracker les membres Gold et Silver.

Le workflow se présente comme suit :

![](assets/readaudience_activity_example1.png)

* Une première activité [Lecture d&#39;audience](../../automating/using/read-audience.md) qui récupère l&#39;audience membres Gold et l&#39;affine en sélectionnant uniquement les profils qui ont entre 18 et 30 ans.
* Une deuxième activité **[!UICONTROL Lecture d&#39;audience]** qui récupère l&#39;audience membres Silver et l&#39;affine en sélectionnant uniquement les profils qui ont entre 18 et 30 ans.
* Une activité [Union](../../automating/using/union.md) qui réunit les populations issues des deux activités **[!UICONTROL Lecture d&#39;audience]** en une population finale.
* Une activité [Diffusion Email](../../automating/using/email-delivery.md) qui envoie l&#39;email à la population en provenance de l&#39;activité **[!UICONTROL Union]**.
