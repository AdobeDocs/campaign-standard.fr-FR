---
title: Rapports dynamiques
description: Avec les rapports dynamiques, placez des variables et des dimensions dans votre environnement de forme libre et analysez les performances de vos campagnes.
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
source-git-commit: 6bf67d05ec8f5b4024df29c7ee7df7fc15e95e0a

---


# Rapports dynamiques{#about-dynamic-reports}

Les rapports dynamiques proposent des rapports entièrement personnalisables en temps réel. Ils offrent la possibilité d&#39;accéder aux données de profil, ce qui permet l&#39;analyse démographique par dimensions de profil, telles que le genre, la ville et l&#39;âge, en plus des données de campagne email fonctionnelles comme les ouvertures et les clics. Grâce à l&#39;interface glisser-déposer, vous pouvez explorer les données, déterminer les performances de vos campagnes email par rapport à vos segments de clients les plus importants et mesurer leur impact sur les destinataires.

>[!NOTE]
>
>Seuls les utilisateurs disposant de droits d&#39;administration ou pour lesquels les entités organisationnelles sont définies sur **Tous** peuvent créer ou enregistrer un nouveau rapport. Voir à ce propos cette [section](../../administration/using/users-management.md).

![](assets/dynamic_report_intro.png)

Grâce à son menu glisser-déposer et à ses visualisations personnalisables, la fonctionnalité rapports dynamiques vous permet de créer n&#39;importe quelle combinaison de dimensions, d&#39;indicateurs métriques et de plage horaire avec un nombre illimité de répartitions et de comparaisons.


**Rubriques connexes :**

* [Liste des rapports](../../reporting/using/defining-the-report-period.md)
* [Entités organisationnelles](../../administration/using/organizational-units.md)
* Vidéo [Rapports dynamiques](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/creating-a-dynamic-report.html)

## Accès aux rapports dynamiques {#accessing-dynamic-reports}

Les rapports sont accessibles :

* From the home page by selecting **[!UICONTROL Reports]** tab in the top bar or the **[!UICONTROL Reports]** card to access reports for all deliveries.

   ![](assets/campaign_reports_access.png)

* dans chaque programme, campagne et message, depuis le bouton **Rapports**, en cliquant sur **Rapports dynamiques** pour consulter uniquement les rapports spécifiques à la diffusion.

   ![](assets/campaign_reports_description.png)

Certains rapports peuvent ne pas être immédiatement disponibles après une diffusion, selon le délai de collecte et de traitement des informations.

Les rapports dynamiques sont divisés en deux catégories :

* les **modèles**, qui peuvent être modifiés après avoir été copiés à l&#39;aide de l&#39;option **Enregistrer sous** (**Projet > Enregistrer sous...**) dans le modèle.
* les **rapports personnalisés** (en bleu), qui peuvent être créés directement en cliquant sur le bouton **Créer un nouveau projet** sur la page d&#39;accueil des **Rapports**.

>[!NOTE]
>
>Les données sont filtrées en fonction de vos entités organisationnelles.

![](assets/dynamic_report_overview.png)

## Accord sur l&#39;utilisation des rapports dynamiques {#dynamic-reporting-usage-agreement}

L&#39;accord sur l&#39;utilisation des rapports dynamiques fonctionne comme un consentement contextuel pour le traitement des données. Par défaut, seuls les utilisateurs auxquels sont affectés des droits d&#39;administration peuvent afficher et accepter ou refuser cet accord.

Trois options sont disponibles :

* **[!UICONTROL Ask me later]**: En cliquant sur **Me demander plus tard**, la fenêtre cessera de s&#39;afficher pendant 24 heures. Tant que vous n&#39;avez pas accepté ou refusé les termes de l&#39;accord, les dimensions de profil ne s&#39;affichent pas dans vos rapports et les PII de vos clients ne sont pas collectées ni envoyées.
* **[!UICONTROL Accept]**: En acceptant cet accord, vous autorisez  Adobe Campaign à collecter les informations d&#39;identification personnelle de vos clients et à les transférer à la ou au centre de données.
* **[!UICONTROL Decline]**: En refusant le contrat, les dimensions de  du n&#39;apparaîtront pas dans vos rapports et les informations d&#39;identification personnelle de vos clients ne seront ni collectées ni envoyées. Notez que dans ce cas, externalID sera toujours collecté et utilisé pour identifier les utilisateurs finaux.

