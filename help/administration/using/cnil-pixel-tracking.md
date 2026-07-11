---
title: Conseils de la CNIL sur les pixels de tracking email
description: Découvrez les conseils mis à jour de la CNIL sur les pixels de tracking e-mail et les contrôles Adobe Campaign Standard qui peuvent prendre en charge vos efforts de conformité.
audience: administration
role: Admin
level: Experienced
hide: true
source-git-commit: 75f1f4ad8f7173f4601c9cff1ea93bf4092f274d
workflow-type: tm+mt
source-wordcount: '1083'
ht-degree: 0%

---


# Comprendre les nouveaux conseils de la CNIL sur les pixels de tracking email {#cnil-pixel-tracking}

>[!BEGINSHADEBOX]

**Sur cette page :** Découvrez la recommandation d’avril 2026 de la CNIL sur les pixels de tracking e-mail et découvrez les contrôles Adobe Campaign Standard (activation du tracking, suivi au niveau des liens, modèle de données de consentement, mécanismes de désinscription et rapports) qui peuvent soutenir vos efforts de conformité.

>[!ENDSHADEBOX]

Cette publication est fournie à titre d&#39;information uniquement. Il ne s&#39;agit pas d&#39;un avis juridique et ne garantit pas votre conformité avec la loi applicable. Les fonctionnalités du produit Adobe Campaign Standard décrites ci-dessous sont des éléments de base qui, configurés et utilisés de manière appropriée, peuvent prendre en charge une implémentation conforme. Chaque client est responsable de déterminer et de respecter ses obligations en vertu de la loi applicable.

## Présentation {#overview}

Le 14 avril 2026, la *Commission nationale de l&#39;informatique et des libertés* (CNIL), l&#39;autorité française de protection des données, a publié une [recommandation sur l&#39;utilisation des pixels de tracking dans les emails](https://www.cnil.fr/sites/default/files/2026-04/recommandation-pixels_de_suivi.pdf). Ces conseils clarifient le moment où le consentement est requis et soulignent l’importance de bonnes pratiques de consentement pour le suivi des pixels d’e-mail. Cette politique peut avoir un impact sur les pratiques d’envoi pour toute entité diffusant des e-mails aux abonnés basés en France.

La CNIL a prévu un délai de trois mois à compter de la date de la recommandation pour que les entreprises informent leurs destinataires d&#39;emails (« utilisateurs ») de la présence des pixels de tracking, de leur finalité et du droit de désinscription des utilisateurs. Pendant cette période de transition, les clients doivent informer les utilisateurs du suivi des pixels et fournir un droit d’opposition si nécessaire. La CNIL devrait commencer ses activités d&#39;application après le 14 juillet 2026.

Alors que la CNIL et d&#39;autres organismes de réglementation clarifient les conseils sur le tracking des pixels et les problèmes associés, Adobe continuera à surveiller les mises à jour et à informer les clients des fonctionnalités techniques des produits Adobe qui prennent en charge le marketing par e-mail, y compris Adobe Campaign Standard.

Les applications d’exécution du marketing par e-mail d’Adobe, notamment Adobe Journey Optimizer, Journey Optimizer B2B, Adobe Campaign et Marketo Engage, fournissent des contrôles qui peuvent aider les clients à gérer le suivi des ouvertures au niveau de la diffusion ou de l’e-mail. Il incombe aux clients de déterminer leurs propres obligations de conformité en vertu des conseils de la CNIL et d’autres lois applicables, mais ces fonctionnalités peuvent soutenir les efforts de conformité des clients.

### Qu’est-ce qu’un pixel de tracking e-mail ? {#tracking-pixel}

Un pixel de tracking d’e-mail est une image transparente 1x1 incorporée dans l’HTML d’un e-mail. Lorsque le client de messagerie du destinataire charge cette image, le pixel envoie un ping à un serveur qui enregistre des données telles qu’une date et une heure, un type d’appareil, un client de messagerie et parfois une adresse IP pour un emplacement approximatif. Ce journal est ensuite lié à l’enregistrement d’un destinataire, ce qui permet aux spécialistes marketing de voir si un e-mail est ouvert.

### Service clientèle {#support}

Les clients qui demandent de l’aide pour mettre en œuvre les modifications décrites ci-dessus peuvent interagir avec leur écosystème Adobe existant. Pour toute question technique sur les fonctionnalités Adobe référencées, contactez votre responsable du succès client ou votre gestionnaire de compte technique.

## Fonctionnalité de Adobe Campaign Standard liée au tracking e-mail {#acs-functionality}

Les clients peuvent utiliser des mécanismes de suivi, de schéma et de personnalisation natifs de Adobe Campaign Standard pour gérer certains éléments lors de la configuration de l’architecture.

### Classification d’e-mail {#email-classification}

Étendez le modèle de diffusion avec un champ personnalisé indiquant le type d’e-mail (authentification, délivrabilité seule, transactionnel, marketing avec consentement, prospection B2B). Dans Campaign Standard, les modèles de diffusion peuvent comporter des champs personnalisés qui s’inscrivent dans la logique des rapports et des workflows. Cette classification détermine le suivi approprié pour chaque envoi.

