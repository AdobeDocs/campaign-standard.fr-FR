---
solution: Campaign Standard
product: campaign
title: DataModel
description: En savoir plus sur le datamodel
audience: developing
content-type: reference
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '144'
ht-degree: 100%

---


# Visiteur (nms:visitor)

## Description de l&#39;objet

<table>
    <tr>
        <th>Nom</th>
        <th>Libellé</th>
        <th>Type (longueur)</th>
        <th>Valeurs d'énumération</th>
    </tr>
    <tr>
        <td>PKey</td>
        <td>Main resource ID</td>
        <td>string </td>
        <td> </td>
    </tr>
    <tr>
        <td>comment</td>
        <td>Referrer comment</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>created</td>
        <td>Created</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>createdBy (userBase)</td>
        <td>Created by</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>delivery (delivery)</td>
        <td>Delivery</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>deliveryId</td>
        <td>ID of the last delivery</td>
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
        <td>External ID</td>
        <td>string (64)</td>
        <td> </td>
    </tr>
    <tr>
        <td>firstName</td>
        <td>First name</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>forwardUrl</td>
        <td>Forward url</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
    <tr>
        <td>geoUnit (geoUnitBase)</td>
        <td>Geographical unit</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastModified</td>
        <td>Last modified</td>
        <td>date </td>
        <td> </td>
    </tr>
    <tr>
        <td>lastName</td>
        <td>Last name</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>modifiedBy (userBase)</td>
        <td>Modified by</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>orgUnit (orgUnitBase)</td>
        <td>Organizational unit</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>origin</td>
        <td>Origin</td>
        <td>enumeration (byte) </td>
        <td>
            <ul>
            <li>Undefined - undefined - 0</li>
            <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
            </ul>
        </td>
    </tr>
    <tr>
        <td>recipient (recipient)</td>
        <td>Identified profile</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>recipientId</td>
        <td>Profile ID</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerEmail</td>
        <td>Referrer email</td>
        <td>string (128)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerFirstName</td>
        <td>Referrer first name</td>
        <td>string (30)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerId</td>
        <td>Referrer ID</td>
        <td>integer </td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerLastName</td>
        <td>Referrer last name</td>
        <td>string (50)</td>
        <td> </td>
    </tr>
    <tr>
        <td>referrerRcp (recipient)</td>
        <td>Referrer</td>
        <td>link </td>
        <td> </td>
    </tr>
    <tr>
        <td>title</td>
        <td>Label</td>
        <td>string (255)</td>
        <td> </td>
    </tr>
</table>

## Filtres

Par nom, prénom ou email (byText)</p>

<table>
        <tr>
        <th>Nom</th>
        <th>Type</th>
        </tr>
        <tr>
        <td>text</td>
        <td>string</td>
        </tr>
    </table>