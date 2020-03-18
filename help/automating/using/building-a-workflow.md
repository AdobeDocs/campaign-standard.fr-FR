---
title: Construire un workflow
description: Cette section détaille les principes généraux et les bonnes pratiques pour la création d'un workflow.
page-status-flag: never-activated
uuid: 11374f64-8d34-40da-937b-09f419250f4c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: c26fcb0e-19d5-4bd5-b7d6-2d22ce92ad90
context-tags: workflow,wizard;workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e04b70012188b455382406df167328f963d577da

---


# Construire un workflow{#building-a-workflow}

Cette section détaille les principes généraux et les bonnes pratiques pour la création d&#39;un nouveau workflow :

* Créer un workflow
* Ajouter et relier les activités
* Configurer les activités

## Créer un workflow   {#creating-a-workflow}

La création d&#39;un workflow est possible au sein d&#39;un programme ou d&#39;une campagne, ou dans la liste des activités marketing.

La création d&#39;une activité marketing est présentée dans la section [Créer une activité marketing](../../start/using/marketing-activities.md#creating-a-marketing-activity).

1. Une fois que vous avez commencé la création d&#39;une activité marketing de type workflow, choisissez le modèle que vous souhaitez utiliser.

   ![](assets/workflow_creation_1.png)

   >[!NOTE]
   >
   >Chaque activité marketing propose plusieurs types par défaut. Ceux-ci permettent de pré-configurer certains paramètres en fonction de vos besoins. Voir à ce propos la section [Gestion des modèles](../../start/using/marketing-activity-templates.md).

1. Renseignez les propriétés générales du workflow.

   ![](assets/workflow_creation_2.png)

   Vous pouvez saisir un nom dans le champ **Libellé** et modifier l&#39;identifiant. Le nom de l&#39;activité et son identifiant apparaissent dans l&#39;interface, mais ne sont pas visibles par les destinataires des messages.

   >[!NOTE]
   >
   >A partir de la liste des activités marketing, vous pouvez créer votre workflow à l&#39;intérieur d&#39;une campagne parente. Sélectionnez celle-ci parmi les campagnes déjà créées.

   Vous pouvez ajouter une description, qui sera visible par l&#39;utilisateur dans le contenu de la campagne.

   Pour trouver plus facilement les workflows qui ne fonctionnent pas de la manière attendue et résoudre les problèmes, Adobe recommande d&#39;attribuer aux workflows des libellés et des noms adéquats. Renseignez également le champ de description du workflow pour que l&#39;opérateur puisse facilement comprendre son objectif.

1. Validez la création de l&#39;activité, dont le tableau de bord s&#39;affiche alors. Voir à ce propos la section [Interface des workflows](../../automating/using/workflow-interface.md).

1. Once the workflow is ready to be configured, you can access additional options by clicking the **[!UICONTROL Edit properties]** button. Vous pouvez, par exemple, définir un fuseau horaire spécifique à utiliser par défaut dans toutes les activités du workflow. Par défaut, le fuseau horaire du workflow est celui défini pour l’opérateur de Campaign actuel.

   ![](assets/workflow_properties.png)

**Rubrique connexe :**

* Vidéo [Créer un workflow](https://docs.adobe.com/content/help/en/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html)
* [Propriétés d&#39;exécution  ](../../automating/using/executing-a-workflow.md#workflow-properties)

## Ajouter et relier les activités {#adding-and-linking-activities}

Vous devez maintenant définir les différentes activités et les relier entre elles dans un diagramme.

>[!NOTE]
>
>Si la palette n&#39;est pas visible, cliquez sur le premier bouton de la barre d&#39;outils pour l&#39;afficher.

Les activités sont regroupées par catégories dans les différentes sections de la palette.

* The first section contains [targeting activities](../../automating/using/about-targeting-activities.md)
* The second section contains the [execution activities](../../automating/using/about-execution-activities.md), which are mainly used for coordinating other activities.
* The third section contains activities that can be used to send messages on different [channels](../../automating/using/about-channel-activities.md). Les activités de cette section peuvent varier en fonction des canaux activés sur votre instance.
* The fourth section contains [file manipulation and data management activities](../../automating/using/about-data-management-activities.md).

Pour construire le diagramme :

1. Ajoutez une activité en la sélectionnant dans la palette et en la relâchant dans le diagramme.

   Par exemple, positionnez une activité de type **[Début](../../automating/using/start-and-end.md)**, puis une activité de type**[ Diffusion Email](../../automating/using/email-delivery.md)** sur le diagramme.

1. Reliez les deux activités en sélectionnant la transition de l&#39;activité **Début** et en la relâchant sur l&#39;activité **Diffusion Email**.

   >[!NOTE]
   >
   >Vous pouvez relier automatiquement une activité à celle qui la précède en déposant la nouvelle activité directement sur l&#39;extrémité de la transition de la précédente.

1. Ajoutez les activités dont vous avez besoin et reliez-les entre elles pour finaliser le workflow.

   >[!NOTE]
   >
   >Vous pouvez également dupliquer les activités existantes en les copiant et en les collant. Ainsi, vous conservez les paramètres qui étaient définis à l&#39;origine. Voir à ce propos [Duplication des activités de workflow](../../automating/using/workflow-interface.md#duplicating-workflow-activities).

Une fois vos activités de workflow reliées, vous pouvez personnaliser les transitions entre elles avec le **libellé** de votre choix. Pour cela, double-cliquez sur la transition pour accéder à ses propriétés.

Moreover, **[!UICONTROL Targeting]** and **[!UICONTROL Data management (ETL)]** activities allows you to define **segment codes** for their outbound transitions. Vous pouvez ensuite créer des rapports à partir de ces codes segment pour mesurer l&#39;efficacité des campagnes marketing. Voir à ce propos [cette section](../../reporting/using/creating-a-report-workflow-segment.md).

**Cas pratiques de workflow :**

* [Cas pratique : création d&#39;une diffusion email hebdomadaire](../../automating/using/workflow-weekly-offer.md)
* [Cas pratique : création d&#39;une diffusion segmentée sur la localisation](../../automating/using/workflow-segmentation-location.md)
* [Cas pratique : création de diffusions avec un complément](../../automating/using/workflow-created-query-with-complement.md)
* [Cas pratique : workflow de reciblage envoyant une nouvelle diffusion aux personnes n&#39;ayant pas ouvert l&#39;email](../../automating/using/workflow-cross-channel-retargeting.md)

## Configurer les activités {#configuring-activities}

Par défaut, les activités ne sont pas définies et ne traiteront pas correctement les données si elles ne sont pas configurées. Chaque activité contient plusieurs onglets permettant de gérer des configurations spécifiques et des options génériques telles que les transitions sortantes, les libellés, etc.

1. Vérifiez que toutes les activités sont correctement reliées entre elles. Certaines activités doivent détecter la structure ou la nature des données entrantes pour proposer les options de configuration adéquates.
1. Double-click an activity or select it and click the **[!UICONTROL Edit]** contextual action to open its configuration window.
1. Editez le libellé de l&#39;activité.
1. Définissez toutes les différentes options dont vous avez besoin pour traiter les données. Pour découvrir les options possibles pour chaque activité, reportez-vous à la section spécifique à l&#39;activité dans cette documentation.
1. Enregistrez l&#39;activité et répétez ces opérations pour chaque activité du workflow.
1. Enregistrez le workflow.
