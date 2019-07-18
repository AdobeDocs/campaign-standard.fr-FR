---
title: Mise à jour de données
seo-title: Mise à jour de données
description: Mise à jour de données
seo-description: L'activité Mise à jour de données permet de mettre à jour en masse les champs de la base de données.
page-status-flag: jamais activé
uuid: 1 dc 55 db 5-affd -4688-b 673-adfb 8 c 1338 b 5
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: gestion des données-activités
discoiquuid: 4 db 83 c 95-4 b 75-4 a 16-8 dbf-bd 8940431 fa 9
context-tags: writer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Mise à jour de données{#update-data}

## Description {#description}

![](assets/data_update.png)

L'activité **[!UICONTROL Mise à jour de données]permet de mettre à jour en masse les champs de la base de données.**

## Contexte d'utilisation {#context-of-use}

L'activité **Mise à jour de données** peut notamment être utilisée suite à un import de fichier, afin d'insérer les données récupérées dans la base de données Adobe Campaign. Plusieurs options permettent de personnaliser la mise à jour des données.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Mise à jour de données]dans votre workflow.**
1. Sélectionnez l'activité puis ouvrez-la à l'aide du bouton ![, disponible dans les actions rapides qui s'affichent.](assets/edit_darkgrey-24px.png)
1. Définissez le **[!UICONTROL Type d'opération]à réaliser :**

   * **[!UICONTROL Ajouter ou mettre à jour]** : ajouter des données ou les mettre à jour si des enregistrements existent déjà dans la base.
   * **[!UICONTROL Ajouter uniquement]** : ajouter des données uniquement. Les enregistrements déjà existants ne sont pas mis à jour. Si des critères de réconciliation sont définis, seuls les enregistrements non réconciliés sont ajoutés.

      Cochez la case **[!UICONTROL Générer une transition sortante pour les rejets]si les données importées comportent certains enregistrements déjà présents en base afin d'éviter toute erreur.**

   * **[!UICONTROL Mettre à jour]** : mettre à jour des données des enregistrements déjà présents en base uniquement.
   * **[!UICONTROL Supprimer]** : supprimer des données.
   >[!NOTE]
   >
   >Le champ **[!UICONTROL Taille du lot]permet de définir la taille maximale du lot des données à télécharger.**

1. Dans l'onglet **[!UICONTROL Identification], indiquez comment identifier les enregistrements dans la base de données :**

   * **[!UICONTROL En utilisant des clés de réconciliation]** : sélectionnez la **[!UICONTROL Dimension à mettre à jour]**, puis définissez les **[!UICONTROL Clés permettant de retrouver les enregistrements]**. Voir à ce sujet [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources).
   * Si les données en entrée correspondent à une dimension de ciblage existante, sélectionnez l'option **[!UICONTROL En utilisant directement la dimension de ciblage.]** Sélectionnez alors la **[!UICONTROL Dimension à mettre à jour]**.
   Si le type d'opération sélectionné implique une mise à jour, vous devez obligatoirement utiliser des clés de réconciliation.

1. Dans l'onglet **[!UICONTROL Champs à mettre à jour], définissez les champs sur lesquels appliquer la mise à jour et, au besoin, ajoutez des conditions pour que cette mise à jour soit réalisée.** Pour cela, utilisez la colonne **[!UICONTROL Prise en compte si.]** Les conditions sont appliquées les unes après les autres, dans l'ordre de la liste. Utilisez les flèches situées à droite pour modifier l'ordre des mises à jour. Vous pouvez utiliser plusieurs fois le même champ de destination.

   Vous pouvez associer automatiquement les champs à l'aide du bouton ![.](assets/wkf_magic_wand-24px.png) L'association automatique détecte les champs portant le même nom.

   Dans le cadre d'une opération de type **[!UICONTROL Ajouter ou mettre à jour], vous pouvez sélectionner individuellement, pour chaque champ, l'opération à appliquer.** Pour cela, sélectionnez la valeur souhaitée dans la colonne **[!UICONTROL Opération].**

   >[!NOTE]
   >
   >**Gestion des mises à jour** Les champs **[!UICONTROL lastmodified]**, **[!UICONTROL modifiedby]**, **[!UICONTROL created]** et **[!UICONTROL createdby]** sont automatiquement mis à jour lorsqu'une activité de données de mise à jour est exécutée, sauf si leur configuration est explicitement effectuée sur le tableau de mise à jour du champ. La mise à jour des enregistrements n'est réalisée que pour les enregistrements pour lesquels au moins une différence a été détectée. Si les valeurs sont les mêmes, aucune mise à jour n'est effectuée.

1. Si besoin, gérez les [Transitions](../../automating/using/executing-a-workflow.md#managing-an-activity-s-outbound-transitions) de l'activité afin d'accéder à des options avancées sur la population transmise en sortie.

   Si vous avez sélectionné **[!UICONTROL Ajouter uniquement]** et que les données importées peuvent comporter des enregistrements déjà présents en base, cochez la case **Générer une transition sortante pour les rejets]afin d'éviter toute erreur.[!UICONTROL **

1. Validez le paramétrage de l'activité et enregistrez le workflow.

## Exemple {#example}

L'exemple suivant montre le paramétrage d'une activité de **[!UICONTROL Mise à jour de données]** suite à un **Chargement de fichier.** Le but du workflow est d'ajouter ou de mettre à jour les profils de la base Adobe Campaign avec les données récupérées depuis le fichier. La clé de réconciliation utilisée est l'adresse email.

Le fichier chargé est un fichier au format **.txt** contenant les données d'exemple suivantes :

```
lastname;firstname;email;birthdate
jackman;megan;megan.jackman@testmail.com;07/08/1975
phillips;edward;phillips@testmail.com;09/03/1986
weaver;justin;justin_w@testmail.com;11/15/1990
martin;babeth;babeth_martin@testmail.net;11/25/1964
reese;richard;rreese@testmail.com;02/08/1987
cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
grimes;daryl;daryl_890@testmail.com;12/06/1979
tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
```

L'activité de **[!UICONTROL Mise à jour de données]est paramétrée comme suit :**

![](assets/deduplication_example2_writer1.png)

![](assets/deduplication_example2_writer2.png)

