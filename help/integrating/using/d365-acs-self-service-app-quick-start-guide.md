---
title: 'Prise en main de l’outil d’intégration '
description: Prise en main de l’outil d’intégration
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 1e05db3fecc87a026750f40acb0ff063706e3f38
workflow-type: tm+mt
source-wordcount: '1104'
ht-degree: 2%

---


# Commencez avec l&#39;application d&#39;intégration en libre-service {#gs-self-service-app}

L&#39;intégration Adobe Campaign Standard avec l&#39;application d&#39;intégration en libre-service Microsoft Dynamics 365 vous permet de configurer des flux de données, de contrôler s&#39;ils sont en cours d&#39;exécution ou non et dans quel environnement. Vous devez toutefois remplir certaines conditions préalables avant de commencer à utiliser l’application d’intégration en libre-service.

## Concepts et restrictions {#concepts-and-restrictions}

Avant de commencer avec l’outil d’intégration, vous devez comprendre les concepts et les garde-fous associés à l’intégration et prendre quelques étapes initiales pour y accéder.

En savoir plus sur ces sections :

* [Prise en main de l’intégration de Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Meilleures pratiques et limites d’intégration](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Découvrez les étapes clés de la mise en oeuvre de cette intégration](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Utilisation de l’intégration de Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Prérequis {#self-service-app-prerequisites}

Vous devez configurer Microsoft Dynamics 365 et Adobe Campaign Standard pour que l&#39;application d&#39;intégration ait accès à vos données. Cette configuration prendra du temps dans Dynamics 365, Adobe Campaign Standard et Adobe I/O ; toutefois, une fois configurés, vous pourrez contrôler l&#39;intégration par le biais de l&#39;interface utilisateur de l&#39;application d&#39;intégration en libre-service.

En savoir plus sur ces sections :

* [Configuration de Microsoft Dynamics 365 pour l’intégration Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configurer Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Mise en correspondance des ressources personnalisées Campaign et des entités personnalisées Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Etapes clés de configuration de l’application d’intégration en libre-service {#self-service-app-configuration-steps}

Vous pouvez ensuite début avec l’outil d’intégration. Suivez les étapes ci-dessous :

1. [Accéder à l’application d’intégration](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configuration de l’application d’intégration en fonction de votre utilisation](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Mise en oeuvre de la synchronisation des données](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configuration des workflows de synchronisation](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Lien vers l’application d’intégration {#self-service-app-link}

Ouvrez un navigateur et accédez au connecteur associé à votre région :

* [Asie-Pacifique](http://d365-acs-ap.ea.adobe.com/)
* [Europe, Moyen-Orient ou Afrique (EMEA)](http://d365-acs-em.ea.adobe.com/)
* [Amériques](http://d365-acs-na.ea.adobe.com/)

## accusé de réception de la demande de confidentialité {#self-service-app-acknowledgement}

Lorsque vous accédez pour la première fois à l’interface utilisateur en libre-service, vous recevrez un accusé de réception de confidentialité. Vous devez reconnaître que vous comprenez votre rôle dans l&#39;exécution des demandes de confidentialité dans Campaign et Microsoft Dynamics 365 séparément avant de pouvoir continuer.
Pour en savoir plus sur vos responsabilités en matière de confidentialité et sur la façon de gérer les demandes de confidentialité, consultez [cette section](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Configuration de vos informations d&#39;identification {#self-service-app-credentials}

Lorsque vous accédez pour la première fois à l’interface utilisateur, une page avec un en-tête se présente comme suit :

![](assets/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Il est normal d&#39;obtenir des alertes indiquant qu&#39;il est &quot;incapable de se connecter&quot; à Adobe Campaign Standard ou Microsoft Dynamics 365 si les paramètres de l&#39;application n&#39;ont pas encore été configurés.

Vérifiez que les sélections &quot;ORG&quot; et &quot;INSTANCE&quot; sont celles que vous prévoyez de configurer.  Dans le cas contraire, cliquez sur la liste déroulante et sélectionnez l’organisation et l’instance appropriées.

>[!IMPORTANT]
>
> Si vous configurez le connecteur pour la première fois et/ou si vous êtes nouveau dans ce processus, **fortement** vous invite à sélectionner l’instance &quot;stage&quot; ou &quot;dev&quot;. Vous devez vérifier que votre configuration fonctionne bien avant de tenter la configuration en production.

Si vous avez l&#39;organisation et l&#39;instance appropriées, cliquez sur le menu &quot;hamburger&quot; pour afficher un menu déroulant. Cliquez ensuite sur **[!UICONTROL Paramètres..]** dans le menu déroulant pour accéder à la page où vous entrez vos informations d&#39;identification pour Microsoft Dynamics 365 et Campaign (voir ci-dessous).

![](assets/d365-to-acs-ui-page-workflows-menu-pointers.png)

Dans la page **[!UICONTROL Paramètres]**, renseignez les sections suivantes :

* Informations d&#39;identification Microsoft Dynamics 365
* Informations d’identification d’Adobe

Allez [ici](../../integrating/using/d365-acs-self-service-app-settings.md) pour trouver des informations plus détaillées sur l&#39;emplacement où trouver les informations pour chaque entrée. Lorsque vous avez terminé, cliquez sur le bouton **[!UICONTROL Enregistrer]** en bas.

## Vérifier la configuration initiale {#self-service-app-initial-config}

En supposant que vous ayez rempli les conditions préalables ci-dessus et ajouté correctement toutes vos informations d’identification, accédez maintenant à la page **[!UICONTROL Workflows]**. Pour en savoir plus sur les workflows de l&#39;application d&#39;intégration, consultez [cette page](../../integrating/using/d365-acs-self-service-app-workflows.md).

Dans la page **[!UICONTROL Workflows]**, cliquez sur l&#39;icône représentant un crayon associée au processus **[!UICONTROL Microsoft Dynamics 365 to Campaign]** pour modifier sa configuration.

![](assets/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

Dans la page **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, vous pouvez accéder à la liste des mappages de table que vous avez configurés.  Vous obtiendrez par défaut un mappage contact/profil prêt à l’emploi. Toutes les autres entités personnalisées devront être configurées séparément.

![](assets/d365-to-acs-ui-page-ingress-top-pointers.png)

Dans la page **[!UICONTROL Modifier le mappage de table]**, consultez la section **[!UICONTROL Mappages]** pour vous assurer que les champs de Microsoft Dynamics 365 sont mappés sur le champ correct dans Campaign. Si vous devez ajouter d’autres mappages, faites-le dès maintenant, ainsi que tout remplacement ou filtres. [En savoir plus](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Pour ajouter de nouveaux mappages, consultez [cette section](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) pour plus d’informations.

Une fois votre configuration correcte, cliquez sur le bouton **[!UICONTROL Lire]** en regard du flux de travaux **[!UICONTROL Microsoft Dynamics 365 à Campaign]** afin de début de l&#39;intégration et du flux de données.

>[!IMPORTANT]
>
>Nous vous recommandons **fortement** de commencer par exécuter cette fonction dans vos environnements Stage ou Dev avant de l’exécuter dans Production. Vérifiez que l&#39;instance stage/dev est sélectionnée dans l&#39;en-tête.


![](assets/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Une fois en cours d&#39;exécution, vous devriez être en mesure de tester en ajoutant ou en modifiant des entrées dans Microsoft Dynamics 365 et en observant ces modifications dans Adobe Campaign dans quelques minutes. Si, à tout moment, vous devez arrêter ce processus, il vous suffit d&#39;appuyer sur le même bouton pour l&#39;arrêter. [En savoir plus](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Espace de travail d&#39;application d&#39;intégration {#self-service-app-workspace}

### En-tête de l’application {#app-header}

L’en-tête de l’application en libre-service vous permet de définir l’organisation et l’instance que vous visualisez et/ou configurez actuellement.

Sélectionnez **ORG** et **INSTANCE** que vous souhaitez vue/modifier. Ces champs apparaissent en lecture seule, mais ils deviennent modifiables lorsque vous placez le curseur de la souris dessus.

Un menu déroulant s&#39;affiche lorsque vous cliquez sur le bouton avec les trois lignes horizontales ![](assets/d365-to-acs-icon-hamburger.png) sur le côté droit de l&#39;en-tête.

Les entrées du menu déroulant sont les suivantes :

* **Paramètres** : Si vous sélectionnez cette option, vous accédez à un écran qui vous permet de spécifier les informations d&#39;identification d&#39;API pour Microsoft Dynamics 365 et Adobe Campaign, ainsi que d&#39;autres paramètres généraux pour l&#39;application.

* **Documentation** : Cette option est un lien vers la documentation Adobe Campaign spécifique à cette intégration.

* **Assistance** clientèle : Il s’agit d’un lien vers la documentation Experience Cloud relative à l’ouverture d’un ticket d’assistance à la clientèle.

* **Déconnexion** : Cela vous déconnectera de l’application et vous permettra de vous reconnecter en tant qu’autre utilisateur.

* **A propos** : Cette boîte de dialogue affiche des informations sur l’application, y compris des informations de copyright.

### Chemins de navigation {#app-breadcrumbs}

Des chemins de navigation s’affichent en haut de certains écrans lorsque vous naviguez dans l’application.

**Exemple:**

Vous trouverez ci-dessous un exemple tiré de l’écran **[!UICONTROL Modifier le mappage de tableau]** qui montre les chemins de navigation et le titre de la page. Dans ce cas, vous pouvez cliquer sur le texte **[!UICONTROL Workflows]** ou **[!UICONTROL Microsoft Dynamics 365 à Campaign]** pour accéder à l&#39;un des écrans précédents. **[!UICONTROL Il n’est pas possible de cliquer sur Modifier la]** correspondance de table dans les chemins de navigation dans ce cas, car il s’agit de l’écran actuel.

![](assets/d365-to-acs-breadcrumbs-ingress.png)

### Boutons courants {#app-buttons}

Les icônes suivantes sont utilisées dans plusieurs pages dans l’application en libre-service.

![](assets/d365-to-acs-icon-add.png) - Ajouter un nouvel élément à une liste.

![](assets/d365-to-acs-icon-edit.png) - Modifier quelque chose qui existe déjà

![](assets/d365-to-acs-icon-delete.png) - Supprimer un élément d&#39;une liste d&#39;éléments
