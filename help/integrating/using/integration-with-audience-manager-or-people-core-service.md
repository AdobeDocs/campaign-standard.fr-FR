---
title: Mise en service et configuration de l'intégration avec Audience Manager ou People core service
description: Découvrez comment configurer l'intégration d'Audience Manager/de People core service pour commencer à partager des audiences ou des segments avec les différentes solutions d'Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: 04d0fe26-a8cc-49ae-aaa9-b470169068ee
source-git-commit: 60386a9e6e424d76b1de0f2ecbeab48dd06fb354
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 98%

---

# Approvisionnement et configuration de l&#39;intégration avec Audience Manager ou People core service{#integration-with-audience-manager-or-people-core-service}

La mise en service et la configuration d&#39;Audience Manager et de People core dans Adobe Campaign se fait en deux étapes : l&#39;[envoi d&#39;une demande à Adobe](#submitting-request-to-adobe), puis la [configuration de l&#39;intégration dans Adobe Campaign](#configuring-the-integration-in-adobe-campaign).

## Envoi d&#39;une demande à Adobe        {#submitting-request-to-adobe}

L&#39;intégration d&#39;Audience Manager ou de People core service permet d&#39;importer et exporter des audiences ou des segments dans Adobe Campaign.

Cette intégration doit d’abord être configurée. Pour demander la configuration de cette intégration, contactez le support Adobe avec les informations suivantes :

<table> 
 <tbody> 
  <tr> 
   <td> <strong>Type de demande :</strong><br /> </td> 
   <td> Configuration de l'intégration AAM/People core service-Campaign </td> 
  </tr> 
  <tr> 
   <td> <strong>Nom de l'organisation :</strong><br /> </td> 
   <td> Nom de votre organisation </td> 
  </tr> 
  <tr> 
   <td> <strong>Identifiant de l’organisation IMS</strong><br /> </td> 
   <td> L’identifiant de votre organisation. <br> Pour trouver l’identifiant de votre organisation, reportez-vous à <a href="https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=fr">cette page</a>.</td> 
  </tr> 
  <tr> 
   <td> <strong>Environnement :</strong><br /> </td> 
   <td> Exemple : Production </td> 
  </tr> 
  <tr> 
   <td> <strong>AAM ou People Service</strong><br /> </td> 
   <td> Exemple : Adobe Audience Manager. Veillez à indiquer à l'équipe de mise en service si vous possédez ou non la licence d'Audience Manager.</td> 
  </tr> 
  <tr> 
   <td> <strong>Declared ID ou Visitor ID</strong><br /> </td> 
   <td> Exemple : Declared ID </td> 
  </tr> 
  <tr> 
   <td> <strong>Informations supplémentaires</strong><br /> </td> 
   <td> Informations ou commentaires utiles que vous souhaitez communiquer </td> 
  </tr> 
 </tbody> 
</table>

## Configuration de l&#39;intégration dans Adobe Campaign   {#configuring-the-integration-in-adobe-campaign}

Après l&#39;envoi de cette demande, Adobe approvisionne l&#39;intégration et vous contacte pour vous fournir des informations afin de terminer la configuration :

