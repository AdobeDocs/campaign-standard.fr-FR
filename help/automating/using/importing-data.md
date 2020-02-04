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
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Importer des données{#importing-data}

## Collecter des données {#collecting-data}

Vous pouvez collecter des données depuis un fichier pour les traiter et/ou les importer dans la base de données Adobe Campaign.

* L&#39;activité **[!UICONTROL Chargement de fichier]**permet d&#39;importer les données d&#39;un fichier sous une forme structurée afin de les utiliser dans Adobe Campaign. Les données importées le sont temporairement et nécessitent l&#39;utilisation d&#39;une autre activité pour les intégrer définitivement dans la base de données Adobe Campaign.
* L&#39;activité **[!UICONTROL Transfert de fichier]**permet de recevoir ou d&#39;envoyer des fichiers, de tester la présence de fichiers ou de lister les fichiers dans Adobe Campaign.

   Vous pouvez utiliser cette activité avant un **[!UICONTROL Chargement de fichier]**si vous devez récupérer le fichier à partir d&#39;une source externe.

## Bonnes pratiques d&#39;import {#import-best-practices}

Pour garantir la cohérence des données au sein de la base de données et éviter les erreurs fréquentes lors de la mise à jour de la base de données ou de l&#39;export de données, faites preuve de précaution et suivez les quelques règles simples détaillées ci-dessous.

### Utiliser les modèles d&#39;import  {#using-import-templates}

La plupart des workflows d&#39;import doivent contenir les activités suivantes : **[!UICONTROL Chargement de fichier]**,**[!UICONTROL  Réconciliation]**, **[!UICONTROL Segmentation]**,**[!UICONTROL  Déduplication]**, **[!UICONTROL Mise à jour de données]**.

L&#39;utilisation de modèles d&#39;import facilite la préparation d&#39;imports similaires et garantit la cohérence des données au sein de la base de données.

Pour de nombreux projets, les imports sont construits sans activité de **[!UICONTROL Déduplication]**car les fichiers utilisés n&#39;ont pas de doublon. Des doublons apparaissent parfois suite à l&#39;import d&#39;autres fichiers. La déduplication est alors difficile. C&#39;est pourquoi l&#39;ajout d&#39;une étape de déduplication est une précaution utile pour tous les workflows d&#39;import.

Ne partez pas de l&#39;hypothèse selon laquelle les données entrantes sont cohérentes et justes ou que le département informatique ou le responsable Adobe Campaign s&#39;en occupera. Gardez la normalisation des données à l&#39;esprit tout au long du projet. Veillez à dédupliquer, à réconcilier et à maintenir la cohérence des données lors des imports.

Un exemple de modèle de workflow générique conçu pour importer des données est disponible dans la section [Exemple : modèle de workflow d&#39;import](#example--import-workflow-template).

>[!NOTE]
>
>Vous pouvez également utiliser des [modèles d&#39;import](../../automating/using/importing-data-with-import-templates.md). Il existe des modèles de workflow définis par un administrateur qui, lorsqu&#39;ils sont activés, permettent uniquement de spécifier le fichier contenant les données à importer.

### Utiliser des formats de fichiers plats  {#using-flat-file-formats}

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

### Utiliser la compression  {#using-compression}

Lorsque cela est possible, utilisez des fichiers compressés pour les imports et les exports. GZIP est pris en charge par défaut. Vous pouvez ajouter une étape de prétraitement lors de l&#39;import des fichiers ou de post-traitement lors de l&#39;extraction des données dans les activités de workflow **[!UICONTROL Chargement de fichier]**et**[!UICONTROL  Extraction de fichier]**.

### Importer en mode Delta {#importing-in-delta-mode}

Les imports standard doivent être effectués en mode delta. Cela signifie qu&#39;au lieu d&#39;envoyer le tableau entier à chaque fois, seules les données modifiées ou nouvelles sont envoyée à Adobe Campaign.

Les imports complets sont réservés au chargement initial.

### Maintenir la cohérence  {#maintaining-consistency}

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

Une fois la requête traitée, les commandes de cryptage/décryptage seront disponibles dans le champ **!UICONTROL Etape de pré-traitement]**des activités**[!UICONTROL  Chargement de données (fichier)]** et **[!UICONTROL Extraction de données (fichier)]**. Vous pouvez les utiliser pour décrypter ou crypter les fichiers à importer ou exporter.

![](assets/preprocessing-encryption.png)

## Exemple : modèle de workflow d&#39;import  {#example--import-workflow-template}

L&#39;utilisation d&#39;un modèle d&#39;import est une bonne pratique si vous devez importer régulièrement des fichiers de structure identique.

Cet exemple montre comment pré-paramétrer un workflow qui pourra être réutilisé pour importer des profils en provenance d&#39;un CRM dans la base de données Adobe Campaign.

1. Créez un nouveau modèle de workflow à partir de **[!UICONTROL Ressources > Modèles > Modèles de workflow]**.
1. Ajoutez les activités suivantes :

   * **[!UICONTROL Chargement de fichier]** : définissez la structure attendue du fichier contenant les données à importer.

      >[!NOTE]
      >
      >Il n&#39;est possible d&#39;importer que les données d&#39;un seul fichier. Si le workflow comporte plusieurs activités de **[!UICONTROL Chargement de fichier]**, le même fichier sera réutilisé à chaque fois.

   * **[!UICONTROL Réconciliation]** : réconciliez les données importées avec les données se trouvant dans la base de données.
   * **[!UICONTROL Segmentation]** : créez des filtres pour traiter les enregistrements différemment selon qu&#39;ils aient pu ou non être réconciliés.
   * **[!UICONTROL Déduplication]** : dédupliquez les données du fichier entrant avant son import dans la base de données.
   * **[!UICONTROL Mise à jour de données]** : mettez la base de données à jour avec les profils importés.
   ![](assets/import_template_example0.png)

1. Configurez l&#39;activité **[!UICONTROL Chargement de fichier]** :

   * Définissez la structure attendue en téléchargeant un fichier exemple. Le fichier exemple ne doit contenir que quelques lignes mais toutes les colonnes nécessaires pour l&#39;import. Vérifiez et éditez le format du fichier pour vous assurer que le type de chaque colonne est paramétré correctement : texte, date, nombre entier, etc.
Par exemple :

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Dans la section **[!UICONTROL Fichier à charger]**, sélectionnez**[!UICONTROL  Transférer un nouveau fichier depuis le poste local]** et laissez le champ vide. A chaque fois qu&#39;un nouveau workflow sera créé à partir de ce modèle, vous pourrez préciser ici le fichier souhaité (tant qu&#39;il correspond à la structure définie).

      Toutes les options sont utilisables, mais il faut modifier le modèle en conséquence. Par exemple, si vous sélectionnez **[!UICONTROL Utiliser le fichier provenant de la transition entrante]**, vous pouvez ajouter une activité**[!UICONTROL  Transfert de fichier]** avant de récupérer le fichier à importer à partir d&#39;un serveur FTP/SFTP.

      Si vous souhaitez que les utilisateurs puissent télécharger un fichier contenant les erreurs qui se sont produites pendant un import, cochez l&#39;option **[!UICONTROL Conserver les rejets dans un fichier]**et indiquez le**[!UICONTROL  Nom du fichier]**.

      ![](assets/import_template_example1.png)

1. Configurez l&#39;activité **[!UICONTROL Réconciliation]**. Dans ce contexte, le but de cette activité est d&#39;identifier les données entrantes.

   * Dans l&#39;onglet **[!UICONTROL Liens]**, sélectionnez**[!UICONTROL  Créer un élément]** et définissez un lien entre les données importées et la dimension de ciblage des destinataires (voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources)). Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** permet de créer la condition de jointure. Utilisez le champ ou la combinaison de champs nécessaire tant que l&#39;identification des enregistrements uniques reste possible.
   * Dans l&#39;onglet **[!UICONTROL Identification]**, laissez l&#39;option**[!UICONTROL  Identifier le document de ciblage à partir des données de travail]** décochée.
   ![](assets/import_template_example2.png)

1. Configurez l&#39;activité **[!UICONTROL Segmentation]**pour récupérer les destinataires réconciliés dans une transition, ainsi que les destinataires qui n&#39;ont pas pu être réconciliés mais qui disposent de suffisamment de données dans une autre transition.

   La transition des destinataires réconciliés peut alors être utilisée pour mettre à jour la base de données. La transition des destinataires inconnus peut servir à créer de nouvelles entrées de destinataires dans la base de données si un ensemble d&#39;informations minimum est disponible dans le fichier.

   Les destinataires ne pouvant pas être réconciliés et ne disposant pas de suffisamment de données sont sélectionnés dans une transition sortante complémentaire et peuvent être exportés dans un fichier séparé ou tout simplement ignorés.

   * Dans l&#39;onglet **[!UICONTROL Général]**de l&#39;activité, définissez le**[!UICONTROL  Type de ressource]** sur **[!UICONTROL Ressource temporaire]**et sélectionnez**[!UICONTROL  Réconciliation]** comme ensemble ciblé.
   * Dans l&#39;onglet **[!UICONTROL Options avancées]**, cochez l&#39;option**[!UICONTROL  Générer le complémentaire]** pour voir si des enregistrements n&#39;ont pas pu être intégrés dans la base de données. Le cas échéant, vous pourrez alors appliquer d&#39;autres traitements aux données complémentaires : export de fichier, mise à jour de liste, etc.
   * Dans le premier segment de l&#39;onglet **[!UICONTROL Segments]**, ajoutez une condition de filtrage sur la population entrante pour sélectionner uniquement les enregistrements pour lesquels l&#39;identifiant dans le CRM du profil est différent de 0. De cette manière, les données du fichier réconciliées avec les profils de la base de données sont sélectionnées dans ce sous-ensemble.

      ![](assets/import_template_example3.png)

   * Ajoutez un second segment pour sélectionner les enregistrements non réconciliés disposant de suffisamment de données pour être intégrés dans la base de données Par exemple : adresse email, prénom et nom de famille. La valeur de l&#39;identifiant dans le CRM des profils des enregistrements qui ne sont pas réconciliés est égale à 0.

      ![](assets/import_template_example3_2.png)

   * Tous les enregistrement qui ne sont pas sélectionnés dans les deux premiers sous-ensembles sont sélectionnés dans le **[!UICONTROL Complémentaire]**.

1. Configurez l&#39;activité **[!UICONTROL Mise à jour de données]**située après la première transition sortante de l&#39;activité**[!UICONTROL  Segmentation]** paramétrée précédemment.

   * Sélectionnez **[!UICONTROL Mise à jour]**comme**[!UICONTROL  Type d&#39;opération]**, puisque la transition entrante contient uniquement des destinataires déjà présents dans la base de données.
   * Dans l&#39;onglet **[!UICONTROL Identification]**, sélectionnez**[!UICONTROL  En utilisant des critères de réconciliation]** et définissez une clé entre la **[!UICONTROL Dimension à mettre à jour]**, Profils dans le cas présent, et le lien créé dans l&#39;activité**[!UICONTROL  Réconciliation]**. Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** est utilisé.

      ![](assets/import_template_example6.png)

   * Dans l&#39;onglet **[!UICONTROL Champs à mettre à jour]**, indiquez les champs de la dimension Profils à mettre à jour avec la valeur de la colonne correspondante du fichier. Si les noms des colonnes du fichier sont identiques ou presque identiques aux noms des champs de la dimension des destinataires, utilisez le bouton baguette magique pour réconcilier les différents champs automatiquement.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si vous envisagez d&#39;envoyer des courriers à ces profils, veillez à inclure une adresse postale, car cette information est indispensable pour l&#39;opérateur de services postaux. Assurez-vous également que la case **[!UICONTROL Adresse renseignée]**est cochée dans les informations des profils. Pour mettre à jour cette option dans un workflow, ajoutez simplement un élément aux champs à mettre à jour. Spécifiez** 1 **comme**[!UICONTROL  Source]** et sélectionnez le champ **`postalAddress/@addrDefined`**comme**[!UICONTROL  Destination]**. Pour plus d&#39;informations sur les courriers et l&#39;utilisation de l&#39;option **[!UICONTROL Adresse renseignée]**, consultez[ce document](../../channels/using/about-direct-mail.md#recommendations).

1. Configurez l&#39;activité **[!UICONTROL Déduplication]**située après la transition contenant les profils non réconciliés :

   * Dans l&#39;onglet **[!UICONTROL Propriétés]**, définissez le**[!UICONTROL  Type de ressource]** sur la ressource temporaire générée à partir de l&#39;activité **[!UICONTROL Réconciliation]**du workflow.

      ![](assets/import_template_example4.png)

   * Dans cet exemple, le champ email est utilisé pour trouver les profils uniques. Vous pouvez utiliser n&#39;importe quel champ dont vous êtes sûr qu&#39;il est rempli et qu&#39;il fait partie d&#39;une combinaison unique.
   * Sélectionnez une **[!UICONTROL Méthode de déduplication]**. Dans ce cas, l&#39;application décide automatiquement quels enregistrements conserver en cas de doublons.
   ![](assets/import_template_example7.png)

1. Configurez l&#39;activité **[!UICONTROL Mise à jour de données]**située après l&#39;activité**[!UICONTROL  Déduplication]** paramétrée précédemment.

   * Sélectionnez **[!UICONTROL Ajouter uniquement]**comme**[!UICONTROL  Type d&#39;opération]**, puisque la transition entrante contient uniquement des profils non présents dans la base de données.
   * Dans l&#39;onglet **[!UICONTROL Identification]**, sélectionnez**[!UICONTROL  En utilisant des critères de réconciliation]** et définissez une clé entre la **[!UICONTROL Dimension à mettre à jour]**, Profils dans le cas présent, et le lien créé dans l&#39;activité**[!UICONTROL  Réconciliation]**. Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** est utilisé.

      ![](assets/import_template_example6.png)

   * Dans l&#39;onglet **[!UICONTROL Champs à mettre à jour]**, indiquez les champs de la dimension Profils à mettre à jour avec la valeur de la colonne correspondante du fichier. Si les noms des colonnes du fichier sont identiques ou presque identiques aux noms des champs de la dimension des destinataires, utilisez le bouton baguette magique pour réconcilier les différents champs automatiquement.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si vous envisagez d&#39;envoyer des courriers à ces profils, veillez à inclure une adresse postale, car cette information est indispensable pour l&#39;opérateur de services postaux. Assurez-vous également que la case **[!UICONTROL Adresse renseignée]**est cochée dans les informations des profils. Pour mettre à jour cette option dans un workflow, ajoutez simplement un élément aux champs à mettre à jour. Spécifiez** 1 **comme**[!UICONTROL  Source]** et sélectionnez le champ **[postalAddress/@addrDefined]**comme**[!UICONTROL  Destination]**. Pour plus d&#39;informations sur les courriers et l&#39;utilisation de l&#39;option **[!UICONTROL Adresse renseignée]**, consultez[ce document](../../channels/using/about-direct-mail.md#recommendations).

1. Après la troisième transition de l&#39;activité **[!UICONTROL Segmentation]**, ajoutez une activité**[!UICONTROL  Extraction de fichier]** et une activité **[!UICONTROL Transfert de fichier]**si vous voulez tracker les données non insérées dans la base de données. Paramétrez ces activités afin d&#39;exporter la colonne dont vous avez besoin et de transférer le fichier sur un serveur FTP ou SFTP, où vous pourrez le récupérer.
1. Ajoutez une activité **[!UICONTROL Fin]**et enregistrez le modèle de workflow.

Le modèle est à présent utilisable et disponible pour chaque nouveau workflow. Il suffira alors de spécifier le fichier contenant les données à importer dans l&#39;activité **[!UICONTROL Chargement de fichier]**.

![](assets/import_template_example9.png)
