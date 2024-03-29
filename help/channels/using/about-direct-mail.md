---
title: À propos du canal Ccourrier
description: Découvrez les spécificités principales du canal Courrier dans Adobe Campaign.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
feature: Direct Mail
role: User
level: Intermediate
exl-id: 815b4a0d-0486-4867-b751-b5ca8b643cb9
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 100%

---

# À propos du courrier{#about-direct-mail}

Le canal Courrier est un canal off-line qui vous permet de personnaliser et de générer le fichier requis par les opérateurs de services postaux. Il vous offre la possibilité de mélanger des canaux off-line et on-line dans les parcours client.

>[!NOTE]
>
>Cette fonctionnalité est en option. Vérifiez votre contrat de licence. Le rôle **[!UICONTROL Export]** est requis pour utiliser le canal Courrier. Veuillez contacter votre administrateur.

Les canaux on-line vous permettent de créer vos messages (email, SMS, diffusion sur des applications mobiles, etc.) et de les envoyer à votre audience directement depuis Adobe Campaign. Les canaux off-line fonctionnent différemment. Lors de la préparation d&#39;une diffusion courrier, Adobe Campaign génère un fichier comprenant tous les profils ciblés et les informations de contact sélectionnées (adresse postale, par exemple). Vous pouvez ensuite envoyer ce fichier à votre opérateur de services postaux qui se chargera de l&#39;envoi.

La section ci-après décrit comment créer et gérer une diffusion courrier ponctuelle. Vous avez également la possibilité d&#39;inclure une activité de type courrier dans un workflow pour orchestrer des campagnes qui associent des canaux on-line et off-line. Voir à ce propos le guide [Workflows](../../automating/using/get-started-workflows.md).

Dans Adobe Campaign, le processus utilisateur est le suivant :

1. Créer la diffusion
1. Définir l&#39;audience
1. Définir le contenu
1. Définir la date de contact
1. Générer le fichier

**Rubriques connexes :**

* [Cas pratique : diffusions conjointes d’emails et de courriers](../../automating/using/coupling-email-direct-mail.md)

## Recommandations {#recommendations}

### Opérateurs de services postaux {#direct-mail-providers}

Tout d&#39;abord, vous devez prendre connaissance des recommandations de votre opérateur de services postaux. Identifiez les informations de profil à inclure dans le fichier d&#39;extraction pour qu&#39;il puisse personnaliser la communication et l&#39;envoyer à l&#39;audience. Il peut s&#39;agir du prénom et du nom de famille, de l&#39;adresse postale, d&#39;un code de promotion, etc. Ces champs sont ceux que vous ajouterez dans l&#39;onglet [Définir l&#39;extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) du contenu du courrier.

Assurez-vous que la case **[!UICONTROL Adresse renseignée]** est cochée dans les informations des profils. Si cette option est activée, le profil est ajouté à la cible. Si ce n&#39;est pas le cas, il est exclu par une règle de typologie pendant la phase de préparation (voir [Créer le courrier](../../channels/using/creating-the-direct-mail.md)). Pendant l&#39;import des profils, pensez à mettre à jour ce champ.

![](assets/direct_mail_22.png)

### Adresses postales      {#postal-addresses}

Lors de l&#39;ajout des champs à inclure dans le fichier d&#39;extraction, les champs d&#39;adresse postale sont accessibles dans le nœud **[!UICONTROL Localisation]**.

Adobe Campaign vous propose un ensemble de champs calculés prédéfinis qui respectent les normes les plus courantes des adresses postales. Ces champs sont accessibles dans le nœud **[!UICONTROL Adresse postale]**.

Par défaut, une adresse peut contenir jusqu&#39;à six lignes : la première ligne (**[!UICONTROL Ligne 1]**) contient le prénom et le nom, les suivantes contiennent les coordonnées postales (rue et compléments) et la dernière contient le code postal et la ville.

![](assets/direct_mail_23.png)
