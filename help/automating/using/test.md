---
title: Test
seo-title: Test
description: Test
seo-description: L'activité Test active une transition en fonction d'un résultat au test.
page-status-flag: jamais activé
uuid: 1562 ec 7 a -253 a -4 f 4 f-b 66 a-c 2948 b 57775 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: exécution-activités
discoiquuid: 2650 bf 1 f -0 bce -4049-a 226-2369 f 6666 b 95
context-tags: jstest, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Test{#test}

## Description {#description}

![](assets/test.png)

L'activité **[!UICONTROL Test]active une transition en fonction d'un résultat au test.**

## Contexte d'utilisation {#context-of-use}

Une activité **Test** active la première transition qui satisfait la condition qui lui est associée.

Si aucune condition n'est satisfaite et que l'option **Utiliser la transition par défaut** est activée, une transition par défaut sera activée.

![](assets/wkf_test_activity_example.png)

Les conditions peuvent être basées sur des **fonctions** ou des **variables**, par exemple des variables d'événements qui ont été déclarées dans l'activité **[!UICONTROL Signal externe]du workflow.**

**Rubriques connexes :**

* [Liste des fonctions](../../automating/using/list-of-functions.md)
* [Appeler un workflow avec des paramètres externes](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Faites glisser une activité **[!UICONTROL Test]et déposez-la dans le workflow.**
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![, disponible dans les actions rapides qui s'affichent.](assets/edit_darkgrey-24px.png)
1. Définissez les attributs de chaque condition :

   Lorsque vous éditez le champ **[!UICONTROL Condition], deux boutons vous aident à appeler des variables d'événements et à éditer des expressions en associant des variables et des fonctions :**

   * ![](assets/extsignal_picker.png) : sélectionnez la variable d'événements parmi toutes les variables disponibles dans le workflow (voir [Personnaliser un workflow avec des paramètres externes](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png) : éditez les expressions en associant des variables et des fonctions. Pour plus d'informations sur l'éditeur d'expression, voir [cette section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

