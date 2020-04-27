---
title: Transfert de fichier
description: L’activité Transfert de fichier permet de recevoir ou d’envoyer des fichiers, de tester la présence de fichiers ou de lister les fichiers dans Adobe Campaign.
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
translation-type: tm+mt
source-git-commit: 3e90acaa1c2b3de2240f01e5dc3440be44e65eba

---


# Transfert de fichier{#transfer-file}

## Description {#description}

![](assets/file_transfer.png)

The **[!UICONTROL Transfer file]** activity allows you to receive or send files, test whether there are files present, or list files in Adobe Campaign.

>[!CAUTION]
>
>À compter de la version 20.3, les fichiers téléchargés avec le   seront supprimés après X jours, où X est déterminé par le **[!UICONTROL Transfer File]** champ situé sous le **[!UICONTROL History in days]** **[!UICONTROL Execution]** menu dans les propriétés du flux de travail.


## Contexte d’utilisation {#context-of-use}

La façon dont les données seront extraites est définie lors du paramétrage de l’activité. Le fichier à charger peut par exemple être une liste de contacts.

You can use this activity to recover data that will then be structured with the **[!UICONTROL Load file]** activity.

## Configuration {#configuration}

1. Déposez un **[!UICONTROL Transfer file]**  dans votre flux de travail.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. Utilisez la liste déroulante du champ **[!UICONTROL Action]** pour sélectionner l’action de l’activité, à savoir :

   ![](assets/wkf_file_transfer_01.png)

   * **Réception de fichier** : vous permet de télécharger un fichier.
   * **Envoi de fichier** : vous permet d’envoyer un fichier. Uploading a file from Adobe Campaign file generates a log entry in the **[!UICONTROL Export audits]** menu. Pour plus d’informations sur les audits des exports, consultez la section [Audits des exports](../../administration/using/auditing-export-logs.md).
   * **Test d’existence de fichier** : vous permet de vérifier l’existence d’un fichier.
   * **Liste des** fichiers : vous permet de  les fichiers présents sur le serveur définis dans l’ **[!UICONTROL Protocol]** onglet. Cette action est principalement utilisée à des fins de débogage, afin de vérifier si le   est configuré en fonction de vos besoins avant de télécharger les fichiers à partir du serveur distant.

