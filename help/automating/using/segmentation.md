---
title: Segmentation
description: L’activité Segmentation permet de créer un ou plusieurs segments à partir d’une population calculée par des activités placées en amont.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: segmentation,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3761ee4a-1ce5-4f9e-b2a5-84388b6b9db8
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 89%

---

# Segmentation{#segmentation}

## Description {#description}

![](assets/segmentation.png)

L’activité **[!UICONTROL Segmentation]** permet de créer un ou plusieurs segments à partir d’une population calculée par des activités placées en amont. En sortie de l’activité, ils peuvent être traités dans une seule transition ou dans des transitions distinctes.

>[!NOTE]
>
>Par défaut, un membre de la population entrante ne peut appartenir qu’à un seul segment. Les filtrages sont appliqués dans l’ordre des segments dans l’activité.

**Rubriques connexes :**
* [Cas pratique : segmentation en fonction de la localisation](../../automating/using/workflow-segmentation-location.md)
* [Cas pratique : segmentation en fonction des tranches d’âge](../../automating/using/segmentation-age-groups.md)

## Contexte d&#39;utilisation  {#context-of-use}

L’activité **[!UICONTROL Segmentation]** est généralement placée après des activités de ciblage (requête, intersection, union, exclusion, etc.) permettant de définir la population de base à partir de laquelle les segments seront formés.

**Rubriques connexes :**

* [Cas pratique : segmentation des profils en fonction de leurs tranches d’âge](../../automating/using/segmentation-age-groups.md).

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Segmentation]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Dans l’onglet **[!UICONTROL Général]**, sélectionnez le **[!UICONTROL type de ressource]** sur lequel la segmentation doit être effectuée :

   * **[!UICONTROL Ressource de la base]** si la segmentation porte sur des données déjà existantes en base de données. Sélectionnez la **[!UICONTROL Dimension de filtrage]** en fonction des données que vous souhaitez segmenter. Par défaut, la segmentation porte sur les **profils**.
   * **[!UICONTROL Ressource temporaire]** si la segmentation porte sur des données temporaires du workflow : sélectionnez l&#39;**[!UICONTROL Ensemble ciblé]** contenant les données à segmenter. Ce cas peut être rencontré à la suite d’un import de fichier ou si des données de la base ont été enrichies.

1. Sélectionnez le type de transition sortante que vous souhaitez :

   * **[!UICONTROL Générer une transition par segment]** : une transition sortante est ajoutée en sortie de l’activité pour chaque segment paramétré.
   * **[!UICONTROL Générer tous les segments dans une même transition]** : tous les segments paramétrés sont regroupés dans la même transition sortante. Indiquez le libellé de la transition. Les membres de chaque segment conservent le code segment qui leur a été associé.

1. Ajoutez un segment à l’aide du bouton ![](assets/add_darkgrey-24px.png) ou **[!UICONTROL Ajouter un élément]** et renseignez ses propriétés de base :

   * **[!UICONTROL Ne pas activer la transition si la population est vide]** : le segment n’est activé que si des données sont récupérées.
   * **[!UICONTROL Filtrer la population initiale (requête)]** : permet de filtrer la population de ce segment.
   * **[!UICONTROL Limiter la population de ce segment]** : permet de limiter la taille du segment.
   * **[!UICONTROL Filtrer et limiter la population de ce segment]** : permet de filtrer la population du segment et d’en limiter la taille.
   * **[!UICONTROL Libellé]** : libellé du segment.
   * **[!UICONTROL Code segment]** : code assigné à la population de segments. Le code segment peut être personnalisé à l&#39;aide d&#39;une expression standard et de variables d&#39;événements (voir [cette page](../../automating/using/customizing-workflow-external-parameters.md)).
   * **[!UICONTROL Exclure ce segment de la population]** : permet d’exclure le segment défini de la population en sortie de l’activité. Cette option ne peut être utilisée que si l’option **[!UICONTROL Générer tous les segments dans une même transition]** est sélectionnée.

   ![](assets/wkf_segment_new_segment.png)

