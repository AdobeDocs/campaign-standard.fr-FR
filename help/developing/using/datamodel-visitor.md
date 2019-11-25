---
title: DataModel
description: En savoir plus sur le modèle de données
uuid: 99277e46-e4f7-49a9-ba27-b878780f90da
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
discoiquuid: 6e21db35-daf9-4edb-977a-6ef606db0e4d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6263623a5a8999c475255709a7d0150437e68c0b

---


# Visiteur (nms:visitor)

## Description de l’objet

<table>
    <tr>
        <th>Nom</th>
        <th>Libellé</th>
        <th>Type (longueur)</th>
        <th>Valeurs d'énumération</th>
    </tr>
    <tr>
        <td>PKey</td>
        <td>Identifiant principal de la ressource</td>
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>commentaire</td>
        <td>Commentaire Référent</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>created</td>
        <td>Créé</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>createdBy (userBase)</td>
        <td>Créé par</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>livraison (livraison)</td>
        <td>Diffusion</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID de la dernière remise</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>desc</td>
        <td>Description</td>
        <td>string (512)</td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>externalId</td>
        <td>Identifiant externe</td>
        <td>string (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>Prénom</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>URL de transfert</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Entité géographique</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Dernière modification</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>Nom</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifyBy (userBase)</td>
        <td>Modification par</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Entité organisationnelle</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>origine</td>
        <td>Origine</td>
        <td>énumération (octet) </td>
        <td>
            <ul>
            <li>Non défini - Non défini - 0</li>
            <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>destinataire (destinataire)</td>
        <td>Profil identifié</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>RecipientId</td>
        <td>Identifiant du profil</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Adresse électronique du référent</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Prénom du référent</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>ID de référent</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Nom du référent</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (destinataire)</td>
        <td>Référent</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>Libellé</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
</table>

## Filtres

Par nom, prénom ou adresse électronique (parTexte)</p>

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>texte</td>
        <td>string</td>
        </tr>
    </table>