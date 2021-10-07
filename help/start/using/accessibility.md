---
title: Accessibilité dans Adobe Campaign Standard
description: Découvrez la prise en charge de l’accessibilité dans l’espace de travail Adobe Campaign Standard.
audience: designing
content-type: reference
topic-tags: accessibility
feature: Campaigns
role: User
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: ht
source-wordcount: '650'
ht-degree: 100%

---

# Accessibilité dans Adobe Campaign Standard {#accessibility-acs}

Découvrez la prise en charge de l’accessibilité dans l’espace de travail Adobe Campaign Standard.

L’accessibilité consiste à rendre des produits utilisables par les personnes ayant des déficiences visuelles, auditives, cognitives, motrices et autres. Les exemples de fonctionnalités d’accessibilité pour les produits logiciels incluent le classement sémantique du contenu structuré de manière sémantique, la prise en charge des lecteurs d’écran, les équivalents textuels pour les graphiques, les raccourcis clavier, etc.

Adobe Campaign Standard offre des fonctionnalités qui rendent plus accessible l’utilisation des contrastes, des libellés, des contenus structurés, de la navigation clavier et de l’aide contextuelle.

## Fonctionnalités d’accessibilité {#accessibility-features}

### Contraste et couleur {#contrast}

L’interface utilisateur d’Adobe Campaign Standard s’efforce de fournir un contraste suffisant dans l’application afin de garantir une expérience d’affichage accessible aux utilisateurs présentant une faible vision ou des défauts de vision des couleurs.

* Le texte et les en-têtes de grande taille ont été améliorés pour atteindre un rapport de contraste de 3:1.

   ![](assets/accessibility_2.png)

* Le contenu de l’aide et le corps de texte de l’application ont été mis à jour pour respecter un rapport de contraste de 4,5:1.

* Les icônes de mise en pause et d’annulation des workflows ont été mises à jour afin d’améliorer le contraste entre les couleurs d’arrière-plan et de premier plan.

   ![](assets/accessibility_1.png)

* La couleur, la forme et l’emplacement ne sont pas les seules méthodes utilisées pour communiquer les informations ou la hiérarchie dans l’application.

### Interface utilisateur {#user-interface}

L’interface utilisateur d’Adobe Campaign Standard facilite l’interaction entre tous les utilisateurs et le contenu en ajoutant des textes alternatifs aux éléments visuels, et en utilisant une structure sémantique pour transmettre des informations visuellement et par programmation.

* Lorsque l’utilisateur laisse vide un champ d’ID obligatoire, un graphique indique visuellement quel champ contient une erreur à l’aide d&#39;un message d’erreur. Ces informations sont également transmises par programmation aux utilisateurs à l’aide de technologies d’assistance, telles que les lecteurs d’écran.

   ![](assets/accessibility_3.png)

* Le contenu qui s’affiche au survol ou au focus peut être ignoré par l’utilisateur et n’obscurcit aucun autre contenu.

   ![](assets/accessibility_4.png)

* Des textes alternatifs pour les images et des noms accessibles pour les boutons ont été ajoutés et peuvent être lus à haute voix avec une technologie d’assistance au lieu de s’appuyer uniquement sur des indices visuels pour identifier les éléments.

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## Aide contextuelle {#contextual-help}

L’aide contextuelle peut vous aider à mieux comprendre les différents champs et fonctionnalités demandés disponibles. Elle vous guide également à travers la documentation du produit pour en savoir plus sur la fonctionnalité sélectionnée.

Lors de la conception d’un email, vous pouvez accéder à une info-bulle qui fournit des descriptions de fonctions et des liens vers la documentation du produit.

![](assets/accessibility_7.png)

## Prise en charge de la technologie d’assistance {#screen-magnifiers}

Nous nous efforçons de rendre l’application Adobe Campaign Standard aussi utilisable que possible par diverses technologies d’assistance, y compris, mais sans s’y limiter, les claviers modifiés, les logiciels de grossissement d’écran, les lecteurs d’écran, les logiciels de reconnaissance vocale et d’autres dispositifs d’assistance.

## Travailler dans la langue que vous préférez {#languages}

Adobe Campaign Standard est disponible dans différentes langues : allemand, anglais et français.

Veuillez noter que la langue est configurée à l’installation et ne peut pas être modifiée par la suite.

## Raccourcis clavier {#shortcuts}

### Page d’accueil {#homepage-shortcuts}

| Action | Raccourci |
| --- | --- |
| Parcourir les différents éléments de l’interface utilisateur | Tabulation |
| Activer l’élément sélectionné | Entrée ou Barre d&#39;espacement |

### Concepteur d&#39;email {#email-designer-shortcuts}

| Action | Raccourci Windows | Raccourci macOS |
| --- | --- | --- |
| Annuler | Ctrl + Z | Commande + Z |
| Rétablir | Ctrl + Y | Maj + Commande + Z |

### Rapports dynamiques {#report-shortcuts}

| Action | Raccourci Windows | Raccourci macOS |
| --- | --- | --- |
| Ouvrir un projet | Ctrl + O | Commande + O |
| Enregistrer | Ctrl + S | Commande + S |
| Enregistrer sous | Maj + Ctrl + S | Maj + Commande + S |
| Actualiser le projet | Alt + R | Commande + R |
| Télécharger le fichier CSV | Maj + Ctrl + V | Maj + Commande + V |
| Imprimer | Alt + P | Commande + P |
| Annuler | Ctrl + Z | Commande + Z |
| Rétablir | Ctrl + Y | Maj + Commande + Z |
| Nouveau panneau vierge | Alt + B | Option + B |
| Nouvelle forme libre | Alt + A | Option + A |
| Nouveau tableau à structure libre | Alt + 1 | Option + 1 |
| Nouvelle ligne | Alt + 2 | Option + 2 |
| Nouvelle barre | Alt + 3 | Option + 3 |
| Envoyer le rapport maintenant | Alt + S | Option + S |
| Envoyer le rapport d’après le planning | Maj + Alt + S | Maj + Option + S |
| Rapports différés | Maj+ Alt + L | <!-- Should be 'Shift + Option + L ' but does not work on Mac --> |

## Autres lectures {#further-reading}

Adobe Campaign Standard s’efforce de fournir un niveau d’accessibilité toujours plus élevé, ce qui rend le produit facile à utiliser pour tous.

Nous vous encourageons à utiliser le [formulaire de commentaires sur l’accessibilité d’Adobe](https://www.adobe.com/accessibility/feedback.html) pour nous faire part de suggestions d’amélioration et des problèmes d&#39;accessibilité que vous rencontrez.

Vous pouvez également consulter les [notes de mise à jour d’Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=fr#release-notes) pour suivre les dernières améliorations et fonctionnalités.
