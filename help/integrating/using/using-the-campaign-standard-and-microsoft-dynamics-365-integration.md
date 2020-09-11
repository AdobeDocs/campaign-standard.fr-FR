---
title: Utilisation de l'intégration Microsoft Dynamics 365
description: Découvrez comment utiliser l’intégration de Microsoft Dynamics 365 avec Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ca6b418351cfbe539da9f1f4a542c2d7014dfc24
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 44%

---


# Utilisation de l&#39;intégration Microsoft Dynamics 365

Cette intégration exécute plusieurs traitements :

* **Entrée**:

   * Placer **des contacts** de Dynamics 365 dans Campaign

   * **Entités** personnalisées : Placez des tables personnalisées de Dynamics 365 à Campaign. En savoir plus dans [cette section](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Entrée**: Faire passer les événements de marketing par courrier électronique de ACS à D365 (envoi de courrier électronique, ouverture, clic, rebond)

* **Exclusion**: Etat d’exclusion de la synchronisation bidirectionnelle (par exemple, liste bloquée)

Vous trouverez plus de détails sur les flux de données [dans cette section](#data-flows).

## Expérience utilisateur Adobe Campaign Standard

Lorsqu&#39;un contact est créé ou modifié (ou supprimé, s&#39;il est activé) dans Dynamics 365, il est envoyé à Campaign.  Ces contacts seront visibles dans l’écran Profils de Campaign et peuvent être ciblés dans les campagnes marketing.  Voir l’écran Profils ci-dessous.

![](assets/MSdynamicsACS-usage1.png)

Lorsqu&#39;un attribut d&#39;exclusion est modifié dans Campaign, il est reflété dans Dynamics 365 si vous avez sélectionné la configuration d&#39;exclusion de Campaign-to-Dynamics 365 ou bidirectionnelle, et si cet attribut particulier est correctement mappé.

## Expérience utilisateur Microsoft Dynamics 365

Pour plus d&#39;informations, les événements de marketing par courriel suivants sont envoyés de Campaign à Dynamics 365 et affichés dans la vue de chronologie Dynamics 365 en tant qu&#39;activités personnalisées :

*  Envoi d’email Adobe Campaign

*  Ouverture d’email Adobe Campaign

*  Clic sur une URL d’email Adobe Campaign

*  Email bounce Adobe Campaign

Pour voir la chronologie d&#39;un contact, accédez à votre liste de contacts en cliquant sur Concentrateur des ventes dans le menu déroulant Dynamics 365.  Cliquez ensuite sur Contacts dans la barre de menu de gauche et sélectionnez un contact.

>[!NOTE]
>
>L&#39;application Adobe Campaign pour Dynamics 365 dans AppSource devra être installée dans votre instance Dynamics 365 afin d’afficher ces événements.

Vous trouverez ci-dessous un instantané de l’écran Contact pour « Utilisateur Dynamics ».  Dans la vue de la chronologie, vous remarquerez que l’utilisateur Dynamics a reçu un email associé au nom Campaign « 2019LoyaltyCamp » et au nom de diffusion « DM190 ». L’utilisateur Dynamics a ouvert l’email et a également cliqué sur une URL contenue dans celui-ci ces deux actions ont créé des événements également présentés ci-dessous.  Si vous regardez dans le coin droit, vous verrez la carte de l&#39;assistant de relations (AR) ; il contient actuellement une tâche de suivi de l’URL sur laquelle l’utilisateur a cliqué.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Reportez au gros plan ci-dessous de la vue de chronologie pour l’utilisateur Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

Vous trouverez ci-dessous un gros plan de la carte de l&#39;assistant de relations (AR). L’application AppSource contient un workflow qui recherche un événement de clic sur l’URL de l’email Adobe.  Lorsque cet événement se produit, il crée une tâche et définit une date d’échéance.  Cela permet à la tâche de s’afficher dans la carte de l’AR, ce qui lui donne une visibilité supplémentaire.  Il existe un workflow similaire pour les événements Email bounce d’Adobe, qui ajoute une tâche pour réconcilier l’adresse email non valide.  Ces workflows peuvent être désactivés dans la solution.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Si vous cliquez sur le sujet de l’événement d’envoi, vous verrez un formulaire similaire à celui ci-dessous.  Les formulaires pour les événements d’ouverture et de rebond sont similaires.

![](assets/do-not-localize/mirror_page_url_send.png)

Le formulaire pour les événements de clic sur l’URL d’un email ajoute un attribut supplémentaire pour l’URL sur laquelle l’utilisateur a cliqué :

![](assets/do-not-localize/mirror_page_url_click.png)

Voici une liste des attributs et une description :

* Objet : objet de l’événement ; composé de l’identifiant de campagne et de l’identifiant de diffusion de la diffusion email

* Propriétaire : utilisateur de l’application créé lors des étapes après la mise en service

* Concernant : Nom du contact

* Nom de la campagne : identifiant de la campagne dans Campaign Standard

* Nom de la diffusion : identifiant de la diffusion dans Campaign Standard

* Date d&#39;envoi/d&#39;ouverture/de clic/de rebond : Date/heure de création de l’événement

* URL de suivi : URL sur laquelle l’utilisateur a cliqué

* URL de page miroir : URL vers la page miroir de l’email envoyé/ouvert/sur lequel l’utilisateur a cliqué/de rebond

>[!NOTE]
>
>La période d&#39;expiration de la page miroir de courriel peut être modifiée dans l&#39;écran de configuration de l&#39;activité de canal de courriel Campaign correspondante (voir Paramètres [de la période de](../../administration/using/configuring-email-channel.md#validity-period-parameters)validité).

>[!NOTE]
Pour l’opt-out, lorsqu’un attribut d’opt-out est modifié dans Dynamics 365, la modification est prise en compte dans Campaign si vous avez sélectionné la configuration d’opt-out de Dynamics 365 vers Campaign ou bidirectionnelle, et si cet attribut est correctement mappé.

## Flux de données {#data-flows}

### Entrée de contact et d&#39;entité personnalisée

Les enregistrements nouveaux et mis à jour (et supprimés, s&#39;ils sont activés) sont envoyés de la table des contacts Dynamics 365 à la table des profils Campaign.

Les mappages de table peuvent être configurés pour mapper les attributs de table Dynamics 365 aux attributs de table Campaign. Les mappages des tables peuvent être modifiés pour ajouter ou supprimer des attributs, si nécessaire.

L&#39;exécution initiale du flux de données est conçue pour transférer tous les enregistrements mappés, y compris ceux marqués comme &quot;inactifs&quot;; par la suite, l’intégration ne traitera que les mises à jour incrémentielles. L’exception à cette règle est le cas où un filtre est configuré ; des règles de filtrage de base basées sur des attributs peuvent être configurées pour déterminer les enregistrements à synchroniser avec Campaign.

Les règles de remplacement de base peuvent être configurées pour remplacer une valeur d’attribut par une autre valeur (par exemple, &quot;vert&quot; pour &quot;#00FF00&quot;, &quot;F&quot; pour 1, etc.).

En fonction du volume d’enregistrements, il se peut que votre enregistrement Campaign SFTP doive être utilisé pour le transfert initial de données.  Reportez-vous à la section relative au transfert initial de données.

L&#39;attribut externeId de la table de profils Campaign doit être renseigné avec l&#39;attribut contactId de l&#39;attribut de contact Dynamics 365 pour que l&#39;entrée de contact fonctionne. Les entités personnalisées Campaign doivent également être renseignées avec un attribut d&#39;ID unique Dynamics 365 ; cependant, cet attribut peut être stocké dans n’importe quel attribut d’entité personnalisée Campaign (c.-à-d. qu’il n’est pas nécessaire qu’il s’agisse d’externalId).

>[!NOTE]
Pour l&#39;entrée d&#39;entité personnalisée, le suivi des modifications doit être activé dans Dynamics 365 pour les entités personnalisées synchronisées.

### Flux de Événement de marketing par courriel

Les événements de marketing par courrier électronique sont envoyés de Campaign à Dynamics 365 pour apparaître dans la vue Chronologie.

Types d&#39;événement marketing pris en charge :
* Envoyer - Envoyer par courrier électronique au destinataire
* Ouvrir - courrier électronique ouvert par le destinataire
* Clic - URL dans le courrier électronique sur lequel clique le destinataire
* Rebond - Le destinataire a connu un rebond brutal dans son courrier électronique

Les attributs de événement suivants sont affichés dans le D365 :
* Nom de la campagne marketing
* Nom de la diffusion de messagerie
* Date et heure
* URL de la page miroir de courriel
* URL sur laquelle l’utilisateur a cliqué (cliquez sur événements uniquement)

Les Événements de marketing par courriel peuvent être activés/désactivés par type (envoyer, ouvrir, cliquer, rebondir) de sorte que seuls les types d&#39;événement sélectionnés seront transmis à Dynamics 365.

### Flux d’exclusion

les valeurs d&#39;exclusion (par exemple, la liste bloquée) sont synchronisées entre les systèmes ; vous avez le choix entre les options suivantes lors de l’intégration :
* Dynamics 365 est une source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Dynamics 365 vers Campaign Standard
* Campaign Standard est la source de vérité pour les désinscriptions : les attributs de désinscription seront synchronisés dans une direction, de Campaign Standard vers Dynamics 365
* Dynamics 365 AND Campaign Standard sont deux sources de vérité : les attributs d&#39;exclusion seront synchronisés bidirectionnellement entre Campaign Standard et Dynamics 365

Si vous disposez également d’un processus distinct pour gérer la synchronisation des exclusions entre les systèmes, le flux de données d’exclusion de l’intégration peut être désactivé.

Le mappage de flux d’exclusion doit être spécifié par le client, car les besoins de l’entreprise peuvent différer d’une société à l’autre.  Du côté Campaign, seuls les attributs d’exclusion prêtes à l’emploi peuvent être utilisés pour le mappage d’exclusion :
* blockList
* blockListEmail
* blockListFax
* blockListMobile
* blockListPhone
* blockListPostalMail
* blockListPushnotification
* ccpaOptOut

Dans Dynamics 365, la plupart des champs d&#39;exclusion comportent le préfixe &quot;donot&quot; ; toutefois, vous pouvez également utiliser d’autres attributs à des fins d’exclusion si les types de données sont compatibles.

### Transfert initial de données

Les tables Dynamics 365 de plus de 500 000 enregistrements devront être exportées vers votre enregistrement Campaign SFTP pour être importées via le processus Campaign.

Le transfert initial de données est un transfert ponctuel de données basé sur des fichiers. Après le transfert des données, l’intégration utilisera des API pour les mises à jour incrémentielles.
