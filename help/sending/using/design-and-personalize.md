---
title: Créer du contenu personnalisé
seo-title: Créer du contenu personnalisé
page-status-flag: never-activated
uuid: a540efc7-105d-4c7f-a2ee-ade4d22b3445
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
discoiquuid: 0cbc4e92-482f-4dac-a1fb-b738e7127938
index: y
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '911'
ht-degree: 79%

---


# Créer du contenu personnalisé {#build-personalized-content}

Lors de la conception du contenu de votre message, évitez les problèmes courants qui peuvent vous empêcher d’exécuter votre diffusion. La plupart du temps, les erreurs possibles sont liées à la [personnalisation](../../designing/using/personalization.md), à la mise en forme lors de l’ [utilisation d’un contenu](../../designing/using/using-existing-content.md) existant - et à la [conversion d’un contenu](../../designing/using/using-existing-content.md#converting-an-html-content) HTML - et aux [images.](../../designing/using/images.md)

## Optimiser la personnalisation {#optimize-personalization}

Pour éviter des problèmes courants qui peuvent vous empêcher d’exécuter votre diffusion et d’améliorer l’expérience de vos destinataires, Adobe Campaign vous permet de personnaliser vos messages.

Vous pouvez utiliser les données des destinataires stockées dans la base de données Adobe Campaign ou collectées par le biais du tracking, des landing pages, des inscriptions, etc.
Les principes de base de la personnalisation sont présentés dans [cette section](../../designing/using/personalization.md).

Vérifiez que le contenu de votre message est correctement conçu pour éviter les erreurs généralement liées à la personnalisation.

Le contenu dynamique peut être ajouté manuellement pour afficher un contenu différent dans vos destinataires en fonction des conditions définies dans l’éditeur d’expressions. Lors de l’ajout de contenu dynamique, vous devez toujours laisser une variante par défaut pour les destinataires qui ne remplissent pas les conditions sélectionnées.
For more on dynamic content, refer to the [this section](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Conseils** : Prévisualisation de votre courrier électronique avec différents profils de test pour vous assurer que votre contenu dynamique a été correctement configuré.

## Créer du contenu optimisé {#optimize-content}

Lorsque vous créez vos emails, tenez compte des bonnes pratiques générales présentées ci-dessous.

* Gardez le design de vos emails simple

* Gardez les utilisateurs d’appareils mobiles à l’esprit

* Évitez les emails basés entièrement sur des images

* Utilisez des polices sécurisées pour les emails

* Encodez les caractères spéciaux

### Objet

Travaillez sur la [ligne d’objet](../../designing/using/subject-line.md) pour améliorer les taux d’ouverture :

* Évitez les objets trop longs. Utilisez 50 caractères au maximum

* Évitez de répéter des mots tels que « gratuit » ou « offre » qui peuvent être considérés comme des messages indésirables

* Évitez les majuscules et les caractères spéciaux tels que « ! », « £ », « € », « $ »

### Page miroir

Incluez toujours un lien de page miroir. La partie supérieure de l’email constitue la position idéale. [En savoir plus](../../designing/using/personalization.md#adding-a-content-block)

### Lien de désabonnement

Le lien désinscription est essentiel. Il doit être visible et valide et le formulaire doit être fonctionnel. Découvrez les consignes relatives aux liens de désinscription [dans cette section](../../designing/using/personalization.md#about-targeting-dimension).

By default, when the message is analyzed, a control [typology rule](../../sending/using/control-rules.md) checks whether an opt-out link has been included and generates a warning if it is missing.

**Conseil** : comme une erreur humaine est toujours possible, vérifiez du début à la fin le bon fonctionnement du lien de désabonnement avant chaque envoi. Par exemple, lors de l’envoi du BAT, vérifiez que le lien est valide, que le formulaire est en ligne et que la valeur du champ Ne plus contacter cette personne est changée en Oui.

Découvrez comment insérer un lien d’exclusion [dans cette section](../../designing/using/personalization.md#adding-a-content-block).

### Taille des emails

Pour éviter des problèmes de performances ou de délivrabilité, la taille maximale recommandée d’un email est d’environ **35 Ko**.

Pour maintenir la taille de l’email sous cette limite, tenez compte des possibilités suivantes :

* Supprimer les styles redondants ou inutilisés

* Déplacer une partie du contenu de l’email vers une landing page

* Minimiser votre code

Veillez à tester toutes les modifications avant l’envoi final

### Longueur des SMS

Par défaut, le nombre de caractère d&#39;un SMS respecte la norme de téléphonie mobile GSM (Global System for Mobile Communications). Les SMS utilisant l&#39;encodage GSM sont limités à 160 caractères, ou 153 caractères par SMS pour les messages envoyés en plusieurs parties.

La translittération consiste à remplacer un caractère d&#39;un SMS par un autre lorsque ce caractère n&#39;est pas pris en charge par la norme GSM. Notez que l&#39;insertion de champs de personnalisation dans le contenu du SMS peut introduire des caractères non pris en charge par l&#39;encodage GSM. Vous pouvez autoriser la translittération des caractères en cochant la case correspondante dans l&#39;onglet des paramètres du canal SMPP du **[!UICONTROL Compte externe]** correspondant.
En savoir plus dans [cette section](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Conseils** :

* Pour conserver tous les caractères de vos SMS, afin de ne pas altérer les noms propres par exemple, n&#39;activez pas la translittération.

* En revanche, si vos SMS contiennent beaucoup de caractères qui ne sont pas pris en charge par la norme GSM, activez la translittération afin de limiter le coût de vos envois.

En savoir plus dans [cette section](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Email en responsive design

Le responsive design des emails permet de s’assurer que le rendu d’un est optimal sur l’appareil sur lequel il est ouvert.

* Utilisez du code HTML en responsive design plutôt que du code HTML web

* Utilisez le mode Aperçu et envoyez des BAT pour tester le rendu sur le plus grand nombre d’appareils possible. Apprenez à [prévisualisation un message](../../sending/using/previewing-messages.md) avant l’envoi.

* Campaign Email Designer est fourni avec des modèles de conception réactifs formatés pour les périphériques mobiles. Learn more [in this page](../../designing/using/using-reusable-content.md#content-templates).

## Gestion des images {#manage-images}

Suivez les instructions ci-dessous pour l’utilisation des images.

### Empêcher le blocage des images

Certains clients de messagerie bloquent les images par défaut, et certains utilisateurs modifient leurs paramètres pour bloquer les images afin de réduire l’utilisation des données. Dans ce cas, si les images ne sont pas téléchargées, il est possible que l’ensemble du message soit perdu. Pour éviter cela :

* Équilibrez le contenu entre image et texte. Évitez les emails basés entièrement sur des images.

* Si le texte doit être contenu dans une image, utilisez du texte de titre et du texte alternatif pour vous assurer que votre message passe bien. Mettez en forme votre texte de titre et alternatif pour améliorer son aspect.

* Évitez d’utiliser des images de fond, car elles ne sont pas prises en charge par certains clients de messagerie.

### Rendre les images réactives

Essayez de rendre les images réactives et redimensionnables. Notez que ceci peut avoir un impact sur les coûts, car la création prend plus de temps.

### Utiliser des références absolues pour l’accès à l’image

Pour être accessibles depuis l&#39;extérieur, les images utilisées dans les emails et les ressources publiques associées aux opérations doivent être présentes sur un serveur accessible de l&#39;extérieur.

## Prévisualisez votre message {#preview-msg}

Adobe recommande de prévisualiser votre message afin de vérifier sa personnalisation et l’affichage de la diffusion par vos destinataires.

In the Email designer, the **[!UICONTROL Preview]** button lets you view the rendering of each content for a recipient. Les champs de personnalisation et les éléments conditionnels du contenu sont remplacés par les informations correspondantes pour le profil sélectionné. [En savoir plus](../../sending/using/previewing-messages.md)
