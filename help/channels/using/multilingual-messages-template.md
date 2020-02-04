---
title: Modèles de messages multilingues
description: Découvrez comment définir et exécuter des diffusions email/SMS multilingues en une seule vague à partir des préférences linguistiques de vos clients segmentés automatiquement. Créez des rapports sur les performances de chaque diffusion en affinant par langue et par niveau individuel.
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
translation-type: tm+mt
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Modèles de messages multilingues {#multilingual-messages-template}

Un modèle multilingue est un modèle spécifique qui permet de gérer les messages multilingues. This kind of template is available for ****Email** and **SMS messages**  and useable in standalone mode, within a workflow or in a recurring delivery.

Dans les modèles multilingues, la gestion des langues repose sur les variantes. **Chaque variante représente une langue**. Il est possible de configurer jusqu&#39;à 40 variantes dans Adobe Campaign Standard.

Adobe Campaign comes with a default language which is set to **EN**. La langue par défaut peut être remplacée par une autre variante, mais ne doit jamais être supprimée.

Pendant la création du modèle, vous pouvez ajouter le nombre de variantes qui correspond à celui des langues dont vous avez besoin pour le message.

Pour créer un modèle de SMS ou de courrier électronique, procédez comme suit :

1. Dupliquez un modèle multilingue existant (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Vous pouvez également modifier un modèle standard existant dans un modèle multilingue en cliquant sur le bouton **[!UICONTROL Initialiser la variante du contenu]**dans les propriétés du modèle.

1. Modifiez les propriétés pour personnaliser le libellé, le tracking, etc.
1. Changez le nombre de variantes en cliquant sur la vignette des variantes. La fenêtre des variantes s&#39;affiche,

   ![](assets/multi_template_variants.png)

   dans laquelle vous pouvez ajouter ou supprimer des variantes. Pour ajouter une variante, renseignez la fenêtre **[!UICONTROL Nouvelle variante du contenu]**.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Ne supprimez pas la variante &quot;default&quot;, car il s&#39;agit de la variante envoyée aux profils lorsqu&#39;aucun paramètre de préférence linguistique n&#39;est indiqué.

1. Customize label variant if needed and click **[!UICONTROL Confirm]**.
1. Vous pouvez aussi ajouter directement le contenu pour chaque variante.

Vous êtes maintenant prêt à créer un email ou un SMS à partir de ce modèle multilingue.

**Rubriques connexes :**

* [Créer un email multilingue](../../channels/using/creating-a-multilingual-email.md)
* [Créer un profil](../../audiences/using/creating-profiles.md)
