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
translation-type: tm+mt
source-git-commit: 021bea88b69a85b9a9535143ec8d689858af517b

---


# Conception d'emails multi-solution {#multi-solution-email-design}

Adobe Campaign propose plusieurs options de création d'email. Vous pouvez utiliser des solutions telles que Dreamweaver pour modifier le contenu de votre courrier électronique et créer des messages réactifs dans le concepteur de courrier électronique. Vous pouvez également envoyer par courrier électronique du contenu avec Adobe Experience Manager et l’utiliser dans vos courriers électroniques dans Adobe Campaign Standard.

## Editer le contenu dans Dreamweaver {#editing-content-in-dreamweaver}

L'intégration d'Adobe Campaign Standard à Dreamweaver permet d'éditer le contenu d'un email dans l'interface de Dreamweaver. Vous avez accès à la puissante interface de Dreamweaver pour concevoir et développer du contenu de messagerie réactive.

* **Synchronisation bidirectionnelle**

   Chaque fois qu’une modification est effectuée dans un produit, elle est mise à jour en temps réel dans l’autre. Si vous souhaitez modifier la couleur du texte dans Dreamweaver, dès que vous le modifiez, la couleur du texte est activée dans Campaign. De plus, lorsque vous sélectionnez du code dans Dreamweaver ou dans Campaign, puisque les numéros de ligne sont identiques, la sélection reste entre les deux produits, ce qui est très utile lorsque vous recherchez quelque chose de spécifique dans le code.

* **Télécharger des images locales vers Adobe Campaign via Dreamweaver**

   Lorsque vous créez ou modifiez un courrier électronique dans Dreamweaver, vous pouvez simplement sélectionner une image sur votre bureau ou sur votre ordinateur local. Même si Dreamweaver vous a toujours permis de le faire, quand Dreamweaver et Campaign sont connectés, le fichier local est immédiatement téléchargé vers le serveur Adobe Campaign. Par conséquent, il n'est pas nécessaire de télécharger les images à mesure que le contenu change. De plus, il garantit que les dernières images sont toujours en direct dans Campaign.

* **Ajout de la personnalisation de campagne dans Dreamweaver**

   Le développeur d'email n'a plus besoin d'ajouter du texte du type `[[FIRSTNAME_PLACEHOLDER]]` ni de rechercher la syntaxe des tables de votre modèle de données. La barre d'outils Campaign dans Dreamweaver se connecte directement au modèle de données de votre instance Campaign. Cela signifie que vous pouvez extraire toutes les données que vous souhaitez pour la personnalisation de quelque chose comme Prénom à Adresse. Si vous avez créé des blocs de contenu dans Campaign, vous pouvez également les placer directement dans Dreamweaver.

Cette fonctionnalité est présentée dans la documentation de Dreamweaver, accessible [ici](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). Une [vidéo](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) de démonstration est également disponible.

## Editer le contenu dans Experience Manager {#editing-content-in-experience-manager}

Un contenu d'email peut être édité dans Experience Manager puis utilisé pour un ou plusieurs messages d'email dans Adobe Campaign Standard. Refer to [this document](../../integrating/using/integrating-with-experience-manager.md).

## Comparaison des options de conception d'email {#email-design-options-comparison}

Adobe Campaign propose plusieurs options de création d'email. Le tableau ci-dessous présente les principales possibilités, les principaux avantages et les principales limites pour chacun d'entre eux.

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
   <td> <strong>Démarrer le courrier électronique vide</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Écriture HTML</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Non pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Mettre à jour HTML</strong><br /> </td> 
   <td> Uniquement dans un composant HTML<br /> </td> 
   <td> Non pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personnalisation de base</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personnalisation avancée</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Non pris en charge<br /> </td> 
   <td> Non pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Preuve/Aperçu</strong><br /> </td> 
   <td> Pris en charge<br /> </td> 
   <td> Aperçu dans AEM<br /> Proof dans Campaign<br /> </td> 
   <td> Aperçu et preuve dans Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Liste des produits</strong><br /> </td> 
   <td> Pris en charge dans les messages transactionnels de courrier électronique<br /> </td> 
   <td> Non pris en charge<br /> </td> 
   <td> Non pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Avantages</strong><br /> </td> 
   <td> 
     <p>- Création facile de courriers électroniques par glisser-déposer</p>
     <p>- Fonctionnalités similaires à l’éditeur de contenu hérité</p>
     <p>- Contenu réutilisable avec des fragments</p>
  </td> 
   <td> 
     <p>- Réutilisation des ressources du site Web dans les courriers électroniques</p>
     <p>- Exploiter la puissance d'Experience Manager dans le contenu des courriers électroniques</p>
    </td> 
   <td> 
    <p>- Possibilité pour un développeur de coder directement un courrier électronique</p>
    <p>- Synchronisation bidirectionnelle</p>
    <p>- Modification hors ligne dans Dreamweaver et synchronisation ultérieure</p>
    <p>- Téléchargement d'images vers Adobe Campaign via Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limites</strong><br /> </td> 
   <td> 
     <p>- Aucun contenu conditionnel dans les fragments</p>
     <p>- Utilisation de fragments Experience Manager impossible</p>
  </td> 
   <td> 
     <p>- Personnalisation avancée difficile à implémenter</p>
     <p>- Besoin d’envoyer des tests dans Adobe Campaign</p>
  </td> 
   <td> Contenu dynamique non pris en charge<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Audience</strong><br /> </td> 
   <td> Les marketeurs qui souhaitent conserver la flexibilité nécessaire pour utiliser les composants HTML en combinaison avec les fonctions de glisser-déposer<br /> </td> 
   <td> Les marketeurs qui utilisent déjà Experience Manager et souhaitent utiliser des modèles de courrier électronique standard avec peu de personnalisation<br /> </td> 
   <td> Développeurs qui souhaitent coder le contenu des courriers électroniques et s’intégrer directement à Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Pour en savoir plus</strong><br /> </td> 
   <td> Voir <a href="../../designing/using/overview.md">A propos du Concepteur d'email</a>.<br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a>.<br /> </td> 
   <td> Consultez la section <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver et Campaign</a> et regardez cette <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vidéo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>
