---
title: Définir une condition de visibilité
seo-title: Définir une condition de visibilité
description: Définir une condition de visibilité
seo-description: Ne rendez visible un élément de la page web que si une condition donnée est respectée.
page-status-flag: jamais activé
uuid: 224005 ba-ef 09-4790-b 2 f 0-30 ed 74 cfa 32 d
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: conception
content-type: référence
topic-tags: définition-conditionnelle-contenu
discoiquuid: c 12125 a 7-a 1 cf -4 bc 1-a 138-57 ff 74974024
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Définir une condition de visibilité{#defining-a-visibility-condition}

Vous pouvez spécifier une condition de visibilité sur n'importe quel élément. Cet élément ne sera visible que si la condition de visibilité est respectée.

Pour ajouter une condition de visibilité, sélectionnez un bloc et saisissez la condition à remplir dans le champ **[!UICONTROL Condition de visibilité]de ses paramètres.**

![](assets/delivery_content_5.png)

Cette option est uniquement proposée pour les éléments suivants : ADDRESS, BLOCKQUOTE, CENTER, DIR, DIV, DL, FIELDSET, FORM, H1, H2, H3, H4, H5, H6, NOSCRIPT, OL, P, PRE, UL, TR, TD.

L'éditeur d'expression est présenté dans la section [Edition avancée d'expressions](../../automating/using/editing-queries.md#about-query-editor).

These conditions adopt the XTK expression syntax (e.g. **context.profile.email !=''** or **context.profile.status='0'**). Par défaut, tous les champs sont visibles.

>[!NOTE]
>
>Il n'est pas possible de définir une condition pour un bloc comprenant déjà un sous-élément avec un contenu dynamique ou un bloc faisant déjà partie d'un contenu dynamique. Les blocs dynamiques non visibles, tels que les menus déroulants, ne peuvent être édités.

