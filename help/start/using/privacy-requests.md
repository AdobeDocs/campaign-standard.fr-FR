---
solution: Campaign Standard
product: campaign
title: Demandes d'accès à des informations personnelles
description: Découvrez comment gérer les demandes d'accès à des informations personnelles dans Adobe Campaign Standard
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: ht
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: ht
source-wordcount: '1829'
ht-degree: 100%

---


# Gestion des demandes d&#39;accès à des informations personnelles {#privacy-requests}

Pour obtenir une présentation générale de la gestion de la protection des données, consultez [cette section](../../start/using/privacy-management.md).

Ces informations s&#39;appliquent au RGPD, au CCPA, au PDPA et au LGPD. Pour plus d&#39;informations sur ces règlementations, consultez [cette section](../../start/using/privacy-management.md#privacy-management-regulations).

Le droit d&#39;opposition (opt-out) à la vente des informations personnelles, spécifique au CCPA, est expliqué dans [cette section](#sale-of-personal-information-ccpa).

>[!IMPORTANT]
>
>À compter de la version 19.4, l&#39;utilisation de l&#39;API et de l&#39;interface de Campaign pour les demandes d&#39;accès et de suppression devient obsolète. Pour toute demande d&#39;accès et de suppression RGPD, CCPA, PDPA ou LGPD, vous devez utiliser la méthode d&#39;intégration de [Privacy Core Service](#create-privacy-request).

## À propos des demandes d&#39;accès à des informations personnelles {#about-privacy-requests}

Pour faciliter la préparation à la protection des données, Adobe Campaign permet désormais de gérer les demandes d&#39;accès et de suppression. Le **droit d&#39;accès** et le **droit à l&#39;oubli** (demande de suppression) sont décrits dans [cette section](../../start/using/privacy-management.md#right-access-forgotten).

Pour effectuer ces demandes, vous devez utiliser l&#39;intégration de **Privacy Core Service**. Les demandes d&#39;accès à des informations personnelles transmises par Privacy Core Service à toutes les solutions Experience Cloud sont automatiquement traitées par Campaign via un workflow dédié.

### Prérequis {#prerequesites}

Adobe Campaign met à la disposition des contrôleurs de données des outils afin de créer et traiter des demandes d&#39;accès à des informations personnelles pour les données stockées dans Adobe Campaign. Il incombe toutefois au contrôleur de données de gérer la relation avec le titulaire de données (email, service à la clientèle ou portail web).

Par conséquent, il est de votre responsabilité, en tant que contrôleur de données, de vérifier l&#39;identité du titulaire de données à l&#39;origine de la demande et de confirmer que les données renvoyées au demandeur concernent le titulaire de données.

>[!NOTE]
>
>Pour plus d&#39;informations sur les données personnelles et sur les différentes entités qui gèrent les données (Contrôleur de données, Responsable du traitement des données et Titulaire de données), consultez [Données personnelles et acteurs impliqués](../../start/using/privacy.md#personal-data).

### Espaces de noms {#namesspaces}

Avant de créer des demandes d&#39;accès à des informations personnelles, vous devez définir l&#39;espace de noms que vous utiliserez. L&#39;espace de noms est la clé qui sera utilisée pour identifier le titulaire de données dans la base de données Adobe Campaign. Deux espaces de noms d&#39;usine sont disponibles : email et téléphone mobile. Si vous avez besoin d&#39;un autre espace de noms (un champ personnalisé de profil, par exemple), suivez les étapes ci-dessous.

Reportez-vous également à ce [tutoriel](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/namespaces-for-privacy-requests.html?lang=fr#privacy) sur la création d&#39;un espace de noms.

>[!NOTE]
>
>Si vous utilisez plusieurs espaces de noms, vous devez créer une demande d&#39;accès à des informations personnelles par espace de noms.

1. Cliquez sur le logo Adobe Campaign, en haut à gauche, puis sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Espaces de noms]**.

   ![](assets/privacy-namespaces.png)

1. Dans la liste des espaces de noms, cliquez sur **[!UICONTROL Créer]**.

   ![](assets/privacy-namespace-create.png)

1. Saisissez un **[!UICONTROL Libellé]**.

   ![](assets/privacy-namespace-label.png)

