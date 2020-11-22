---
solution: Campaign Standard
product: campaign
title: Prise en main des rapports dynamiques
description: Avec les rapports dynamiques, placez des variables et des dimensions dans votre environnement de forme libre et analysez les performances de vos campagnes.
audience: reporting
content-type: reference
topic-tags: about-reporting
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 100%

---


# Prise en main des rapports dynamiques {#about-dynamic-reports}

Les rapports dynamiques proposent des rapports entièrement personnalisables en temps réel. Ils offrent la possibilité d&#39;accéder aux données de profil, ce qui permet l&#39;analyse démographique par dimensions de profil, telles que le genre, la ville et l&#39;âge, en plus des données de campagne email fonctionnelles comme les ouvertures et les clics. Grâce à l&#39;interface glisser-déposer, vous pouvez explorer les données, déterminer les performances de vos campagnes email par rapport à vos segments de clients les plus importants et mesurer leur impact sur les destinataires.

>[!NOTE]
>
>Seuls les utilisateurs disposant de droits d&#39;administration ou pour lesquels les entités organisationnelles sont définies sur **Tous** peuvent créer ou enregistrer un nouveau rapport. Voir à ce propos cette [section](../../administration/using/users-management.md).

## Accès aux rapports dynamiques {#accessing-dynamic-reports}

Les rapports sont accessibles :

* depuis la page d&#39;accueil, en sélectionnant l&#39;onglet **[!UICONTROL Rapports]** dans la barre supérieure ou la vignette **[!UICONTROL Rapports]** pour accéder aux rapports relatifs à toutes les diffusions ;

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

* **[!UICONTROL Me demander plus tard]** : Lorsque vous cliquez sur **Me demander plus tard**, la fenêtre ne s&#39;affiche plus pendant 24 heures. Tant que vous n&#39;avez pas accepté ou refusé les termes de l&#39;accord, les dimensions de profil ne s&#39;affichent pas dans vos rapports et les PII de vos clients ne sont pas collectées ni envoyées.
* **[!UICONTROL Accepter]** : lorsque vous acceptez les termes de cet accord, vous autorisez Adobe Campaign à collecter les PII de vos clients et à les transférer au centre de données ou de reporting.
* **[!UICONTROL Refuser]** : lorsque vous refusez les termes de l&#39;accord, les dimensions de profil ne s&#39;affichent pas dans vos rapports et les PII de vos clients ne sont pas collectées ni envoyées. Notez que dans ce cas, externalID sera toujours collecté et utilisé pour identifier les utilisateurs finaux.

Le tableau ci-dessous indique ce qui se passe après l&#39;acceptation de cet accord selon votre zone géographique.

|  | Rapports dynamiques | Connecteur Microsoft Dynamics 365 |
|---|---|---|
| Amériques et Asie-Pacifique | **Fonctionnalité disponible**. <br>Toutes les informations de profil personnalisées et d&#39;usine (ville, pays/région, état, genre et segments selon l&#39;âge) sont transmises au centre de reporting des Etats-Unis. Pour plus d&#39;informations sur les dimensions de profil, consultez cette [page](../../reporting/using/list-of-components-.md) | **Fonctionnalité disponible**. <br>Tous les champs de profil personnalisés et d&#39;usine, ainsi que les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données des Etats-Unis. |
| EMEA (Europe, Moyen-Orient et Afrique) | **Fonctionnalité disponible**. <br>Toutes les informations de profil personnalisées et d&#39;usine (ville, pays/région, état, genre et segments selon l&#39;âge) sont transmises au centre de reporting EMEA. Pour plus d&#39;informations sur les dimensions de profil, consultez cette [page](../../reporting/using/list-of-components-.md) | **Fonctionnalité disponible.** <br>Tous les champs de profil personnalisés et d&#39;usine, ainsi que les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données EMEA. Les <br>**[!UICONTROL données de contrôle ]**qui contiennent les données d&#39;enregistrement Adobe I/O et les identifiants des événements utilisateur des clients sont envoyés et stockés dans le centre de données des Etats-Unis. |

Le tableau ci-dessous indique ce qui se passe après le refus de cet accord selon votre zone géographique. Notez que même si vous refusez cet accord, le reporting sur les diffusions et l&#39;intégration de Microsoft Dynamics 365 sera toujours disponible.

| Zone géographique | Rapports dynamiques | Connecteur Microsoft Dynamics 365 |
|---|---|---|
| Amériques et Asie-Pacifique | **Fonctionnalité disponible**. <br> Aucune information de profil personnalisée et d&#39;usine n&#39;est transmise au centre de reporting des Etats-Unis, à l&#39;exception d&#39;ExternalID. | **Fonctionnalité disponible**. <br>Aucun champ de profil personnalisé et d&#39;usine n&#39;est envoyé au centre de données des Etats-Unis, à l&#39;exception des champs Identifiant externe et Identifiant du destinataire. <br>Tous les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données des États-Unis, à l&#39;exception de l&#39;ID de la page miroir. <br>Pour plus d&#39;informations sur l&#39;intégration de Microsoft Dynamics 365, consultez cette [page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |
| EMEA (Europe, Moyen-Orient et Afrique) | **Fonctionnalité disponible**. <br>Aucune information de profil personnalisée et d&#39;usine n&#39;est transmise au centre de reporting EMEA, à l&#39;exception d&#39;ExternalID. | **Fonctionnalité disponible.** <br>Aucun champ de profil personnalisé et d&#39;usine n&#39;est envoyé au centre de données EMEA, à l&#39;exception des champs Identifiant externe et Identifiant du destinataire. <br>Tous les champs d&#39;événement Adobe Campaign Standard sont traités dans le centre de données EMEA, à l&#39;exception de l&#39;ID de la page miroir.  Les <br>**[!UICONTROL données de contrôle ]**qui contiennent les données d&#39;enregistrement Adobe I/O et les identifiants des événements utilisateur des clients sont envoyés et stockés dans le centre de données des Etats-Unis.<br>Pour plus d&#39;informations sur l&#39;intégration de Microsoft Dynamics 365, consultez cette [page](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md). |

Ce choix n&#39;est pas définitif. Vous pouvez toujours changer d&#39;option en sélectionnant **[!UICONTROL Autoriser le transfert des données de PII vers les Etats-Unis afin d&#39;utiliser le reporting sur les données de profil]** dans **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** > **[!UICONTROL Options]**.

La valeur peut être modifiée à tout moment. La valeur 1 correspond à **[!UICONTROL Me demander plus tard]**, 2 à **[!UICONTROL Refuser]** et 3 à **[!UICONTROL Accepter]**.

![](assets/pii_window_2.png)
