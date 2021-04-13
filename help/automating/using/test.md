---
solution: Campaign Standard
product: campaign
title: Test
description: L’activité Test active une transition en fonction d’un résultat au test.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 62a064f7-6d0b-49ca-9834-eccb5bf42496
translation-type: ht
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: ht
source-wordcount: '197'
ht-degree: 100%

---

# Test{#test}

## Description {#description}

![](assets/test.png)

L’activité **[!UICONTROL Test]** active une transition en fonction d’un résultat au test.

## Contexte d’utilisation {#context-of-use}

Une activité **Test** active la première transition qui satisfait la condition qui lui est associée.

Si aucune condition n’est satisfaite et que l’option **Utiliser la transition par défaut** est activée, une transition par défaut sera activée.

![](assets/wkf_test_activity_example.png)

Les conditions peuvent être basées sur des **fonctions** ou des **variables**, par exemple des variables d’événements qui ont été déclarées dans l’activité **[!UICONTROL Signal externe]** du workflow.

**Rubriques connexes :**

* [Liste des fonctions](../../automating/using/list-of-functions.md)
* [Appeler un workflow avec des paramètres externes](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuration {#configuration}

1. Faites glisser une activité **[!UICONTROL Test]** et déposez-la dans le workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Définissez les attributs de chaque condition :

   Lorsque vous éditez le champ **[!UICONTROL Condition]**, deux boutons vous aident à appeler des variables d’événements et à éditer des expressions en associant des variables et des fonctions :

   * ![](assets/extsignal_picker.png) : sélectionnez la variable d&#39;événements parmi toutes les variables disponibles dans le workflow (voir [cette page](../../automating/using/customizing-workflow-external-parameters.md)).

      Par exemple, vous pouvez vérifier le nombre de fichiers téléchargés après une activité [Transfert de fichier](../../automating/using/transfer-file.md) à l’aide de la variable **[!UICONTROL filesCount]**.

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png) : éditez les expressions en associant des variables et des fonctions. Pour plus d’informations sur l’éditeur d’expression, voir [cette section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)
