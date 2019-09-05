---
title: Rapports dynamiques
seo-title: Rapports dynamiques
description: Rapports dynamiques
seo-description: Avec les rapports dynamiques, placez des variables et des dimensions dans votre environnement de forme libre et analysez les performances de vos campagnes.
page-status-flag: never-activated
uuid: a84a18bd-4e33-466e-a6ce-d7008fe12746
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: reporting
content-type: reference
topic-tags: about-reporting
discoiquuid: bbb41c38-12c1-4625-85d5-69627e2f4b39
internal: n
snippet: y
translation-type: ht
source-git-commit: 4d95fe00c1958399ff4d22d5f0e7762f895b4032

---


# Rapports dynamiques{#about-dynamic-reports}

>[!NOTE]
>
>Seuls les utilisateurs disposant de droits d'administration ou pour lesquels les entités organisationnelles sont définies sur **Tous** peuvent créer ou enregistrer un nouveau rapport. Voir à ce propos cette [section](../../administration/using/users-management.md).

![](assets/dynamic_report_intro.png)

Les rapports dynamiques proposent des rapports entièrement personnalisables en temps réel. Ils offrent la possibilité d'accéder aux données de profil, ce qui permet l'analyse démographique par dimensions de profil, telles que le genre, la ville et l'âge, en plus des données de campagne email fonctionnelles comme les ouvertures et les clics. Grâce à l'interface glisser-déposer, vous pouvez explorer les données, déterminer les performances de vos campagnes email par rapport à vos segments de clients les plus importants et mesurer leur impact sur les destinataires.

Grâce à son menu glisser-déposer et à ses visualisations personnalisables, la fonctionnalité rapports dynamiques vous permet de créer n'importe quelle combinaison de dimensions, d'indicateurs métriques et de plage horaire avec un nombre illimité de répartitions et de comparaisons.


**Rubriques connexes :**

* [Liste des rapports](../../reporting/using/defining-the-report-period.md)
* [Entités organisationnelles](../../administration/using/organizational-units.md)
* Vidéo [Rapports dynamiques](https://helpx.adobe.com/fr/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html)

## Accès aux rapports dynamiques {#accessing-dynamic-reports}

Les rapports sont accessibles :

* depuis la page d'accueil, en sélectionnant l'onglet **[!UICONTROL Rapports]** dans la barre supérieure ou la vignette **[!UICONTROL Rapports]** pour accéder aux rapports relatifs à toutes les diffusions ;

   ![](assets/campaign_reports_access.png)

* dans chaque programme, campagne et message, depuis le bouton **Rapports**, en cliquant sur **Rapports dynamiques** pour consulter uniquement les rapports spécifiques à la diffusion.

   ![](assets/campaign_reports_description.png)

Certains rapports peuvent ne pas être immédiatement disponibles après une diffusion, selon le délai de collecte et de traitement des informations.

Les rapports dynamiques sont divisés en deux catégories :

* les **modèles**, qui peuvent être modifiés après avoir été copiés à l'aide de l'option **Enregistrer sous** (**Projet &gt; Enregistrer sous...**) dans le modèle.
* les **rapports personnalisés** (en bleu), qui peuvent être créés directement en cliquant sur le bouton **Créer un nouveau projet** sur la page d'accueil des **Rapports**.

>[!NOTE]
>
>Les données sont filtrées en fonction de vos entités organisationnelles.

![](assets/dynamic_report_overview.png)


## Accord sur l'utilisation du reporting dynamique {#dynamic-reporting-usage-agreement}

Les rapports dynamiques permettent de filtrer un rapport selon les données de profil avec des dimensions de profil.

Les dimensions de profil ne peuvent être affichées et utilisées dans vos rapports qu'une fois que vous avez accepté l'Accord d'utilisation du reporting dynamique. Par défaut, seuls les utilisateurs auxquels sont affectés des droits d'administration peuvent afficher et accepter ou refuser cet accord.

Cet accord autorise le transfert et le stockage aux Etats-Unis des données de profil suivantes : ville, pays/zone géographique, état, genre et segments sur la base de l'âge.

En acceptant le présent accord, toutes les données européennes et non européennes seront transférées aux États-Unis.

![](assets/pii_window.png)

Trois options sont disponibles :

* **[!UICONTROL Me demander plus tard]** : lorsque vous cliquez sur Me demander plus tard, la fenêtre ne s'affiche plus pendant 24 heures.
* **[!UICONTROL Accepter]** : lorsque vous acceptez les termes de cet accord, vous autorisez Adobe Campaign à collecter les PII de vos clients et à les transférer vers les États-Unis.
* **[!UICONTROL Refuser]** : lorsque vous refusez les termes de l'accord, les dimensions de profil ne s'affichent pas dans vos rapports et les PII de vos clients ne sont pas collectées ni envoyées.

Ce choix n'est pas définitif. Vous pouvez toujours changer d'option en sélectionnant **[!UICONTROL Autoriser le transfert des données de PII vers les Etats-Unis afin d'utiliser le reporting sur les données de profil]** dans **[!UICONTROL Administration]** &gt; **[!UICONTROL Paramétrage de l'application]** &gt; **[!UICONTROL Options]**.

La valeur peut être modifiée à tout moment. La valeur -1 correspond à **[!UICONTROL Me demander plus tard]**, 1 à **[!UICONTROL Accepter]** et 0 à **[!UICONTROL Refuser]**.

![](assets/pii_window_2.png)

