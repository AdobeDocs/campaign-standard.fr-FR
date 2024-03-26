---
title: Création de contenu personnalisé
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Découvrez comment concevoir le contenu de votre message et évitez les problèmes courants qui peuvent vous empêcher d'exécuter votre diffusion. 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1049'
ht-degree: 100%

---

# Création de contenu personnalisé {#build-personalized-content}

Lors de la conception du contenu de votre message, évitez les problèmes courants qui peuvent vous empêcher d&#39;exécuter votre diffusion. La plupart du temps, les erreurs possibles sont liées à la [personnalisation](../../designing/using/personalization.md), à la mise en forme lors de l&#39;[utilisation d&#39;un contenu existant](../../designing/using/using-existing-content.md) et à la [conversion d&#39;un contenu HTML](../../designing/using/using-existing-content.md#converting-an-html-content), ainsi qu&#39;aux [images](../../designing/using/images.md).

## Optimiser la personnalisation {#optimize-personalization}

Pour éviter des problèmes courants qui peuvent vous empêcher d&#39;exécuter votre diffusion et d&#39;améliorer l&#39;expérience de vos destinataires, Adobe Campaign vous permet de personnaliser vos messages.

Vous pouvez utiliser les données des destinataires stockées dans la base de données Adobe Campaign ou collectées par le biais du tracking, des landing pages, des inscriptions, etc.
Les principes de base de la personnalisation sont présentés dans [cette section](../../designing/using/personalization.md).

Vérifiez que le contenu de votre message est correctement conçu pour éviter les erreurs généralement liées à la personnalisation.

Vous pouvez ajouter manuellement du contenu dynamique pour afficher différents éléments à vos destinataires selon les conditions définies au moyen de l&#39;éditeur d&#39;expression. Lorsque vous ajoutez du contenu dynamique, vous devez toujours laisser une variante par défaut pour les destinataires qui ne répondent pas aux conditions sélectionnées.
Pour plus d&#39;informations sur les contenu dynamique, consultez [cette section](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Conseils** : prévisualisez votre e-mail avec différents profils de test pour vous assurer que le contenu dynamique est correctement paramétré.

## Créer du contenu optimisé {#optimize-content}

Lorsque vous créez vos e-mails, tenez compte des bonnes pratiques générales présentées ci-dessous.

* Gardez le design de vos e-mails simple

* Gardez les utilisateurs d&#39;appareils mobiles à l&#39;esprit

* Évitez les e-mails basés entièrement sur des images

* Utilisez des polices sécurisées pour les e-mails

* Encodez les caractères spéciaux

### Objet

