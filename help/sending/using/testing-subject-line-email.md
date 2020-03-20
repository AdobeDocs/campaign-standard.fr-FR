---
title: Test de l'objet d'un email
description: Découvrez comment définir l'objet d'un email dans le Concepteur d'email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---

# Test de l&#39;objet d&#39;un email {#testing-a-subject}


## About predictive subject line {#about-predictive-subject-line}

Lors de l&#39;édition d&#39;un email, vous pouvez tester différents objets et obtenir une estimation de son taux d&#39;ouverture avant l&#39;envoi.

Cette fonctionnalité est désactivée par défaut. Elle est activée lors de l&#39;import d&#39;un premier modèle. Un modèle est créé à partir de jeux de données d&#39;apprentissage spécifiques à un secteur d&#39;activité donné. Les modèles permettent au système d&#39;estimer le taux d&#39;ouverture d&#39;un email lorsqu&#39;un nouvel objet est soumis.

>[!NOTE]
>
>Cette fonctionnalité est disponible pour les emails et les bases de données dont le contenu est en anglais uniquement. Si votre instance contient des emails dans d&#39;autres langues, le modèle entraîné sera incohérent et donnera des résultats erronés. L&#39;option permettant de tester un objet n&#39;est visible que si un modèle est disponible dans votre instance.

