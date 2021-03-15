---
solution: Campaign Standard
product: campaign
title: Enrichissement
description: L'activité Enrichissement est une activité avancée qui permet de définir des données additionnelles à traiter dans un workflow.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Workflows
role: Data Architect
level: Intermédiaire
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 99%

---


# Enrichissement{#enrichment}

## Description {#description}

![](assets/enrichment.png)

L&#39;activité **[!UICONTROL Enrichissement]** est une activité avancée qui permet de définir des données additionnelles à traiter dans un workflow.

## Contexte d’utilisation {#context-of-use}

L&#39;activité **[!UICONTROL Enrichissement]** est généralement utilisée à la suite des activités de ciblage ou d&#39;un import de fichier et avant les activités permettant de consommer les données ciblées.

Cette activité contient plus de fonctions avancées d&#39;enrichissement que l&#39;activité **[!UICONTROL Requête]**. Certains cas simples d&#39;enrichissement peuvent être directement effectués dans l&#39;[activité Requête](../../automating/using/query.md#enriching-data).

Avec l&#39;activité **[!UICONTROL Enrichissement]**, vous pouvez utiliser la transition entrante et configurer l&#39;activité pour ajouter des données additionnelles à la transition sortante. Elle permet de combiner des données provenant de plusieurs ensembles ou de créer des liens avec une ressource temporaire.

**Rubriques connexes :**

* [Cas pratique : enrichissement des données de profil avec des données contenues dans un fichier](../../automating/using/enriching-profile-data-file.md).
* [Cas pratique : envoi d’un email contenant des champs enrichis](../../automating/using/sending-email-enriched-fields.md)

## Configuration {#configuration}

Pour configurer une activité **[!UICONTROL Enrichissement]** :

1. Placez une activité **[!UICONTROL Enrichissement]** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Si l&#39;activité possède plusieurs transitions entrantes, sélectionnez l&#39;**[!UICONTROL Ensemble principal]**. Les données additionnelles configurées dans cette activité seront ajoutées à cet ensemble principal dans la transition sortante.

   Si l&#39;ensemble principal contient déjà des données additionnelles, vous pouvez choisir de les conserver ou de les supprimer. Si vous décochez l&#39;option **[!UICONTROL Conserver toutes les données additionnelles de l&#39;ensemble principal]**, seules les données additionnelles configurées dans l&#39;**[!UICONTROL Enrichissement]** sont conservées dans la transition sortante.

1. S&#39;il existe plusieurs transitions entrantes, définissez les relations entre l&#39;ensemble principal et les autres données entrantes dans l&#39;onglet **[!UICONTROL Relations avancées]** de l&#39;activité. Vous pouvez ajouter plusieurs relations à l&#39;aide du bouton **[!UICONTROL Ajouter un élément]**.

   Lorsque vous définissez une nouvelle relation, sélectionnez l&#39;ensemble de données entrantes à associer à l&#39;ensemble principal. Définissez ensuite le type de relation. Selon les données entrantes et le modèle de données, plusieurs types de relation sont proposées :

   * **[!UICONTROL Lien simple de cardinalité 1]** : chaque enregistrement des données entrantes est associé à un seul enregistrement de l&#39;ensemble principal. Chaque enregistrement de l&#39;ensemble principal est associé à un enregistrement des données liées.
   * **[!UICONTROL Lien de collection de cardinalité N]** : 0, 1 ou davantage (N) d&#39;enregistrements des données liées peuvent être associés à 1 enregistrement de l&#39;ensemble principal.
   * **[!UICONTROL Lien simple de cardinalité 0 ou 1]** : les enregistrements de l&#39;ensemble principal peuvent être associés à 0 ou 1 enregistrement des données liées (et pas plus de un).

   Une fois la **[!UICONTROL Cardinalité]** définie, définissez un **[!UICONTROL Critère de réconciliation]**. L&#39;**[!UICONTROL Expression source]** du critère de réconciliation peut être un champ de la ressource cible, une [expression](../../automating/using/advanced-expression-editing.md) ou une valeur indiquée entre guillemets.

   Définissez un **[!UICONTROL Libellé]** et un **[!UICONTROL Identifiant]** qui pourront être facilement identifiés plus tard dans le workflow.

   >[!NOTE]
   >
   >Vous ne pouvez définir des relations qu&#39;entre l&#39;ensemble principal et les autres transitions entrantes reliées à l&#39;activité **[!UICONTROL Enrichissement]**. Pour des cas plus simples visant à définir des relations avec des ressources de la base de données, utilisez une activité [Réconciliation](../../automating/using/reconciliation.md).

1. Définissez les données additionnelles dans l&#39;onglet **[!UICONTROL Données additionnelles]** de l&#39;activité. Vous pouvez définir des données additionnelles (champs simples, agrégats et collections) liées à la dimension de ciblage de l&#39;ensemble principal ou reposant sur les liens créés dans l&#39;onglet **[!UICONTROL Relations avancées]** de l&#39;activité **[!UICONTROL Enrichissement]**.

   Consultez la section [Enrichir des données](../../automating/using/query.md#enriching-data).

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Les données peuvent maintenant être utilisées dans les activités reliées qui se trouvent à la suite de l&#39;**[!UICONTROL Enrichissement]**. Par exemple, vous pouvez les retrouver via le lien **[!UICONTROL Données additionnelles (targetData)]** de l&#39;explorateur des champs de personnalisation dans un contenu d&#39;email.
