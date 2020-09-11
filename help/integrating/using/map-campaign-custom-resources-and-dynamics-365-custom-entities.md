---
title: Mappage des ressources personnalisées Campaign et des entités personnalisées Dynamics 365
description: Découvrez comment mapper des ressources et des entités dans le contexte de l'intégration entre Adobe Campaign Standard et Microsoft Dynamics 365.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e11de4d4482400e62be2db076c88da5ae30d60cc
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 5%

---


# Mise en correspondance des ressources Campaign et des entités Dynamics 365

Découvrez comment mapper des ressources personnalisées et des entités personnalisées dans le contexte de l&#39;intégration entre Adobe Campaign Standard et Microsoft Dynamics 365.

>[!CAUTION]
>
>Cette fonctionnalité n&#39;est pas disponible en standard dans le cadre du produit. La mise en oeuvre nécessite l’engagement de Adobes Consulting. Veuillez contacter votre représentant Adobe pour en savoir plus.

## Conditions préalables requises

L&#39;intégration [](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md) Microsoft Dynamics 365-Adobe Campaign Standard prend en charge les entités personnalisées, ce qui permet de synchroniser les entités personnalisées dans Dynamics 365 avec les ressources personnalisées correspondantes dans Campaign.

Les nouvelles données des ressources personnalisées peuvent être utilisées à plusieurs fins, notamment la segmentation et la personnalisation.

L’intégration prend en charge les tables liées et non liées. La liaison est prise en charge jusqu’à trois niveaux (niveau1->niveau2->niveau3).

>[!CAUTION]
>
>Si un enregistrement de ressource personnalisée Campaign contient des informations personnelles, des recommandations spécifiques s’appliquent. En savoir plus dans [cette section](../../integrating/using/notices-and-recommendations-for-acs-and-ms-dynamics.md#privacy-linked-resources).

## Avis

Lors de la configuration des flux de données d&#39;entité personnalisés, il est important de tenir compte des points suivants :

* La création et la modification de ressources personnalisées Campaign sont des opérations délicates qui doivent être effectuées uniquement par des utilisateurs experts.
* Pour les flux de données d&#39;entité personnalisés, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.
* Si un enregistrement enfant parent et lié est créé presque au même moment dans Dynamics 365, en raison du traitement parallèle de l&#39;intégration, il y a de faibles chances qu&#39;un nouvel enregistrement enfant puisse être écrit à Campaign avant son enregistrement parent.

* Si le parent et l’enfant sont liés du côté Campaign à l’aide de l’option de lien **simple de cardinalité** 1, l’enregistrement enfant reste masqué et inaccessible (via l’interface utilisateur ou l’API) jusqu’à ce que l’enregistrement parent arrive dans Campaign.

* (En supposant que le lien **simple de la cardinalité** 1 soit présent dans Campaign) Si l&#39;enregistrement enfant est mis à jour ou supprimé dans Dynamics 365 et que cette modification est écrite à Campaign avant que l&#39;enregistrement parent ne s&#39;affiche dans Campaign (ce n&#39;est pas probable, mais une possibilité distante), cette mise à jour ou suppression ne sera pas traitée dans Campaign et une erreur sera générée. Dans le cas d&#39;une mise à jour, l&#39;enregistrement en question devra être mis à jour à nouveau dans Dynamics 365 pour synchroniser l&#39;enregistrement mis à jour. Dans le cas de la suppression, l&#39;enregistrement en question devra être pris en charge séparément du côté Campaign car il n&#39;y a plus d&#39;enregistrement dans Dynamics 365 à supprimer ou à mettre à jour.

* Si vous rencontrez une situation dans laquelle vous pensez avoir masqué des enregistrements enfants et n&#39;avoir aucun moyen d&#39;y accéder, vous pouvez temporairement changer le type de lien de cardinalité en lien **simple de cardinalité** 0 ou 1 pour accéder à ces enregistrements.

A more comprehensive overview of Campaign custom resources can be found [in this section](../../developing/using/key-steps-to-add-a-resource.md).
