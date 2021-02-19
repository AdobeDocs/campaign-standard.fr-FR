---
title: Configuration de l’intégration d’Adobe IO pour Microsoft Dynamics 365
description: Découvrez comment configurer l’intégration d’Adobe IO pour Microsoft Dynamics 365.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 100%

---


# Configuration d&#39;Adobe Campaign Standard et d’Adobe I/O pour l&#39;intégration de Microsoft Dynamics 365

Cet article explique comment configurer Adobe Campaign Standard et Adobe I/O pour permettre à l&#39;application d&#39;intégration d&#39;accéder aux données.

## Configurer Adobe Campaign Standard {#campaign-standard}

### Extensions de profil

Activez les « extensions de profil » dans Adobe Campaign Standard.   Cette activation est nécessaire pour que les champs personnalisés de la ressource Profil soient synchronisés à partir de Microsoft Dynamics 365.   Les étapes pour les activer sont les suivantes :

1. Accédez à Paramètres -> Administration -> Développement -> Publication.
1. Cliquez sur « Préparer la publication » pour préparer une publication.
1. Une fois la préparation terminée, cochez la case « Créer l&#39;API Profiles &amp; Services Ext » et cliquez sur « Publier ».

## Configurer Adobe I/O {#adobe-io}

Adobe I/O vous permet d&#39;activer l’accès à l’API pour Adobe Campaign Standard et d’autres produits Adobe.   Cet article explique en détail comment configurer Adobe I/O afin de permettre à l&#39;intégration Adobe Campaign Standard avec Microsoft Dynamics 365 d&#39;accéder à la synchronisation des données.

### Vue d’ensemble 

Avant d’exécuter la configuration préalable à l’intégration décrite dans cet article, il est supposé que vous avez déjà été approvisionné et que vous disposez d’un accès administrateur à l’instance Campaign Standard de votre organisation.  Si ce n’est pas le cas, vous devrez contacter l’assistance clientèle d’Adobe pour terminer l’approvisionnement de Campaign.

>[!CAUTION]
>
>Les étapes décrites ci-dessous doivent être exécutées par un administrateur.

### Configuration 

Vous devez créer un projet Adobe IO et le configurer pour l’intégration.

#### Créer un projet

Pour ce faire, procédez comme suit :

1. Accédez à la [console d’Adobe IO](https://console.adobe.io/home#) et sélectionnez votre ID d’organisation Adobe IMS dans le menu déroulant de la partie supérieure droite de l’écran.

1. Cliquez ensuite sur **[!UICONTROL Créer un projet]** sous **[!UICONTROL Démarrage rapide]**.

   ![](assets/adobeIO1.png)

1. Sous **[!UICONTROL Commencer votre projet]**, cliquez sur **[!UICONTROL Ajouter l’API]**.

   ![](assets/adobeIO2.png)

1. Sélectionnez l’API Adobe Campaign (vous devrez peut-être faire défiler l’écran vers le bas) et cliquez sur **[!UICONTROL Suivant]**.

   ![](assets/adobeIO3.png)

1. Sur l’écran suivant, vous aurez la possibilité de télécharger votre propre clé publique ou de laisser Adobe IO générer la paire de clés pour vous. Ces instructions suivront la deuxième option. Si vous décidez de laisser Adobe IO générer la paire de clés, cliquez sur l’option 1 ; cliquez ensuite sur le bouton **[!UICONTROL Générer la paire de clés]**.

   ![](assets/adobeIO4.png)

1. Sur l’écran suivant, vous serez invité à attribuer un nom et à sélectionner l’emplacement de téléchargement du fichier zip de la paire de clés.

Une fois le fichier téléchargé, vous pouvez le décompresser pour afficher les clés publique et privée. Adobe IO aura déjà appliqué la clé publique à votre projet Adobe IO. Vous devrez conserver votre clé privée pour plus tard ; elle sera utilisée lors de la configuration préalable à l’intégration de l’outil d’intégration.

1. Cliquez sur **[!UICONTROL Suivant]** pour continuer

   ![](assets/adobeIO5.png)

1. Sur l’écran suivant, vous devez sélectionner les profils de produits à associer à ce projet. Sélectionnez le profil de produits contenu dans le titre : Identifiant du tenant de votre instance Campaign - [!UICONTROL Administrateurs]

   Exemple : Campaign Standard - votre-identifiantdutenant-campaign - Administrateurs

1. Cliquez sur **[!UICONTROL Enregistrer l’API configurée]**.

   ![](assets/adobeIO6.png)

1. Dans l’écran suivant, vous pouvez voir les détails de votre nouveau projet Adobe IO. Cliquez sur **[!UICONTROL Ajouter au projet]** dans la partie supérieure gauche de l’écran et sélectionnez **API** dans la liste déroulante.

   ![](assets/adobeIO7.png)

1. Sur l’écran suivant, vous devez sélectionner l’API des événements I/O, puis cliquer sur **[!UICONTROL Suivant]**.

1. Sur l’écran suivant, cliquez sur **[!UICONTROL Enregistrer l’API configurée]**.  Vous serez redirigé vers l’écran des détails du projet.

1. Cliquez maintenant sur **[!UICONTROL Ajouter au projet]** dans la partie supérieure gauche de l’écran et sélectionnez **API** dans la liste déroulante, comme vous l’avez fait précédemment.

1. Sur l’écran suivant, vous devez sélectionner l’API de gestion I/O, puis cliquer sur **[!UICONTROL Suivant]**.

1. Sur l’écran suivant, cliquez sur **[!UICONTROL Enregistrer l’API configurée]**.

La configuration préalable à l’intégration dans Campaign est maintenant terminée.

**Rubriques connexes**

* [Configurer Adobe IO pour l&#39;intégration Microsoft Dynamics 365](../../integrating/using/d365-acs-configure-adobe-io.md) est l&#39;étape suivante de la configuration de l&#39;intégration
* [Présentation de l&#39;application d&#39;intégration en libre-service](../../integrating/using/d365-acs-self-service-app-quick-start-guide.md) comprend la liste complète des étapes permettant d&#39;activer et de lancer l&#39;intégration.


* [Adobe IO - Intégration de compte de service](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)
* [Campaign Standard - Configuration de l’accès à l’API](../../api/using/setting-up-api-access.md)
* [Campaign Standard - Intégration de Dynamics 365](../../integrating/using/d365-acs-configure-d365.md)
