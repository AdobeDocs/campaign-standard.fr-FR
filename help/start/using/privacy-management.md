---
title: Gestion de la confidentialité dans Adobe Campaign Standard
description: Découvrez en détail les fonctionnalités de gestion de la confidentialité d’Adobe Campaign Standard.
audience: start
content-type: reference
topic-tags: discovering-the-interface
feature: Privacy
role: User
level: Intermediate
exl-id: 84cf8f6e-9ba0-4cd5-80e2-a61cefa31e0a
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: ht
source-wordcount: '788'
ht-degree: 100%

---

# Gestion de la confidentialité {#privacy-management}

Adobe Campaign propose un ensemble d’outils pour vous aider à vous conformer aux [règlements sur la protection des données](#privacy-management-regulations) (notamment RGPD, CCPA, PDPA, LGPD).

Voici les cinq principales capacités offertes par Adobe Campaign pour s’assurer du respect du RGPD et d’autres règlements sur la protection des données :

![](assets/privacy-gdpr-use-cases.png)

* **Droit d’accès**

* **Droit de suppression**

Pour plus d’informations, consultez la section [Droit d&#39;accès et Droit à l&#39;oubli](#right-access-forgotten).

* **Gestion du consentement**

* **Conservation des données**

* **Gestion des droits**

Pour plus d’informations, consultez la section [Consentement, conservation des données et rôles](#consent-retention-roles).

<!--This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

It also contains information on important features to manage Privacy ([consent, data retention and user roles](#consent-retention-roles)), as well as best practices to help you with your Privacy compliance when using Adobe Campaign.-->

## Règlements relatifs à la gestion de la confidentialité {#privacy-management-regulations}

Les fonctionnalités d’Adobe Campaign vous aident à respecter les réglementations suivantes :

* **Le RGPD** ([Règlement général sur la protection des données](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_fr)) est la loi de l’Union européenne (UE) sur la protection de la vie privée. Il harmonise et modernise les exigences en matière de protection des données pour les pays de l’UE. Suivez les liens ci-dessous pour obtenir des renseignements généraux sur le RGPD : 

   * https://www.adobe.com/fr/privacy/general-data-protection-regulation.html
   * https://www.adobe.com/fr/marketing-cloud/campaign/general-data-protection-regulation.html

* **Le CCPA** ([California Consumer Privacy Act](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) fournit aux résidents de la Californie de nouveaux droits relatifs aux informations personnelles et impose des responsabilités en matière de protection des données à certaines entités qui exercent des activités en Californie.
* **Le PDPA** ([Personal Data Protection Act)](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) est la nouvelle loi sur la protection de la vie privée qui harmonise et modernise les exigences en matière de protection des données en Thaïlande.
* **Le LGPD** ([Lei Geral de Proteção de Dados](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) entrera en vigueur début 2021 pour toutes les sociétés qui collectent ou traitent des données personnelles au Brésil.

Tous ces règlements s’appliquent aux clients Adobe Campaign qui détiennent des données pour les titulaires de données résidant dans les régions ou pays respectifs mentionnés ci-dessus (UE, Californie, Thaïlande, Brésil).

>[!NOTE]
>
>Pour plus d’informations sur les données personnelles et sur les différentes entités qui gèrent les données (contrôleur de données, responsable du traitement des données et titulaire de données), consultez la section [Données personnelles et personas](../../start/using/privacy.md#personal-data).

## Droit d’accès et droit à l’oubli {#right-access-forgotten}

Pour faciliter la préparation à la protection des données, Adobe Campaign permet désormais de gérer les demandes d’**accès** et de **suppression**.

* Le **droit d’accès** permet au titulaire de données de demander au contrôleur de données si les données personnelles le concernant sont traitées ou non, et le cas échéant, de savoir où et à quelles fins elles le sont. Le contrôleur de données doit fournir gratuitement une copie des données personnelles dans un format électronique.

* Également appelé « Effacement de données », le **Droit à l’oubli** (demande de suppression) autorise le titulaire de données à demander au contrôleur de données d’effacer ses données personnelles, de cesser la diffusion des données et de faire éventuellement cesser le traitement des données par des tiers.

Pour découvrir comment créer des demandes d’**accès** et de **suppression**, ainsi que leur traitement par Adobe Campaign, consultez la section [Étapes d’implémentation](../../start/using/privacy-requests.md#about-privacy-requests).

Vous trouverez également des informations sur la gestion de la protection des données dans Campaign Standard [ici](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=fr#privacy).

>[!NOTE]
>
>Pour plus d’informations sur les données personnelles et sur les différentes entités qui gèrent les données (contrôleur de données, responsable du traitement des données et titulaire de données), consultez la section [Données personnelles et personas](../../start/using/privacy.md#personal-data).

## Consentement, conservation des données et rôles {#consent-retention-roles}

En plus des récentes options **Droit d’accès** et **Droit à l’oubli**, Adobe Campaign propose d’autres fonctionnalités importantes qui sont essentielles pour la protection des données :

* [Gestion du consentement](#consent-management) : fonctionnalité d&#39;abonnement pour la gestion des préférences.
* [Conservation des données](../../administration/using/data-retention.md) : périodes de conservation des données pour toutes les tables de logs d&#39;usine ; des périodes de conservation supplémentaires peuvent être configurées avec des workflows.
* [Gestion des droits](#rights-management) : accès aux données géré par les droits nommés

### Gestion du consentement {#consent-management}

Le consentement signifie l&#39;accord donné par le titulaire des données pour le traitement des données personnelles le concernant. C&#39;est le contrôleur des données qui est responsable d&#39;obtenir les consentements nécessaires pour ce traitement. Bien qu&#39;Adobe Campaign puisse proposer certaines fonctionnalités permettant à un client de gérer les consentements relatifs au service, Adobe n&#39;est pas responsable des consentements. Les clients doivent collaborer avec leurs services juridiques pour établir leurs propres procédures et pratiques pour tout consentement nécessaire.

Depuis le début, Adobe Campaign se sert de certaines fonctionnalités pour gérer certains aspects du consentement. Grâce au processus de gestion des abonnements, les clients peuvent déterminer quels destinataires ont choisi quel type d&#39;abonnement, qu&#39;il s&#39;agisse de newsletters, de promotions quotidiennes ou hebdomadaires ou de tout autre type de programme marketing.

![](assets/privacy-consent-management.png)

Pour plus d&#39;informations sur la gestion du consentement, consultez les sections [À propos des abonnements](../../audiences/using/about-subscriptions.md) et [Prise en main des landing pages](../../channels/using/getting-started-with-landing-pages.md).

Outre les outils de gestion du consentement fournis par Adobe Campaign, vous pouvez suivre si un client s&#39;est opposé à la vente de ses informations personnelles. Voir [cette section](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Gestion des droits {#rights-management}

Adobe Campaign permet de gérer les droits assignés aux divers opérateurs Campaign par l&#39;intermédiaire de différents rôles préconfigurés ou personnalisés.

Vous pouvez ainsi gérer qui, dans votre entreprise, peut accéder à différents types de données. Par exemple, plusieurs spécialistes marketing peuvent couvrir des secteurs géographiques différents en n’ayant accès qu’aux données de leur secteur.

De même, cette fonctionnalité vous permet de configurer différentes fonctionnalités pour chaque utilisateur, telles que la limitation des expéditeurs autorisés à envoyer des diffusions. Il est même possible, en rapport avec la confidentialité, de déterminer qui peut modifier ou exporter des données.

![](assets/privacy-user-management.png)

Pour plus d&#39;informations sur la gestion des accès, consultez [cette section](../../administration/using/about-access-management.md).
