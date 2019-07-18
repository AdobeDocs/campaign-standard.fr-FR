---
title: Configurer les propriétés d'une image
seo-title: Configurer les propriétés d'une image
description: Configurer les propriétés d'une image
seo-description: Découvrez comment gérer les propriétés des images incluses dans votre contenu.
page-status-flag: jamais activé
uuid: 1 a 439105-d 9 aa -4 b 30-a 00 d-bcf 731 a 04 e 08
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: conception
content-type: référence
topic-tags: using-images
discoiquuid: 80 c 9 c 1 a 5-6050 0-443 d -810 a -6 bb 755 d 39 dca
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Configurer les propriétés d'une image{#setting-up-image-properties}

Lorsque vous sélectionnez un bloc contenant une image, les propriétés suivantes sont proposées dans la palette :

* **Activer la personnalisation** permet de personnaliser la source de l'image. Voir [Personnaliser la source d'une image](../../designing/using/personalizing-an-image-source.md).
* **Titre de l'image** permet de définir un titre pour l'image.
* **Texte alternatif** (email) ou **Légende** (landing page) permet de définir la légende associée à l'image (correspond à l'attribut HTML **alt**).
* Lors de l'édition d'un email, **Style** permet d'indiquer la taille, l'arrière-plan et la bordure de l'image.
* Lors de l'édition d'une landing page, **Dimensions** permet de spécifier la taille de l'image en pixels.

L'éditeur permet de travailler avec **tous types d'images** dont le format est compatible avec les navigateurs. Pour être compatible avec l'éditeur, les **animations de type "Flash"** doivent être insérées dans une page HTML de la manière suivante :      

```
<object type="application/x-shockwave-flash" data="http://www.mydomain.com/flash/your_animation.swf" width="200" height="400">
 <param name="movie" value="http://www.mydomain.com/flash/your_animation.swf" />
 <param name="quality" value="high" />
 <param name="play" value="true"/>
 <param name="loop" value="true"/> 
</object>
```

