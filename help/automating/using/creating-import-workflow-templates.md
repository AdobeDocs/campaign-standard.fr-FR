---
title: Création de modèles de workflow pour importer des données
description: Découvrez comment créer des modèles de workflow pour importer des données.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 100%

---


# Création de modèles de workflow pour importer des données {#import-workflow-template}

L’utilisation d’un modèle d’import est une bonne pratique si vous devez importer régulièrement des fichiers de structure identique.

Cet exemple montre comment pré-paramétrer un workflow qui pourra être réutilisé pour importer des profils en provenance d’un CRM dans la base de données Adobe Campaign.

1. Créez un nouveau modèle de workflow à partir de **[!UICONTROL Ressources > Modèles > Modèles de workflow]**.
1. Ajoutez les activités suivantes :

   * **[!UICONTROL Chargement de fichier]** : définissez la structure attendue du fichier contenant les données à importer.

      >[!NOTE]
      >
      >Il n’est possible d’importer que les données d’un seul fichier. Si le workflow comporte plusieurs activités de **[!UICONTROL Chargement de fichier]**, le même fichier sera réutilisé à chaque fois.

   * **[!UICONTROL Réconciliation]** : réconciliez les données importées avec les données se trouvant dans la base de données.
   * **[!UICONTROL Segmentation]** : créez des filtres pour traiter les enregistrements différemment selon qu’ils aient pu ou non être réconciliés.
   * **[!UICONTROL Déduplication]** : dédupliquez les données du fichier entrant avant son import dans la base de données.
   * **[!UICONTROL Mise à jour de données]** : mettez la base de données à jour avec les profils importés.

   ![](assets/import_template_example0.png)

1. Configurez l’activité **[!UICONTROL Chargement de fichier]** :

   * Définissez la structure attendue en téléchargeant un fichier exemple. Le fichier exemple ne doit contenir que quelques lignes mais toutes les colonnes nécessaires pour l’import. Vérifiez et éditez le format du fichier pour vous assurer que le type de chaque colonne est paramétré correctement : texte, date, nombre entier, etc.
Par exemple :

      ```
      lastname;firstname;birthdate;email;crmID
      Smith;Hayden;23/05/1989;hayden.smith@mailtest.com;123456
      ```

   * Dans la section **[!UICONTROL Fichier à charger]**, sélectionnez **[!UICONTROL Transférer un nouveau fichier depuis le poste local]** et laissez le champ vide. A chaque fois qu’un nouveau workflow sera créé à partir de ce modèle, vous pourrez préciser ici le fichier souhaité (tant qu’il correspond à la structure définie).

      Toutes les options sont utilisables, mais il faut modifier le modèle en conséquence. Par exemple, si vous sélectionnez **[!UICONTROL Utiliser le fichier provenant de la transition entrante]**, vous pouvez ajouter une activité **[!UICONTROL Transfert de fichier]** avant de récupérer le fichier à importer à partir d’un serveur FTP/SFTP.

      Si vous souhaitez que les utilisateurs puissent télécharger un fichier contenant les erreurs qui se sont produites pendant un import, cochez l’option **[!UICONTROL Conserver les rejets dans un fichier]** et indiquez le **[!UICONTROL Nom du fichier]**.

      ![](assets/import_template_example1.png)

