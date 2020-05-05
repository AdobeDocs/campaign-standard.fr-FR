---
title: Confidentialité et consentement dans Adobe Campaign Standard
description: Cette section présente un aperçu de la gestion de la vie privée, des données personnelles et du consentement dans Adobe Campaign Standard, ainsi que les outils disponibles pour les gérer.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: faddcc870adcf9e71e50004a69a219b16ddc044f

---


# Privacy and Consent{#privacy-and-consent}

## Recommandations générales {#general-recommendations}

Adobe Campaign est un puissant outil de collecte et de traitement de très grandes quantités de données, y compris des informations personnelles et des données sensibles. C&#39;est pourquoi la confidentialité doit être gérée avec soin.

* Faire toujours un usage responsable et éthique des renseignements personnels.

* Ne pas envoyer de messages électroniques non sollicités, de notifications Push et de messages SMS (&quot;spam&quot;). Adobe croit fermement aux principes de permission marketing qui favorisent la valeur et la fidélité de la clientèle tout au long de sa vie. Par conséquent, il interdit strictement l’utilisation de Adobe Campaign pour envoyer des messages non sollicités.

### Règles relatives à la confidentialité {#privacy-regulations}

Pour gérer correctement la confidentialité et les données personnelles, travaillez dans le cadre des législations applicables à la ou aux régions où vous opérez. Ces règlements comprennent :
* [RGPD](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Règlement général européen sur la protection des données)
* [DPA](https://www.gov.uk/data-protection) (mise en oeuvre du RGPD au Royaume-Uni)
* [Directive européenne sur la protection de la vie privée et les communications électroniques](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (loi des États-Unis fixant les règles et les exigences pour les courriels commerciaux)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (loi thaïlandaise sur la protection des données personnelles)

>[!NOTE]
>
>Pour plus d&#39;informations sur la façon dont les RMMD, l&#39;ACCP et l&#39;APPE s&#39;appliquent à Adobe Campaign, consultez [cette page](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaign fait partie des solutions Adobe Experience Cloud. La manière dont la confidentialité est gérée dans Campaign obéit aux principes généraux d’Adobe Experience Cloud, tels que :

* **Quelles informations sont collectées lors de l’utilisation d’Adobe Experience Cloud ?**

   En tant que société utilisant les solutions Adobe Experience Cloud, vous choisissez les informations à collecter et à envoyer à votre compte Adobe Experience Cloud. Parmi les types d’informations pouvant être collectées, citons l’activité de navigation Web, les adresses IP, les informations d’emplacement des périphériques mobiles, les taux de réussite des campagnes, les articles achetés ou placés dans le panier, etc.

   >[!NOTE]
   >
   >Comme pour tous les produits Adobe, Campaign collecte des informations sur les utilisateurs d’applications et de sites Web. Pour plus d’informations à ce sujet, voir la Politique [de confidentialité](https://www.adobe.com/privacy/policy.html)Adobe.

* **Utilisation d’Adobe Experience Cloud pour la collecte d’informations**

   * Les solutions Adobe Experience Cloud utilisent des cookies et des technologies similaires, telles que des balises Web (également appelées balises ou pixels), pour vous permettre de collecter des informations. Pour en savoir plus sur les cookies et les fonctionnalités de suivi avec Adobe Campaign, consultez [cette section](#tracking-capabilities).
   * Vous pouvez également utiliser les technologies Adobe Experience Cloud dans vos applications mobiles. Pour plus d&#39;informations sur l&#39;envoi de diffusions mobiles avec Campaign, consultez [cette page](https://helpx.adobe.com/fr/campaign/kb/acs-mobile.html).

* **Les choix de confidentialité des utilisateurs concernant votre utilisation d’Adobe Experience Cloud**

   Adobe vous demande de fournir à vos clients des stratégies de confidentialité décrivant :

   * Vos pratiques de confidentialité en rapport avec Adobe Experience Cloud
   * Comment les utilisateurs peuvent-ils définir leurs préférences pour la collecte ou l’utilisation de leurs informations en relation avec Adobe Experience Cloud ?
   >[!NOTE]
   >
   >En ce qui concerne tous les produits Adobe, les utilisateurs de Campaign peuvent désactiver le partage des informations collectées à leur sujet par le biais d’applications et de sites Web. Pour en savoir plus sur ce sujet, consultez la FAQ [sur l’utilisation d’](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)Adobe Experience Cloud.

Pour plus d’informations sur la confidentialité d’Adobe Experience Cloud, voir [cette page](https://www.adobe.com/privacy/marketing-cloud.html).

## Données personnelles et personnes {#personal-data}

Lors de la gestion de la protection des renseignements personnels, il est important de définir quelles données doivent être traitées avec soin et par qui.
* **Les données** personnelles sont des informations qui peuvent identifier directement ou indirectement un individu vivant.
* **Les données** personnelles sensibles sont des renseignements relatifs à la race, aux vues politiques, aux croyances religieuses, aux antécédents criminels, aux renseignements génétiques, aux données sur la santé, aux préférences sexuelles, aux renseignements biométriques ainsi qu’à l’appartenance à une union commerciale.

Les [principales législations](#privacy-regulations) se réfèrent aux différentes entités qui gèrent les données comme suit :
* Un contrôleur **des** données est l&#39;autorité qui détermine les moyens et les objectifs de la collecte, de l&#39;utilisation et du partage des données personnelles.
* Un processeur **de** données est un individu ou une partie qui collecte, utilise ou partage des données personnelles selon les instructions du contrôleur de données.
* Une **personne** de données est toute personne vivante dont les données à caractère personnel sont collectées, utilisées ou partagées et qui peut être identifiée, directement ou indirectement, par référence à ces données à caractère personnel.

Par conséquent, en tant que société de collecte et de partage de données personnelles, vous êtes le contrôleur de données, vos clients sont les sujets de données et Adobe Campaign agit comme un processeur de données lors du traitement de leurs données personnelles tel que vous le souhaitez. Notez qu’en tant que contrôleur de données, il vous appartient de gérer les relations avec les objets de données, par exemple lors de la gestion des demandes [de](#privacy-requests)confidentialité.

Lors de l’intégration de Campaign à d’autres solutions Experience Cloud dans lesquelles des audiences peuvent être transférées d’un système à un autre, telles que le service [Destinations des](../../audiences/using/aep-about-audience-destinations-service.md)Audiences, [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager ou le service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)principal People, ou avec d’autres solutions telles que [Microsoft Dynamics 365, vous devez accorder un soin supplémentaire à la protection des données personnelles.](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)

## Acquisition de données {#data-acquisition}

Adobe Campaign vous permet de collecter des données, y compris des informations personnelles et sensibles. Il est donc essentiel que vous receviez et surveilliez le consentement de vos destinataires.

* Demandez toujours aux destinataires d&#39;accepter de recevoir des communications. Pour ce faire, continuez à honorer les demandes d’exclusion le plus rapidement possible et vérifiez le consentement par le biais d’un processus d’inclusion doublon. Pour plus d’informations à ce sujet, reportez-vous à la section [Gestion des options d’inclusion et d’exclusion dans Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) et [Configuration d’un processus](../../channels/using/setting-up-a-double-opt-in-process.md)d’inclusion doublon.
* N&#39;importez pas de listes frauduleuses et utilisez des pièges pour vérifier que votre fichier client n&#39;est pas utilisé frauduleusement. Pour plus d’informations à ce sujet, voir [Utilisation des pièges](../../sending/using/using-traps.md).
* Grâce à la gestion des droits et du consentement, vous pouvez suivre les préférences de vos destinataires et gérer qui au sein de votre organisation peut accéder aux données qui vous intéressent. Voir à ce propos [cette section](#consent).
* Faciliter et gérer les demandes de confidentialité de vos destinataires. Voir à ce propos [cette section](#privacy-requests).

## Gestion de la confidentialité {#privacy-management}

La gestion de la vie privée se rapporte à tous les processus et outils qui peuvent vous aider à vous conformer aux règlements sur la protection des renseignements personnels (RGPD, ACCP, etc.). Obtenez un aperçu de la gestion de la confidentialité sur [cette page](https://helpx.adobe.com/fr/campaign/kb/campaign-privacy-overview.html).

Adobe Campaign propose divers ensembles de fonctionnalités dédiées à la gestion de la confidentialité :
* Gestion du consentement, rétention des données et rôles utilisateur. Reportez-vous à [cette section](#consent).
* Demande de confidentialité (Droit d&#39;accès et Droit d&#39;être oublié). Reportez-vous à [cette section](#privacy-requests).
* Exclusion pour la vente de renseignements personnels (selon l&#39;ACFPC). Reportez-vous à [cette section](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#ccpa).

Les principales fonctionnalités de confidentialité de Campaign et un exemple des personnes impliquées sont présentés dans [cette section](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Consentement, conservation des données et rôles {#consent}

À l&#39;origine, Adobe Campaign offre des fonctions importantes qui sont essentielles à la vie privée :

* **Gestion des** consentements : Grâce au processus de gestion des abonnements, vous pouvez gérer vos préférences de destinataires et déterminer quels destinataires ont choisi le type d&#39;abonnement. Pour en savoir plus sur ce sujet, voir [Abonnements](../../audiences/using/about-subscriptions.md) et [Landings page](../../channels/using/getting-started-with-landing-pages.md).
* **Conservation** des données : Toutes les tables de journalisation standard intégrées comportent des périodes de rétention prédéfinies, limitant généralement leur enregistrement de données à 6 mois ou moins. Des périodes de rétention supplémentaires peuvent être définies avec des workflows. Pour plus d’informations à ce sujet, contactez les consultants ou les administrateurs techniques d’Adobe.
* **Rights Management**: Adobe Campaign vous permet de gérer les droits attribués aux différents opérateurs Campaign par le biais de différents rôles prédéfinis ou personnalisés. Cela vous permet de gérer qui dans votre société peut accéder à différents types de données, les modifier ou les exporter. For more on this, see [About access management](../../administration/using/about-access-management.md).

Pour en savoir plus sur ces fonctionnalités et sur la façon de les gérer en Adobe Campaign, consultez [cette page](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent).

### Privacy requests {#privacy-requests}

Adobe Campaign fournit des fonctionnalités supplémentaires pour vous aider à vous préparer en tant que contrôleur de données pour certaines demandes de confidentialité :

* Le **droit d&#39;accès** est le droit pour la personne concernée d&#39;obtenir de la part du contrôleur de données la confirmation que des données à caractère personnel les concernant sont traitées, où et pourquoi.

* Le **droit à l&#39;oubli** (demande de suppression) autorise le contrôleur de données à effacer ses données personnelles.

>[!NOTE]
>
>Cet ensemble d&#39;outils vous aide à respecter vos exigences en matière de confidentialité pour les RGMD, les ACCP et les PDPA. Pour en savoir plus sur ces différentes réglementations, consultez [cette page](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

Les demandes **d’accès** et de **suppression** sont présentées sur [cette page](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess). Les étapes de mise en oeuvre pour créer ces requêtes sont détaillées sur [cette page](https://helpx.adobe.com/fr/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Des didacticiels sont également disponibles [ici](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Fonctionnalités de suivi {#tracking-capabilities}

Grâce à ses fonctionnalités de suivi, Adobe Campaign vous permet de suivre le comportement de vos destinataires de diffusion à l’aide de cookies de session et de cookies permanents. For more on tracking, see [this page](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Des règlements tels que le Règlement général sur la protection des données (RGPD) stipulent que les sociétés exigent l&#39;accord des utilisateurs du site Web avant d&#39;installer des cookies. Vous devez informer les utilisateurs que vos sites sont équipés d’outils de suivi Web par le biais d’une demande d’autorisation.

Vous pouvez également ajouter des liens [](../../designing/using/links.md#about-tracked-urls) suivis dans vos messages afin de mesurer l’impact de votre comportement de diffusion et de destinataire dans le rapport intégré des indicateurs [de](../../reporting/using/tracking-indicators.md) suivi ou créer vos propres rapports [](../../reporting/using/about-dynamic-reports.md)dédiés.
