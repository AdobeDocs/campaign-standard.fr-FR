---
solution: Campaign Standard
product: campaign
title: Chargement de fichier
description: L'activité Chargement de fichier permet d'importer les données d'un fichier sous une forme structurée afin de les utiliser dans Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
translation-type: ht
source-git-commit: c29eff0d241cd561a7e609ab44222700e2a8868d
workflow-type: ht
source-wordcount: '1526'
ht-degree: 100%

---


# Chargement de fichier {#load-file}

## Description {#description}

>[!CAUTION]
>
>Lorsque vous utilisez cette fonctionnalité, gardez à l’esprit les limites du stockage SFTP, du stockage en base de données et des profils actifs en fonction de votre contrat Adobe Campaign.

![](assets/data_loading.png)

L’activité **[!UICONTROL Chargement de fichier]** permet d’importer les données d’un fichier sous une forme structurée afin de les utiliser dans Adobe Campaign. Les données importées le sont temporairement et nécessitent l&#39;utilisation d&#39;une autre activité pour les intégrer définitivement dans la base de données Adobe Campaign.

## Contexte d’utilisation {#context-of-use}

La façon dont les données seront extraites est définie lors du paramétrage de l’activité. Le fichier à charger peut par exemple être une liste de contacts.

Vous pouvez ainsi :

* utiliser la structure du fichier pour l&#39;appliquer aux données d&#39;un autre fichier (récupéré grâce à l&#39;activité **[!UICONTROL Transfert de fichier]**) ou,
* utiliser la structure et les données du fichier pour les importer dans Adobe Campaign.

>[!IMPORTANT]
>
>Seuls les fichiers à structure &quot;plate&quot; sont pris en charge, comme par exemple les fichiers .txt, .csv, etc.

**Rubriques connexes :**

* [Cas pratique : mise à jour de la base de données avec des données externes](../../automating/using/update-database-file.md)
* [Cas pratique : mise à jour des données à l’aide d’un téléchargement automatique de fichier](../../automating/using/update-data-automatic-download.md)
* [Cas pratique : envoi d’un email contenant des champs enrichis](../../automating/using/sending-email-enriched-fields.md)
* [Cas pratique : réconcilier une audience de type fichier avec la base de données](../../automating/using/reconcile-file-audience-with-database.md)

## Configuration {#configuration}

Le paramétrage de l&#39;activité se déroule en deux temps. Tout d&#39;abord, vous devez définir la structure du fichier attendue en téléchargeant un fichier d&#39;exemple. Une fois cela réalisé, vous pouvez spécifier la provenance du fichier dont les données seront importées.

>[!NOTE]
>
>Les données du fichier d&#39;exemple sont utilisées pour le paramétrage de l&#39;activité mais ne sont pas importées. Il est recommandé d&#39;utiliser un fichier d&#39;exemple avec peu de données.

1. Placez une activité **[!UICONTROL Chargement de fichier]** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.
1. Téléchargez le fichier d&#39;exemple qui permettra de définir la structure attendue lors de l&#39;import du fichier final.

   ![](assets/wkf_file_loading.png)

   Deux nouveaux onglets s&#39;affichent dans l&#39;activité après le téléchargement du fichier de données : **[!UICONTROL Structure du fichier]** et **[!UICONTROL Définition des colonnes]**.

1. Depuis l&#39;onglet **[!UICONTROL Structure du fichier]**, visualisez la structure automatiquement détectée du fichier d&#39;exemple.

   Si la structure du fichier a été détectée de manière incorrecte, vous disposez de plusieurs options permettant de corriger les éventuelles erreurs :

   * Vous pouvez choisir d&#39;utiliser la structure d&#39;un autre fichier en sélectionnant l&#39;option **[!UICONTROL Détecter la structure depuis un nouveau fichier]**.
   * Vous pouvez modifier les paramètres de détection par défaut afin de les adapter à votre fichier. Le champ **[!UICONTROL Type de fichier]** permet d&#39;indiquer si le fichier à importer est composé de colonnes à longueur fixe. Si c&#39;est le cas, vous devez également spécifier le nombre maximal de caractères pour chaque colonne dans l&#39;onglet **[!UICONTROL Définition des colonnes]**.

      Dans **[!UICONTROL Format du fichier]** sont regroupées toutes les options de détection nécessaires pour récupérer correctement les données du fichier. Vous pouvez les modifier puis détecter à nouveau la structure du dernier fichier chargé dans l&#39;activité en prenant en compte ces nouveaux paramètres. Utilisez pour cela le bouton **[!UICONTROL Appliquer la configuration]**. Vous pouvez par exemple spécifier un séparateur de colonnes différent.

      >[!NOTE]
      >
      >Cette opération prend en compte le dernier fichier téléchargé dans l&#39;activité. Si le fichier détecté est volumineux, l&#39;aperçu des données porte seulement sur les 30 premières lignes.

      ![](assets/wkf_file_loading3.png)

      Dans la section **[!UICONTROL Format du fichier]**, l&#39;option **[!UICONTROL Vérifier les colonnes du fichier par rapport aux définitions de colonne]** vous permet de vérifier que les colonnes du fichier que vous téléchargez correspondent à la définition des colonnes.

      Si le nombre et/ou le nom des colonnes ne correspond pas à la définition des colonnes, un message d&#39;erreur apparaîtra lors de l&#39;exécution du workflow. Si l&#39;option n&#39;est pas activée, les avertissements figureront dans le log.

      ![](assets/wkf_file_loading_check.png)

