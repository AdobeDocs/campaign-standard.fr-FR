---
title: 'Conception d''emails par le biais des intégrations d''Adobe Campaign '
description: Découvrez comment concevoir des emails via les intégrations d'Adobe Campaign dans le Concepteur d'email.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: ht
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---

# Conception d'emails multi-solution {#multi-solution-email-design}

## Editer le contenu dans Dreamweaver {#editing-content-in-dreamweaver}

L'intégration d'Adobe Campaign Standard à Dreamweaver permet d'éditer le contenu d'un email dans l'interface de Dreamweaver. Vous avez accès à l'interface puissante de Dreamweaver pour concevoir du contenu d'email réactif.

* **Synchronisation bidirectionnelle**

   Dès qu'un élément est édité dans un produit, il est mis à jour en temps réel dans l'autre. Si vous voulez changer la couleur du texte dans Dreamweaver, dès que vous réalisez ce changement, la couleur du texte est synchronisée dans Campaign. En outre, lorsque vous sélectionnez du code dans Dreamweaver ou Campaign, la sélection demeure entre les deux produits, car les numéros de lignes sont identiques. Cela peut se révéler très utile lorsque vous recherchez un élément spécifique dans le code.

* **Télécharger des images locales vers Adobe Campaign via Dreamweaver**

   Lorsque vous créez ou éditez un email au sein de Dreamweaver, vous pouvez simplement sélectionner une image de votre ordinateur de bureau ou poste local. Même si Dreamweaver vous a toujours permis de le faire, quand Dreamweaver et Campaign sont connectés, le fichier local est immédiatement téléchargé vers le serveur Adobe Campaign. Par conséquent, il n'est pas nécessaire de télécharger les images à mesure que le contenu change. De plus, cela assure que les images les plus récentes sont toujours en ligne dans Campaign.

* **Ajouter la personnalisation de Campaign dans Dreamweaver**

   Le développeur d'email n'a plus besoin d'ajouter du texte du type `[[FIRSTNAME_PLACEHOLDER]]` ni de rechercher la syntaxe des tables de votre modèle de données. La barre d'outils Campaign dans Dreamweaver se connecte directement au modèle de données de votre instance Campaign. Cela signifie que vous pouvez extraire toutes les données que vous voulez pour les personnaliser, du prénom à l'adresse. Si vous avez créé des blocs de contenu au sein de Campaign, vous pouvez également les intégrer directement dans Dreamweaver.

Cette fonctionnalité est présentée dans la documentation de Dreamweaver, accessible [ici](https://helpx.adobe.com/fr/dreamweaver/using/working-with-dreamweaver-and-campaign.html). Une [vidéo](https://helpx.adobe.com/fr/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) de démonstration est également disponible.

## Editer le contenu dans Experience Manager {#editing-content-in-experience-manager}

Un contenu d'email peut être édité dans Experience Manager puis utilisé pour un ou plusieurs messages d'email dans Adobe Campaign Standard. Reportez-vous à [ce document](../../integrating/using/integrating-with-experience-manager.md).

## Comparaison des options de conception d'email {#email-design-options-comparison}

Adobe Campaign propose plusieurs options de création d'email. Le tableau ci-après présente les possibilités, avantages et limites de chacune d'elles.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Concepteur d'email<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Commencer à partir d'un email vide</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Prise en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ecrire du code HTML</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Pas pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mettre à jour le code HTML</strong><br /> </td> 
   <td> Uniquement à l'intérieur d'un composant HTML<br /> </td> 
   <td> Pas pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personnalisation de base</strong><br /> </td> 
   <td> Prise en charge<br /> </td> 
   <td> Prise en charge<br /> </td> 
   <td> Prise en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personnalisation avancée</strong><br /> </td> 
   <td> Prise en charge<br /> </td> 
   <td> Pas prise en charge<br /> </td> 
   <td> Pas prise en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>BAT/Prévisualisation</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Prévisualisation dans AEM<br /> BAT dans Campaign<br /> </td> 
   <td> Prévisualisation et BAT dans Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Listes de produits</strong><br /> </td> 
   <td> Prises en charge dans les emails transactionnels<br /> </td> 
   <td> Pas prises en charge<br /> </td> 
   <td> Pas prises en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avantages</strong><br /> </td> 
   <td> 
     - Création facile d'emails grâce aux opérations de glisser-déposer<br/>
     - Fonctionnalités similaires à celles de l'ancien éditeur de contenu<br/>
     - Contenu réutilisable avec des fragments
  </td> 
   <td> 
     - Réutilisation des ressources du site web dans les emails<br/>
     - Utilisation des fonctionnalités d'Experience Manager dans les contenus d'email
    </td> 
   <td> 
    - Possibilité pour un développeur de coder directement un email<br/>
    - Synchronisation bidirectionnelle<br/>
    - Edition hors connexion dans Dreamweaver et synchronisation ultérieure<br/>
    - Chargement d'images dans Adobe Campaign via Dreamweaver
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limites</strong><br /> </td> 
   <td> 
     - Pas de contenu conditionnel dans les fragments<br/>
     - Utilisation impossible des fragments Experience Manager
  </td> 
   <td> 
     - Mise en œuvre difficile de la personnalisation avancée<br/>
     - Envoi de tests nécessaires dans Adobe Campaign
  </td> 
   <td> Contenu dynamique non pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Public visé</strong><br /> </td> 
   <td> Les marketeurs qui souhaitent conserver la possibilité d'utiliser des composants HTML avec des fonctionnalités de glisser-déposer.<br /> </td> 
   <td> Les marketeurs qui utilisent déjà Experience Manager et qui souhaitent utiliser des modèles d'email standard avec peu de personnalisation.<br /> </td> 
   <td> Les développeurs qui souhaitent coder des contenus d'email et s'intégrer directement avec Adobe Campaign.<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Pour en savoir plus</strong><br /> </td> 
   <td> Voir <a href="../../designing/using/overview.md">A propos du Concepteur d'email</a><br /> </td> 
   <td> Voir <a href="../../integrating/using/integrating-with-experience-manager.md">Intégration avec Experience Manager</a><br /> </td> 
   <td> Consultez la section <a href="https://helpx.adobe.com/fr/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver et Campaign</a> et regardez cette <a href="https://helpx.adobe.com/fr/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vidéo</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
