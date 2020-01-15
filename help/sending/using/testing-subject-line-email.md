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
source-git-commit: 0bc487606fe3715b20452f3cf8eae52900539a32

---

# Test de l&#39;objet d&#39;un email {#testing-a-subject}

Pour tester un objet, procédez comme suit :

1. Créez un email ou ouvrez un email existant.
1. Ouvrez le contenu et saisissez l&#39;objet de l&#39;email dans le champ de saisie prévu à cet effet.
1. Cliquez sur le bouton **[!UICONTROL Tester l&#39;objet]**pour afficher la fenêtre**[!UICONTROL  Tester la ligne d&#39;objet]**. Vous pouvez toujours éditer l&#39;objet dans cette fenêtre.
1. Choisissez le bon modèle à prendre en compte pour la prédiction du taux d&#39;ouverture. Plusieurs modèles sont disponibles. Chacun d&#39;entre eux correspond à un secteur d&#39;activité spécifique.
1. Cliquez sur **[!UICONTROL Tester]**.

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

## Importer des modèles {#importing-models}

Par défaut, aucun modèle n&#39;est exécuté sur le serveur Adobe Campaign. Deux méthodes permettent d&#39;obtenir un modèle et d&#39;activer la fonctionnalité :

* Vous pouvez entraîner un modèle local à partir des données des emails envoyés :

   * Si vous utilisez déjà Adobe Campaign, le modèle local sera automatiquement entraîné avec les messages que vous avez déjà envoyés.
   * Si vous découvrez Adobe Campaign, vous pouvez extraire un fichier CSV de votre système/ESP précédent, qui contient 4 colonnes : date, sujet, ouverture, envoi. Pour cela, accédez à **[!UICONTROL Administration]**>**[!UICONTROL  Canaux]** > **[!UICONTROL Email]**>**[!UICONTROL  Import d&#39;objet]**, puis suivez les instructions affichées dans les différents écrans. Lorsque le téléchargement des objets est terminé, importez un modèle local en suivant la procédure qui est décrite ci-après. Le modèle local est automatiquement entraîné avec les données que vous avez téléchargées.
   * Si vous utilisez Adobe Campaign pour la première fois et si vous ne pouvez pas obtenir de fichier CSV comme décrit plus haut, vous pouvez utiliser un modèle pré-entraîné ou attendre que le système dispose de suffisamment de données de diffusion pour entraîner un modèle local. Le système détermine automatiquement si le jeu de données actuel contient suffisamment de données pour reconnaître des constantes et entraîner le modèle.

      >[!NOTE]
      >
      >Il n&#39;y a pas de nombre défini d&#39;objets requis pour entraîner votre propre modèle. Pour l&#39;entraîner, les objets doivent être variés et ne pas présenter de doublons. Si les données à traiter ne sont pas suffisantes, le système ne sera pas en mesure d&#39;entraîner le modèle. Votre instance ne peut contenir qu&#39;un seul modèle entraîné.
   Pour entraîner un modèle local, téléchargez le fichier subjectLineTraining.xml depuis [cet emplacement](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) et utilisez la fonctionnalité d&#39;[import de package](../../automating/using/managing-packages.md) pour le charger dans votre instance Adobe Campaign. Un workflow technique entraînera automatiquement le modèle.

   Lorsque vous entraînez un modèle pour la première fois, un administrateur peut forcer le démarrage du **[!UICONTROL Workflow d&#39;apprentissage de l&#39;objet]**depuis le menu**[!UICONTROL  Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** >**[!UICONTROL  Workflows]**.

   Une fois un modèle téléchargé et entraîné, la fonctionnalité est automatiquement activée. Une nouvelle option apparaît alors en regard de l&#39;objet de vos messages.

   Le workflow technique continue ensuite l&#39;apprentissage du modèle toutes les semaines.

* Vous pouvez importer des modèles pré-entraînés qui sont spécifiques à certains secteurs d&#39;activité (médical, etc.) à l&#39;aide de la fonctionnalité d&#39;[import de package](../../automating/using/managing-packages.md) Ces modèles sont disponibles [ici](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) et ne peuvent pas faire l&#39;objet d&#39;un apprentissage.

   Une fois un modèle téléchargé, la fonctionnalité est automatiquement activée. Une nouvelle option apparaît alors en regard de l&#39;objet de vos messages.

>[!NOTE]
>
>L&#39;import et la génération de modèles entraînés peuvent être uniquement effectués par un administrateur.

Les modèles disponibles sont les suivants :

* Secteur cosmétique : subjectInsightCosmetic.xml
* Secteur alimentaire : subjectInsightSupermarket.xml
* Secteur médical : subjectInsightMedical.xml
* Modèle à entraîner : subjectlineTraining.xml.
