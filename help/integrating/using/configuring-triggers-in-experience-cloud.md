---
title: Configuration des Triggers dans Experience Cloud
description: 'Découvrez comment configurer l''intégration des Triggers Adobe Experience Cloud pour commencer à envoyer des diffusions personnalisées à vos clients selon leurs comportements précédents. '
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 50e9fb7a-b28a-40b0-9f2c-3673c792529a
source-git-commit: 5a7e48da3d62b186f96cd7451fb5a7b2cf94e09c
workflow-type: ht
source-wordcount: '0'
ht-degree: 100%

---

# Configuration des Triggers dans Experience Cloud{#configuring-triggers-in-experience-cloud}

## Activation de la fonctionnalité {#activating-the-functionality}

Cette fonctionnalité doit être activée dans Adobe Campaign par Adobe. Contactez votre chargé de compte Adobe ou votre partenaire de services professionnels.

L&#39;équipe Adobe aura besoin des informations suivantes pour activer les déclencheurs :

* Nom de la société Experience Cloud
* Identifiant de l’organisation
* Identifiant de société Analytics (peut être identique au nom de la société Experience Cloud)

## Configuration des solutions et services      {#configuring-solutions-and-services}

Afin de pouvoir utiliser cette fonction, vous devez avoir accès aux solutions/core services suivants :

* Adobe Campaign
* Adobe Analytics Ultimate, Premium, Foundation, OD, Select, Prime, Applications mobiles, Select ou Standard.
* Core Service Triggers Experience Cloud

   ![](assets/trigger_uc_prereq_1.png)

* Core Service DTM Experience Cloud

   ![](assets/trigger_uc_prereq_2.png)

* Identifiant du visiteur Experience Cloud et Core Service People Experience Cloud

   ![](assets/trigger_uc_prereq_3.png)

Il vous faudra également un site web opérationnel.

![](assets/trigger_uc_prereq_4.png)

>[!CAUTION]
>
>La configuration de sous-domaine est également un élément clé de la délivrabilité. Assurez-vous que les emails Adobe Campaign sont envoyés à partir du même domaine que celui utilisé par le site web.

