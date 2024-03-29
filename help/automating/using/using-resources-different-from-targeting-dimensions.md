---
title: Utiliser des ressources différentes des dimensions de ciblage
description: Découvrez comment utiliser une ressource différente de la dimension de ciblage.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5805bdfa-fb33-4a46-ba1e-7a10b067349b
source-git-commit: 9c14fc3de60d8e0304f8a7ebd46e7be34d2e0499
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 100%

---

# Utiliser des ressources différentes des dimensions de ciblage {#using-resources-different-from-targeting-dimensions}

Ces cas pratiques montrent comment utiliser une ressource différente de la dimension de ciblage, par exemple, pour rechercher un enregistrement spécifique dans un tableau distant.

Pour plus d’informations sur les dimensions de ciblage et les ressources, reportez-vous à [cette section](../../automating/using/query.md#targeting-dimensions-and-resources)

**Exemple 1 : identification des profils ciblés par la diffusion avec le libellé « Ravi de vous revoir parmi nous »**.

* Dans ce cas, nous voulons cibler des profils. La dimension de ciblage sera donc définie sur **[!UICONTROL Profils (profile)]**.
* Nous voulons également filtrer les profils sélectionnés en fonction du libellé de la diffusion. La ressource sera donc définie sur **[!UICONTROL Logs de diffusion]**. Ainsi, nous appliquons un filtre directement dans la table des logs de diffusion, ce qui offrira de meilleures performances.

![](assets/targeting_dimension6.png)

![](assets/targeting_dimension7.png)

**Exemple 2 : identification des profils qui n’étaient pas ciblés par la diffusion avec le libellé « Ravi de vous revoir parmi nous ».**

Dans l’exemple précédent, nous avons utilisé une ressource différente de la dimension de ciblage. Cette opération n’est possible que si vous recherchez un enregistrement qui **se trouve** dans la table distante (logs de diffusion dans le cas présent).

Si nous recherchons un enregistrement qui **ne figure pas** dans la table distante (comme des profils n’étant pas ciblés par une diffusion spécifique), nous devons utiliser les mêmes ressource et dimension de ciblage dans la mesure où l’enregistrement ne se trouve pas dans la table distante (logs de diffusion).

* Dans ce cas, nous voulons cibler des profils. La dimension de ciblage sera donc définie sur **[!UICONTROL Profils (profile)]**.
* Nous voulons également filtrer les profils sélectionnés en fonction du libellé de la diffusion. Il n’est pas possible d’appliquer directement un filtre sur les logs de diffusion dans la mesure où nous recherchons un enregistrement qui ne figure pas dans la table des logs de diffusion. La ressource sera donc définie sur **[!UICONTROL Profil (profile)]** et la requête sera créée sur la table des profils.

![](assets/targeting_dimension8.png)

![](assets/targeting_dimension9.png)