1. Ouvrez le détail du segment afin d’accéder aux options de configuration de ce dernier. Pour cela, cochez la case correspondante dans la liste des segments de l’activité, puis sélectionnez ![](assets/wkf_segment_parameters_24px.png).
1. Si vous avez coché une option permettant de filtrer la population initiale, ouvrez l’onglet **[!UICONTROL Filtrage]** et définissez la population de votre segment. Les filtres sont basés sur la dimension de filtrage sélectionnée à l’étape 4. Pour plus d’informations sur le filtrage de la population, consultez la section [Edition de requête](../../automating/using/editing-queries.md).

   Si la segmentation porte sur une ressource temporaire, le comptage et la prévisualisation de la population ne sont pas disponibles dans cet onglet.

1. Si vous avez coché une option permettant de limiter la taille du segment, ouvrez l’onglet **[!UICONTROL Limitation]**.

   Sélectionnez tout d’abord le **[!UICONTROL Type de limitation]** que vous souhaitez appliquer :

   * **[!UICONTROL Tirage aléatoire]** : la population du segment est sélectionnée de manière aléatoire, en tenant compte du paramétrage réalisé dans l’onglet **[!UICONTROL Filtrage]**, le cas échéant.
   * **[!UICONTROL Tirage ordonné]** : la population du segment est sélectionnée de manière ordonnée. Vous devez alors définir les colonnes à prendre en compte et le type de tri à appliquer. Par exemple, si vous choisissez le champ **Age** comme colonne de tri, en appliquant un **[!UICONTROL Tri descendant]**, et que vous définissez ensuite une limite de 100, seuls les 100 profils les plus âgés seront conservés.

   Définissez ensuite la taille **[!UICONTROL Limite]** du segment :

   * **[!UICONTROL Taille (en % de la population initiale)]** : définissez la taille du segment à l’aide d’un pourcentage de la population initiale de l’activité.
   * **[!UICONTROL Taille maximale]** : définissez un nombre maximum de membres pour la population du segment.
   * **[!UICONTROL Par groupement de données]** : vous pouvez limiter la population du segment en fonction des valeurs d’un champ précis de la population entrante. Sélectionnez le champ sur lequel appliquer le groupement puis définissez les valeurs à utiliser.
   * **[!UICONTROL Par groupement de données (en %)]** : vous pouvez limiter la population du segment en fonction des valeurs d’un champ précis de la population entrante à l’aide d’un pourcentage. Sélectionnez le champ sur lequel appliquer le groupement puis définissez les valeurs à utiliser.

      >[!NOTE]
      >
      >Vous pouvez choisir des limitations différentes pour chaque valeur. Par exemple, vous pouvez définir un groupement sur le champ **[!UICONTROL Genre]** et limiter la population dont le genre est **[!UICONTROL Masculin]** à 10 et la population dont le genre est **[!UICONTROL Féminin]** à 30. Si vous utilisez plusieurs champs pour le groupement de données, tous les groupements doivent être de la même taille.
   ![](assets/wkf_segment_limit_by_grouping.png)

1. Validez la configuration du segment.
1. Ajoutez autant de segments que nécessaire en répétant les étapes 6 à 10 de cette procédure.
1. Si nécessaire, éditez les paramètres de l’onglet **[!UICONTROL Options avancées]** de l’activité :

   * Le **[!UICONTROL Permettre le recouvrement des populations de sortie]** permet de définir comment gérer les profils appartenant à plusieurs segments :
      * Lorsque l’option n’est pas activée, la variable **[!UICONTROL Segmentation]** l&#39;activité vérifie qu&#39;un profil n&#39;est pas présent dans plusieurs transitions en sortie, même si ce profil répond aux critères de plusieurs sous-ensembles.
      * Lorsque l&#39;option est activée, les profils se trouvent dans plusieurs sous-ensembles s&#39;ils répondent à leurs critères de filtrage.
   * Si un code segment que vous souhaitez conserver a déjà été affecté à la population entrante, cochez la case **[!UICONTROL Concaténer le code de chaque segment]** . Le code segment défini dans l’activité sera ajouté au code segment initial.
   * Si vous devez exploiter la population restante, cochez la case **[!UICONTROL Générer le complémentaire]** . Voir le [Cas pratique : création de diffusions avec un complémentaire](../../automating/using/workflow-created-query-with-complement.md).

1. Validez le paramétrage de l’activité et enregistrez le workflow.
