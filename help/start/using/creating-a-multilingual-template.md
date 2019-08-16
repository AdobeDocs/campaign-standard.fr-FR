---
title: Créer un modèle multilingue
seo-title: Créer un modèle multilingue
description: Créer un modèle multilingue
seo-description: Découvrez comment définir et exécuter des diffusions email/SMS multilingues en une seule vague à partir des préférences linguistiques de vos clients segmentés automatiquement. Créez des rapports sur les performances de chaque diffusion en affinant par langue et par niveau individuel.
page-status-flag: never-activated
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Créer un modèle multilingue{#creating-a-multilingual-template}

Un modèle multilingue est un modèle spécifique qui permet de gérer les messages multilingues.

Ce type de modèle est disponible pour les **emails et SMS** et peut être utilisé en mode autonome, dans un workflow ou dans une diffusion récurrente.

Dans les modèles multilingues, la gestion des langues repose sur les variantes. **Chaque variante représente une langue.**

Il est possible de configurer jusqu'à 40 variantes dans Adobe Campaign Standard.

Adobe Campaign est livré avec une langue par défaut définie sur EN. La langue par défaut peut être remplacée par une autre variante, mais ne doit jamais être supprimée.

Pendant la création du modèle, vous pouvez ajouter le nombre de variantes qui correspond à celui des langues dont vous avez besoin pour le message.

Pour créer un modèle d'email ou de SMS, procédez comme suit :

1. Dupliquez un modèle multilingue existant (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Vous pouvez également modifier un modèle standard existant dans un modèle multilingue en cliquant sur le bouton **[!UICONTROL Initialiser la variante du contenu]** dans les propriétés du modèle.

1. Modifiez les propriétés pour personnaliser le libellé, le tracking, etc.
1. Changez le nombre de variantes en cliquant sur la vignette des variantes. La fenêtre des variantes s'affiche,

   ![](assets/multi_template_variants.png)

   dans laquelle vous pouvez ajouter ou supprimer des variantes. Pour ajouter une variante, renseignez la fenêtre **[!UICONTROL Nouvelle variante du contenu]**.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Ne supprimez pas la variante "default", car il s'agit de la variante envoyée aux profils lorsqu'aucun paramètre de préférence linguistique n'est indiqué.

1. Au besoin, personnalisez la variante du libellé et cliquez sur Confirmer.
1. Vous pouvez aussi ajouter directement le contenu pour chaque variante.

Vous êtes maintenant prêt à créer un email ou un SMS à partir de ce modèle multilingue.

**Rubriques connexes :**

* [Créer un email multilingue](../../channels/using/creating-a-multilingual-email.md)
* [Créer un profil](../../audiences/using/creating-profiles.md)