* [Étape 1 : Configuration ou vérification des comptes externes dans Adobe Campaign](#step-1--configure-or-check-the-external-accounts-in-adobe-campaign)
* [Étape 2 : Configuration des sources de données      ](#step-2--configure-the-data-sources)
* [Étape 3 : Configuration du serveur de tracking Campaign](#step-3--configure-campaign-tracking-server)
* [Étape 4 : Configuration du service d&#39;identification des visiteurs](#step-4--configure-the-visitor-id-service)

### Étape 1 : Configuration ou vérification des comptes externes dans Adobe Campaign           {#step-1--configure-or-check-the-external-accounts-in-adobe-campaign}

Il nous faut tout d&#39;abord configurer ou vérifier les comptes externes dans Adobe Campaign Ces comptes doivent avoir été configurés par Adobe. De plus, les informations nécessaires ont dû vous être communiquées.

Pour ce faire :

1. Dans le menu avancé, sélectionnez **Application > Paramétrage de l&#39;application > Comptes externes**.

   Sélectionnez l&#39;un des comptes externes suivants disponibles pour cette intégration :

   ![](assets/integration_aam_1.png)

1. Saisissez le **[!UICONTROL serveur du récepteur]** au format suivant
1. Saisissez l&#39;**[!UICONTROL ID de clé d&#39;accès AWS]**, la **[!UICONTROL clé d&#39;accès secrète]** et la **[!UICONTROL région AWS]**.

Vos comptes externes sont à présent configurés pour cette intégration.

### Étape 2 : Configuration des sources de données        {#step-2--configure-the-data-sources}

Les deux sources de données suivantes ont été créées dans Audience Manager : Adobe Campaign (MID) et Adobe Campaign (DeclaredId). En même temps, ces deux sources de données sont disponibles dans Adobe Campaign :

* **[!UICONTROL Destinataire - Id Visiteur (Defaultdatasources)]** : il s&#39;agit d&#39;une source de données d&#39;usine configurée par défaut pour Id Visiteur. Les segments créés à partir de Campaign feront partie de cette source de données.
* Source de données **ID déclaré** : cette source de données doit être créée et mappée avec la définition de source de données **[!UICONTROL DeclaredId]** depuis Audience Manager.

Dans le cas de plusieurs sites web avec des domaines différents, Adobe Campaign ne prend pas en charge la réconciliation basée sur ECID.

Pour configurer la source de données **[!UICONTROL Destinataire - Id Visiteur (Defaultdatasources)]** :

1. Dans **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** > **[!UICONTROL Sources de données partagées]**, sélectionnez **[!UICONTROL Destinataire - Id Visiteur (Defaultdatasources)]**.

   ![](assets/integration_aam_2.png)

1. Choisissez **[!UICONTROL Adobe Campaign]** dans le menu déroulant **[!UICONTROL Source de données/alias]**.
1. Saisissez le **[!UICONTROL AAM Destination ID]** fourni par Adobe.

   ![](assets/integration_aam_3.png)

1. Dans la catégorie **[!UICONTROL Processus de réconciliation]**, nous vous conseillons de ne pas modifier les critères de réconciliation et de toujours utiliser l&#39;**[!UICONTROL identifiant du visiteur]**.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

Pour créer la source de données **[!UICONTROL ID déclaré]** :

1. Dans **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** > **[!UICONTROL Sources de données partagées]**, cliquez sur le bouton **[!UICONTROL Créer]**.
1. Modifiez le **[!UICONTROL libellé]** de votre source de données.
1. Dans le menu déroulant **[!UICONTROL Source de données/alias]**, choisissez la source de données correspondant à **[!UICONTROL DeclaredID]** depuis Audience Manager.
1. Configurez votre source de données en saisissant les **[!UICONTROL sources de données/alias]** et le **[!UICONTROL AAM Destination ID]** fournis par Adobe.
1. Définissez le **[!UICONTROL processus de réconciliation]** selon vos besoins.
1. Cliquez sur **[!UICONTROL Enregistrer]**.

>[!NOTE]
>
>Le champ **[!UICONTROL AAM Destination ID]** n&#39;est pas obligatoire si vous configurez la data source partagée pour l&#39;[intégration des Triggers Campaign](../../integrating/using/configuring-triggers-in-experience-cloud.md). **[!UICONTROL La priorité]** n&#39;est nécessaire que lors de la configuration de l&#39;intégration des Triggers Campaign. La priorité détermine quelle source de données sera configurée en premier. Il peut s&#39;agit d&#39;un nombre tel que 1 ou 100. Plus la priorité est élevée, plus la préférence est importante lors de la réconciliation.

### Étape 3 : Configuration du serveur de tracking Campaign        {#step-3--configure-campaign-tracking-server}

Pour la configuration de l&#39;intégration avec People Core service ou Audience Manager, il faut également configurer le serveur de tracking Campaign.

Pour permettre aux audiences partagées de fonctionner avec les identifiants visiteur, le domaine du serveur de tracking doit être un sous-domaine de l’URL sur laquelle l’utilisateur ou l’utilisatrice a cliqué ou du site Web principal.

>[!IMPORTANT]
>
> Vous devez vérifier que le serveur de tracking Campaign est enregistré sur le domaine (CNAME). Vous trouverez des informations supplémentaires sur la configuration des noms de domaine dans [cet article](https://helpx.adobe.com/fr/campaign/kb/domain-name-delegation.html).

### Étape 4 : Configuration du service d&#39;identification des visiteurs {#step-4--configure-the-visitor-id-service}

Si le service des identifiants visiteurs (Visitor ID) n’a jamais été configuré dans vos propriétés/sites Web, reportez-vous à ce [document](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-aam-analytics.html?lang=fr) ou cette [vidéo](https://helpx.adobe.com/fr/marketing-cloud/how-to/email-marketing.html#step-two) pour découvrir comment configurer ce service.

Synchronisez les identifiants client avec l’identifiant déclaré à l’aide de la fonction `setCustomerID` dans le service ID Experience Cloud avec le code d’intégration : `AdobeCampaignID`. Le `AdobeCampaignID` doit correspondre à la valeur de la clé de réconciliation définie dans la source de données destinataires configurée dans [Étape 2 : configuration des sources de données](#step-2--configure-the-data-sources).

La configuration et la mise en service sont terminées. L’intégration peut être maintenant utilisée pour importer et exporter des audiences ou des segments.
