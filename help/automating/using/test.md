---
title: Test
description: L’activité Test active une transition en fonction d’un résultat au test.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 62a064f7-6d0b-49ca-9834-eccb5bf42496
TQID: 'https://experienceleague.adobe.com/oyXhQ4Fgx2-cooFelMxsoFiP1qx48-ZQ1eoAudNivF8'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 100%
---
# Test{#test}

## Description {#description}

![](assets/test.png)

L’activité **[!UICONTROL Test]** active une transition en fonction d’un résultat au test.

## Contexte d&#39;utilisation {#context-of-use}

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

   * ![](assets/extsignal_picker.png) : sélectionnez la variable d’événements parmi toutes les variables disponibles dans le workflow (voir [cette page](../../automating/using/customizing-workflow-external-parameters.md)).

     Par exemple, vous pouvez vérifier le nombre de fichiers téléchargés après une activité [Transfert de fichier](../../automating/using/transfer-file.md) à l’aide de la variable **[!UICONTROL filesCount]**.

     ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png) : éditez les expressions en associant des variables et des fonctions. Pour plus d’informations sur l’éditeur d’expression, voir [cette section](../../automating/using/advanced-expression-editing.md).

     ![](assets/wkf_test_activity_variables_expression.png)
