---
title: Notes de mise à jour initiales
description: Notes de mise à jour initiales
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 46c5454ad712910c88bfda7c067fda0337b043d9
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 28%

---


# Notes de mise à jour initiales {#e-new-release}

Cette page décrit les améliorations et correctifs inclus dans la prochaine version de Campaign Standard.

>[!CAUTION]
>
> Ce contenu est sujet à des modifications sans préavis jusqu&#39;à la date de mise à niveau des environnements d&#39;évaluation. Pour en savoir plus, consultez la [page du calendrier des versions](../../rn/using/release-planning.md).

## Version 23.2 - Version d’automne/hiver 2023 {#fall-23}

>[!AVAILABILITY]
>
>Cette version est disponible uniquement pour un ensemble d’organisations (disponibilité limitée). Pour plus d’informations, contactez votre représentant Adobe.

### Améliorations {#e-rn-improvements}

* **Intégration avec Adobe Experience Manager**. Lors de la création d&#39;un modèle de diffusion personnalisé pour les messages transactionnels dans Adobe Experience Manager, vous pouvez désormais sélectionner et utiliser les champs de personnalisation définis dans Campaign Standard dans une liste déroulante.

* **Expiration des cookies** - L’expiration par défaut des cookies est désormais fixée à 6 mois, conformément aux recommandations de l’Agence française de protection des données (CNIL).

* **Amélioration de la recherche de profil** - La recherche de profil a été optimisée afin que les scénarios de délai d’expiration de la recherche puissent être réduits.

* **Localisation** - Les traductions du terme &quot;audience&quot; lorsqu’elles font référence à un groupe de profils destinés à recevoir un message ont été harmonisées dans tous les produits Digital Experience pour les langues suivantes :

   * Allemand : Zielgruppe
   * Portugais du Brésil : público-alvo
   * Espagnol : público desatario

  Ces modifications seront progressivement déployées avec la prochaine interface utilisateur et les prochaines versions de la documentation.

### Autres changements  {#e-rn-other-changes}

* Les messages transactionnels prennent désormais en charge l’utilisation de plusieurs affinités séparées par des virgules.

### Correctifs {#e-rn-fixes}

* Correction d’une régression qui pouvait entraîner des problèmes de performances lors de l’utilisation de workflows volumineux. (CAMP-53369)
* Correction d’un problème qui empêchait le fonctionnement du lien de l’email dans une alerte de workflow ou une notification. (CAMP-51874)
