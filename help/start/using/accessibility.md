---
solution: Campaign Standard
product: campaign
title: Accessibilité dans Adobe Campaign Standard
description: Découvrez la prise en charge de l’accessibilité dans l’espace de travail Adobe Campaign Standard.
audience: designing
content-type: reference
topic-tags: accessibility
translation-type: tm+mt
source-git-commit: 6632216ce4697892ea08b32641c9c026482ca713
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 100%

---


# Accessibilité dans Adobe Campaign Standard {#accessibility-acs}

Découvrez la prise en charge de l’accessibilité dans l’espace de travail Adobe Campaign Standard.

L’accessibilité consiste à rendre des produits utilisables par les personnes ayant des déficiences visuelles, auditives, cognitives, motrices et autres. Parmi les exemples de fonctionnalités d’accessibilité pour les logiciels, citons la prise en charge des lecteurs d’écran, les équivalents de texte pour les graphiques, les raccourcis clavier, le changement des couleurs d’affichage en contraste élevé, etc.

Adobe Campaign Standard fournit quelques outils qui le rendent accessible pour l’utilisation, tels que le contraste, la navigation au clavier, l’aide contextuelle et le redimensionnement réactif.

## Fonctionnalités d’accessibilité {#accessibility-features}

### Contraste {#contrast}

L’interface utilisateur d’Adobe Campaign Standard s’efforce de fournir un contraste suffisant dans l’application afin de garantir une expérience d’affichage accessible aux utilisateurs présentant une faible vision ou des défauts de vision des couleurs.

* Les icônes de mise en pause et d’annulation des workflows ont été mises à jour afin d’améliorer le contraste entre l’arrière-plan et le premier plan.

   ![](assets/accessibility_1.png)

* Le texte affiché en cas de réussite d’une diffusion contenait un texte vert volumineux avec un contraste insuffisant entre l’arrière-plan et le premier plan. Le contraste a été mis à jour avec un rapport minimum de 3:1.

   ![](assets/accessibility_2.png)

* Adobe Campaign Standard s’assure que la couleur, la forme ou l’emplacement ne sont pas les seules méthodes utilisées pour communiquer des informations ou la hiérarchie.

### Interface utilisateur {#user-interface}

L’interface utilisateur d’Adobe Campaign Standard facilite l’affichage et l’écoute du contenu, notamment la séparation du premier plan de l’arrière-plan et l’ajout de textes alternatifs aux différents boutons disponibles.

* Lorsque l’utilisateur laisse vide un champ d’ID obligatoire, un graphique indique visuellement quel champ comporte une erreur avec un texte de message d’erreur.

   ![](assets/accessibility_3.png)

* Le contenu qui s’affiche au survol ou au focus peut être ignoré par l’utilisateur et n’obscurcit aucun autre contenu.

   ![](assets/accessibility_4.png)

* Des textes alternatifs pour les boutons d’image ont été ajoutés et peuvent être lus au lieu d’afficher une illustration.

   ![](assets/accessibility_5.png)

* Lors de l’utilisation de listes, les cellules d’en-têtes de tableau de données ne sont pas vides dans l’angle du tableau.

### Créer un redimensionnement réactif pour plusieurs appareils {#resize-devices}

Lors de la conception pour plusieurs appareils et plateformes, il est important de créer une expérience transparente pour les tailles d’écran dans les résolutions des appareils mobiles et des ordinateurs de bureau.

Adobe Campaign Standard vous permet de concevoir et de tester des emails et des notifications push sur différents appareils, tels que : iPhone, appareils Android, iPad, tablette Android et bureau.

![](assets/accessibility_6.png)

## Aide contextuelle {#contextual-help}

L’aide contextuelle peut vous aider à mieux comprendre les différents champs et fonctionnalités demandés disponibles. Il vous guide également à travers la documentation du produit pour en savoir plus sur la fonctionnalité sélectionnée.

Lors de la conception d’un email, vous pouvez placer le curseur sur le bouton d’informations. Une info-bulle s’affiche, fournissant des descriptions de fonctionnalités et des liens vers la documentation du produit.

![](assets/accessibility_7.png)

## Prise en charge des agrandisseurs d’écran {#screen-magnifiers}

Un lecteur d’écran lit le texte qui s’affiche sur l’écran de l’ordinateur. Il lit également les informations non textuelles, telles que les libellés de boutons ou les descriptions d’images dans l’application, fournies dans les balises ou attributs d’accessibilité.

Dans Adobe Campaign Standard, le contenu et les fonctionnalités sont toujours disponibles même si l’utilisateur remplace les propriétés d’espacement du texte.

## Travailler dans la langue que vous préférez {#languages}

Adobe Campaign Standard est disponible dans différentes langues : anglais, français et allemand.

Veuillez noter que la langue est configurée à l’installation et ne peut pas être modifiée par la suite.

## Raccourcis clavier {#shortcuts}

### Page d’accueil {#homepage-shortcuts}

| Raccourci | Action |
|:-:|:-:|
| Onglet | Parcourir les différents éléments de l’interface utilisateur |
| Entrée ou Espace | Activer l’élément sélectionné |

### Concepteur d’email {#email-designer-shortcuts}

| Raccourci | Action |
|:-:|:-:|
| Ctrl + Z | Annuler |
| Ctrl + Y | Rétablir |

### Rapports dynamiques {#report-shortcuts}

| Raccourci | Action |
|:-:|:-:|
| Ctrl + O | Ouvrir le projet |
| Ctrl + S | Enregistrer |
| Maj + Ctrl + S | Enregistrer sous |
| Alt + R | Actualiser le projet |
| Maj + Ctrl + V | Télécharger le fichier CSV |
| Alt + P | Imprimer |
| Ctrl + Z | Annuler |
| Ctrl + Maj + Z | Rétablir |
| Alt + B | Nouveau panneau vierge |
| Alt + A | Nouvelle forme libre |
| Alt + 1 | Nouveau tableau à structure libre |
| Alt + 2 | Nouvelle ligne |
| Alt + 3 | Nouvelle barre |
| Alt + S | Envoyer le rapport maintenant |
| Maj + Alt + S | Envoyer le rapport d’après le planning |
| Maj = Alt + L | Rapports différés |

## Autres lectures {#further-reading}

Adobe Campaign Standard s’efforce de fournir un niveau d’accessibilité toujours plus élevé, ce qui rend le produit facile à utiliser pour tous.

Nous vous encourageons à utiliser le [formulaire de commentaires sur l’accessibilité d’Adobe](https://www.adobe.com/accessibility/feedback.html) pour nous faire part de suggestions d’amélioration et des problèmes d&#39;accessibilité que vous rencontrez.

Vous pouvez également consulter les [notes de mise à jour d’Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=fr#release-notes) pour suivre les dernières améliorations et fonctionnalités.