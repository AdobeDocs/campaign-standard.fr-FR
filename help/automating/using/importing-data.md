---
title: Importer des données
description: Découvrez comment importer des données avec un workflow.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b71d19672efe24040d676bbcff3f90177b3fbcae

---


# Importer des données{#importing-data}

## Collecter des données {#collecting-data}

Vous pouvez collecter des données depuis un fichier pour les traiter et/ou les importer dans la base de données Adobe Campaign.

* The **[!UICONTROL Load file]** activity allows you to import data in one structured form to use this data in Adobe Campaign. Les données importées le sont temporairement et nécessitent l&#39;utilisation d&#39;une autre activité pour les intégrer définitivement dans la base de données Adobe Campaign.

   For more on how to use this activity, refer to [this section](../../automating/using/load-file.md).

* The **[!UICONTROL Transfer file]** activity allows you to receive or send files, test whether there are files present, or list files in Adobe Campaign.
You can use this activity before a **[!UICONTROL Load file]** in case you need to retrieve the file from an external source.

   For more on how to use this activity, refer to [this section](../../automating/using/transfer-file.md).

## Bonnes pratiques d&#39;import {#import-best-practices}

Pour garantir la cohérence des données au sein de la base de données et éviter les erreurs fréquentes lors de la mise à jour de la base de données ou de l&#39;export de données, faites preuve de précaution et suivez les quelques règles simples détaillées ci-dessous.

### Utiliser les modèles d&#39;import   {#using-import-templates}

La plupart des  d’importation doivent contenir  suivants : **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

L&#39;utilisation de modèles d&#39;import facilite la préparation d&#39;imports similaires et garantit la cohérence des données au sein de la base de données.

In many projects, imports are built without **[!UICONTROL Deduplication]** activity because the files used in the project do not have duplicates. Des doublons apparaissent parfois suite à l&#39;import d&#39;autres fichiers. La déduplication est alors difficile. C&#39;est pourquoi l&#39;ajout d&#39;une étape de déduplication est une précaution utile pour tous les workflows d&#39;import.

Ne partez pas de l&#39;hypothèse selon laquelle les données entrantes sont cohérentes et justes ou que le département informatique ou le responsable Adobe Campaign s&#39;en occupera. Gardez la normalisation des données à l&#39;esprit tout au long du projet. Veillez à dédupliquer, à réconcilier et à maintenir la cohérence des données lors des imports.

