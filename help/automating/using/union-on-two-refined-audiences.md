---
title: Union sur deux audiences affinées
description: Ce cas pratique montre l’union de deux activités Lecture d’audience.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6261f800-11bd-4b02-a587-49ddb0da240f
TQID: https://experienceleague.adobe.com/NZA7DqSxrgPvNPfo4dgWvyJaOp-2Ma07MZJuHff3sAA
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 163
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
