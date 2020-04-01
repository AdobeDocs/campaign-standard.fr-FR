---
title: Demande et configuration de Microsoft Dynamics 365 avec intégration Campaign Standard
description: Découvrez comment demander et configurer Microsoft Dynamics 365 avec l'intégration Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Demande de Microsoft Dynamics 365 avec intégration Campaign Standard

Pour configurer cette intégration, vous devez suivre les étapes ci-dessous.

Notez que cette intégration utilise un fournisseur tiers, Unifi.  En relation avec vos demandes d’assistance, Adobe peut être tenu de partager vos informations d’instance de Adobe Campaign  avec Unifi.

Veuillez suivre les détails de l&#39;organigramme et de l&#39;organigramme ci-dessous pour demander et configurer l&#39;intégration.

![](assets/provisioning-wf.png)

Détails de l’organigramme (mappage aux étapes ci-dessus) :

1. Vous devez déjà avoir Campaign Standard et Microsoft Dynamics 365 configurés, avec l&#39;accès administrateur au  implémenter cette intégration.

1. Lisez cet article, vérifiez les avis et les étapes de configuration.

1. Envoyez une demande de compte à adobe-support@unifisoftware.com; Unifi nécessite les informations suivantes lorsque vous demandez un compte :
* Prénom de l’utilisateur
* Nom d’utilisateur
* Adresse électronique de l’utilisateur
* Nom 
* Région (Amérique du Nord, EMEA ou APAC)
* Type d’utilisation :  Type de client (utilisateurs clients qui utiliseront leurs données de production dans cette intégration), ou Type de partenaire (consultants partenaires qui testent l’intégration pour mieux comprendre afin d’aider leurs clients Campaign) ou Type interne (utilisateurs internes d’Adobe qui testent l’intégration pour mieux comprendre la solution)
* Campaign Standard l’état des données (en commençant par une base de données propre ou en apportant des données existantes à l’intégration)
* Campaign ID de client (voir Configuration Campaign section d’intégration étape 3 pour obtenir votre ID de client)
* URL de l’instance Campaign

Temps de réponse attendu Unifi : 1 heure pendant les heures d&#39;ouverture normales aux États-Unis (de 9 h à 17 h, heure du Pacifique, du lundi au vendredi, hors jours fériés).

1. Suivez les étapes de post-configuration pour Microsoft Dynamics 365 et pour Campaign Standard.
De plus, envoyez un ticket au service à la clientèle d’Adobe (directement ou par l’intermédiaire de votre contact Adobe) pour que l’indicateur de fonction de connexion unique soit activé dans votre instance Campaign. Les partenaires doivent contacter leur représentant sandbox de partenaire Adobe, au lieu de contacter le service à la clientèle Adobe, pour activer l’indicateur de fonctionnalité.
Si vous avez des données existantes dans Campaign que vous prévoyez d’incorporer dans l’intégration, suivez les instructions de la section &quot;Données Campaign existantes&quot; et consultez votre contact technique Adobe avant de continuer.

1. Suivez les premières étapes de l&#39;intégration dans Unifi en accédant à Unifi, en cliquant sur les écrans d&#39;intégration, en saisissant les informations d&#39;identification des comptes Dynamics 365 et Campaign Standard et en informant Unifi une fois terminé.

1. Unifi demandera au client la configuration d’exclusion souhaitée et le mappage des attributs d’exclusion.

1. Le client indiquera la configuration d’exclusion sélectionnée et le mappage d’attributs d’exclusion.
Temps de réponse attendu Unifi : 1 jour ouvrable (du lundi au vendredi, hors jours fériés)

1. La configuration d&#39;Unifi implique la révision des mappages d&#39;objets hors champ, des , des tâches, etc. et apporter des modifications, si nécessaire.  Pour plus d’informations, consultez le Guide de l’utilisateur Unifi.
Cette étape implique de définir la fréquence d&#39;exécution des planifications Unifi
* Définissez la fréquence d&#39;exécution des planifications dans l&#39;écran Planifications dans Unifi ; toutefois, pour les planifications &quot;d’entrée&quot; et &quot;d’entrée&quot;, exécutez-les manuellement une fois avant de définir la fréquence de planification.
* Les fréquences de planification suivantes sont recommandées : Entrée (15 minutes), Sortie (15 minutes), Suppressions (une fois par jour), Exclusions (une fois par jour)

**Il est recommandé de travailler avec le service de conseil Unifi et/ou Adobe (contactez votre équipe de compte Adobe) lors de la configuration du service de conseil Unifi.**

Pour activer l&#39;intégration entre  Adobe Campaign Standard et Microsoft Dynamics 365, les clients doivent créer un compte utilisateur auprès d&#39;Unifi, un fournisseur tiers, comme décrit dans cette .   En tant qu&#39;utilisateur final du système Unifi, pour toute demande de données initiée par le client dans le système Unifi, le client doit contacter Unifi.

## Configuration de cette intégration

Trois systèmes doivent être configurés et configurés pour cette intégration :  Adobe Campaign Standard, Microsoft Dynamics 365 pour les ventes et Unifi. Les articles de configuration sont liés ci-dessous.

>[!CAUTION]
>
>Pour chaque système, ces étapes doivent être exécutées par un administrateur.
>
>Les étapes des articles ci-dessous vous guideront tout au long de la création d’intégrations/inscriptions impliquant l’attribution d’autorisations et/ou d’accès administrateur.  Il est de votre responsabilité de vous assurer que ces étapes sont conformes à vos  politiques de avant de les exécuter et de les exécuter avec précaution.

Dans  ADOBE CAMPAIGN, vous devez configurer l’accès à l’API et configurer une nouvelle intégration pour Unifi. Pour ce faire, reportez-vous à [cet article](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

Dans MICROSOFT DYNAMICS 365, vous devez créer une nouvelle inscription d’application et permettre à un utilisateur d’utiliser l’intégration.  Pour configurer Microsoft Dynamics 365 pour cette intégration, reportez-vous à [cet article](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Dans UNIFI, vous devez configurer l’intégration et configurer le mappage ou ajouter des attributs personnalisés. Pour configurer Unifi pour cette intégration, reportez-vous à [cet article](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md).

## Demande d&#39;assistance

Si vous rencontrez des problèmes, contactez le service clientèle d&#39;Unifi : [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net).

Temps de réponse attendu Unifi : 4 heures pendant les heures d&#39;ouverture normales aux États-Unis (de 9 h à 17 h, heure du Pacifique, du lundi au vendredi, hors jours fériés).

>[!CAUTION]
>
>Dans le cadre de votre demande d’assistance, Adobe peut être tenu de partager vos informations d’instance de Adobe Campaign  avec Unifi.