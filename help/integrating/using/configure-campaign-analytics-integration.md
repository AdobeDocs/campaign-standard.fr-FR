---
title: Configurer l'intégration Campaign-Analytics
description: Découvrez comment configurer l'intégration d'Adobe Analytics pour commencer à mesurer les performances de vos diffusions email.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a6748b4b-36c5-4961-a599-ace73a8504cc
TQID: 'https://experienceleague.adobe.com/bt1FQbafwhEuRao-YFhynO-ecg5EaiUDskSFvxuFv-k'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: ca3c1dd6-bdd2-41a9-bc5a-e35f5cca9e63
    internal-label: Application settings
  - id: c3bf7e1e-1db5-4c72-9293-e2f0b1ab73d0
    internal-label: Triggers
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 100%
---
# Configurer l&#39;intégration Campaign-Analytics{#configure-campaign-analytics-integration}

Cette intégration vous permet de partager vos données de KPI (Key Performance Indicator) directement d&#39;Adobe Campaign vers Adobe Analytics Standard ou Premium.

Pour commencer l&#39;intégration entre Adobe Campaign Standard et Adobe Analytics, vous devez d&#39;abord configurer le compte externe associé à Adobe Analytics.

Les comptes externes et les workflows techniques peuvent uniquement être gérés par l&#39;administrateur fonctionnel de la plateforme.

1. Dans le menu avancé, via le logo Adobe Campaign, sélectionnez **[!UICONTROL Administration > Paramétrage de l&#39;application > Comptes externes]**.
1. Sélectionnez le compte externe **[!UICONTROL Partager les KPI avec Adobe Analytics]**.

   ![](assets/analytics_2.png)

1. Renseignez le **[!UICONTROL Nom d&#39;utilisateur du service Web]** et le **[!UICONTROL Secret partagé du service Web]** dans le champ **[!UICONTROL Connexion]**.

   Ces paramètres sont accessibles dans Analytics en sélectionnant **[!UICONTROL Admin > Paramètres de la société > Services Web]**.

   ![](assets/analytics_1.png)

1. Cliquez sur le bouton **[!UICONTROL Actualiser les suites de rapports]**.
1. Dans la liste déroulante **[!UICONTROL Suite de rapports par défaut Analytics]**, sélectionnez la suite de rapports Adobe Analytics que vous souhaitez enrichir avec les données Adobe Campaign.

   Votre compte externe est maintenant prêt et associé à Adobe Analytics. Vous pouvez le désactiver à tout moment en cochant la case **[!UICONTROL Activé]**.

   ![](assets/analytics.png)

Le workflow technique **[!UICONTROL Partager les KPI avec Adobe Analytics]** va maintenant être lancé automatiquement. Il est consultable depuis le menu avancé en sélectionnant **[!UICONTROL Administration > Paramétrage de l&#39;application > Workflow]**. Ce workflow technique peut conserver jusqu&#39;à 6 mois de broadlogs. Notez que ce workflow est incrémentiel et transmet les données du jour précédent.

![](assets/analytics_3.png)

Vos données sont à présent disponibles dans Adobe Analytics.

**Rubriques connexes :**

* [Comptes externes](../../administration/using/external-accounts.md)
* [Workflows techniques](../../administration/using/technical-workflows.md)
* Vidéo [Partager les KPI pour le reporting intégré de Campaign](https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html)
