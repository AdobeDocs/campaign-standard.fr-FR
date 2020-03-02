---
title: Transfert de fichier
description: L'activité Transfert de fichier permet de recevoir ou d'envoyer des fichiers, de tester la présence de fichiers ou de lister les fichiers dans Adobe Campaign.
page-status-flag: never-activated
uuid: a2f18118-b681-4310-aee0-9e82179d2032
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 752f2aed-f897-485e-b329-f3cc1756ee8e
context-tags: fileTransfer,main
internal: n
snippet: y
translation-type: ht
source-git-commit: ff3b41589f47e7697a69bb68824aefd4d9036793

---


# Transfert de fichier{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

L&#39;activité **[!UICONTROL Transfert de fichier]** permet de recevoir ou d&#39;envoyer des fichiers, de tester la présence de fichiers ou de lister les fichiers dans Adobe Campaign.

## Contexte d&#39;utilisation {#context-of-use}

La façon dont les données seront extraites est définie lors du paramétrage de l&#39;activité. Le fichier à charger peut par exemple être une liste de contacts.

Vous pouvez utiliser cette activité pour récupérer des données qui seront ensuite structurées avec l&#39;activité **[!UICONTROL Chargement de fichier]**.

## Configuration {#configuration}

1. Placez une activité **[!UICONTROL Transfert de fichier]** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.
1. Utilisez la liste déroulante du champ **[!UICONTROL Action]** pour sélectionner l&#39;action de l&#39;activité, à savoir :

   ![](assets/wkf_file_transfer_01.png)

   * **Réception de fichier** : vous permet de télécharger un fichier.
   * **Envoi de fichier** : vous permet d&#39;envoyer un fichier. Le téléchargement d&#39;un fichier depuis Adobe Campaign génère une entrée de journal dans le menu **[!UICONTROL Audits des exports]**. Pour plus d&#39;informations sur les audits des exports, consultez la section [Audits des exports](../../administration/using/auditing-export-logs.md).
   * **Test d&#39;existence de fichier** : vous permet de vérifier l&#39;existence d&#39;un fichier.
   * **Listage de fichiers** : vous permet de lister les fichiers présents dans Adobe Campaign.
   En fonction de l&#39;action sélectionnée, un ou plusieurs protocoles sont disponibles :

   * **HTTP** : ce protocole permet de lancer le téléchargement d&#39;un fichier depuis un compte externe ou une URL.

      * Cliquez sur l&#39;option **[!UICONTROL Utiliser des paramètres de connexion définis dans un compte externe]** puis sélectionnez le compte désiré et indiquez le chemin du fichier à télécharger.

         ![](assets/wkf_file_transfer_03.png)

      * Cliquez sur l&#39;option **[!UICONTROL Configuration rapide]** puis entrez l&#39;URL dans le champ qui s&#39;affiche.

         ![](assets/wkf_file_transfer_04.png)
   * **S3** : ce protocole permet de lancer le téléchargement d&#39;un fichier depuis une URL ou un compte externe via Amazon Simple Storage Service (S3).

      * Sélectionnez le compte externe et spécifiez le chemin du fichier à télécharger.

         ![](assets/wkf_file_transfer_08.png)
   * **SFTP** : ce protocole permet de lancer le téléchargement d&#39;un fichier depuis une URL ou un compte externe.

      * Cliquez sur l&#39;option **[!UICONTROL Utiliser des paramètres de connexion définis dans un compte externe]** puis sélectionnez le compte désiré et indiquez le chemin du fichier à télécharger.

         ![](assets/wkf_file_transfer_07.png)

         >[!CAUTION]
         >
         >Les caractères génériques sont supportés.

      * Cliquez sur l&#39;option **[!UICONTROL Configuration rapide]** puis entrez l&#39;URL dans le champ qui s&#39;affiche.
      * Si vous voulez trier les fichiers importés, sélectionnez l&#39;option **[!UICONTROL Trier par ordre alphanumérique]** dans la section **[!UICONTROL Options supplémentaires]**. Les fichiers sont ensuite traités en ordre séquentiel.

         ![](assets/wkf_file_transfer_sort.png)
   * **Fichier(s) présent(s) sur le serveur Adobe Campaign** : ce protocole correspond au répertoire contenant le ou les fichiers à récupérer.

      Les métacaractères, ou caractères génériques (par exemple * ou ?) peuvent être utilisés pour filtrer les fichiers.

      Complétez ce champ et confirmez votre activité pour utiliser ce protocole.

      >[!NOTE]
      >
      >Le chemin doit être relatif au répertoire d&#39;espace de stockage du serveur Adobe Campaign. Les fichiers se trouvent dans le répertoire **sftp&lt;nomdevotreinstance>/**. Il est également impossible de parcourir les niveaux de répertoires supérieurs à l&#39;espace de stockage. Par exemple :

      >**user&lt;nomdevotreinstance>/my_recipients.csv** est correct.
      **../hello/my_recipients.csv** est incorrect.
      **//myserver/hello/myrecipients.csv** est incorrect.
   Choisissez votre protocole et complétez les champs associés.

   L&#39;option **[!UICONTROL Utiliser un chemin d&#39;accès au fichier dynamique]**, disponible pour chaque protocole, vous permet d&#39;utiliser une expression standard et des variables d&#39;événements afin de personnaliser le nom du fichier à transférer. Voir à ce propos la section [Personnaliser les activités avec des variables d&#39;événements](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

