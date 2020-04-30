---
title: 'Questions fréquentes sur Designer de messagerie '
description: Questions fréquentes sur le concepteur de courrier électronique.
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 23d6c78f924635a8ce512fd91b4a46db395e8bd1

---


# Questions fréquentes sur Designer de messagerie

## Quelle est la différence entre les blocs de contenu et les fragments de contenu ?

Les blocs de contenu et les fragments de contenu sont des éléments de contenu réutilisables qui sont communs à plusieurs courriers électroniques. Elles sont utilisées pour assurer la cohérence entre les courriels et pour optimiser/normaliser la création des courriels. Les différences entre les blocs de contenu et les fragments de contenu sont le niveau de personnalisation possible.

* Les blocs de contenu sont du code HTML pur, où le code HTML est inséré manuellement (ce n’est pas une interface utilisateur conviviale, c’est du code source direct). Bien qu’il soit vraiment orienté vers les personnes ayant des connaissances en HTML, il permet un niveau de personnalisation non disponible dans les fragments de contenu.

* Les fragments de contenu sont des éléments visuels de contenu créés via le concepteur de courrier électronique, à l’aide de son interface utilisateur conviviale. Cependant, il n’est pas possible de personnaliser le contenu. Si la personnalisation est requise, elle ne peut être effectuée que par le biais de blocs de contenu.

## Comment ajouter un remplissage à un élément à partir de la structure HTML ?

Vous pouvez ajouter un remplissage à l’aide du chemin de navigation HTML.

1. Dans le coin inférieur gauche de l’écran, cliquez sur le chemin de navigation HTML.

   ![](assets/breadcrumb.png)

1. Cliquez sur l’élément que vous souhaitez ajouter à un remplissage.
1. Cliquez sur la balise parente dans le chemin de navigation HTML.
Vous pouvez maintenant ajouter un remplissage à cet élément.

## Puis-je importer du contenu HTML dans le concepteur de courrier électronique ?

Vous pouvez télécharger votre propre contenu HTML vers le concepteur de courrier électronique. S’il n’a pas été créé via Email Designer, il se charge en mode de compatibilité, conçu pour conserver le code HTML d’origine, mais limite certaines fonctionnalités d’édition par le biais de l’interface utilisateur.

Pour plus d’informations, voir Mode [de compatibilité](../../designing/using/using-existing-content.md#compatibility-mode)

## Comment créer mon premier contenu de courrier électronique ?

Tout d&#39;abord, créez un e-mail à partir du  de.
Ensuite, pour ajouter du contenu à un courrier électronique, vous devez ajouter un composant de structure et y insérer un composant de contenu.

Pour plus d’informations, voir [Création d’un courrier électronique à partir de zéro.](../../designing/using/quick-start.md#from-scratch-email)

## Pourquoi dois-je mettre à jour les fragments ?

Le Concepteur d&#39;email est sans cesse amélioré. Si vous avez créé un contenu de courrier électronique à partir de zéro, d’un modèle prêt à l’emploi ou si vous avez créé des fragments, vous devrez peut-être mettre à jour votre contenu vers la dernière version afin d’éviter des problèmes tels que les problèmes de collision CSS.

Pour plus d’informations, voir [Mise à jour des fragments](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## Puis-je enregistrer des styles dans un thème ?

Les styles ne peuvent pas être enregistrés en tant que thème pour une réutilisation ultérieure. Le style CSS peut toutefois être enregistré dans un modèle de contenu ou dans un email.

For more information, refer to [Styles](../../designing/using/styles.md)

## Quelles polices sont disponibles ?

Lors de la modification des styles, seules les polices Web officiellement prises en charge par la plupart des clients de messagerie sont disponibles par défaut via l’interface utilisateur. L’utilisation de polices personnalisées nécessite la mise à jour du code HTML.
