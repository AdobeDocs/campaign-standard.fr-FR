---
title: Mappage des ressources personnalisées de Campaign et des entités personnalisées de Dynamics 365
description: Découvrez comment mapper des ressources et des entités dans le contexte de l’intégration entre Adobe Campaign Standard et Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 100%

---


# Mappage des ressources de Campaign et des entités de Dynamics 365

Découvrez comment mapper des ressources personnalisées et des entités personnalisées dans le contexte de l’intégration entre Adobe Campaign Standard et Microsoft Dynamics 365.

>[!CAUTION]
>
>Cette fonctionnalité ne fait pas partie des paramètres d’usine du produit. La mise en œuvre nécessite l’implication d’Adobe Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.

## Conditions préalables requises

L’[intégration Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) prend en charge les entités personnalisées, ce qui permet de synchroniser les entités personnalisées de Dynamics 365 avec les ressources personnalisées correspondantes dans Campaign.

Les nouvelles données des ressources personnalisées peuvent être utilisées à plusieurs fins, notamment pour la segmentation et la personnalisation.

L’intégration prend en charge les tables liées et non liées. La liaison est prise en charge jusqu’à trois niveaux (niveau1->niveau2->niveau3).

>[!CAUTION]
>
>Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, des recommandations spécifiques s’appliquent. En savoir plus dans [cette section](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Remarques

Lors de la configuration des flux de données d’entités personnalisées, il est important de tenir compte des points suivants :

* La création et la modification de ressources personnalisées Campaign sont des opérations délicates qui doivent être effectuées uniquement par des utilisateurs experts.
* Pour les flux de données d’entités personnalisées, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.
* Si un enregistrement parent et et un enregistrement enfant lié sont créés presque au même moment dans Dynamics 365, en raison du traitement parallèle de l’intégration, il peut arriver qu’un nouvel enregistrement enfant soit créé dans Campaign avant l’enregistrement de son parent.

* Si les enregistrements parent et enfant sont liés du côté Campaign à l’aide de l’option **Lien simple de cardinalité 1**, l’enregistrement enfant reste masqué et inaccessible (via l’interface utilisateur ou l’API) jusqu’à ce que l’enregistrement parent arrive dans Campaign.

* (En supposant que le **lien simple de cardinalité 1** est présent dans Campaign) Si l’enregistrement enfant est mis à jour ou supprimé dans Dynamics 365 et que cette modification est écrite dans Campaign avant que l’enregistrement parent ne s’affiche dans Campaign (ce qui est peu probable, mais qui peut parfois arriver), cette mise à jour ou suppression ne sera pas traitée dans Campaign et une erreur sera générée. Dans le cas d’une mise à jour, l’enregistrement en question devra de nouveau être mis à jour dans Dynamics 365 pour synchroniser l’enregistrement mis à jour. Dans le cas de la suppression, l’enregistrement en question devra être pris en charge séparément du côté Campaign, car il n’y aura plus d’enregistrement dans Dynamics 365 à supprimer ou à mettre à jour.

* Si vous vous trouvez dans une situation où vous pensez avoir masqué des enregistrements enfants sans avoir aucun moyen d’y accéder, vous pouvez temporairement changer le type de lien de cardinalité en **lien simple de cardinalité 0 ou 1** pour accéder à ces enregistrements.

Vous trouverez une présentation plus exhaustive des ressources personnalisées de Campaign dans [cette section](../../developing/using/key-steps-to-add-a-resource.md).