Pour plus d’informations sur l’importation de modèles, reportez-vous à cette [section](#importing-models).

## Test de la ligne d’objet {#testing-subject-line}

Pour tester un objet, procédez comme suit :

1. Créez un email ou ouvrez un email existant.
1. Ouvrez le contenu et saisissez l&#39;objet de l&#39;email dans le champ de saisie prévu à cet effet.
1. Cliquez sur le **[!UICONTROL Test subject]** bouton pour accéder à la **[!UICONTROL Test your subject line]** fenêtre. Vous pouvez toujours éditer l&#39;objet dans cette fenêtre.
1. Choisissez le bon modèle à prendre en compte pour la prédiction du taux d&#39;ouverture. Plusieurs modèles sont disponibles. Chacun d&#39;entre eux correspond à un secteur d&#39;activité spécifique. Pour plus d’informations sur l’utilisation des modèles, reportez-vous à cette [section](#importing-models).
1. Clics **[!UICONTROL Test]**.

Votre objet est alors analysé.

>[!NOTE]
>
>Si l&#39;objet est trop court, il ne peut pas être analysé et un message d&#39;erreur s&#39;affiche.

Plusieurs indicateurs sont calculés et un ensemble d&#39;outils s&#39;affiche en vue de vous aider :

* **Taux d&#39;ouverture estimé** : ce graphique donne une idée du taux d&#39;ouverture escompté de l&#39;email avec l&#39;objet actuellement testé.
* **Longueur de l&#39;objet** : cet indicateur permet de déterminer si la longueur actuelle de l&#39;objet est correcte ou si elle doit être allongée ou raccourcie.
* **Mots en couleur** : lors du test de l&#39;objet, les mots surlignés en vert correspondent à ceux qui contribuent le plus à l&#39;augmentation de la prédiction du taux d&#39;ouverture. Les mots surlignés en rouge, quant à eux, correspondent à ceux qui contribuent le moins à l&#39;augmentation de la prédiction du taux d&#39;ouverture. Si vous ajoutez ou supprimez des mots de l&#39;objet, les mots surlignés changent.
* **Catégories et suggestions de mots** : la partie inférieure de la fenêtre contient plusieurs catégories pertinentes pour le modèle sélectionné. Ces catégories, triées par ordre d&#39;importance, permettent de déterminer si l&#39;objet contient des mots qui leur sont associés grâce à une coche. Chaque catégorie contient un ensemble de mots proposés qui peuvent être utilisés dans votre objet afin de le rendre plus pertinent et augmenter le taux d&#39;ouverture. Ces mots correspondent à ceux qui sont le plus souvent utilisés dans une catégorie donnée.

>[!NOTE]
>
>Les champs de personnalisation et les signes de ponctuation ne sont pas pris en compte dans l&#39;analyse de l&#39;objet. Pour les textes dynamiques/conditionnels, toutes les variantes sont traitées comme un seul objet.

![](assets/predictive_subject_line_example.png)

## Importer des modèles   {#importing-models}

Par défaut, aucun modèle n&#39;est exécuté sur le serveur Adobe Campaign. Deux méthodes permettent d&#39;obtenir un modèle et d&#39;activer la fonctionnalité :

* Vous pouvez former un modèle local à partir des données de vos précédents messages électroniques.
* Vous pouvez importer des modèles pré-entraînés qui sont spécifiques à certains secteurs d&#39;activité (médical, etc.) à l&#39;aide de la fonctionnalité d&#39;[import de package](../../automating/using/managing-packages.md)

### Formation d’un modèle local {#training-local-model}

* Si vous utilisez déjà Adobe Campaign, le modèle local sera automatiquement entraîné avec les messages que vous avez déjà envoyés.
* Si vous utilisez Adobe Campaign pour la première fois, vous pouvez extraire de votre précédent système/fournisseur de services de messagerie un fichier CSV contenant 4 colonnes : date, objet, ouvertures, envoyés. Pour ce faire, accédez à **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** et suivez les instructions fournies sur les écrans suivants. Lorsque le téléchargement des objets est terminé, importez un modèle local en suivant la procédure qui est décrite ci-après. Le modèle local est automatiquement entraîné avec les données que vous avez téléchargées.
* If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a [pre-trained model](#pre-trained-models) or wait until you have enough delivery data in your system to train a local model. Le système détermine automatiquement si le jeu de données actuel contient suffisamment de données pour reconnaître des constantes et entraîner le modèle.

>[!NOTE]
>
>Il n&#39;y a pas de nombre défini d&#39;objets requis pour entraîner votre propre modèle. For more on this, see [Troubleshooting](#troubleshooting).
>
>Votre instance ne peut contenir qu&#39;un seul modèle entraîné.

Pour former un modèle local :
1. Download the subjectLineTraining.xml from [here](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) and use the [package import](../../automating/using/managing-packages.md) feature to upload it to your Adobe Campaign instance. Un workflow technique entraînera automatiquement le modèle.
1. The first time you want to train a model, an administrator can force the **[!UICONTROL SubjectLine Training workflow]** to start from the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** menu.
1. Une fois un modèle téléchargé et entraîné, la fonctionnalité est automatiquement activée. Une nouvelle option apparaît alors en regard de l&#39;objet de vos messages.
1. Le workflow technique continue ensuite l&#39;apprentissage du modèle toutes les semaines.

### Importation de modèles préformés {#pre-trained-models}

Pour accéder à ces modèles, cliquez [ici](https://support.neolane.net/webApp/extranetLogin) et allez à **[!UICONTROL Download Center]**. Utilisez la fonction d’importation [du](../../automating/using/managing-packages.md) package pour télécharger un modèle vers votre instance Adobe Campaign .

Les modèles disponibles sont les suivants :

* Secteur cosmétique : subjectInsightCosmetic.xml
* Secteur alimentaire : subjectInsightSupermarket.xml
* Secteur médical : subjectInsightMedical.xml
* Modèle à entraîner : subjectlineTraining.xml.

Ces modèles ne peuvent être formés.

Une fois un modèle téléchargé, la fonctionnalité est automatiquement activée. Une nouvelle option apparaît alors en regard de l&#39;objet de vos messages.

>[!NOTE]
>
>L&#39;import et la génération de modèles entraînés peuvent être uniquement effectués par un administrateur.

## Résolution des problèmes {#troubleshooting}

La ligne de sujet prédictif est un processus d’apprentissage automatique qui prend en compte toutes les lignes de sujet que vous avez téléchargées avec leurs taux d’ouverture. Cela permet au système de prévoir le taux d’ouverture d’un courrier électronique lorsqu’une nouvelle ligne d’objet est envoyée.

Pour être en mesure de former votre propre modèle, les lignes de sujet doivent être variées et ne doivent pas avoir de , quel que soit le nombre de lignes de sujet utilisées pour former votre modèle.

La qualité des sujets est essentielle. S&#39;il n&#39;y a pas assez de données de qualité à traiter, ou si toutes les lignes d&#39;objet précédentes sont trop similaires, le système ne sera pas en mesure de former le modèle et vous pourriez obtenir un message d&#39;erreur. Cela signifie que votre jeu de dossiers existant ne permet pas de fournir une suggestion de prévision fiable.

Dans ce cas, vous devez examiner les données que vous téléchargez et vous assurer que les lignes d’objet sont suffisamment variées pour former efficacement votre modèle.

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
