---
title: Configurer Adobe Developer pour l’intégration Microsoft Dynamics 365
description: Découvrez comment configurer Adobe Developer pour l’intégration Microsoft Dynamics 365
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: ab21b694-d05c-4ba4-b828-936803651b82
source-git-commit: c701043cbba22711de1ea7ddc5266e193d771e14
workflow-type: ht
source-wordcount: '602'
ht-degree: 100%

---

# Configurer Adobe Campaign Standard et Adobe Developer pour l&#39;intégration de Microsoft Dynamics 365

Cet article explique comment configurer Adobe Campaign Standard et Adobe I/O pour permettre à l’application d’intégration d’accéder aux données.

## Configurer Adobe Campaign Standard {#campaign-standard}

### Extensions de profil

Activez les « extensions de profil » dans Adobe Campaign Standard.   Cette activation est nécessaire pour que les champs personnalisés de la ressource Profil soient synchronisés depuis Microsoft Dynamics 365.   Les étapes pour les activer sont les suivantes :

1. Accédez à Paramètres -> Administration -> Développement -> Publication.
1. Cliquez sur « Préparer la publication » pour préparer une publication.
1. Une fois la préparation terminée, cochez la case « Créer l&#39;API Profiles &amp; Services Ext » et cliquez sur « Publier ».

## Configurer Adobe I/O {#adobe-io}

Adobe I/O vous permet d&#39;activer l&#39;accès de l’API à Adobe Campaign Standard et d&#39;autres produits Adobe. Cet article explique en détail comment configurer Adobe I/O afin de permettre à l&#39;intégration d&#39;Adobe Campaign Standard avec Microsoft Dynamics 365 d&#39;accéder à la synchronisation des données.

### Vue d’ensemble 

Avant d’exécuter la configuration préalable à l’intégration décrite dans cet article, il est supposé que vous avez déjà été approvisionné et que vous disposez d’un accès administrateur à l’instance Campaign Standard de votre organisation.  Si ce n’est pas le cas, vous devrez contacter l’assistance clientèle d’Adobe pour terminer l’approvisionnement de Campaign.

>[!CAUTION]
>
>Les étapes décrites ci-dessous doivent être exécutées par un administrateur.

### Configuration 

Vous devez créer un projet Adobe Developer et le configurer pour l’intégration.

#### Créer un projet

Pour ce faire, procédez comme suit :

1. Accédez à [Adobe Developer Console](https://console.adobe.io/home#) et sélectionnez votre ID d’organisation Adobe dans le menu déroulant situé dans la partie supérieure droite de l’écran.

1. Cliquez ensuite sur **[!UICONTROL Créer un projet]** sous **[!UICONTROL Démarrage rapide]**.

   ![](assets/adobeIO1.png)

1. Sous **[!UICONTROL Commencer votre projet]**, cliquez sur **[!UICONTROL Ajouter l’API]**.

   ![](assets/adobeIO2.png)

1. Sélectionnez Adobe Campaign et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/adobeIO3.png)

1. Dans l’écran suivant, vous aurez la possibilité de choisir un type d’authentification. Vous pouvez choisir OAuth serveur à serveur ou Compte de service (JWT). Notez que les informations d’identification du compte de service (JWT) ne sont plus recommandées pour les nouveaux projets et ont été abandonnées au profit des informations d’identification OAuth serveur à serveur plus récentes. Les instructions fournies dans ce guide s’appliquent uniquement à l’authentification OAuth serveur à serveur.

   ![](assets/adobeIO4.png)

1. Sur l’écran suivant, vous devez sélectionner les profils de produits à associer à ce projet. Sélectionnez le profil de produits contenu dans le titre : Identifiant du tenant de votre instance Campaign - [!UICONTROL Administrateurs]

   Exemple : Campaign Standard - votre-identifiantdutenant-campaign - Administrateurs

1. Cliquez sur **[!UICONTROL Enregistrer l’API configurée]**.

   ![](assets/adobeIO5.png)

1. Dans l’écran suivant, vous pouvez voir les détails de votre nouveau projet Adobe Developer. Cliquez sur **[!UICONTROL Ajouter au projet]** dans la partie supérieure gauche de l’écran et sélectionnez **API** dans la liste déroulante.

   ![](assets/adobeIO6.png)

1. Sur l’écran suivant, vous devez sélectionner l’API des événements I/O, puis cliquer sur **[!UICONTROL Suivant]**.

1. Sur l’écran suivant, cliquez sur **[!UICONTROL Enregistrer l’API configurée]**.  Vous serez redirigé vers l’écran des détails du projet.

1. Cliquez maintenant sur **[!UICONTROL Ajouter au projet]** dans la partie supérieure gauche de l’écran et sélectionnez **API** dans la liste déroulante, comme vous l’avez fait précédemment.

1. Sur l’écran suivant, vous devez sélectionner l’API de gestion I/O, puis cliquer sur **[!UICONTROL Suivant]**.

1. Sur l’écran suivant, cliquez sur **[!UICONTROL Enregistrer l’API configurée]**.

La configuration préalable à l’intégration dans Campaign est maintenant terminée.

**Rubriques connexes**

* [Configurer Adobe Developer pour l’intégration Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) est l’étape suivante de la configuration de l’intégration.
* [Présentation de l’application d’intégration en libre-service](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) comprend la liste complète des étapes permettant de rendre l’intégration opérationnelle.
* [Adobe Developer - Intégration de compte de service](https://developer.adobe.com/developer-console/docs/guides/#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuration de l’accès à l’API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Intégration de Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
* [Migration des informations d’identification de JWT vers OAuth serveur à serveur](../../integrating/using/d365-acs-self-service-app-migrate-credentials.md) contient les étapes de migration des informations d’identification de JWT vers OAuth serveur à serveur.
