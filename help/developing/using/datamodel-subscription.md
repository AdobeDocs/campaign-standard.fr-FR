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
source-git-commit: c7e83d7d5130ce93b880e4835e634dad03504ebb

---


# Abonnement, événement (nms:rtEvent)

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
        <td>ctx</td>
        <td>Contexte de l'événement</td>
        <td>item </td>
        <td> </td>
    </tr>
    <tr>
        <td>email</td>
        <td>Email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>emailFormat</td>
        <td>Format des emails</td>
        <td>énumération (octet) </td>
        <td>
            <ul>
            <li>Texte - Texte - 1</li>
            <li>HTML - html - 2</li>
            <li>VALEUR NON VALIDE - __Invalid_value__ - __Invalid_value__</li>
            <li>Inconnu - inconnu - 0</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>eventHistoId</td>
        <td>ID d’événement archivé</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>mobilePhone</td>
        <td>Numéro de mobile</td>
        <td>string (32)</td>
        <td> </td>
    </tr>
    <tr>
        <td>serverUrl</td>
        <td>ServerUrl</td>
        <td>string </td>
        <td> </td>
    </tr>
</table>

## Filtres

Par courriel (par courriel)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>email</td>
    <td>string</td>
    </tr>
</table>

Par état ou type (byStatusOrType)

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>status</td>
        <td>enumeration</td>
        </tr>
        <tr>
        <td>type</td>
        <td>string</td>
        </tr>
    </table>