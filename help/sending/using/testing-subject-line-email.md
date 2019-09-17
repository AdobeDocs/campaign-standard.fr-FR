---
title: Test de la ligne d'objet d'un e-mail
seo-title: Test de la ligne d'objet d'un e-mail
description: Test de la ligne d'objet d'un e-mail
seo-description: Découvrez comment définir la ligne d'objet d'un e-mail dans le Concepteur de e-mails.
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
source-git-commit: 62992dbedea7209ca26ae9e1a475a0c87405a4d9

---

# Tester un objet {#testing-a-subject}

Pour tester un objet, procédez comme suit :

1. Créez un email ou ouvrez un email existant.
1. Ouvrez le contenu et saisissez l'objet de l'email dans le champ de saisie prévu à cet effet.
1. Cliquez sur le bouton **[!UICONTROL Tester l'objet]** pour afficher la fenêtre **[!UICONTROL Tester la ligne d'objet]**. Vous pouvez toujours éditer l'objet dans cette fenêtre.
1. Choisissez le bon modèle à prendre en compte pour la prédiction du taux d'ouverture. Plusieurs modèles sont disponibles. Chacun d'entre eux correspond à un secteur d'activité spécifique.
1. Cliquez sur **[!UICONTROL Tester]**.

Votre objet est alors analysé.

>[!NOTE]
>
>Si l'objet est trop court, il ne peut pas être analysé et un message d'erreur s'affiche.

Plusieurs indicateurs sont calculés et un ensemble d'outils s'affiche en vue de vous aider :

* **Taux d'ouverture estimé** : ce graphique donne une idée du taux d'ouverture escompté de l'email avec l'objet actuellement testé.
* **Longueur de l'objet** : cet indicateur permet de déterminer si la longueur actuelle de l'objet est correcte ou si elle doit être allongée ou raccourcie.
* **Mots en couleur** : lors du test de l'objet, les mots surlignés en vert correspondent à ceux qui contribuent le plus à l'augmentation de la prédiction du taux d'ouverture. Les mots surlignés en rouge, quant à eux, correspondent à ceux qui contribuent le moins à l'augmentation de la prédiction du taux d'ouverture. Si vous ajoutez ou supprimez des mots de l'objet, les mots surlignés changent.
* **Catégories et suggestions de mots** : la partie inférieure de la fenêtre contient plusieurs catégories pertinentes pour le modèle sélectionné. Ces catégories, triées par ordre d'importance, permettent de déterminer si l'objet contient des mots qui leur sont associés grâce à une coche. Chaque catégorie contient un ensemble de mots proposés qui peuvent être utilisés dans votre objet afin de le rendre plus pertinent et augmenter le taux d'ouverture. Ces mots correspondent à ceux qui sont le plus souvent utilisés dans une catégorie donnée.

>[!NOTE]
>
>Les champs de personnalisation et les signes de ponctuation ne sont pas pris en compte dans l'analyse de l'objet. Pour les textes dynamiques/conditionnels, toutes les variantes sont traitées comme un seul objet.

![](assets/predictive_subject_line_example.png)

## Importer des modèles  {#importing-models}

Par défaut, aucun modèle n'est exécuté sur le serveur Adobe Campaign. Deux méthodes permettent d'obtenir un modèle et d'activer la fonctionnalité :

* Vous pouvez entraîner un modèle local à partir des données des emails envoyés :

   * Si vous utilisez déjà Adobe Campaign, le modèle local sera automatiquement entraîné avec les messages que vous avez déjà envoyés.
   * Si vous utilisez Adobe Campaign pour la première fois, vous pouvez extraire de votre précédent système/fournisseur de services de messagerie un fichier CSV contenant 4 colonnes : date, subject, sent, opens. Pour cela, accédez à **[!UICONTROL Administration]** &gt; **[!UICONTROL Canaux]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Import d'objet]**, puis suivez les instructions affichées dans les différents écrans. Lorsque le téléchargement des objets est terminé, importez un modèle local en suivant la procédure qui est décrite ci-après. Le modèle local est automatiquement entraîné avec les données que vous avez téléchargées.
   * Si vous utilisez Adobe Campaign pour la première fois et si vous ne pouvez pas obtenir de fichier CSV comme décrit plus haut, vous pouvez utiliser un modèle pré-entraîné ou attendre que le système dispose de suffisamment de données de diffusion pour entraîner un modèle local. Le système détermine automatiquement si le jeu de données actuel contient suffisamment de données pour reconnaître des constantes et entraîner le modèle.

      >[!NOTE]
      >
      >Il n'y a pas de nombre défini d'objets requis pour entraîner votre propre modèle. Pour l'entraîner, les objets doivent être variés et ne pas présenter de doublons. Si les données à traiter ne sont pas suffisantes, le système ne sera pas en mesure d'entraîner le modèle. Votre instance ne peut contenir qu'un seul modèle entraîné.
   Pour entraîner un modèle local, téléchargez le fichier subjectLineTraining.xml depuis [cet emplacement](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) et utilisez la fonctionnalité d'[import de package](../../automating/using/managing-packages.md) pour le charger dans votre instance Adobe Campaign. Un workflow technique entraînera automatiquement le modèle.

   Lorsque vous entraînez un modèle pour la première fois, un administrateur peut forcer le démarrage du **[!UICONTROL Workflow d'apprentissage de l'objet]** depuis le menu **[!UICONTROL Administration]** &gt; **[!UICONTROL Paramétrage de l'application]** &gt; **[!UICONTROL Workflows]**.

   Une fois un modèle téléchargé et entraîné, la fonctionnalité est automatiquement activée. Une nouvelle option apparaît alors en regard de l'objet de vos messages.

   Le workflow technique continue ensuite l'apprentissage du modèle toutes les semaines.

* Vous pouvez importer des modèles pré-entraînés qui sont spécifiques à certains secteurs d'activité (médical, etc.) à l'aide de la fonctionnalité d'[import de package](../../automating/using/managing-packages.md) Ces modèles sont disponibles [ici](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) et ne peuvent pas faire l'objet d'un apprentissage.

   Une fois un modèle téléchargé, la fonctionnalité est automatiquement activée. Une nouvelle option apparaît alors en regard de l'objet de vos messages.

>[!NOTE]
>
>L'import et la génération de modèles entraînés peuvent être uniquement effectués par un administrateur.

Les modèles disponibles sont les suivants :

* Secteur cosmétique : subjectInsightCosmetic.xml
* Secteur alimentaire : subjectInsightSupermarket.xml
* Secteur médical : subjectInsightMedical.xml
* Modèle à entraîner : subjectlineTraining.xml.