Travaillez sur la [ligne d&#39;objet](../../designing/using/subject-line.md) pour améliorer les taux d&#39;ouverture :

* Évitez les objets trop longs. Utilisez 50 caractères au maximum

* Évitez de répéter des mots tels que &quot;gratuit&quot; ou &quot;offre&quot; qui peuvent être considérés comme des messages indésirables

* Évitez les majuscules et les caractères spéciaux tels que &quot;!&quot;, &quot;£&quot;, &quot;€&quot;, &quot;$&quot;

### Page miroir

Incluez toujours un lien de page miroir. La partie supérieure de l&#39;e-mail constitue la position idéale. [En savoir plus](../../designing/using/personalization.md#adding-a-content-block)

### Lien de désabonnement

Le lien de désabonnement est indispensable. Il doit être visible, valide et le formulaire fonctionnel. Découvrez les consignes relatives aux liens de désabonnement [dans cette section](../../designing/using/personalization.md#about-targeting-dimension).

Par défaut, une [règle de typologie](../../sending/using/control-rules.md) de contrôle vérifie au moment de l&#39;analyse du message qu&#39;un lien d&#39;opt-out est bien présent dans le contenu d&#39;une diffusion et génère un avertissement en cas d&#39;absence.

**Conseil** : comme une erreur humaine est toujours possible, vérifiez du début à la fin le bon fonctionnement du lien de désabonnement avant chaque envoi. Par exemple, lors de l&#39;envoi du BAT, vérifiez que le lien est valide, que le formulaire est en ligne et que la valeur du champ Ne plus contacter cette personne est changée en Oui.

Découvrez comment insérer un lien d&#39;opt-out [dans cette section](../../designing/using/personalization.md#adding-a-content-block).

### Taille des e-mails  {#email-size}

Pour éviter des problèmes de performances ou de délivrabilité, la taille maximale recommandée d’un email est d’environ **35 Ko**.

Pour maintenir la taille de l&#39;e-mail sous cette limite, tenez compte des possibilités suivantes :

* Supprimer les styles redondants ou inutilisés

* Déplacer une partie du contenu de l&#39;e-mail vers une [landing page](../../channels/using/getting-started-with-landing-pages.md)

* Minimiser votre code

Veillez à tester toutes les modifications avant l’envoi final.

Dans Adobe Campaign, la taille maximale par défaut d&#39;un e-mail est définie sur **100 Mo**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Si la limite est atteinte, le message qui dépasse la limite échoue et un message d&#39;erreur s&#39;affiche dans les logs de diffusion. Les autres messages d&#39;une même diffusion ne seront pas impactés. Dans ce cas, vous devez adapter la partie dynamique du modèle d&#39;e-mail ou les fragments de contenu utilisés par la diffusion. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

Adobe recommande de conserver la valeur par défaut de la taille maximale de message. Cependant, cette valeur peut être modifiée dans l&#39;option **[!UICONTROL Taille maximale de message]**, via le menu **[!UICONTROL Administration]** > **[!UICONTROL Paramétrage de l&#39;application]** > **[!UICONTROL Options]**, mais uniquement par les [administrateurs fonctionnels](../../administration/using/users-management.md#functional-administrators).

>[!IMPORTANT]
>
>Si vous définissez cette valeur sur zéro, aucune limite ne sera appliquée.

### Longueur des SMS

Par défaut, le nombre de caractère d&#39;un SMS respecte la norme de téléphonie mobile GSM (Global System for Mobile Communications). Les SMS utilisant l&#39;encodage GSM sont limités à 160 caractères, ou 153 caractères par SMS pour les messages envoyés en plusieurs parties.

La translittération consiste à remplacer un caractère de SMS par un autre lorsque ce caractère n’est pas pris en charge par la norme GSM. Notez que l’insertion de champs de personnalisation dans le contenu de votre SMS peut introduire des caractères qui ne sont pas pris en charge par l’encodage GSM. Vous pouvez autoriser la translittération des caractères en cochant la case correspondante dans l’onglet Paramètres du canal SMPP du **[!UICONTROL compte externe]** correspondant.
En savoir plus dans [cette section](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Conseils** :

* Pour conserver tous les caractères de vos SMS, afin de ne pas altérer les noms propres par exemple, n&#39;activez pas la translittération.

* En revanche, si vos SMS contiennent beaucoup de caractères qui ne sont pas pris en charge par la norme GSM, activez la translittération afin de limiter le coût de vos envois.

En savoir plus dans [cette section](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### E-mail en responsive design

Le responsive design des e-mails permet de s&#39;assurer que le rendu d&#39;un est optimal sur l&#39;appareil sur lequel il est ouvert.

* Utilisez du code HTML en responsive design plutôt que du code HTML web

* Utilisez le mode Aperçu et envoyez des BAT pour tester le rendu sur le plus grand nombre d’appareils possible. Apprenez à [prévisualiser un message](../../sending/using/previewing-messages.md) avant l&#39;envoi.

* Le concepteur d’e-mail de Campaign est fourni avec des modèles mis en forme en responsive design pour les appareils mobiles. En savoir plus [dans cette page](../../designing/using/using-reusable-content.md#content-templates).

## Gestion des images {#manage-images}

Suivez les instructions ci-dessous pour l&#39;utilisation des images.

### Empêcher le blocage des images

Certains clients de messagerie bloquent les images par défaut, et certains utilisateurs modifient leurs paramètres pour bloquer les images afin de réduire l&#39;utilisation des données. Dans ce cas, si les images ne sont pas téléchargées, il est possible que l&#39;ensemble du message soit perdu. Pour éviter cela :

* Équilibrez le contenu entre image et texte. Évitez les e-mails basés entièrement sur des images.

* Si le texte doit être contenu dans une image, utilisez du texte de titre et du texte alternatif pour vous assurer que votre message passe bien. Mettez en forme votre texte de titre et alternatif pour améliorer son aspect.

* Évitez d’utiliser des images d’arrière-plan, car elles ne sont pas prises en charge par certains clients de messagerie.

### Rendre les images réactives

Essayez de rendre les images réactives et redimensionnables. Notez que ceci peut avoir un impact sur les coûts, car la création prend plus de temps.

### Utiliser des références absolues pour l&#39;accès à l&#39;image

Pour être accessibles depuis l&#39;extérieur, les images utilisées dans les e-mails et les ressources publiques associées aux opérations doivent être présentes sur un serveur accessible de l&#39;extérieur.

## Prévisualisez votre message {#preview-msg}

Adobe recommande de prévisualiser votre message afin de vérifier sa personnalisation et l&#39;affichage de la diffusion par vos destinataires.

Dans le concepteur d’e-mail, le bouton **[!UICONTROL Aperçu]** vous permet de visualiser le rendu de chaque contenu pour un destinataire. Les champs de personnalisation et les éléments conditionnels du contenu sont remplacés par les informations correspondantes pour le profil sélectionné. [En savoir plus](../../sending/using/previewing-messages.md)
