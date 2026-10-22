---
title: Visiteur du modèle de données
description: En savoir plus sur le datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: 20dafd81-8546-450a-87a0-59a2509efb7a
TQID: 'https://experienceleague.adobe.com/jzmKAer7SITNpxJRT1CsPf-LWW-bglgNhDl5NKP6mzU'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: a1681cd8-6b2e-4955-9113-33b5f7a22b8c
    internal-label: Data model architecture
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 100%
---
# Visiteur ou visiteuse (nms:visitor)

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
        <td>Diffusion</td>
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
        <td>Libellé</td>
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
