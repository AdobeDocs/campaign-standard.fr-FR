---
title: Mise à jour des données à l’aide de la réconciliation
description: L'exemple suivant illustre un workflow permettant de créer une audience de profils directement à partir d'un fichier importé contenant des nouveaux clients.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: reconciliation,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: cfca6202-791d-4baf-b5ed-677d2480cf06
TQID: https://experienceleague.adobe.com/cEXfESw1LZcrQVlLsgrlDB8J2aGz4zCoSUrIAshECo0
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: ht
source-wordcount: 128
ht-degree: 100%

---

# Mise à jour des données à l&#39;aide de la réconciliation {#data-update-reconciliation}

L&#39;exemple suivant illustre un workflow permettant de créer une audience de profils directement à partir d&#39;un fichier importé contenant des nouveaux clients. Il se compose des activités suivantes :

![](assets/identification_example2.png)

* Une activité [Chargement de fichier](../../automating/using/load-file.md) qui permet de charger et de détecter les données du fichier à importer. Le fichier importé contient les données suivantes :

  ```
  lastname;firstname;email;dateofbirth
  jackman;megan;megan.jackman@testmail.com;07/08/1975
  phillips;edward;phillips@testmail.com;09/03/1986
  weaver;justin;justin_w@testmail.com;11/15/1990
  martin;babeth;babeth_martin@testmail.net;11/25/1964
  reese;richard;rreese@testmail.com;02/08/1987
  cage;nathalie;cage.nathalie227@testmail.com;07/03/1989
  xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992
  grimes;daryl;daryl_890@testmail.com;12/06/1979
  tycoon;tyreese;tyreese_t@testmail.net;10/08/1971
  ```

* une activité de [Réconciliation](../../automating/using/reconciliation.md) permettant d&#39;associer chaque colonne du fichier chargé à une colonne de la dimension des profils. Les enregistrements de fichiers non identifiables (données manquantes, type de données incompatible, etc.) sont ignorés pour préserver l’intégrité des données d’audience finales.

  ![](assets/identification_example1.png)

* une activité de [Sauvegarde d&#39;audience](../../automating/using/save-audience.md) permettant d&#39;enregistrer l&#39;audience de profils.

  ![](assets/identification_example3.png)
