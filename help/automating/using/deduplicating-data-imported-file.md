---
title: Dédupliquer les données d’un fichier importé
description: Cet exemple montre comment dédupliquer les données d'un fichier importé avant de les charger dans la base de données.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 631eb661-a696-4352-aa58-9097b391723e
TQID: 'https://experienceleague.adobe.com/7zC8CU4kl3WkPT6l2QM-dN3fFsKTrS2lEpGQUaV2GI8'
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
source-wordcount: '340'
ht-degree: 100%
---
# Dédupliquer les données d&#39;un fichier importé {#deduplicating-the-data-from-an-imported-file}

Cet exemple montre comment dédupliquer les données d&#39;un fichier importé avant de les charger dans la base de données. Ce procédé permet d&#39;améliorer la qualité des données chargées dans la base.

Le workflow est constitué comme suit :

![](assets/deduplication_example2_workflow.png)

* Un fichier contenant une liste profils est importé à l&#39;aide d&#39;un [Chargement de fichier](../../automating/using/load-file.md). Dans cet exemple, le fichier importé est au format .csv et contient 10 profils :

  ```
  lastname;firstname;dateofbirth;email
  Smith;Hayden;23/05/1989;hayden.smith@example.com
  Mars;Daniel;17/11/1987;dannymars@example.com
  Smith;Clara;08/02/1989;hayden.smith@example.com
  Durance;Allison;15/12/1978;allison.durance@example.com
  Lucassen;Jody;28/03/1988;jody.lucassen@example.com
  Binder;Tom;19/01/1982;tombinder@example.com
  Binder;Tommy;19/01/1915;tombinder@example.com
  Connor;Jade;10/10/1979;connor.jade@example.com
  Mack;Clarke;02/03/1985;clarke.mack@example.com
  Ross;Timothy;04/07/1986;timross@example.com
  ```

  Ce fichier peut également servir de fichier d&#39;exemple pour détecter et définir le format des colonnes. Depuis l&#39;onglet **[!UICONTROL Définition des colonnes]**, assurez-vous que chaque colonne du fichier importé est correctement paramétrée.

  ![](assets/deduplication_example2_fileloading.png)

* Une activité de [Déduplication](../../automating/using/deduplication.md). La déduplication est réalisée directement après l&#39;import du fichier et avant que les données soient insérées dans la base. Il faut donc se baser sur la **[!UICONTROL Ressource temporaire]** issue de l&#39;activité de **[!UICONTROL Chargement de fichier]**.

  Pour cet exemple, nous souhaitons conserver une seule entrée par adresse email unique contenue dans le fichier. L&#39;identification des doublons est donc réalisée sur la colonne **email** de la ressource temporaire. Or, deux adresses email apparaissent deux fois dans le fichier. Deux lignes seront donc considérées comme des doublons.

  ![](assets/deduplication_example2_dedup.png)

* Une activité de [Mise à jour de données](../../automating/using/update-data.md), permettant d&#39;insérer dans la base de données les données conservées à l&#39;issue de la déduplication. Ce n&#39;est qu&#39;au moment de la mise à jour de données que les données importées sont identifiées comme appartenant à la dimension des profils.

  Nous souhaitons ici **[!UICONTROL Ajouter uniquement]** les profils qui n&#39;existent pas déjà dans la base, en utilisant la colonne email du fichier et le champ email de la dimension **Profil** comme clé de réconciliation.

  ![](assets/deduplication_example2_writer1.png)

  Indiquez les mappings entre les colonnes du fichier dont vous souhaitez insérer les données et les champs de la base depuis l&#39;onglet **[!UICONTROL Champs à mettre à jour]**.

  ![](assets/deduplication_example2_writer2.png)

Lancez ensuite le workflow. Les enregistrements conservés à l&#39;issue de la déduplication sont alors ajoutés aux profils de votre base de données.