1. Si vous souhaitez utiliser un espace de noms du service d&#39;identités existant, sélectionnez **[!UICONTROL Mappage depuis le service d&#39;espace de noms d&#39;identité]**, puis un espace de noms dans la liste **[!UICONTROL Espaces de noms du service d&#39;identités]**.

   ![](assets/privacy-map-from-namespace.png)

   Si vous souhaitez créer un espace de noms dans le **[!UICONTROL Service d&#39;identités]** et le mapper dans Campaign, sélectionnez **[!UICONTROL Créer]** et entrez un nom dans le champ **[!UICONTROL Nom de l&#39;espace de noms d&#39;identité.]**

   ![](assets/privacy-create-new-namespace.png)

   Pour en savoir plus sur les espaces de noms d&#39;identité, consultez la documentation d&#39;[Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=fr).

1. Un espace de noms du service d&#39;identités est mappé sur un espace de noms de Campaign. Vous devez indiquer comment l&#39;espace de noms sera réconcilié dans Campaign.

   Sélectionnez un mapping de ciblage (**[!UICONTROL Destinataires]**, **[!UICONTROL Événement en temps réel]** ou **[!UICONTROL Abonnements à une application]**). Si vous souhaitez utiliser plusieurs mappings de ciblage, vous devez créer un espace de noms par mapping de ciblage.

   ![](assets/privacy-namespace-target-mapping.png)

1. Sélectionnez la **[!UICONTROL Clé de réconciliation]**. Il s&#39;agit du champ qui sera utilisé pour identifier le titulaire de données dans la base de données Adobe Campaign.

   ![](assets/privacy-namespace-reconciliation-key.png)

1. Cliquez sur **[!UICONTROL Créer]**. Vous pouvez maintenant créer des demandes d&#39;accès à des informations personnelles basées sur votre nouvel espace de noms. Si vous utilisez plusieurs espaces de noms, vous devez créer une demande d&#39;accès à des informations personnelles par espace de noms.

### Création d&#39;une demande d&#39;accès à des informations personnelles {#create-privacy-request}

>[!IMPORTANT]
>
>L&#39;intégration de **Privacy Core Service** est la méthode appropriée pour toutes les demandes d&#39;accès et de suppression.
>
>À compter de la version 19.4, l&#39;utilisation de l&#39;API et de l&#39;interface de Campaign pour les demandes d&#39;accès et de suppression devient obsolète. Utilisez Privacy Core Service pour toute demande d&#39;accès et de suppression relative au RGPD, au CCPA, au PDPA ou au LGPD.

L&#39;intégration avec Privacy Core Service vous permet d&#39;automatiser vos demandes d&#39;accès à des informations personnelles dans un contexte multisolution grâce à un seul appel API JSON. Les demandes d&#39;accès à des informations personnelles transmises par Privacy Core Service à toutes les solutions Experience Cloud sont automatiquement traitées par Campaign via un workflow dédié.

Reportez-vous à la documentation d&#39;[Experience Platform Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=fr) pour savoir comment créer des demandes d&#39;accès à des informations personnelles à partir de Privacy Core Service.

Chaque traitement du Privacy Core Service est divisé en plusieurs demandes d&#39;accès à des informations personnelles dans Campaign en fonction du nombre d&#39;espaces de noms utilisés (une demande correspondant à un espace de noms). En outre, un traitement peut être exécuté sur plusieurs instances. C&#39;est pourquoi plusieurs fichiers sont créés pour un seul traitement. Par exemple, si une demande contient deux espaces de noms et est exécutée sur trois instances, six fichiers sont envoyés. Soit un fichier par espace de noms et par instance.

Le modèle d&#39;un nom de fichier est le suivant : `<InstanceName>-<NamespaceId>-<ReconciliationKey>.xml`

* **NomInstance** : nom de l&#39;instance dans Campaign
* **IdEspaceDeNoms** : identifiant de l&#39;espace de noms du service d&#39;identités utilisé
* **CléRéconciliation** : clé de réconciliation encodée

### Liste des ressources {#list-of-resources}

Lors de l&#39;exécution d&#39;une demande d&#39;accès à des informations personnelles ou de suppression, Adobe Campaign recherche toutes les données du titulaire de données en fonction de la valeur de **réconciliation** dans toutes les ressources ayant un lien avec la ressource de profils (type own).

Voici la liste des ressources d&#39;usine qui sont prises en compte lors de l&#39;exécution des demandes d&#39;accès à des données personnelles :

* Profils (recipient)
* Logs de diffusion des profils (broadLogRcp)
* Logs de tracking des profils (trackingLogRcp)
* Logs de diffusion (Abonnements à une application) (broadLogAppSubRcp)
* Logs de tracking (Abonnements à une application) (trackingLogAppSubRcp)
* Abonnements à une application (appSubscriptionRcp)
* Historique des abonnements des profils (subHistoRcp)
* Abonnements des profils (subscriptionRcp)
* Visiteurs (visitor)

Si vous avez créé des ressources personnalisées ayant un lien vers la ressource de profils (type own), celles-ci sont également prises en compte. Par exemple, si une ressource de transaction est liée à la ressource de profils et si une ressource de détails de transaction est liée à la ressource de transaction, elles sont toutes deux prises en compte.

Reportez-vous également à [ce tutoriel](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/custom-resources-for-privacy-requests.html?lang=fr#privacy) sur la modification des ressources personnalisées.

Pour que cela fonctionne, vous devez sélectionner l&#39;option **[!UICONTROL La suppression de l&#39;enregistrement cible entraîne la suppression des enregistrements référencés par le lien]** dans la ressource personnalisée.

1. Cliquez sur le logo Adobe Campaign, en haut à gauche, puis sélectionnez **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Ressources personnalisées]**.

1. Sélectionnez une ressource personnalisée qui a un lien vers la ressource profils (type own).

1. Cliquez sur la section **[!UICONTROL Liens]**.

1. Pour chaque lien, cliquez sur l&#39;icône représentant un crayon (**[!UICONTROL Éditer les propriétés]**).

1. Dans la section **[!UICONTROL Comportement en cas de suppression/duplication]**, sélectionnez l&#39;option **[!UICONTROL La suppression de l&#39;enregistrement cible entraîne la suppression des enregistrements référencés par le lien]**.

   ![](assets/privacy-cus-resource-option.png)

### États des demandes d&#39;accès à des informations personnelles {#privacy-request-statuses}

Voici les différents états des demandes d&#39;accès à des informations personnelles :

* **[!UICONTROL Nouveau]**/**[!UICONTROL Reprise en attente]** : en cours, le workflow n&#39;a pas encore traité la demande.
* **[!UICONTROL Traitement]**/**[!UICONTROL Reprise en cours]** : le workflow traite la demande.
* **[!UICONTROL Suppression en attente]** : le workflow a identifié toutes les données du destinataire à supprimer.
* **[!UICONTROL Suppression en cours]** : le workflow traite la suppression.
   <!--**[!UICONTROL Delete Confirmation Pending]** (Delete request in 2-steps process mode): the workflow has processed the Access request. Manual confirmation is requested to perform the deletion. The button is available for 15 days.-->
* **[!UICONTROL Terminé]** : le traitement de la demande s&#39;est terminé sans erreur.
* **[!UICONTROL Erreur]** : le workflow a rencontré une erreur. La raison apparaît dans la colonne **[!UICONTROL État de la demande]** de la liste des demandes d&#39;accès à des informations personnelles. Par exemple, le statut **[!UICONTROL Erreur : données introuvables]** indique qu&#39;aucune donnée du destinataire correspondant à la **[!UICONTROL Valeur de réconciliation]** du titulaire de données n&#39;a été trouvée dans la base de données.

### Désactivation de la procédure en 2 étapes {#disabling-two-step-process}

Privacy Core Service ne prend pas en charge la procédure en 2 étapes.

>[!IMPORTANT]
>
>Avant d&#39;utiliser l&#39;intégration de Privacy Core Service pour gérer vos demandes d&#39;accès à des informations personnelles, vous devez désactiver la procédure en 2 étapes pour les demandes de suppression depuis l&#39;interface de Campaign Standard.

Si cette option n&#39;est pas désactivée, toutes les demandes de suppression gérées avec Privacy Core Service resteront en attente et ne seront pas terminées.

La procédure en 2 étapes est activée par défaut.

Pour modifier ce mode, cliquez sur **[!UICONTROL Editer les propriétés]**, dans l&#39;angle supérieur droit de l&#39;écran **[!UICONTROL Demandes d&#39;accès à des informations personnelles]**, puis désactivez l&#39;option **[!UICONTROL Activer la procédure en 2 étapes]**.

![](assets/privacy-disable-2-step-process.png)

## Droit d&#39;opposition (opt-out) à la vente des informations personnelles (CCPA) {#sale-of-personal-information-ccpa}

Le **CCPA** (California Consumer Privacy Act) fournit aux résidents de la Californie de nouveaux droits relatifs aux informations personnelles et impose des responsabilités en matière de protection des données à certaines entités qui exercent des activités en Californie.

La configuration et l&#39;usage des demandes d&#39;accès et de suppression sont identiques pour le RGPD et le CCPA. Cette section présente le droit d&#39;opposition à la vente des données personnelles, qui est spécifique au CCPA.

Outre les outils de [gestion du consentement](../../start/using/privacy-management.md#consent-management) fournis par Adobe Campaign, vous pouvez suivre si un client s&#39;est opposé à la vente de ses informations personnelles.

Un consommateur décide, par l&#39;intermédiaire de votre système, qu&#39;il n&#39;autorise pas la vente de ses informations personnelles à un tiers. Dans Adobe Campaign, vous pourrez stocker et suivre ces informations.

>[!NOTE]
>
>Vous pouvez exploiter l&#39;opt-out de la vente des informations personnelles via l&#39;API et l&#39;interface de Campaign. Vous ne pouvez pas l&#39;utiliser par l&#39;intermédiaire du Privacy Core Service.

>[!IMPORTANT]
>
>En tant que contrôleur de données, il vous incombe de recevoir la demande du titulaire de données et de suivre les dates de la demande pour le CCPA. En tant que fournisseur de technologie, nous offrons uniquement une option d&#39;opt-out. Pour plus d&#39;informations sur votre rôle en tant que contrôleur de données, voir [Données personnelles et acteurs impliqués](../../start/using/privacy.md#personal-data).

### Condition préalable requise pour les tables personnalisées {#ccpa-prerequisite}

À compter de la version 19.4, le champ **[!UICONTROL Option d&#39;Opt-out du CCPA]** est fourni dans l&#39;API et l&#39;interface de Campaign. Par défaut, le champ est disponible pour la ressource **[!UICONTROL Profil]** standard.

Si vous utilisez une ressource de profil personnalisée, vous devez étendre la ressource et ajouter le champ. Nous vous recommandons d&#39;utiliser un nom différent du nom d&#39;origine du champ, par exemple : **[!UICONTROL Opt-out du CCPA]** (optoutccpa). Lorsqu&#39;un champ est créé, il est automatiquement pris en charge par l&#39;API de Campaign.

Pour plus d&#39;informations sur la façon d&#39;étendre la ressource de profil, consultez [cette section](../../developing/using/extending-the-profile-resource-with-a-new-field.md).

>[!NOTE]
>
>La modification des ressources est une opération sensible qui ne doit être effectuée que par des utilisateurs expérimentés.

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Ressources personnalisées]**. Cliquez sur la ressource de profil personnalisée. Pour plus d&#39;informations sur l&#39;extension d&#39;une ressource, consultez [cette section](../../developing/using/creating-or-extending-the-resource.md).

   ![](assets/privacy-ccpa-extend-cus.png)

1. Cliquez sur **[!UICONTROL Ajouter un champ]** ou **[!UICONTROL Créer un élément]**, ajoutez le libellé, l&#39;identifiant et choisissez le type **[!UICONTROL Booléen]**. Pour le nom, utilisez **Opt-out pour le CCPA**. Pour l&#39;identifiant, utilisez : **optOutCcpa**.

   ![](assets/privacy-ccpa-extend-field.png)

1. Dans l&#39;onglet **[!UICONTROL Définition des écrans]**, sous **[!UICONTROL Configuration de l&#39;écran de détail]**, ajoutez le champ et sélectionnez **[!UICONTROL Champ de saisie]**. Le champ devient ainsi disponible dans les détails et la liste des profils.  Pour plus d&#39;informations sur la configuration de la définition des écrans, voir [cette section](../../developing/using/configuring-the-screen-definition.md).

   ![](assets/privacy-ccpa-extend-screen.png)

1. Accédez à **[!UICONTROL Administration]** > **[!UICONTROL Développement]** > **[!UICONTROL Publication]**, préparez la publication et publiez les modifications. Pour plus d&#39;informations sur la publication d&#39;une ressource, consultez [cette section](../../developing/using/updating-the-database-structure.md).

   ![](assets/privacy-ccpa-extend-pub.png)

1. Vérifiez que le champ est disponible sur les détails d&#39;un profil. Voir à ce propos [cette section](#usage).

### Utilisation {#usage}

Il est de la responsabilité du contrôleur de données d&#39;indiquer la valeur du champ et de suivre les règles et les directives du CCPA relatives à la vente des données.

Pour indiquer les valeurs, plusieurs méthodes peuvent être utilisées :

* À l&#39;aide de l&#39;interface de Campaign en éditant les détails du destinataire (voir ci-dessous).
* À l&#39;aide de l&#39;API Campaign de protection des données (voir la [documentation de l&#39;API](../../api/using/managing-ccpa-opt-out.md)).
* Par l&#39;intermédiaire d&#39;un workflow d&#39;import de données.

Vous devez ensuite vous assurer de ne jamais vendre à une quelconque tierce partie les informations personnelles des profils qui s&#39;y sont opposés.

1. Dans l&#39;interface de Campaign, éditez un profil pour modifier le statut d&#39;opt-out.

   ![](assets/privacy-ccpa-profile-opt-out.png)

1. Lorsque la valeur du champ est **[!UICONTROL True]**, les informations s&#39;affichent dans les détails du profil.

   ![](assets/privacy-ccpa-profile-opt-out-true.png)

1. Vous pouvez configurer la liste des profils pour qu&#39;elle affiche la colonne d&#39;opt-out. Pour savoir comment configurer des listes, consultez [cette section](../../start/using/customizing-lists.md).

   ![](assets/privacy-ccpa-profile-configure-list.png)

1. Vous pouvez cliquer sur la colonne afin de trier les destinataires selon les informations d&#39;opt-out.

   ![](assets/privacy-ccpa-profile-sorting.png)