Un exemple de modèle de workflow générique conçu pour importer des données est disponible dans la section [Exemple : modèle de workflow d&#39;import](#example--import-workflow-template).

>[!NOTE]
>
>Vous pouvez également utiliser des [modèles d&#39;import](../../automating/using/importing-data-with-import-templates.md). Il existe des modèles de workflow définis par un administrateur qui, lorsqu&#39;ils sont activés, permettent uniquement de spécifier le fichier contenant les données à importer.

**Rubriques connexes :**

* [Charger le fichier ](../../automating/using/load-file.md)
* [de réconciliation](../../automating/using/reconciliation.md)
* [Activité Segmentation](../../automating/using/segmentation.md)
* [Deduplication activity](../../automating/using/deduplication.md)
* [Mettre à jour les données](../../automating/using/update-data.md)

### Utiliser des formats de fichiers plats   {#using-flat-file-formats}

Le format le plus efficace pour les imports est le fichier plat. Les fichiers plats peuvent être importés en masse au niveau de la base de données.

Par exemple :

* Séparateur : onglet ou point virgule
* Première ligne avec en-têtes
* Pas de délimiteur de chaîne
* Format de date : AAAA/MM/JJ HH:mm:SS

Voici un exemple de fichier à importer :

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

### Utiliser la compression   {#using-compression}

Lorsque cela est possible, utilisez des fichiers compressés pour les imports et les exports. GZIP est pris en charge par défaut. You can add pre-processing when importing files or post-processing when extracting data, respectively in the **[!UICONTROL Load file]** and **[!UICONTROL Extract file]** workflow activities.

**Rubriques connexes :**

* [Charger le fichier ](../../automating/using/load-file.md)
* [Extraire le fichier ](../../automating/using/extract-file.md)

### Importer en mode Delta {#importing-in-delta-mode}

Les imports standard doivent être effectués en mode delta. Cela signifie qu&#39;au lieu d&#39;envoyer le tableau entier à chaque fois, seules les données modifiées ou nouvelles sont envoyée à Adobe Campaign.

Les imports complets sont réservés au chargement initial.

### Maintenir la cohérence   {#maintaining-consistency}

Pour maintenir la cohérence des données dans la base de données Adobe Campaign, veuillez appliquer les principes suivants :

* Si les données importées correspondent à une table de référence dans Adobe Campaign, elles doivent être réconciliées avec ce tableau dans le workflow. Les enregistrements sans correspondance doivent être rejetés.
* Assurez-vous que les données importées soient toujours **« normalisées »** (email, numéro de téléphone, adresse postale) et que cette normalisation soit fiable et ne risque pas de changer pas au fil des années. Si ce n&#39;est pas le cas, des doublons risquent d&#39;apparaître dans la base de données, et dans la mesure où Adobe Campaign ne fournit pas d&#39;outils de « correspondance approximative », leur suppression sera très difficile.
* Les données transactionnelles doivent être dotées d&#39;une clé de réconciliation et être réconciliées avec les données existantes afin d&#39;éviter la création de doublons.
* **Les fichiers liés doivent être importés dans l&#39;ordre**. Si l&#39;import est composé de fichiers multiples et interdépendants, le workflow doit vérifier que les fichiers sont importés dans l&#39;ordre. Si un fichier échoue, les autres fichiers ne sont pas importés.
* **Dédupliquez**, réconciliez et maintenez la cohérence lorsque vous importez des données.

## Gérer des données cryptées {#managing-encrypted-data}

Dans certains cas, les données que vous souhaitez importer peuvent être cryptées, par exemple si elles contiennent des données d’identification personnelle.

Pour pouvoir importer ou exporter des fichiers cryptés, vous devez d’abord contacter l’Assistance clientèle d’Adobe pour obtenir votre instance avec les commandes de cryptage/décryptage nécessaires.

Pour ce faire, envoyez une requête indiquant :

* Le **libellé** qui s’affichera dans l’interface de Campaign pour utiliser la commande. Par exemple, « Crypter le fichier ».
* La **commande** à installer sur votre instance.
Par exemple, pour décrypter un fichier à l’aide de PGP, la commande sera :

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Une fois la requête traitée, les commandes de chiffrement/déchiffrement seront disponibles dans le **!UICONTROL Pre-processing stage]** champ à partir du **[!UICONTROL Load file]** et de l&#39; de **[!UICONTROL Extract file]** . Vous pouvez les utiliser pour décrypter ou crypter les fichiers à importer ou exporter.

![](assets/preprocessing-encryption.png)

**Rubriques connexes :**

* [Chargement de fichier](../../automating/using/load-file.md)
* [Extraction de fichier](../../automating/using/extract-file.md)

## Création de modèles de processus pour importer des données {#example--import-workflow-template}

L&#39;utilisation d&#39;un modèle d&#39;import est une bonne pratique si vous devez importer régulièrement des fichiers de structure identique.

Cet exemple montre comment pré-paramétrer un workflow qui pourra être réutilisé pour importer des profils en provenance d&#39;un CRM dans la base de données Adobe Campaign.

1. Créez un modèle de processus à partir de **[!UICONTROL Resources > Templates > Workflow templates]**.
1. Ajoutez les activités suivantes :

   * **[!UICONTROL Load file]**: Définissez la structure attendue du fichier contenant les données à importer.

      >[!NOTE]
      >
      >Il n&#39;est possible d&#39;importer que les données d&#39;un seul fichier. If the workflow has multiple **[!UICONTROL Load file]** activities, the same file will be used each time.

   * **[!UICONTROL Reconciliation]**: Rapprochez les données importées des données de base de données.
   * **[!UICONTROL Segmentation]** : créez des filtres pour traiter les enregistrements différemment selon qu&#39;ils aient pu ou non être réconciliés.
   * **[!UICONTROL Deduplication]**: Dédupliquez les données du fichier entrant avant de les insérer dans la base de données.
   * **[!UICONTROL Update data]**: Mettez à jour la base de données avec le  importé.
   ![](assets/import_template_example0.png)

1. Configurez le   : **[!UICONTROL Load file]**

   * Définissez la structure attendue en téléchargeant un fichier exemple. Le fichier exemple ne doit contenir que quelques lignes mais toutes les colonnes nécessaires pour l&#39;import. Vérifiez et éditez le format du fichier pour vous assurer que le type de chaque colonne est paramétré correctement : texte, date, nombre entier, etc.
Par exemple :

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Dans la **[!UICONTROL File to load]** section, sélectionnez **[!UICONTROL Upload a new file from the local machine]** et laissez le champ vide. A chaque fois qu&#39;un nouveau workflow sera créé à partir de ce modèle, vous pourrez préciser ici le fichier souhaité (tant qu&#39;il correspond à la structure définie).

      Toutes les options sont utilisables, mais il faut modifier le modèle en conséquence. Par exemple, si vous sélectionnez **[!UICONTROL Use the file specified in the inbound transition]**, vous pouvez ajouter un **[!UICONTROL Transfer file]** avant de récupérer le fichier à importer à partir d’un serveur FTP/SFTP.

      Si vous souhaitez que les utilisateurs puissent télécharger un fichier contenant des erreurs survenues au cours d’une importation, cochez l’ **[!UICONTROL Keep the rejects in a file]** option et spécifiez le **[!UICONTROL File name]**.

      ![](assets/import_template_example1.png)

1. Configurez le **[!UICONTROL Reconciliation]** . Dans ce contexte, le but de cette activité est d&#39;identifier les données entrantes.

   * In the **[!UICONTROL Relations]** tab, select **[!UICONTROL Create element]** and define a link between the imported data and the recipients targeting dimension (see [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** permet de créer la condition de jointure. Utilisez le champ ou la combinaison de champs nécessaire tant que l&#39;identification des enregistrements uniques reste possible.
   * Dans l’ **[!UICONTROL Identification]** onglet, laissez l’ **[!UICONTROL Identify the document from the working data]** option désactivée.
   ![](assets/import_template_example2.png)

1. Configurez l&#39;activité **[!UICONTROL Segmentation]** pour récupérer les destinataires réconciliés dans une transition, ainsi que les destinataires qui n&#39;ont pas pu être réconciliés mais qui disposent de suffisamment de données dans une autre transition.

   La transition des destinataires réconciliés peut alors être utilisée pour mettre à jour la base de données. La transition des destinataires inconnus peut servir à créer de nouvelles entrées de destinataires dans la base de données si un ensemble d&#39;informations minimum est disponible dans le fichier.

   Les destinataires ne pouvant pas être réconciliés et ne disposant pas de suffisamment de données sont sélectionnés dans une transition sortante complémentaire et peuvent être exportés dans un fichier séparé ou tout simplement ignorés.

   * Dans l’ **[!UICONTROL General]** onglet de la  , définissez la **[!UICONTROL Resource type]** valeur **[!UICONTROL Temporary resource]** et sélectionnez **[!UICONTROL Reconciliation]** comme jeu ciblé.
   * In the **[!UICONTROL Advanced options]** tab, check the **[!UICONTROL Generate complement]** option to be able to see if any record cannot be inserted in the database. Le cas échéant, vous pourrez alors appliquer d&#39;autres traitements aux données complémentaires : export de fichier, mise à jour de liste, etc.
   * Dans le premier segment de l&#39;onglet **[!UICONTROL Segments]**, ajoutez une condition de filtrage sur la population entrante pour sélectionner uniquement les enregistrements pour lesquels l&#39;identifiant dans le CRM du profil est différent de 0. De cette manière, les données du fichier réconciliées avec les profils de la base de données sont sélectionnées dans ce sous-ensemble.

      ![](assets/import_template_example3.png)

   * Ajoutez un second segment pour sélectionner les enregistrements non réconciliés disposant de suffisamment de données pour être intégrés dans la base de données Par exemple : adresse email, prénom et nom de famille. La valeur de l&#39;identifiant dans le CRM des profils des enregistrements qui ne sont pas réconciliés est égale à 0.

      ![](assets/import_template_example3_2.png)

   * All records that are not selected in the first two subsets are selected in the **[!UICONTROL Complement]**.

1. Configure the **[!UICONTROL Update data]** activity located after the first outbound transition of the **[!UICONTROL Segmentation]** activity configured previously.

   * Select **[!UICONTROL Update]** as **[!UICONTROL Operation type]** since the inbound transition only contains recipients already present in the database.
   * Dans l’ **[!UICONTROL Identification]** onglet, sélectionnez **[!UICONTROL Using reconciliation criteria]** et définissez une clé entre le **[!UICONTROL Dimension to update]** -  de dans ce cas - et le lien créé dans le **[!UICONTROL Reconciliation]** . Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** est utilisé.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Si les noms des colonnes du fichier sont identiques ou presque identiques aux noms des champs de la dimension des destinataires, utilisez le bouton baguette magique pour réconcilier les différents champs automatiquement.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si vous envisagez d&#39;envoyer des courriers à ces profils, veillez à inclure une adresse postale, car cette information est indispensable pour l&#39;opérateur de services postaux. Also make sure that the **[!UICONTROL Address specified]** box in your profiles&#39; information is checked. Pour mettre à jour cette option dans un workflow, ajoutez simplement un élément aux champs à mettre à jour. Spécifiez **1** comme **[!UICONTROL Source]** et sélectionnez le champ **postalAddress/@addrDefined** comme **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. Configure the **[!UICONTROL Deduplication]** activity located after the transition containing unreconciled profiles:

   * In the **[!UICONTROL Properties]** tab, set the **[!UICONTROL Resource type]** to the temporary resource generated from the **[!UICONTROL Reconciliation]** activity of the workflow.

      ![](assets/import_template_example4.png)

   * Dans cet exemple, le champ email est utilisé pour trouver les profils uniques. Vous pouvez utiliser n&#39;importe quel champ dont vous êtes sûr qu&#39;il est rempli et qu&#39;il fait partie d&#39;une combinaison unique.
   * Choose a **[!UICONTROL Deduplication method]**. Dans ce cas, l&#39;application décide automatiquement quels enregistrements conserver en cas de doublons.
   ![](assets/import_template_example7.png)

1. Configurez le **[!UICONTROL Update data]**  situé après le **[!UICONTROL Deduplication]** configuré précédemment.

   * Select **[!UICONTROL Insert only]** as **[!UICONTROL Operation type]** since the inbound transition only contains profiles not present in the database.
   * Dans l’ **[!UICONTROL Identification]** onglet, sélectionnez **[!UICONTROL Using reconciliation criteria]** et définissez une clé entre le **[!UICONTROL Dimension to update]** -  de dans ce cas - et le lien créé dans le **[!UICONTROL Reconciliation]** . Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** est utilisé.

      ![](assets/import_template_example6.png)

   * In the **[!UICONTROL Fields to update]** tab, indicate the fields from the Profiles dimension to update with the value of the corresponding column from the file. Si les noms des colonnes du fichier sont identiques ou presque identiques aux noms des champs de la dimension des destinataires, utilisez le bouton baguette magique pour réconcilier les différents champs automatiquement.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si vous envisagez d&#39;envoyer des courriers à ces profils, veillez à inclure une adresse postale, car cette information est indispensable pour l&#39;opérateur de services postaux. Also make sure that the **[!UICONTROL Address specified]** box in your profiles&#39; information is checked. Pour mettre à jour cette option dans un workflow, ajoutez simplement un élément aux champs à mettre à jour. Spécifiez **1** comme **[!UICONTROL Source]** et sélectionnez le champ **[postalAddress/@addrDefined]** comme **[!UICONTROL Destination]**. For more on direct mail and the use of the **[!UICONTROL Address specified]** option, see [this document](../../channels/using/about-direct-mail.md#recommendations).

1. After the third transition of the **[!UICONTROL Segmentation]** activity, add a **[!UICONTROL Extract file]** activity and a **[!UICONTROL Transfer file]** activity if you want to keep track of data not inserted in the database. Paramétrez ces activités afin d&#39;exporter la colonne dont vous avez besoin et de transférer le fichier sur un serveur FTP ou SFTP, où vous pourrez le récupérer.
1. Add an **[!UICONTROL End]** activity and save the workflow template.

Le modèle est à présent utilisable et disponible pour chaque nouveau workflow. All is needed is then to specify the file containing the data to import in the **[!UICONTROL Load file]** activity.

![](assets/import_template_example9.png)
