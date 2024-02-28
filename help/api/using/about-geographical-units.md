---
title: À propos des entités géographiques
description: Découvrez les entités géographiques et les API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: ht
source-wordcount: '127'
ht-degree: 100%

---


# À propos des entités géographiques {#about-geographical-units}

>[!CAUTION]
>
>La fonctionnalité d’entité géographique a été abandonnée dans la version 18.7 de Campaign Standard.
>
>Par conséquent, les nouvelles instances de Campaign Standard, ainsi que les instances existantes sans entités géographiques, ne peuvent pas bénéficier de cette fonctionnalité à partir de la version 18.7.
>
>Pour plus d’informations à ce sujet, consultez la page <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=fr">Fonctionnalités obsolètes</a>.

Le point d’entrée **geoUnitBase** vous permet d’interagir avec les entités géographiques, par exemple pour mettre à jour leurs attributs ou l’entité d’un profil.

Le champ **Entité géographique** est ajouté à un profil lors de l’extension de la ressource de profil. Par conséquent, n’oubliez pas d’utiliser systématiquement le point d’entrée **profileAndServicesExt** pour interagir avec les entités géographiques. Pour plus d’informations sur l’extension de ressource du profil, consultez la [documentation Campaign](https://helpx.adobe.com/fr/campaign/standard/administration/using/organizational-units.html#partitioning-profiles).
