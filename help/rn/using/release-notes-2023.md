---
title: Notes de mise à jour 2023
description: Cette page répertorie toutes les versions 2023 d’Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 5817c4d2-4788-4695-bf9a-ec04cc042190
source-git-commit: 30e96494dd7fa3313601e48deeec8ef98dcdce85
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 100%

---

# Notes de mise à jour 2023 {#release-notes-2023}

## Version 23.2 - Version d’automne/hiver 2023 {#fall-23}

>[!AVAILABILITY]
>
>Cette version est disponible uniquement pour un ensemble d’organisations (disponibilité limitée). Pour plus d’informations, contactez votre personne représentante Adobe.

### Améliorations {#fall-23-rn-improvements}

* **Intégration avec Adobe Experience Manager**. Lors de la création d’un modèle de diffusion personnalisé pour les messages transactionnels dans Adobe Experience Manager, vous pouvez désormais sélectionner et utiliser les champs de personnalisation définis dans Campaign Standard dans une liste déroulante. [En savoir plus](../../integrating/using/creating-email-experience-manager.md)

* **Expiration des cookies** : l’expiration par défaut des cookies est désormais fixée à 6 mois, conformément aux recommandations de l’Agence française de protection des données (CNIL).

* **Amélioration de la recherche de profil** : la recherche de profil a été optimisée afin que les scénarios de délai d’expiration de la recherche puissent être réduits.

* **Localisation** : les traductions du terme « audience » lorsqu’il fait référence à un groupe de profils destinés à recevoir un message ont été harmonisées dans tous les produits Digital Experience pour les langues suivantes :

   * Allemand : Zielgruppe
   * Portugais du Brésil : público-alvo
   * Espagnol : público desatario

  Ces modifications seront progressivement déployées avec la prochaine UI et les prochaines versions de la documentation.


### Autres changements {#fall-23-rn-other-changes}

* Les messages transactionnels prennent désormais en charge l’utilisation de plusieurs affinités séparées par des virgules. [En savoir plus](../../sending/using/managing-typologies.md)

### Correctifs {#fall-23-rn-fixes}

* Correction d’une régression qui pouvait entraîner des problèmes de performances lors de l’utilisation de workflows volumineux. (CAMP-53369)
* Correction d’un problème qui empêchait le fonctionnement du lien dans une alerte e-mail de workflow ou une notification. (CAMP-51874)

## Version 23.1 - Version printemps/été 2023 {#apr-23}

### Améliorations {#e-rn-improvements}

* Le service de messagerie push a été modernisé afin d’optimiser le support. (CAMP-47959)
* Le service de messagerie SMS a été optimisé afin d’offrir une meilleure stabilité. (CAMP-52217)
* Adobe a apporté de nombreux correctifs d’accessibilité afin d’améliorer la facilité d’utilisation globale de l’application. Voici quelques exemples d’amélioration de l’accessibilité :
   * L’accessibilité clavier de l’interface a été optimisée dans de nombreux écrans.
   * L’application a été améliorée pour les utilisateurs et utilisatrices d’écrans tactiles.
   * La couleur de plusieurs éléments de l’interface a été modifiée afin d’améliorer la visibilité.

### Autres changements  {#e-rn-changes}

* Ajout du **Workflow de création d’enrichissement de rapports** prêt à l’emploi. Une fois que vous avez importé un mapping de ciblage d’une instance à une autre, il vous suffit d’exécuter le workflow pour importer les entrées d’enrichissement de rapports correspondantes. (CAMP-52452)

### Problèmes résolus{#e-rn-patches}

* Correction d’un problème qui entraînait une erreur de délai d’expiration lors de l’affichage du rapport **Hot Click**. (CAMP-51582)
* Correction d’un problème qui empêchait l’utilisation de l’intégration au service **Places**. (CAMP-51923)
* Correction d’un problème qui empêchait le bon fonctionnement du planificateur de workflow. (CAMP-52003)
* Correction d’un problème qui empêchait l’affichage des détails de la répartition lors de la visualisation de la version PDF d’un rapport dynamique personnalisé contenant un grand nombre de données. (CAMP-52178)
* Correction d’un problème qui entraînait l’affichage d’un message d’erreur lors de l’accès aux rapports. (CAMP-52500)
* Correction d’un problème qui appliquait par erreur le paramètre du connecteur SMS **Limiter les instances MTA pour ce compte** à tous les canaux au lieu de l’appliquer uniquement aux SMS. (CAMP-52640)