1. Configurez l’activité **[!UICONTROL Réconciliation]**. Dans ce contexte, le but de cette activité est d’identifier les données entrantes.

   * Dans l’onglet **[!UICONTROL Liens]**, sélectionnez **[!UICONTROL Créer un élément]** et définissez un lien entre les données importées et la dimension de ciblage des destinataires (voir [Dimensions de ciblage et ressources](../../automating/using/query.md#targeting-dimensions-and-resources)). Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** permet de créer la condition de jointure. Utilisez le champ ou la combinaison de champs nécessaire tant que l’identification des enregistrements uniques reste possible.
   * Dans l’onglet **[!UICONTROL Identification]**, laissez l’option **[!UICONTROL Identifier le document de ciblage à partir des données de travail]** décochée.

   ![](assets/import_template_example2.png)

1. Configurez l’activité **[!UICONTROL Segmentation]** pour récupérer les destinataires réconciliés dans une transition, ainsi que les destinataires qui n’ont pas pu être réconciliés mais qui disposent de suffisamment de données dans une autre transition.

   La transition des destinataires réconciliés peut alors être utilisée pour mettre à jour la base de données. La transition des destinataires inconnus peut servir à créer de nouvelles entrées de destinataires dans la base de données si un ensemble d’informations minimum est disponible dans le fichier.

   Les destinataires ne pouvant pas être réconciliés et ne disposant pas de suffisamment de données sont sélectionnés dans une transition sortante complémentaire et peuvent être exportés dans un fichier séparé ou tout simplement ignorés.

   * Dans l’onglet **[!UICONTROL Général]** de l’activité, définissez le **[!UICONTROL Type de ressource]** sur **[!UICONTROL Ressource temporaire]** et sélectionnez **[!UICONTROL Réconciliation]** comme ensemble ciblé.
   * Dans l’onglet **[!UICONTROL Options avancées]**, cochez l’option **[!UICONTROL Générer le complémentaire]** pour voir si des enregistrements n’ont pas pu être intégrés dans la base de données. Le cas échéant, vous pourrez alors appliquer d’autres traitements aux données complémentaires : export de fichier, mise à jour de liste, etc.
   * Dans le premier segment de l’onglet **[!UICONTROL Segments]**, ajoutez une condition de filtrage sur la population entrante pour sélectionner uniquement les enregistrements pour lesquels l’identifiant dans le CRM du profil est différent de 0. De cette manière, les données du fichier réconciliées avec les profils de la base de données sont sélectionnées dans ce sous-ensemble.

      ![](assets/import_template_example3.png)

   * Ajoutez un second segment pour sélectionner les enregistrements non réconciliés disposant de suffisamment de données pour être intégrés dans la base de données Par exemple : adresse email, prénom et nom de famille. La valeur de l’identifiant dans le CRM des profils des enregistrements qui ne sont pas réconciliés est égale à 0.

      ![](assets/import_template_example3_2.png)

   * Tous les enregistrement qui ne sont pas sélectionnés dans les deux premiers sous-ensembles sont sélectionnés dans le **[!UICONTROL Complémentaire]**.

1. Configurez l’activité **[!UICONTROL Mise à jour de données]** située après la première transition sortante de l’activité **[!UICONTROL Segmentation]** paramétrée précédemment.

   * Sélectionnez **[!UICONTROL Mise à jour]** comme **[!UICONTROL Type d’opération]**, puisque la transition entrante contient uniquement des destinataires déjà présents dans la base de données.
   * Dans l’onglet **[!UICONTROL Identification]**, sélectionnez **[!UICONTROL En utilisant des critères de réconciliation]** et définissez une clé entre la **[!UICONTROL Dimension à mettre à jour]**, Profils dans le cas présent, et le lien créé dans l’activité **[!UICONTROL Réconciliation]**. Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** est utilisé.

      ![](assets/import_template_example6.png)

   * Dans l’onglet **[!UICONTROL Champs à mettre à jour]**, indiquez les champs de la dimension Profils à mettre à jour avec la valeur de la colonne correspondante du fichier. Si les noms des colonnes du fichier sont identiques ou presque identiques aux noms des champs de la dimension des destinataires, utilisez le bouton baguette magique pour réconcilier les différents champs automatiquement.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si vous envisagez d’envoyer des courriers à ces profils, veillez à inclure une adresse postale, car cette information est indispensable pour l’opérateur de services postaux. Assurez-vous également que la case **[!UICONTROL Adresse renseignée]** est cochée dans les informations des profils. Pour mettre à jour cette option dans un workflow, ajoutez simplement un élément aux champs à mettre à jour. Spécifiez **1** comme **[!UICONTROL Source]** et sélectionnez le champ `postalAddress/@addrDefined` comme **[!UICONTROL Destination]**. Pour plus d’informations sur les courriers et l’utilisation de l’option **[!UICONTROL Adresse renseignée]**, consultez [ce document](../../channels/using/about-direct-mail.md#recommendations).

1. Configurez l’activité **[!UICONTROL Déduplication]** située après la transition contenant les profils non réconciliés :

   * Dans l’onglet **[!UICONTROL Propriétés]**, définissez le **[!UICONTROL Type de ressource]** sur la ressource temporaire générée à partir de l’activité **[!UICONTROL Réconciliation]** du workflow.

      ![](assets/import_template_example4.png)

   * Dans cet exemple, le champ email est utilisé pour trouver les profils uniques. Vous pouvez utiliser n’importe quel champ dont vous êtes sûr qu’il est rempli et qu’il fait partie d’une combinaison unique.
   * Sélectionnez une **[!UICONTROL Méthode de déduplication]**. Dans ce cas, l’application décide automatiquement quels enregistrements conserver en cas de doublons.

   ![](assets/import_template_example7.png)

1. Configurez l’activité **[!UICONTROL Mise à jour de données]** située après l’activité **[!UICONTROL Déduplication]** paramétrée précédemment.

   * Sélectionnez **[!UICONTROL Ajouter uniquement]** comme **[!UICONTROL Type d’opération]**, puisque la transition entrante contient uniquement des profils non présents dans la base de données.
   * Dans l’onglet **[!UICONTROL Identification]**, sélectionnez **[!UICONTROL En utilisant des critères de réconciliation]** et définissez une clé entre la **[!UICONTROL Dimension à mettre à jour]**, Profils dans le cas présent, et le lien créé dans l’activité **[!UICONTROL Réconciliation]**. Dans cet exemple, le champ personnalisé **Identifiant dans le CRM** est utilisé.

      ![](assets/import_template_example6.png)

   * Dans l’onglet **[!UICONTROL Champs à mettre à jour]**, indiquez les champs de la dimension Profils à mettre à jour avec la valeur de la colonne correspondante du fichier. Si les noms des colonnes du fichier sont identiques ou presque identiques aux noms des champs de la dimension des destinataires, utilisez le bouton baguette magique pour réconcilier les différents champs automatiquement.

      ![](assets/import_template_example6_2.png)

      >[!NOTE]
      >
      >Si vous envisagez d’envoyer des courriers à ces profils, veillez à inclure une adresse postale, car cette information est indispensable pour l’opérateur de services postaux. Assurez-vous également que la case **[!UICONTROL Adresse renseignée]** est cochée dans les informations des profils. Pour mettre à jour cette option dans un workflow, ajoutez simplement un élément aux champs à mettre à jour. Spécifiez **1** comme **[!UICONTROL Source]** et sélectionnez le champ **[postalAddress/@addrDefined]** comme **[!UICONTROL Destination]**. Pour plus d’informations sur les courriers et l’utilisation de l’option **[!UICONTROL Adresse renseignée]**, consultez [ce document](../../channels/using/about-direct-mail.md#recommendations).

1. Après la troisième transition de l’activité **[!UICONTROL Segmentation]**, ajoutez une activité **[!UICONTROL Extraction de fichier]** et une activité **[!UICONTROL Transfert de fichier]** si vous voulez tracker les données non insérées dans la base de données. Paramétrez ces activités afin d’exporter la colonne dont vous avez besoin et de transférer le fichier sur un serveur FTP ou SFTP, où vous pourrez le récupérer.
1. Ajoutez une activité **[!UICONTROL Fin]** et enregistrez le modèle de workflow.

Le modèle est à présent utilisable et disponible pour chaque nouveau workflow. Il suffira alors de spécifier le fichier contenant les données à importer dans l’activité **[!UICONTROL Chargement de fichier]**.

![](assets/import_template_example9.png)
