---
title: Bonnes pratiques relatives à la conception de contenu
seo-title: Bonnes pratiques relatives à la conception de contenu
description: Bonnes pratiques relatives à la conception de contenu
seo-description: Lisez ces recommandations afin de garantir un fonctionnement optimal de l'éditeur.
page-status-flag: jamais activé
uuid: ad 74 f 49 d -999 f -4140-89 b 0-d 1 ead 8642 d 89
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: conception
content-type: référence
topic-tags: about-content-design
discoiquuid: d 33 f 5 f 14-a 4 e 3-4327-bd 16-eb 3135 a 32076
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Bonnes pratiques relatives à la conception de contenu{#content-design-best-practices}

Afin de garantir un fonctionnement optimal de l'éditeur, il est recommandé de respecter les recommandations suivantes :

* Les feuilles de style SCSS ne sont pas prises en charge. Utilisez des feuilles de style CSS standard si vous importez des fichiers ZIP comportant votre contenu HTML.
* Lors de l'édition du **contenu d'un email** :

   Prévisualisez vos messages avant de les envoyer. Adobe Campaign permet de tester le rendu des emails à l'aide de Litmus. Voir à ce propos la section [Rendu des emails](../../sending/using/email-rendering.md).

* Lors de l'édition du **contenu d'une landing page** :

   * Avant d'importer un modèle de page HTML dans Adobe Campaign, assurez-vous que le modèle s'ouvre et s'affiche correctement dans les différents navigateurs.
   * Si la page HTML contient des scripts en langage JavaScript, ils doivent s'exécuter sans erreur hors de l'éditeur. Evitez en général d'utiliser des scripts dans le contenu des messages pour qu'il soit correctement traité par les clients de messagerie.
   * Lors de la construction d'un modèle, il est conseillé d'ajouter un attribut **'type'** aux balises . Cette information sera interprétée par l'éditeur et aidera l'utilisateur à associer un champ de la base de données au champ du formulaire lors du paramétrage de l'application Web.

      Exemple de code HTML dans le modèle :

      ```
      <input id="email" type="email" name="email"/>
      ```

      La liste officielle des attributs 'type' est disponible à l'adresse suivante : [http://www.w3schools.com/tags/att_input_type.asp](http://www.w3schools.com/tags/att_input_type.asp)

D'autres bonnes pratiques générales et de conception relatives aux messages sont présentées dans le guide pas à pas Adobe Campaign suivant : [Bonnes pratiques de diffusion avec Adobe Campaign](https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_DeliveryBestPractices.html).