1. Sélectionnez le protocole que vous souhaitez utiliser :
   * [HTTP](#HTTP-configuration-wf)
   * [SFTP](#SFTP-configuration-wf)
   * [Amazon S3](#S3-configuration-wf)
   * [Stockage Blob de Microsoft Azure](#azure-blob-configuration-wf)
   * [Fichier(s) présent(s) sur le serveur Adobe Campaign](#files-server-configuration-wf)

1. The **[!UICONTROL Additional options]** section, available depending on the protocol selected, allows you to add parameters to your protocol. Vous pouvez ainsi :

   * **[!UICONTROL Delete the source files after transfer]**
   * **[!UICONTROL Disable passive mode]**
   * **[!UICONTROL List all files]**: cette option est disponible lors de la sélection du fichier **[!UICONTROL File listing]** .action dans l’ **[!UICONTROL General]** onglet. Elle permet de répertorier tous les fichiers présents sur le serveur dans la variable d’événement **vars.filenames**. Les noms des fichiers y sont séparés par les caractères **’n’**.

1. The **[!UICONTROL If no files are found]** section of the **[!UICONTROL Advanced options]** tab allows you to configure specific actions if any errors or inexistent files are detected when the activity is started.

   Vous pouvez également définir de nouvelles tentatives. Les différentes tentatives apparaissent dans le journal d’exécution du workflow.

   ![](assets/wkf_file_transfer_09.png)

1. Validez le paramétrage de l’activité et enregistrez le workflow.

### Configuration avec HTTP {#HTTP-configuration-wf}

Le protocole HTTP permet de lancer le téléchargement d’un fichier depuis un compte externe ou une URL.

Avec ce profil, vous pouvez choisir d’ **[!UICONTROL Use connection parameters defined in an external account]** opter. Dans ce cas, sélectionnez le compte de votre choix et indiquez le chemin d’accès au fichier à télécharger.
![](assets/wkf_file_transfer_03.png)

Vous pouvez également choisir l’ **[!UICONTROL Quick configuration]** option. Il suffit de saisir l’URL dans le champ URL.
![](assets/wkf_file_transfer_04.png)

### Configuration avec SFTP {#SFTP-configuration-wf}

Le protocole SFTP permet de lancer le téléchargement d’un fichier depuis une URL ou un compte externe.

Avec ce profil, vous pouvez choisir d’ **[!UICONTROL Use connection parameters defined in an external account]** opter, puis sélectionner le compte que vous souhaitez et spécifier le chemin d’accès du fichier à télécharger.
![](assets/wkf_file_transfer_07.png)

>[!CAUTION]
>
>Les caractères génériques sont pris en charge.

Vous pouvez également choisir l’ **[!UICONTROL Quick configuration]** option. Il suffit de saisir l’URL dans le champ URL.

### Configuration avec Amazon S3 {#S3-configuration-wf}

Le protocole Amazon S3 permet de lancer le téléchargement d’un fichier depuis une URL ou un compte externe via Amazon Simple Storage Service (S3).

1. Sélectionnez un compte externe Amazon S3. Pour plus d’informations à ce propos, consultez cette [page](../../administration/using/external-accounts.md#amazon-s3-external-account).

2. Choisissez si vous le voulez **[!UICONTROL Define a file path]** ou **[!UICONTROL Use a dynamic file path]**.

3. Indiquez le chemin d’accès au fichier à télécharger.

   ![](assets/wkf_file_transfer_08.png)

4. Si vous souhaitez supprimer vos fichiers source une fois le transfert terminé, cochez **[!UICONTROL Delete the source files after transfer]**.

### Configuration avec le stockage Blob Microsoft Azure {#azure-blob-configuration-wf}

Le protocole Blob Microsoft Azure permet d’accéder à l’objet Blob situé sur un compte de stockage Blob Microsoft Azure.

1. Sélectionnez un **[!UICONTROL Microsoft Azure Blob]** . Pour plus d’informations à ce propos, consultez cette [page](../../administration/using/external-accounts.md#microsoft-azure-external-account).

1. Choisissez si vous le voulez **[!UICONTROL Define a file path]** ou **[!UICONTROL Use a dynamic file path]**.

   ![](assets/wkf_file_transfer_10.png)

1. Indiquez le chemin d’accès au fichier à télécharger ; il peut correspondre à plusieurs objets Blob. In that case, the **[!UICONTROL File transfer]** activity will activate the outgoing transition once per blob found. Ils seront ensuite traités par ordre alphabétique.

   >[!CAUTION]
   >
   >Les caractères génériques ne sont pas pris en charge pour faire correspondre plusieurs noms du fichier. Vous devez saisir un préfixe. Tous les noms d’objets Blob correspondant à ce préfixe seront éligibles.

   Voici une liste d’exemples de chemins de fichier :

   * **&quot;campaign/&quot;** : correspond à tous les objets Blob dans le dossier Campaign situé à la racine du conteneur.
   * **&quot;campaign/new-&quot;** : correspond à tous les objets Blob avec un nom de fichier commençant par « new- » et se trouvant dans le dossier Campaign.
   * **&quot;&quot;** : l’ajout d’un chemin d’accès vide permet de faire correspondre tous les objets Blob disponibles dans le conteneur.

### Configuration avec des fichiers présents sur le serveur Adobe Campaign {#files-server-configuration-wf}

Le **[!UICONTROL File(s) present on the Adobe Campaign server]** protocole correspond au référentiel contenant le ou les fichiers à récupérer.
Les métacaractères, ou caractères génériques (par exemple * ou ?) peuvent être utilisés pour filtrer les fichiers.

Choisissez si vous souhaitez **[!UICONTROL Define a file path]** ou **[!UICONTROL Use a dynamic file path]** l’ **[!UICONTROL Use a dynamic file path]** option, vous permet d’utiliser un  de  standard et des variables de pour personnaliser le nom du fichier à transférer. Voir à ce propos la section [Personnaliser les activités avec des variables d’événements](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

Veuillez noter que le chemin doit être relatif au répertoire d’espace de stockage du serveur Adobe Campaign. Les fichiers se trouvent dans le répertoire **sftp&lt;nomdevotreinstance>/**. Il est également impossible de parcourir les niveaux de répertoires supérieurs à l’espace de stockage. Par exemple :

    >**user&amp;lt;nomdevotreinstance>/my_recipients.csv** est correct.
    >
    >**../hello/my_recipients.csv** est incorrect.
    >
    >**//myserver/hello/myrecipients.csv** est incorrect.

## Paramètres d’historisation   {#historization-settings}

Every time a **[!UICONTROL Transfer file]** activity is executed, it stores the uploaded or downloaded files in a dedicated folder. One folder is created for each **[!UICONTROL Transfer file]** activity of a workflow. Par conséquent, il est important de pouvoir limiter la taille de ce dossier de façon à préserver l’espace physique sur le serveur.

Pour ce faire, vous pouvez définir **[!UICONTROL Historization settings]** dans la **[!UICONTROL Advanced options]** partie de l&#39; du **[!UICONTROL Transfer File]** .

**[!UICONTROL Historization settings]** permet de définir un nombre maximal de fichiers ou une taille totale pour le dossier  du . Par défaut, 100 fichiers et 50 Mo sont autorisés.

A chaque exécution de l’activité, le dossier est vérifié comme suit :

* Seuls les fichiers créés plus de 24 heures avant l’exécution de l’activité sont pris en compte.
* If the number of files taken into account is greater than the value of the **[!UICONTROL Maximum number of files]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum number of files]** allowed is reached.
* If the total size of files taken into account is greater than the value of the **[!UICONTROL Maximum size (in MB)]** parameter, the oldest files are deleted until the **[!UICONTROL Maximum size (in MB)]** allowed is reached.

>[!NOTE]
>
>Si l’activité n’est pas exécutée à nouveau, son dossier ne sera pas vérifié ni purgé. Faites donc preuve de prudence lorsque vous transférez des fichiers de grande taille.

## Exemple {#example}

L’exemple suivant montre le paramétrage d’une activité **Transfert de fichier** qui sera ensuite suivie d’une activité **Chargement de fichier** puis **Mise à jour de données**. Le but de ce workflow est d’ajouter ou de mettre à jour les profils de la base Adobe Campaign avec les données récupérées par le workflow.

1. Placez une activité **Transfert de fichier** dans votre workflow.
1. Sélectionnez l’activité puis ouvrez-la à l’aide du bouton ![](assets/edit_darkgrey-24px.png), disponible dans les actions rapides qui s’affichent.
1. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Sélectionnez l’option **Utiliser des paramètres de connexion définis dans un compte externe**.
1. Renseignez le nom du compte externe.
1. Renseignez le **chemin des fichiers sur le serveur distant**.

   ![](assets/wkf_file_transfer_07.png)

1. Validez votre activité et sauvegardez votre workflow.