Le tableau ci-dessous indique ce qui se passe après l&#39;acceptation de cet accord selon votre zone géographique.

|  | Rapports dynamiques | Connecteur Microsoft Dynamics 365 |
|---|---|---|
| Amériques et Asie-Pacifique | **Fonctionnalité disponible**. <br>Toutes les informations de profil personnalisées et d&#39;usine (ville, pays/région, état, genre et segments selon l&#39;âge) sont transmises au centre de reporting des Etats-Unis. Pour plus d&#39;informations sur les dimensions de profil, consultez cette [page](../../reporting/using/list-of-components-.md) | **Fonctionnalité disponible**. <br>Tous les champs de profil personnalisés et d&#39;usine, ainsi que les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données des Etats-Unis. |
| EMEA (Europe, Moyen-Orient et Afrique) | **Fonctionnalité disponible**. <br>Toutes les informations de profil personnalisées et d&#39;usine (ville, pays/région, état, genre et segments selon l&#39;âge) sont transmises au centre de reporting EMEA. Pour plus d&#39;informations sur les dimensions de profil, consultez cette [page](../../reporting/using/list-of-components-.md) | **Fonctionnalité disponible.** <br>Tous les champs de profil personnalisés et d&#39;usine, ainsi que les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données EMEA. <br>**[!UICONTROL Control data]** qui contient les données d’enregistrement des E/S Adobe et les ID des d’utilisateurs finaux du client envoyés et stockés dans le centre de données des États-Unis. |

Le tableau ci-dessous indique ce qui se passe après le refus de cet accord selon votre zone géographique. Notez que même si vous refusez cet accord, le reporting sur les diffusions et l&#39;intégration de Microsoft Dynamics 365 sera toujours disponible.

| Zone géographique | Rapports dynamiques | Connecteur Microsoft Dynamics 365 |
|---|---|---|
| Amériques et Asie-Pacifique | **Fonctionnalité disponible**. <br> Aucune information de profil personnalisée et d&#39;usine n&#39;est transmise au centre de reporting des Etats-Unis, à l&#39;exception d&#39;ExternalID. | **Fonctionnalité disponible**. <br>Aucun champ de profil personnalisé et d&#39;usine n&#39;est envoyé au centre de données des Etats-Unis, à l&#39;exception des champs Identifiant externe et Identifiant du destinataire. <br>Tous les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données des États-Unis, à l&#39;exception de l&#39;ID de la page miroir. <br>Pour plus d&#39;informations sur l&#39;intégration de Microsoft Dynamics 365, consultez cette [page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |
| EMEA (Europe, Moyen-Orient et Afrique) | **Fonctionnalité disponible**. <br>Aucune information de profil personnalisée et d&#39;usine n&#39;est transmise au centre de reporting EMEA, à l&#39;exception d&#39;ExternalID. | **Fonctionnalité disponible.** <br>Aucun champ de profil personnalisé et d&#39;usine n&#39;est envoyé au centre de données EMEA, à l&#39;exception des champs Identifiant externe et Identifiant du destinataire. <br>Tous les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données EMEA, à l&#39;exception de l&#39;ID de la page miroir.  <br>**[!UICONTROL Control data]** qui contient les données d’enregistrement des E/S Adobe et les ID des d’utilisateurs finaux du client envoyés et stockés dans le centre de données des États-Unis.<br>Pour plus d&#39;informations sur l&#39;intégration de Microsoft Dynamics 365, consultez cette [page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |

Ce choix n’est pas définitif, vous pouvez toujours le modifier en le sélectionnant **[!UICONTROL Enable PII data to be transferred to US region to use reporting on Profile data]** dans **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**.

La valeur peut être modifiée à tout moment. La valeur 1 correspond à **[!UICONTROL Ask me later]**, 2 **[!UICONTROL Decline]** et 3 **[!UICONTROL Accept]**.

![](assets/pii_window_2.png)