1. La section **[!UICONTROL Options supplémentaires]**, disponible en fonction du protocole choisi, vous permet d&#39;ajouter des paramètres à votre protocole. Vous pouvez ainsi :

   * **[!UICONTROL Effacer les fichiers source après leur transfert]**.
   * **[!UICONTROL Désactiver le mode passif]**.
   * **[!UICONTROL Lister tous les fichiers]** : cette option est disponible lors de la sélection de l&#39;action **[!UICONTROL Listage de fichiers]**. Elle permet de répertorier tous les fichiers présents sur le serveur dans la variable d&#39;événement **vars.filenames**. Les noms des fichiers y sont séparés par les caractères **&#39;n&#39;**.

1. La section **[!UICONTROL En cas d&#39;absence de fichier]** de l&#39;onglet **[!UICONTROL Options avancées]** vous permet d&#39;agir sur les erreurs ou les fichiers inexistants détectés lors du lancement de l&#39;activité.

   Vous pouvez également définir de nouvelles tentatives. Les différentes tentatives apparaissent dans le journal d&#39;exécution du workflow.

   ![](assets/wkf_file_transfer_09.png)

1. Validez le paramétrage de l&#39;activité et enregistrez le workflow.

## Paramètres d&#39;historisation  {#historization-settings}

A chacune de ses exécutions, l&#39;activité **[!UICONTROL Transfert de fichier]** stocke les fichiers transférés ou téléchargés dans un dossier dédié. Un dossier est créé pour chaque activité **[!UICONTROL Transfert de fichier]** d&#39;un workflow. Par conséquent, il est important de pouvoir limiter la taille de ce dossier de façon à préserver l&#39;espace physique sur le serveur.

Pour cela, vous pouvez définir les **[!UICONTROL Paramètres d&#39;historisation]** dans les **[!UICONTROL Options avancées]** de l&#39;activité **[!UICONTROL Transfert de fichier]**.

**[!UICONTROL Les Paramètres d&#39;historisation]** permettent de définir un nombre maximum de fichiers ou la taille totale du dossier de l&#39;activité. Par défaut, 100 fichiers et 50 Mo sont autorisés.

A chaque exécution de l&#39;activité, le dossier est vérifié comme suit :

* Seuls les fichiers créés plus de 24 heures avant l&#39;exécution de l&#39;activité sont pris en compte.
* Si le nombre de fichiers pris en compte est supérieur à la valeur du paramètre **[!UICONTROL Nombre maximum de fichiers]**, les fichiers les plus anciens sont supprimés jusqu&#39;à ce que le **[!UICONTROL Nombre maximum de fichiers]** soit atteint.
* Si la taille totale des fichiers pris en compte est supérieure à la valeur du paramètre **[!UICONTROL Taille maximale (en Mo)]**, les fichiers les plus anciens sont supprimés jusqu&#39;à ce que la **[!UICONTROL Taille maximale (en Mo)]** soit atteinte.

>[!NOTE]
Si l&#39;activité n&#39;est pas exécutée à nouveau, son dossier ne sera pas vérifié ni purgé. Faites donc preuve de prudence lorsque vous transférez des fichiers de grande taille.

## Exemple {#example}

L&#39;exemple suivant montre le paramétrage d&#39;une activité **Transfert de fichier** qui sera ensuite suivie d&#39;une activité **Chargement de fichier** puis **Mise à jour de données**. Le but de ce workflow est d&#39;ajouter ou de mettre à jour les profils de la base Adobe Campaign avec les données récupérées par le workflow.

1. Placez une activité **Transfert de fichier** dans votre workflow.
1. Sélectionnez l&#39;activité puis ouvrez-la à l&#39;aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s&#39;affichent.
1. Dans l&#39;onglet **[!UICONTROL Protocole]**, choisissez le protocole **SFTP**.
1. Sélectionnez l&#39;option **Utiliser des paramètres de connexion définis dans un compte externe**.
1. Renseignez le nom du compte externe.
1. Renseignez le **chemin des fichiers sur le serveur distant**.

   ![](assets/wkf_file_transfer_07.png)

1. Validez votre activité et sauvegardez votre workflow.

