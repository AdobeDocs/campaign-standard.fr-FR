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
translation-type: tm+mt
source-git-commit: c606612b1bfb313e8eb20e45cf631609ec07aa84

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
* Vidéo [Rapports dynamiques](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-dynamic-report-feature-video-use.html)

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

>[!NOTE]
>
> Depuis la version 19.4 de Campaign Standard, la fenêtre contextuelle de consentement pour la création de rapports dynamiques a été mise à jour afin d’inclure Adobe Campaign Standard et l’intégration de Microsoft Dynamics 365.

L’accord d’utilisation des rapports dynamiques a pour objectif de fonctionner comme un consentement contextuel pour le traitement des données. Par défaut, seuls les utilisateurs auxquels sont affectés des droits d'administration peuvent afficher et accepter ou refuser cet accord.

Trois options sont disponibles :

* **[!UICONTROL Me demander plus tard]****** : lorsque vous cliquez sur Me demander plus tard, la fenêtre ne s'affiche plus pendant 24 heures. Tant que vous n’acceptez pas ou refusez le contrat, les dimensions du profil n’apparaîtront pas dans vos rapports et les informations d’identification personnelle de vos clients ne seront pas collectées ni envoyées.
* **[!UICONTROL Accepter]**: En acceptant cet accord, vous autorisez Adobe Campaign à collecter les informations d’identification personnelle de vos clients et à les transférer au centre de création de rapports ou de données.
* **[!UICONTROL Refuser]** : lorsque vous refusez les termes de l'accord, les dimensions de profil ne s'affichent pas dans vos rapports et les PII de vos clients ne sont pas collectées ni envoyées. Notez que dans ce cas, externalID sera toujours collecté et utilisé pour identifier les utilisateurs finaux.

Le tableau ci-dessous indique ce qui se passe après l’acceptation de cet accord selon votre région.

|  | Reporting dynamique | Connecteur Microsoft Dynamics 365 |
|---|---|---|
| Amériques et Asie-Pacifique | **Fonction disponible**. <br>Toutes les informations prêtes à l’emploi (c.-à-d. ville, pays/région, état, sexe et segments selon l’âge) et les profils personnalisés sont transmis au centre de création de rapports des États-Unis. For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **Fonction disponible**. <br>Tous les champs de profil personnalisés et prêts à l’emploi et d’événement Adobe Campaign Standard sont traités dans le centre de données des États-Unis. |
| EMEA (Europe, Moyen-Orient et Afrique) | **Fonction disponible**. <br>Toutes les informations prêtes à l'emploi (c.-à-d. ville, pays/région, état, sexe et segments sur la base de l'âge) et les profils personnalisés sont envoyés dans le centre de création de rapports EMEA. For more information on profile dimensions, refer to this [page](../../reporting/using/list-of-components-.md) | **Fonction disponible.** <br>Tous les champs de profils personnalisés et prêts à l’emploi et d’événements Adobe Campaign Standard sont traités dans le centre de données EMEA. <br>**[!UICONTROL Contrôlez les données]** qui contiennent les données d’enregistrement des E/S Adobe et les ID des événements d’utilisateur final envoyés et stockés dans le centre de données des États-Unis. |

Le tableau ci-dessous indique ce qui se passe après la déclinaison de cet accord selon votre région. Notez que même si vous refusez cet accord, la création de rapports sur les livraisons et l'intégration de Microsoft Dynamics 365 sera toujours disponible.

| Région | Reporting dynamique | Connecteur Microsoft Dynamics 365 |
|---|---|---|
| Amériques et Asie-Pacifique | **Fonction disponible**. <br> Aucune information prête à l’emploi ni aucune information sur les profils personnalisés n’est transmise au centre de rapports des États-Unis, à l’exception de ExternalID. | **Fonction disponible**. <br>Aucun champ de profil personnalisé ou prêt à l’emploi n’est envoyé au centre de données des États-Unis, à l’exception des champs ID externe et ID de destinataire. <br>Tous les champs d’événement Adobe Campaign Standard sont traités dans le centre de données des États-Unis, à l’exception de l’ID de page miroir. <br>Pour plus d'informations sur l'intégration de Microsoft Dynamics 365, consultez cette [page](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html). |
| EMEA (Europe, Moyen-Orient et Afrique) | **Fonction disponible**. <br>Aucune information prête à l’emploi et aucun profil personnalisé n’est envoyé vers le centre de rapports EMEA, à l’exception de ExternalID. | **Fonction disponible.** <br>Aucun champ de profil personnalisé ou prêt à l’emploi n’est envoyé au centre de données EMEA, à l’exception des champs ID externe et ID de destinataire. <br>Tous les champs d’événement Adobe Campaign Standard sont traités dans le centre de données EMEA, à l’exception de l’ID de page miroir.  <br>**[!UICONTROL Contrôlez les données]** qui contiennent les données d’enregistrement des E/S Adobe et les ID des événements d’utilisateur final envoyés et stockés dans le centre de données des États-Unis.<br>Pour plus d'informations sur l'intégration de Microsoft Dynamics 365, consultez cette [page](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html). |

Ce choix n'est pas définitif. Vous pouvez toujours changer d'option en sélectionnant **[!UICONTROL Autoriser le transfert des données de PII vers les Etats-Unis afin d'utiliser le reporting sur les données de profil]** dans **[!UICONTROL Administration]** &gt; **[!UICONTROL Paramétrage de l'application]** &gt; **[!UICONTROL Options]**.

La valeur peut être modifiée à tout moment. The value 1 corresponds to **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** and 3 **[!UICONTROL Accept]**.

Notez que pour les versions antérieures à Adobe Campaign Standard 19.4, la valeur -1 correspond à **[!UICONTROL Me demander plus tard]**, 0 **[!UICONTROL refuser]** et 1 **[!UICONTROL accepter]**.

![](assets/pii_window_2.png)
