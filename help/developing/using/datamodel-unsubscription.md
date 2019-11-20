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


# Événement de désabonnement (nms:rtEvent)

## Description de l’objet

<table>
               <tr>
                  <th>Nom</th>
                  <th>Lecture seule</th>
                  <th>Type</th>
                  <th>Obligatoire</th>
               </tr>
               <tr>
                  <td>PKey</td>
                  <td>Faux</td>
                  <td>string</td>
                  <td>Faux</td>
               </tr>
               <tr>
                  <td>ctx</td>
                  <td>Faux</td>
                  <td>item</td>
                  <td>Faux</td>
               </tr>
               <tr>
                  <td>email</td>
                  <td>Faux</td>
                  <td>string</td>
                  <td>Faux</td>
               </tr>
               <tr>
                  <td>emailFormat</td>
                  <td>Faux</td>
                  <td>enumeration</td>
                  <td>Faux</td>
               </tr>
               <tr>
                  <td>mobilePhone</td>
                  <td>Faux</td>
                  <td>string</td>
                  <td>Faux</td>
               </tr>
               <tr>
                  <td>serverUrl</td>
                  <td>Vrai</td>
                  <td>string</td>
                  <td>Faux</td>
               </tr>
            </table>

## Filtres

byEmail

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

byStatusOrType

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