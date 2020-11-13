---
title: Règles de contrôle
description: Apprenez comment renforcer la vérification de la qualité des messages avec les règles de contrôle.
page-status-flag: never-activated
uuid: 33a1c90c-534e-4fe1-982c-f4e1858d4d2d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 305cadde-6424-4c6f-b11b-1e8bdbad6ef1
translation-type: ht
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: ht
source-wordcount: '488'
ht-degree: 100%

---


# Cas des règles de contrôle {#control-rules}

Les règles de contrôle permettent de vérifier la validité et la qualité des messages avant leur envoi : affichage des caractères, taille des SMS, format des adresses, etc.

>[!NOTE]
>
>Pour des raisons de sécurité, les règles de contrôle sont en lecture seule et ne peuvent pas être modifiées.

## Règles de contrôle par défaut {#default-control-rules}

Un ensemble de règles par défaut garantit les contrôles standard. Le tableau ci-dessous fournit des informations sur ces règles, ainsi que sur le canal et les [phases d’exécution](#control-rules-execution-phases) associés.

| Libellé | Canal | Phase d’exécution | Description |
---------|----------|---------|---------
| **[!UICONTROL Test A/B]** | Email | Au début de la personnalisation | Extrait la population d&#39;apprentissage pour une diffusion avec test A/B. |
| **[!UICONTROL Vérifier la taille de la diffusion]** | Tous | Après le ciblage | Vérifie la taille des messages. |
| **[!UICONTROL Vérifier que le contenu de l&#39;email n&#39;est pas vide]** | Email | Après le ciblage | Génère une erreur si le contenu du message est vide. |
| **[!UICONTROL Vérifier le contenu In-App pour le modèle de message de diffusion]** | In-App | Au début de la personnalisation | Vérifie que le contenu/les triggers In-App ne sont pas vides pour le modèle de diffusion. |
| **[!UICONTROL Vérifier le contenu In-App pour le modèle de profil]** | In-App | Au début de la personnalisation | Vérifie que le contenu/les triggers In-App ne sont pas vides pour le modèle de profil. |
| **[!UICONTROL Vérifier le contenu In-App pour le modèle d&#39;abonné]** | In-App | Au début de la personnalisation | Vérifie que le contenu/les triggers In-App ne sont pas vides pour le modèle d&#39;abonné. |
| **[!UICONTROL Vérifier la taille du BAT]** | Tous | Après le ciblage | Génère un message d’erreur si la population cible du BAT dépasse 100 destinataires. |
| **[!UICONTROL Vérifier le lien de partage vers les réseaux sociaux]** | Email | Au début de la personnalisation | Vérifie la présence d’un lien vers une page miroir lors de l&#39;inclusion d&#39;un lien de partage vers les réseaux sociaux (ViralLinks) dans le contenu. |
| **[!UICONTROL Vérifier le sujet]** | Email | Au début de la personnalisation | Vérifie que le sujet et l&#39;adresse de l&#39;expéditeur du message ne contiennent pas de caractères spéciaux, susceptibles de poser des problèmes sur certains agents de messagerie, et vérifie que l&#39;objet du message est bien renseigné. |
| **[!UICONTROL Vérifier le lien de désabonnement]** | Email | Au début de la personnalisation | Vérifie la présence d&#39;au moins une URL de désabonnement (URL de type opt-out) dans chacun des contenus (HTML et Texte). |
| **[!UICONTROL Vérifier les libellés d&#39;URL]** | Email | Au début de la personnalisation | Vérifie que chaque URL de tracking comporte un libellé. |
| **[!UICONTROL Vérifier les URL]** | Email | Au début de la personnalisation | Vérifie les URL de tracking (présence du caractère « &amp; »). |

## Phases d’exécution des règles de contrôle {#control-rules-execution-phases}

Les règles de contrôle peuvent être appliquées à différentes phases du cycle de vie de la diffusion :

* **Au début du ciblage** : la règle de contrôle peut être appliquée à cette phase afin que l&#39;étape de personnalisation ne soit pas exécutée en cas d&#39;erreur.

* **Après le ciblage** : l’exécution après le ciblage vous permet de connaître le volume de la cible afin d’appliquer la règle de contrôle.

   Par exemple, la règle de contrôle **Vérifier la taille du BAT** s&#39;applique obligatoirement après l&#39;étape de ciblage : cette règle permet de ne pas préparer la personnalisation des messages si les destinataires du BAT sont trop nombreux.

* **Au début de la personnalisation**: s’applique lorsque la vérification concerne la validation de la personnalisation des messages. La personnalisation des messages est réalisée au cours de la phase d&#39;analyse.

* **A la fin de l&#39;analyse**: lorsqu’une vérification nécessite que la personnalisation du message soit effectuée.
