---
title: Principes de fonctionnement des workflows
seo-title: Principes de fonctionnement des workflows
description: Principes de fonctionnement des workflows
seo-description: Découvrez les principaux aspects des workflows.
page-status-flag: jamais activé
uuid: 85755 e 85-617 b -4 a 9 b-bb 30-96 ba 8333 f 4 f 0
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatisation
content-type: référence
topic-tags: about-workflows-and-data-management
discoiquuid: 3 a 13785 d -1 ef 7-4043-9927-2 d 495 b 83709 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Principes de fonctionnement des workflows{#workflow-operating-principles}

Un workflow est un **enchaînement d'activités paramétrables**. Chaque activité possède un rôle précis dans le processus. Le résultat de chaque activité est transmis à l'activité suivante via une **transition**, représentée par une flèche.

Le type des données transmises d'une activité à une autre peut influer sur le paramétrage des activités suivantes. Par exemple, si une population est définie avant une activité de diffusion d'email, elle peut servir de cible pour l'email en question.

Vous pouvez ouvrir les activités afin d'en vérifier ou modifier les paramètres avant ou après l'exécution du workflow.

Vous pouvez ouvrir les transitions afin de vérifier que les données transmises sont correctes pendant ou après l'exécution du workflow. Pour accéder au détail des transitions, vous devez cocher l'option **[!UICONTROL Conserver les résultats intermédiaires]** dans la section **Exécution]des propriétés du workflow.[!UICONTROL **

![](assets/workflow_overview.png)