Pour suivre ces cas pratiques, vous devez configurer [Experience Cloud DTM Core Service](#configuring-experience-cloud-dtm-core-service), [Experience Cloud People Core Service](#configuring-experience-cloud-people-core-service) et [Campaign](#configuring-triggers-and-aliases-in-campaign).

### Configurer Experience Cloud DTM Core Service  {#configuring-experience-cloud-dtm-core-service}

1. Dans le DTM (Dynamic Tag Management) Core Service DTM Experience Cloud, activez l&#39;Identifiant Experience Cloud et Adobe Analytics pour les pages de votre site web.

   ![](assets/trigger_uc_conf_1.png)

1. La réconciliation des identifiants entre le site Web, Adobe Analytics et Adobe Campaign requiert l&#39;utilisation d&#39;alias. Créez un alias « visitorid », par exemple.

   ![](assets/trigger_uc_conf_2.png)

### Configurer Experience Cloud People Core Service  {#configuring-experience-cloud-people-core-service}

L&#39;alias référencé précédemment dans DTM doit être créé dans le Core Service People Experience Cloud via un Attribut Client. Veillez à en créer un nouveau et à référencer le même alias DTM dans le code d&#39;intégration (« visitorid », par exemple).

![](assets/trigger_uc_conf_3.png)

>[!NOTE]
>
>Cet Attribut client sera utilisé dans la Data source dans Adobe Campaign (étape suivante).

### Configurer les déclencheurs et les alias dans Campaign    {#configuring-triggers-and-aliases-in-campaign}

1. Vérifiez que les **[!UICONTROL déclencheurs Experience Cloud]** sont visibles sur votre instance Adobe Campaign Standard. Si ce n’est pas le cas, contactez les administrateurs Adobe Campaign.

   ![](assets/remarketing_1.png)

1. Les alias permettent la réconciliation d&#39;un contact d&#39;Analytics avec un profil de Campaign. Vous devez faire correspondre les alias définis dans le service Experience Cloud ID avec une source de données partagée de Campaign. Vous devez configurer la résolution des alias dans Adobe Campaign via une source de données (**[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l’application]** > **[!UICONTROL Source de données partagées]**). Veillez à sélectionner la bonne source de données dans le menu déroulant **[!UICONTROL Source de données/alias]**, qui est mappée avec la même source de données Attribut client créée à l&#39;étape précédente.

   ![](assets/trigger_uc_conf_5.png)

   >[!NOTE]
   >
   >Vous pouvez réconcilier vos déclencheurs pour les utilisateurs anonymes et enregistrés. Pour les utilisateurs anonymes, le profil doit exister dans Adobe Campaign et un email a déjà été envoyé à l&#39;utilisateur. Pour cela, la configuration d&#39;identifiant de visiteur suffit. Toutefois, si vous souhaitez réconcilier des déclencheurs pour les utilisateurs enregistrés, vous devez paramétrer la source de données ID déclaré. Pour en savoir plus, consultez [Configuration de la source de données](../../integrating/using/integration-with-audience-manager-or-people-core-service.md#step-2--configure-the-data-sources).

## Création d&#39;un trigger dans l&#39;interface d&#39;Experience Cloud  {#creating-a-trigger-in-the-experience-cloud-interface}

Un déclencheur Adobe Experience Cloud doit être créé pour pouvoir l&#39;utiliser dans Campaign.

Créez un déclencheur dans Experience Cloud et assurez-vous de sélectionner la suite de rapports utilisée sur votre site Web. Veillez à choisir les bonnes dimensions pour que le déclencheur fonctionne.

Consultez la [documentation Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/activation/triggers.html?lang=fr) et regardez cette [vidéo](https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html#step-two).

## Bonnes pratiques et limites de Triggers {#triggers-best-practices-and-limitations}

Voici la liste des bonnes pratiques et des limites qui s’appliquent à l’utilisation de l’intégration Campaign - Triggers :

* Si vous disposez de plusieurs instances Campaign Standard, toutes ces instances peuvent recevoir des Triggers tant qu’elles sont dans la même organisation. Analytics doit lui aussi être dans la même organisation.
* Vous ne pouvez pas créer de déclencheur dans le Trigger Core Service à l&#39;aide d&#39;événements provenant de deux suites de rapports différentes.
* Les déclencheurs se basent sur les messages transactionnels. Les messages transactionnels sont utilisés dès que vous devez envoyer un message très rapidement. Vous ne pouvez pas mettre en liste d&#39;attente des messages transactionnels et les faire s&#39;exécuter en boucle dans un lot.
* Par nature, les déclencheurs ne sont pas déterministes. Lorsqu&#39;un déclencheur est généré, il envoie tous les alias associés au cookie. Par conséquent, en cas de navigateurs partagés comme dans les bornes de magasins, les bibliothèques, les cybercafés, ou sur les appareils partagés au domicile (mari et femme se connectant sur un même appareil), il n&#39;est pas possible de se mapper au bon ID. Tous les ID utilisés pour se connecter au navigateur sont envoyés à Campaign, qui transmet un message en fonction de la première réconciliation. S&#39;il existe plusieurs « ID d&#39;emails » éligibles pour la réconciliation, Campaign n&#39;envoie pas d&#39;email. Campaign n&#39;a aucun moyen de déterminer le bon ID d&#39;email, sauf s&#39;il est récupéré et communiqué par Analytics.
* Vous ne pouvez pas stocker de contenu de la payload dans Campaign. Les déclencheurs ne peuvent pas être utilisés pour mettre à jour les données d&#39;un profil.
* Les attributs du client ne sont pas pris en charge dans Triggers (ce qui signifie que seules les données d&#39;une suite de rapports peuvent être utilisées pour définir les règles métier Triggers).
* Les collections de collections ne sont pas prises en charge dans Campaign.

>[!CAUTION]
>
>Votre site Web doit s&#39;exécuter sur le même domaine que le serveur Adobe Campaign. Dans le cas contraire, vous ne pouvez pas utiliser d&#39;ID de visiteur pour réconcilier et joindre les utilisateurs visitant le site Web anonymement.
