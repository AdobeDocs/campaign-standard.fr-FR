---
title: A propos du canal Ccourrier
description: Découvrez les spécificités principales du canal Courrier dans Adobe Campaign.
page-status-flag: never-activated
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: efb1f14e0094e200d186423f98bfad65d25cfab2

---


# A propos du canal Courrier{#about-direct-mail}

Le canal Courrier est un canal off-line qui vous permet de personnaliser et de générer le fichier requis par les opérateurs de services postaux. Il vous offre la possibilité de mélanger des canaux off-line et on-line dans les parcours client.

>[!NOTE]
>
>Cette fonctionnalité est en option. Vérifiez votre contrat de licence. Le rôle **[!UICONTROL Export]** est requis pour utiliser le canal Courrier. Veuillez contacter votre administrateur.

Les canaux on-line vous permettent de créer vos messages (email, SMS, diffusion sur des applications mobiles, etc.) et de les envoyer à votre audience directement depuis Adobe Campaign. Les canaux off-line fonctionnent différemment. Lors de la préparation d&#39;une diffusion courrier, Adobe Campaign génère un fichier comprenant tous les profils ciblés et les informations de contact sélectionnées (adresse postale, par exemple). Vous pouvez ensuite envoyer ce fichier à votre opérateur de services postaux qui se chargera de l&#39;envoi.

La section ci-après décrit comment créer et gérer une diffusion courrier ponctuelle. Vous avez également la possibilité d&#39;inclure une activité de type courrier dans un workflow pour orchestrer des campagnes qui associent des canaux on-line et off-line. Voir à ce propos le guide [Workflows](../../automating/using/workflow-data-and-processes.md).

Dans Adobe Campaign, le processus utilisateur est le suivant :

1. Créer la diffusion
1. Définir l&#39;audience
1. Définir le contenu
1. Définir la date de contact
1. Générer le fichier

## Recommandations {#recommendations}

### Opérateurs de services postaux {#direct-mail-providers}

Tout d&#39;abord, vous devez prendre connaissance des recommandations de votre opérateur de services postaux. Identifiez les informations de profil à inclure dans le fichier d&#39;extraction pour qu&#39;il puisse personnaliser la communication et l&#39;envoyer à l&#39;audience. Il peut s&#39;agir du prénom et du nom de famille, de l&#39;adresse postale, d&#39;un code de promotion, etc. Ces champs sont ceux que vous ajouterez dans l&#39;onglet [Définir l&#39;extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) du contenu du courrier.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles&#39; information. Si cette option est activée, le profil est ajouté à la cible. Si ce n&#39;est pas le cas, il est exclu par une règle de typologie pendant la phase de préparation (voir [Créer le courrier](../../channels/using/creating-the-direct-mail.md)). Pendant l&#39;import des profils, pensez à mettre à jour ce champ.

![](assets/direct_mail_22.png)

### Adresses postales {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

Adobe Campaign vous propose un ensemble de champs calculés prédéfinis qui respectent les normes les plus courantes des adresses postales. The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field (**[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