[Découvrez comment créer et utiliser des modèles de diffusion](../../channels/using/creating-an-email.md)

### Modèle de données de consentement {#consent-data-model}

Étendez la ressource Profil via le mécanisme des ressources personnalisées de Campaign Standard (**Administration > Développement > Ressources personnalisées**) pour utiliser des indicateurs de consentement spécifiques, des horodatages de consentement et la date de l’ouverture la plus récente (date uniquement — aucun composant d’heure). Une ressource personnalisée distincte liée au profil capture le journal des événements de consentement en ajout seul qui prend en charge les preuves de consentement individuelles. Comme les pages de destination de Campaign Standard peuvent écrire directement dans les champs de profil, l’état de consentement actuel est gérable en mode natif ; le journal de consentement est écrit via l’API REST Adobe Campaign Standard (`/profileAndServicesExt`) une fois qu’une préférence est envoyée.

[Découvrez comment créer ou étendre une ressource](../../developing/using/creating-or-extending-the-resource.md)

[Découvrez comment interagir avec des ressources personnalisées via l’API.](../../api/using/interacting-with-custom-resources.md)

### Émission de pixels {#pixel-emission}

Adobe Campaign Standard contrôle le tracking au niveau de la diffusion via le bouton (bascule) **[!UICONTROL Activer le tracking]** dans les propriétés de la diffusion ou du modèle. Pour les diffusions pour lesquelles le suivi des ouvertures n’est pas légal (e-mails d’authentification uniquement ou de re-sollicitation), ce bouton est désactivé. Pour les diffusions pour lesquelles l’émission de pixels par objectif est appropriée, une approche consiste à désactiver le pixel standard inséré automatiquement et à utiliser des blocs de contenu contenant des éléments d’image suivis 1×1 conditionnels (un par objectif) où chaque image se voit attribuer une catégorie d’URL (`PIX_DELIV`, `PIX_PERF`, `PIX_PROFILE`, `PIX_FRAUD`) et s’affiche uniquement lorsque l’indicateur de consentement correspondant du destinataire est défini sur true.

[Découvrez comment configurer les paramètres de tracking e-mail](configuring-email-channel.md#tracking-parameters)

[Découvrez comment gérer les URL trackées dans Email Designer](../../designing/using/links.md#about-tracked-urls)

[Découvrez comment ajouter des blocs de contenu](../../designing/using/personalization.md#adding-a-content-block)

### Retrait {#withdrawal}

Ajoutez un lien **Gérer les préférences du suivi** à chaque pied de page d’e-mail, distinct du lien de désabonnement. Le lien pointe vers une page de destination Campaign Standard authentifiée par le biais du mécanisme de `recipientId` ou de `urlSubscription`. Le destinataire bascule ses indicateurs de consentement par objectif et les envois. Lors de la confirmation, un petit appel à l’API REST Campaign Standard écrit l’événement de retrait dans le journal de consentement. La recommandation indique que ce lien est lui-même exempté de l’exigence de suivi en matière de sécurité.

[Découvrez comment configurer des pages de destination d’opt-in et d’opt-out](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md#setting-up-opt-in-and-opt-out-landing-pages)

[Découvrez comment commencer à utiliser les pages de destination](../../channels/using/getting-started-with-landing-pages.md)

### Preuve de consentement {#consent-proof}

Chaque modification du consentement (capture lors de l’inscription, mise à jour à partir de la page Préférences, expiration) crée une ligne dans la ressource personnalisée du journal de consentement, portant le code de version du libellé, l’horodatage de capture, la source de capture et la portée. Ce journal peut être interrogé via l’explorateur Campaign Standard, exposé via l’API REST et exportable pour révision DPO via un workflow planifié.

[Découvrez comment interagir avec des ressources personnalisées via l’API.](../../api/using/interacting-with-custom-resources.md)

### Gouvernance de la re-sollicitation {#re-solicitation}

Un champ de `cusLastPixelRefusalDate` personnalisé sur le profil, associé à une règle de filtrage de typologie qui exclut les profils où ce champ se trouve dans une période choisie, empêche la nouvelle sollicitation des destinataires qui ont décliné l’offre au cours de cette période. Un workflow planifié gère les délais d’expiration du consentement des clients en signalant les enregistrements obsolètes et en écrivant les événements d’expiration dans le journal de consentement.

[Découvrez comment utiliser les règles de typologie.](../../sending/using/about-typology-rules.md)

[Découvrez comment gérer les règles de typologie](../../sending/using/managing-typology-rules.md)

### Reporting {#reporting}

Les rapports dynamiques Campaign Standard reposent sur des catégories d’URL et des dimensions de profil. Les catégories d’URL spécifiques introduites au-dessus de la surface dans les rapports dynamiques sous la forme de nouvelles dimensions, ce qui permet aux opérateurs de découper les données d’ouverture et de clic par objectif. La distinction entre le suivi consenti et non consenti est visible en mode natif une fois que les catégories d’URL sont en place.

[Découvrez comment commencer à utiliser les rapports dynamiques](../../reporting/using/about-dynamic-reports.md)

[Découvrez les indicateurs de tracking](../../reporting/using/tracking-indicators.md)