1. Depuis l&#39;onglet **[!UICONTROL Définition des colonnes]**, vérifiez le format des données de chaque colonne et ajustez les paramètres si nécessaire.

   L&#39;onglet **[!UICONTROL Définition des colonnes]** vous permet de définir précisément la structure des données de chaque colonne pour importer des données qui ne contiennent pas d&#39;erreur (grâce à la gestion des nulls par exemple) et les faire correspondre aux types pré-existants de la base Adobe Campaign pour des opérations ultérieures.

   Vous pouvez par exemple modifier le libellé d&#39;une colonne, sélectionner son type (chaîne, nombre entier, date, etc.) ou encore définir le traitement des erreurs.

   Voir à ce sujet [Format des colonnes](#column-format).

   ![](assets/wkf_file_loading4.png)

1. Dans l&#39;onglet **[!UICONTROL Exécution]**, spécifiez si le fichier à exploiter pour le chargement des données :

   * provient de la transition entrante dans le workflow ;
   * est celui que vous avez téléchargé lors de l&#39;étape précédente ;
   * est un nouveau fichier à télécharger depuis le poste local. L&#39;option **[!UICONTROL Transférer un nouveau fichier depuis le poste local]** s&#39;affiche si le téléchargement d&#39;un premier fichier a déjà été défini dans le workflow. Elle vous permet de télécharger un autre fichier à exploiter si le fichier actuel ne convient pas.

      ![](assets/wkf_file_loading1.png)

1. Si le fichier dont vous souhaitez charger les données est compressé dans un fichier GZIP (.gz), sélectionnez l’option **[!UICONTROL Décompression]** dans le champ **[!UICONTROL Ajouter une étape de pré-traitement]**. Cela permet de décompresser le fichier avant de procéder au chargement des données. Cette option est disponible uniquement si le fichier provient de la transition entrante de l&#39;activité.

   Le champ **[!UICONTROL Ajouter une étape de pré-traitement]** permet également de décrypter un fichier avant de l’importer dans la base de données. Pour plus d’informations sur l’utilisation des fichiers cryptés, voir [cette section](../../automating/using/managing-encrypted-data.md)

1. L&#39;option **[!UICONTROL Conserver les rejets dans un fichier]** permet de télécharger un fichier contenant des erreurs s&#39;étant produites lors de l&#39;import et de l&#39;appliquer à une étape de post-traitement. Lorsque l&#39;option est activée, la transition sortante est renommée &quot;Rejets&quot;.

   >[!NOTE]
   >
   >L&#39;option **[!UICONTROL Ajoutez la date et l&#39;heure au nom du fichier]** permet d&#39;ajouter un horodatage au nom du fichier contenant les rejets.

   ![](assets/wkf_file_loading_keeprejects.png)

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

Si une erreur se produit dans l&#39;activité après l&#39;exécution du workflow, consultez les journaux pour obtenir plus de détails sur les valeurs incorrectes dans le fichier. Pour plus d&#39;informations sur les jounaux de workflows, reportez-vous à cette [section](../../automating/using/monitoring-workflow-execution.md)..

## Format des colonnes         {#column-format}

Lorsque vous téléchargez un fichier d&#39;exemple, le format des colonnes est automatiquement détecté avec des paramètres par défaut pour chaque type de données. Vous pouvez modifier ces paramètres par défaut afin de spécifier des traitements particulier à appliquer à vos données, notamment en cas d&#39;erreur ou de valeur vide.

Pour cela, sélectionnez **[!UICONTROL Editer les propriétés]** dans les actions rapides de la colonne dont vous souhaitez définir le format. La fenêtre de détail du format de la colonne s&#39;ouvre.

![](assets/wkf_file_loading4.png)

Vous pouvez alors modifier le formatage de chaque colonne.

Le formatage des colonnes permet de définir le traitement des valeurs de chaque colonne :

* **[!UICONTROL Ignorer la colonne]** : permet de ne pas traiter cette colonne lors du chargement des données.
* **[!UICONTROL Type de données]** : permet de spécifier le type de données attendu dans la colonne.
* **[!UICONTROL Format et séparateurs]**, **Propriétés** : permettent de définir les propriétés d&#39;un texte, le format des heures, des dates et des valeurs numériques ainsi que le séparateur spécifié par le contexte de la colonne.

   * **[!UICONTROL Nombre de caractères maximum]** : permet de spécifier le nombre maximum de caractères pour les colonnes de type chaîne.

      Ce champ doit être renseigné lors du chargement des fichiers composés de colonnes à longueur fixe.

   * **[!UICONTROL Gestion de la casse]** : permet de définir si un traitement au niveau de la casse doit être appliqué pour les données de type **Texte**.
   * **[!UICONTROL Gestion des espaces]** : permet d&#39;indiquer si certains espaces doivent être ignorés dans une chaîne pour les données de type **Texte**.
   * **[!UICONTROL Format des heures]**, **[!UICONTROL Format des dates]** : permettent de définir le format des heures ou des dates pour les données de type **Date**, **Heure**, **Date et Heure**.
   * **[!UICONTROL Format]** : permet de définir le format des valeurs numériques pour les données de type **Nombre entier** et **Nombre flottant**.
   * **[!UICONTROL Séparateur]** : permet de définir le séparateur spécifié par le contexte de la colonne (séparateur de milliers ou séparateur décimal pour les valeurs numériques, séparateur pour les dates et les heures) pour les données de type **Date**, **Heure**, **Date et Heure**, **Nombre entier** et **Nombre flottant**.

* **[!UICONTROL Recodification des valeurs]** : ce champ est disponible uniquement dans le paramétrage du détail d&#39;une colonne. Il permet de transformer certaines valeurs lors de l&#39;import. Par exemple, vous pouvez transformer &quot;trois&quot; en &quot;3&quot;.
* **[!UICONTROL Traitement des erreurs]** : permet de définir le comportement en cas d&#39;erreur.

   * **[!UICONTROL Ignorer la valeur]** : la valeur est ignorée. Un avertissement est généré dans le journal d&#39;exécution du workflow.
   * **[!UICONTROL Rejeter la ligne]** : la ligne entière n&#39;est pas traitée.
   * **[!UICONTROL Utiliser une valeur par défaut]** : remplace la valeur causant l&#39;erreur par une valeur par défaut, définie dans le champ **[!UICONTROL Valeur par défaut]**.
   * **[!UICONTROL Utiliser une valeur par défaut en cas d&#39;absence de recodification]** : remplace la valeur causant l&#39;erreur par une valeur par défaut, définie dans le champ **[!UICONTROL Valeur par défaut]**, sauf si une recodification a été définie pour la valeur en erreur (voir option **[!UICONTROL Recodification des valeurs]** ci-dessus).
   * **[!UICONTROL Rejeter la ligne en cas d&#39;absence de recodification]** : la ligne entière n&#39;est pas traitée sauf si une recodification a été définie pour la valeur en erreur (voir option **[!UICONTROL Recodification des valeurs]** ci-dessus).

   >[!NOTE]
   >
   >**[!UICONTROL Le Traitement des erreurs]** concerne les erreurs au niveau des valeurs renseignées dans le fichier importé. Par exemple, un mauvais type de données rencontré (&quot;quatre&quot; en toutes lettres pour une colonne de type &quot;Nombre entier&quot;), une chaîne contenant plus de caractères que le nombre maximum autorisé, une date avec les mauvais séparateurs, etc. En revanche, cette option ne concerne pas les erreurs générées par la gestion des valeurs vides.

* **[!UICONTROL Valeur par défaut]** : permet de spécifier la valeur par défaut en fonction du choix concernant le traitement des erreurs.
* **[!UICONTROL Gestion des valeurs vides]** : permet d&#39;indiquer comment gérer les valeurs vides rencontrées lors du chargement des données.

   * **[!UICONTROL Générer une erreur pour les champs numériques]** : génère une erreur pour les champs numériques uniquement, sinon insère la valeur NULL.
   * **[!UICONTROL Insérer NULL dans le champ correspondant]** : autorise les valeurs vides. La valeur NULL est alors insérée.
   * **[!UICONTROL Générer une erreur]** : génère une erreur en cas de valeur vide.
