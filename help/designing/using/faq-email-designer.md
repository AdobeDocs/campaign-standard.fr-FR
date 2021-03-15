---
solution: Campaign Standard
product: campaign
title: 'Questions fréquentes sur le Concepteur d’email '
description: Questions fréquentes sur le Concepteur d’email.
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Conception de courrier électronique
role: Professionnel
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 99%

---


# Questions fréquentes sur le Concepteur d’email

## Quelle est la différence entre les blocs de contenu et les fragments de contenu ?

Les blocs de contenu et les fragments de contenu sont des éléments de contenu réutilisables communs à plusieurs emails. Ils sont utilisés pour assurer la cohérence entre les emails et pour optimiser/standardiser leur création. Les différences entre les blocs de contenu et les fragments de contenu concernent le niveau de personnalisation possible.

* Les blocs de contenu sont constitués de code HTML pur, inséré manuellement (il s’agit de code source direct, créé à l’aide d’une interface utilisateur dépourvue de convivialité). Bien qu’ils s’adressent aux personnes expérimentées en HTML, ces blocs de contenu permettent un niveau de personnalisation impossible dans les fragments de contenu.

* Les fragments de contenu sont des éléments visuels de contenu créés à l’aide du Concepteur d’email avec son interface utilisateur conviviale. Cependant, il n’est pas possible de personnaliser ce contenu. Si une personnalisation est nécessaire, elle ne peut être réalisée que par le biais de blocs de contenu.

## Comment ajouter une marge intérieure à un élément de la structure HTML ?

Vous pouvez ajouter une marge intérieure à l’aide du chemin de navigation HTML.

1. Dans l’angle inférieur gauche de l’écran, cliquez sur le chemin de navigation HTML.

   ![](assets/do-not-localize/breadcrumb.png)

1. Cliquez sur l’élément auquel vous souhaitez ajouter une marge intérieure.
1. Cliquez sur la balise parent dans le chemin de navigation HTML.
Vous pouvez maintenant ajouter une marge intérieure à cet élément.

## Puis-je importer du contenu HTML dans le Concepteur d’email ?

Vous pouvez transférer votre propre contenu HTML dans le Concepteur d’email. Si ce contenu n’a pas été créé à l’aide du Concepteur d’email, il sera chargé en mode de compatibilité, conçu pour conserver le code HTML d’origine, mais en limitant certaines fonctionnalités d’édition par le biais de l’interface utilisateur.

Pour plus d’informations, voir la section [Mode de compatibilité](../../designing/using/using-existing-content.md#compatibility-mode).

## Comment puis-je créer mon premier contenu d’email ?

Tout d’abord, créez un email à partir de la page d’accueil.
Ensuite, pour ajouter du contenu à un email, vous devez ajouter un composant de structure et y insérer un composant de contenu.

Pour plus d’informations, voir la section [Création d’un email à partir de zéro](../../designing/using/quick-start.md#from-scratch-email)

## Pourquoi dois-je mettre à jour les fragments ?

Le Concepteur d’email est sans cesse amélioré. Si vous avez créé un contenu d’email à partir de zéro, à l’aide d’un modèle d’usine, ou si vous avez créé des fragments, vous devrez peut-être mettre à jour votre contenu vers la version la plus récente pour éviter certains problèmes comme les collisions CSS.

Pour plus d’informations, voir la section [Mise à jour des fragments](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## Puis-je enregistrer des styles dans un thème ?

Les styles ne peuvent pas être enregistrés en tant que thème pour une réutilisation ultérieure. Le style CSS peut toutefois être enregistré dans un modèle de contenu ou dans un email.

Voir à ce sujet la section [Styles](../../designing/using/styles.md)

## Quelles sont les polices disponibles ?

Lors de la modification des styles, seules les polices web officiellement prises en charge par la plupart des clients de messagerie sont disponibles par défaut via l’interface utilisateur. L’utilisation de polices personnalisées nécessite la mise à jour du code HTML.
