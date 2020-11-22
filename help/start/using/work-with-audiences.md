---
solution: Campaign Standard
product: campaign
title: Personnalisation des listes
description: '"Découvrez comment personnaliser l''affichage et exécuter des actions sur les écrans de type Liste dans Adobe Campaign Standard : tri, filtrage, suppression ou duplication d''éléments. Les écrans de type Liste affichent les éléments d''une ou plusieurs ressources données."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '793'
ht-degree: 100%

---


# Utilisation des profils et audiences

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="conditions" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>Profils client</td>
<td>Enrichissement de votre base de données</td>
<td>Organisation de vos audiences</td>
<td>Gestion de la confidentialité</td>
</tr>
</table>

## Profils client {#customer-profiles}

<img width="60px" alt="conditions" src="assets/icon_profile.svg"/>

Les profils Adobe Campaign représentent l&#39;ensemble des contacts stockés dans la base de données. Chaque profil correspond à une entrée dans la base de données qui contient les informations nécessaires pour faire l&#39;objet de ciblage, qualification et tracking individuel. Ainsi, un profil peut être : un client, un prospect, un individu inscrit à une newsletter, un destinataire, un utilisateur, ou toute autre dénomination selon l&#39;organisation.

**En savoir plus**

* [A propos des profils](../../audiences/using/about-profiles.md)
* [Accès au nombre de profils actifs dans votre organisation](../../audiences/using/active-profiles.md)

## Enrichissement de votre base de données {#populating-database}

<img width="60px" alt="conditions" src="assets/icon_populate.svg"/>

Campaign Standard propose plusieurs outils pour vous aider à développer votre base de données marketing. Cette section décrit les différentes méthodes que vous pouvez utiliser pour injecter des données dans Campaign et contient des références à la documentation dédiée.

### Import de données par le biais de workflows {#importing-data-through-workflows}

Les workflows permettent de collecter des données et de les importer dans la base de données Campaign via les activités de [**[!UICONTROL Data management. ]**](../../automating/using/about-data-management-activities.md) Les informations génériques et les bonnes pratiques relatives à l&#39;import de données par le biais de workflows sont présentées dans [cette section](../../automating/using/about-data-import-and-export.md).

Vous pouvez en outre configurer des modèles pour importer des données. L&#39;utilisation de modèles d&#39;import est recommandée si vous devez importer régulièrement des fichiers avec la même structure. Vous pouvez configurer deux types de modèles :

* **Modèles de workflow** : il s&#39;agit de workflows préconfigurés que vous pouvez paramétrer une fois selon vos besoins. Vous pouvez ensuite les réutiliser chaque fois que vous souhaitez importer des données et mettre à jour la base de données. Vous trouverez un exemple de modèle de workflow pour importer des données dans [cette section](../../automating/using/creating-import-workflow-templates.md).

* **Modèles de données d&#39;import** : tout comme les modèles de workflow, il s&#39;agit de modèles reposant sur des workflows qui sont configurés pour télécharger des fichiers afin de mettre à jour la base de données. Une fois configurés, ils sont mis à disposition des utilisateurs avec une vue simplifiée dans le menu **[!UICONTROL Profil &amp; audiences]** / **[!UICONTROL Imports.]** Pour plus d&#39;informations sur les modèles de données d&#39;import, reportez-vous à la [documentation dédiée](../../automating/using/importing-data-with-import-templates.md).

### Collecte de données à partir de landing pages {#collecting-data-from-landing-pages}

Les landing pages sont des formulaires web qui peuvent être utilisés pour collecter des données et créer ou mettre à jour des informations existantes dans votre base de données. Le principe est le suivant :

* Créez et concevez votre landing page en ajoutant des champs d&#39;entrée pour collecter des données (prénom, nom, email, etc.).
* Faites correspondre chaque champ d&#39;entrée avec le champ correspondant de la base de données.
* Rendez la landing page disponible en ligne via un site web ou un lien direct dans un message.

Pour plus d&#39;informations sur les landing pages, reportez-vous à la [documentation dédiée](../../channels/using/getting-started-with-landing-pages.md).

**En savoir plus**

* xxxx
* xxxx

### Synchronisation des profils à partir de Microsoft Dynamics 365

L&#39;intégration de Campaign Standard avec Microsoft Dynamics 365 vous permet de transmettre les données de contact de Microsoft Dynamics 365 à la base de données Campaign.
Ces contacts sont alors visibles dans la liste Profils et peuvent être ciblés dans les campagnes marketing. Pour plus d&#39;informations sur cette intégration, reportez-vous à la [documentation dédiée](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!NOTE]
>
>Veuillez noter que le connecteur Campaign Standard-Microsoft Dynamics 365 est actuellement à disponibilité limitée et qu&#39;il est soumis à plusieurs restrictions, détaillées dans la documentation.

**En savoir plus**

* xxxx
* xxxx

### Import de données par le biais d&#39;appels d&#39;API

Les API Campaign Standard vous permettent d&#39;effectuer des opérations pour mettre à jour la base de données comme créer, mettre à jour ou supprimer des profils ou des services. Pour plus d&#39;informations sur l&#39;utilisation des API, reportez-vous à la [documentation dédiée](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Avant d&#39;effectuer une mise à jour ou une création en masse de profils via des appels d&#39;API, vérifiez les limites d&#39;échelle correspondant à votre contrat de licence. Voir à ce propos [cette page](https://helpx.adobe.com/fr/legal/product-descriptions/campaign-standard.html#RessourcesdinfrastructureinformatiqueparniveauxdeProfilsactifs).

**En savoir plus**

* xxxx
* xxxx

## Organisation de vos audiences {#organizing-audiences}

<img width="60px" alt="conditions" src="assets/icon_audience.svg"/>

Pour vous permettre de diffuser des messages pertinents et performants, ainsi que d&#39;atteindre vos clients efficacement, Adobe Campaign intègre des fonctionnalités de ciblage et d&#39;analyse avancée.

Grâce aux workflows et à l&#39;éditeur de requêtes, vous pouvez créer des audiences qui seront ciblées par vos différentes campagnes, selon les informations dont vous disposez à leur sujet, leurs activités, leur langue, leurs préférences ou leur historique marketing. De cette façon, vous pouvez, par exemple, filtrer les profils abonnés ou créer des audiences de la cible en fonction d&#39;un nombre illimité de critères.

**En savoir plus**

* [A propos des audiences](../../audiences/using/about-audiences.md)
* [Création d’une audience](../../audiences/using/creating-audiences.md)

## Gestion de la confidentialité {#privacy-management}

<img width="60px" alt="conditions" src="assets/icon_privacy.svg"/>

Le RGPD est la nouvelle loi de l&#39;Union européenne (UE) sur la protection de la vie privée. Il harmonise et modernise les exigences en matière de protection des données. Il s&#39;applique aux clients Adobe Campaign qui détiennent des données pour des titulaires de données résidant dans l&#39;UE. Outre les fonctionnalités de protection des données déjà disponibles dans Adobe Campaign (notamment la gestion des accords, les paramètres de rétention des données et les rôles utilisateur), nous incluons, dans le cadre de notre rôle de fournisseur de service de traitement des données, des fonctionnalités supplémentaires pour faciliter votre préparation en tant que Contrôleur de données à certaines demandes RGPD.

Pour plus d&#39;informations sur les outils et fonctionnalités proposés par Adobe Campaign pour vous aider à être en conformité avec le RGPD, reportez-vous à ce [guide](https://docs.campaign.adobe.com/doc/standard/getting_started/fr/ACS_GDPR.html).

**En savoir plus**

* xxxx
* xxxx