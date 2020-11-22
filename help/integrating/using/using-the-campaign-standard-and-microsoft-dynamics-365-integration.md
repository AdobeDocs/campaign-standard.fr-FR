---
solution: Campaign Standard
product: campaign
title: Utilisation de l’intégration de Microsoft Dynamics 365
description: Découvrez comment utiliser l’intégration de Microsoft Dynamics 365 avec Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 100%

---


# Utilisation de l’intégration de Microsoft Dynamics 365

Cette intégration exécute plusieurs traitements :

* **Entrée** :

   * import des **contacts** de Dynamics 365 dans Campaign.

   * **Entités personnalisées** : import des tables personnalisées de Dynamics 365 dans Campaign. En savoir plus dans [cette section](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Sortie** : import des événements de marketing email d’ACS dans D365 (envoi d’email, ouverture, clic, bounce).

* **Opt-out** : statut de désinscription de la synchronisation bidirectionnelle (par exemple, liste bloquée)

Vous trouverez plus de détails sur les flux de données [dans cette section](#data-flows).

## Expérience utilisateur Adobe Campaign Standard

Lorsqu’un contact est créé ou modifié (ou supprimé, s’il est activé) dans Dynamics 365, il est envoyé à Campaign.  Ces contacts seront visibles dans l’écran Profils de Campaign et peuvent être ciblés dans les campagnes marketing.  Voir l’écran Profils ci-dessous.

![](assets/MSdynamicsACS-usage1.png)

Lorsqu’un attribut de désinscription est modifié dans Campaign, la modification est prise en compte dans Dynamics 365 si vous avez sélectionné la configuration de Campaign vers Dynamics 365 ou bidirectionnelle et si cet attribut est correctement mappé.

## Expérience utilisateur Microsoft Dynamics 365

Pour la sortie, les événements de marketing email suivants sont envoyés de Campaign vers Dynamics 365 et affichés dans la vue de chronologie Dynamics 365 sous forme d’activités personnalisées :

*  Envoi d’email Adobe Campaign

*  Ouverture d’email Adobe Campaign

*  Clic sur une URL d’email Adobe Campaign

*  Email bounce Adobe Campaign

Pour voir la chronologie d’un contact, accédez à votre liste de contacts en cliquant sur Concentrateur des ventes dans le menu déroulant Dynamics 365.  Cliquez ensuite sur Contacts dans la barre de menu de gauche et sélectionnez un contact.

>[!NOTE]
>
>L’application Adobe Campaign pour Dynamics 365 dans AppSource devra être installée dans votre instance Dynamics 365 afin d’afficher ces événements.

Vous trouverez ci-dessous un instantané de l’écran Contact pour « Utilisateur Dynamics ».  Dans la vue de la chronologie, vous remarquerez que l’utilisateur Dynamics a reçu un email associé au nom Campaign « 2019LoyaltyCamp » et au nom de diffusion « DM190 ». L’utilisateur Dynamics a ouvert l’email et a également cliqué sur une URL contenue dans celui-ci ces deux actions ont créé des événements également présentés ci-dessous.  Si vous regardez dans le coin droit, vous verrez la carte de l’assistant de relations (AR) ; il contient actuellement une tâche de suivi de l’URL sur laquelle l’utilisateur a cliqué.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Reportez au gros plan ci-dessous de la vue de chronologie pour l’utilisateur Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Vous trouverez ci-dessous un gros plan de la carte de l’assistant de relations (AR). L’application AppSource contient un workflow qui recherche un événement de clic sur l’URL de l’email Adobe.  Lorsque cet événement se produit, il crée une tâche et définit une date d’échéance.  Cela permet à la tâche de s’afficher dans la carte de l’AR, ce qui lui donne une visibilité supplémentaire.  Il existe un workflow similaire pour les événements Email bounce d’Adobe, qui ajoute une tâche pour réconcilier l’adresse email non valide.  Ces workflows peuvent être désactivés dans la solution.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Si vous cliquez sur le sujet de l’événement d’envoi, vous verrez un formulaire similaire à celui ci-dessous.  Les formulaires pour les événements d’ouverture et de rebond sont similaires.

![](assets/do-not-localize/mirror_page_url_send.png)

Le formulaire pour les événements de clic sur l’URL d’un email ajoute un attribut supplémentaire pour l’URL sur laquelle l’utilisateur a cliqué :

![](assets/do-not-localize/mirror_page_url_click.png)

Voici une liste des attributs et une description :

* Objet : objet de l’événement ; composé de l’identifiant de campagne et de l’identifiant de diffusion de la diffusion email

* Propriétaire : utilisateur de l’application créé lors des étapes après la mise en service

* Concernant : nom du contact

* Nom de la campagne : identifiant de la campagne dans Campaign Standard

* Nom de la diffusion : identifiant de la diffusion dans Campaign Standard

* Date d’envoi/d’ouverture/de clic/de rebond : Date/heure de création de l’événement

* URL de suivi : URL sur laquelle l’utilisateur a cliqué

* URL de page miroir : URL vers la page miroir de l’email envoyé/ouvert/sur lequel l’utilisateur a cliqué/de rebond

>[!NOTE]
>
>La période d’expiration de la page miroir d’email peut être modifiée dans l’écran de configuration de l’activité email Campaign correspondante (voir [Paramètres de la période de validité](../../administration/using/configuring-email-channel.md#validity-period-parameters)).

>[!NOTE]
>
>Pour la désinscription, lorsqu’un attribut de désinscription est modifié dans Dynamics 365, la modification est prise en compte dans Campaign si vous avez sélectionné la configuration de la désinscription de Dynamics 365 vers Campaign ou bidirectionnelle, et si cet attribut est correctement mappé.

## Flux de données {#data-flows}

### Entrée de contact et d’entité personnalisée

Les enregistrements nouveaux et mis à jour (et supprimés, s’ils sont activés) sont envoyés de la table des contacts Dynamics 365 à la table des profils Campaign.

Les mappages de table peuvent être configurés pour mapper les attributs de table Dynamics 365 sur les attributs de table Campaign. Les mappages des tables peuvent être modifiés pour ajouter ou supprimer des attributs, si nécessaire.

L’exécution initiale du flux de données est conçue pour transférer tous les enregistrements mappés, y compris ceux marqués comme « inactifs » ; par la suite, l’intégration ne traitera que les mises à jour incrémentielles. L’exception à cette règle est le cas où un filtre est configuré ; des règles de filtrage de base basées sur des attributs peuvent être configurées pour déterminer les enregistrements à synchroniser avec Campaign.

Les règles de remplacement de base peuvent être configurées pour remplacer une valeur d’attribut par une autre (par exemple, « vert » pour « #00FF00 », « F » pour 1, etc.).

En fonction du volume d’enregistrements, il se peut que votre stockage SFTP dans Campaign doive être utilisé pour le transfert initial de données.  Reportez-vous à la section relative au « transfert initial de données ».

L’attribut ‘ExternalId’ de la table de profils Campaign doit être renseigné avec l’attribut de contact ‘contactId’ Dynamics 365 pour que l’entrée de contact fonctionne. Les entités personnalisées Campaign doivent également être renseignées avec un attribut d’identifiant unique Dynamics 365 ; cependant, cet attribut peut être stocké dans n’importe quel attribut d’entité personnalisée Campaign (c.-à-d. qu’il n’est pas nécessaire qu’il s’agisse d’externalId).

>[!NOTE]
>
>Pour l’entrée d’entités personnalisées, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.

### Flux d’événements de marketing email

Les événements de marketing email sont envoyés de Campaign à Dynamics 365 pour apparaître dans la vue Planning.

Types d’événements de marketing pris en charge :
* Envoi - email envoyé au destinataire
* Ouverture- email ouvert par le destinataire
* Clic - URL dans l’email sur lequel clique le destinataire
* Bounce - l’email envoyé au destinataire a fait l’objet d’un hard bounce

Les attributs des événements suivants sont affichés dans D365 :
* Nom de la campagne marketing
* Nom de la diffusion Email
* Date et heure
* URL de la page miroir de l’email
* URL sur laquelle l’utilisateur a cliqué (événements de clic uniquement)

Les événements de marketing email peuvent être activés/désactivés par type (envoi, ouverture, clic, bounce) de sorte que seuls les types d’événements sélectionnés seront transmis à Dynamics 365.

### Flux de désinscription (opt-out)

Les valeurs de désinscription (par exemple, denyList) sont synchronisées entre les systèmes ; vous avez le choix entre les options suivantes lors de l’intégration :
* Dynamics 365 est une source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Dynamics 365 vers Campaign Standard
* Campaign Standard est la source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Campaign Standard vers Dynamics 365
* Dynamics 365 ET Campaign Standard sont les deux sources de vérité : les attributs de désinscription seront synchronisés de façon bidirectionnelle entre Campaign Standard et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des désinscriptions entre les systèmes, le flux de données de désinscription de l’intégration peut être désactivé.

Le mappage de flux de désinscription doit être spécifié par le client, car les besoins métier peuvent varier d’une société à l’autre.  Du côté Campaign, seuls les attributs de désinscription d’usine peuvent être utilisés pour le mappage de désinscription :
* denyList
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

Dans Dynamics 365, la plupart des champs de désinscription ont le préfixe « donot » ; toutefois, vous pouvez également utiliser d’autres attributs personnalisés à des fins de désinscription si les types de données sont compatibles.

### Transfert initial de données

Les tables Dynamics 365 de plus de 500 000 enregistrements devront être exportées vers votre stockage SFTP dans Campaign pour être importées via le workflow Campaign.

Le transfert initial de données est un transfert ponctuel de données basé sur des fichiers. Après le transfert des données, l’intégration utilisera des API pour les mises à jour incrémentielles.
