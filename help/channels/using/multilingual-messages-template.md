---
title: Modèles de messages multilingues
description: Découvrez comment définir et exécuter des diffusions email/SMS multilingues en une seule vague à partir des préférences linguistiques de vos clients segmentés automatiquement. Créez des rapports sur les performances de chaque diffusion en affinant par langue et par niveau individuel.
audience: start
content-type: reference
topic-tags: managing-templates
feature: Multilingual Messages
role: User
level: Intermediate
exl-id: 3d869f31-7dfb-4546-aba5-80a2787e00be
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 100%

---

# Modèles de messages multilingues {#multilingual-messages-template}

Un modèle multilingue est un modèle spécifique qui permet de gérer les messages multilingues. Ce type de modèle est disponible pour les **** emails et SMS **et peut être utilisé en mode autonome, dans un workflow ou dans une diffusion récurrente.**

Dans les modèles multilingues, la gestion des langues repose sur les variantes. **Chaque variante représente une langue**. Il est possible de configurer jusqu&#39;à 40 variantes dans Adobe Campaign Standard.

Adobe Campaign est livré avec une langue par défaut définie sur **EN**. La langue par défaut peut être remplacée par une autre variante, mais ne doit jamais être supprimée.

Pendant la création du modèle, vous pouvez ajouter le nombre de variantes qui correspond à celui des langues dont vous avez besoin pour le message.

Pour créer un modèle d’email ou de SMS, procédez comme suit :

1. Dupliquez un modèle multilingue existant (SMS ou Email).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >Vous pouvez également modifier un modèle standard existant dans un modèle multilingue en cliquant sur le bouton **[!UICONTROL Initialiser la variante du contenu]** dans les propriétés du modèle.

1. Modifiez les propriétés pour personnaliser le libellé, le tracking, etc.

1. Changez le nombre de variantes en cliquant sur la vignette des variantes. La fenêtre des variantes s&#39;affiche,

   ![](assets/multi_template_variants.png)

   dans laquelle vous pouvez ajouter ou supprimer des variantes. Pour ajouter une variante, renseignez la fenêtre **[!UICONTROL Nouvelle variante du contenu]**.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >Ne supprimez pas la variante &quot;default&quot;, car il s&#39;agit de la variante envoyée aux profils lorsqu&#39;aucun paramètre de préférence linguistique n&#39;est indiqué.

1. Au besoin, personnalisez la variante du libellé et cliquez sur **[!UICONTROL Confirmer]**.

1. Vous pouvez aussi ajouter directement le contenu pour chaque variante.

Vous êtes maintenant prêt à créer un email ou un SMS à partir de ce modèle multilingue.

**Rubriques connexes :**

* [Créer un e-mail multilingue](../../channels/using/creating-a-multilingual-email.md)
* [Créer un profil](../../audiences/using/creating-profiles.md)
