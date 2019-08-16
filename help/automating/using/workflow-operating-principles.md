---
title: Principes de fonctionnement des workflows
seo-title: Principes de fonctionnement des workflows
description: Principes de fonctionnement des workflows
seo-description: Découvrez les principaux aspects des workflows.
page-status-flag: never-activated
uuid: 85755e85-617b-4a9b-bb30-96ba8333f4f0
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
discoiquuid: 3a13785d-1ef7-4043-9927-2d495b83709f
internal: n
snippet: y
translation-type: ht
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Principes de fonctionnement des workflows{#workflow-operating-principles}

Un workflow est un **enchaînement d'activités paramétrables**. Chaque activité possède un rôle précis dans le processus. Le résultat de chaque activité est transmis à l'activité suivante via une **transition**, représentée par une flèche.

Le type des données transmises d'une activité à une autre peut influer sur le paramétrage des activités suivantes. Par exemple, si une population est définie avant une activité de diffusion d'email, elle peut servir de cible pour l'email en question.

Vous pouvez ouvrir les activités afin d'en vérifier ou modifier les paramètres avant ou après l'exécution du workflow.

Vous pouvez ouvrir les transitions afin de vérifier que les données transmises sont correctes pendant ou après l'exécution du workflow. Pour accéder au détail des transitions, vous devez cocher l'option **[!UICONTROL Conserver les résultats intermédiaires]** dans la section **[!UICONTROL Exécution]** des propriétés du workflow.

![](assets/workflow_overview.png)

