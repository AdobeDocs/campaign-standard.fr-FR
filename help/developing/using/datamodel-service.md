---
title: Service du modèle de données
description: En savoir plus sur le datamodel
audience: developing
content-type: reference
feature: Data Model
role: Developer
level: Experienced
exl-id: a326b38f-ca88-4a44-a7c2-b6e34497a364
TQID: https://experienceleague.adobe.com/kGtxG4yKA8Uxzc0hZbZFk1VLiVM9FPTvCoIoMd--n4M
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 100%

---

# Service (nms:service)

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
                  <td>builtIn</td>
                  <td>Objet d’application natif</td>
                  <td>boolean </td>
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
                  <td>cusPrice</td>
                  <td>Price</td>
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
                  <td>end</td>
                  <td>Date de fin</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>geoUnit (geoUnitBase)</td>
                  <td>Geographical unit</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>history</td>
                  <td>Subscription history</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isExternal</td>
                  <td>Is external resource</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>isTemplate</td>
                  <td>Template</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>label</td>
                  <td>Libellé</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>lastModified</td>
                  <td>Last modified</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>limitedDuration</td>
                  <td>Limited duration</td>
                  <td>boolean </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>mainDate</td>
                  <td>Date</td>
                  <td>date (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>messageType</td>
                  <td>Canal</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Mobile (SMS) - sms - 1</li>
                        <li>Email - email - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>mode</td>
                  <td>Mode</td>
                  <td>enumeration (byte) </td>
                  <td>
                     <ul>
                        <li>Viral - viral - 1</li>
                        <li>Newsletter - newsletter - 0</li>
                        <li>INVALID VALUE - __Invalid_value__ - __Invalid_value__</li>
                     </ul>
                  </td>
               </tr>
               <tr>
                  <td>modifiedBy (userBase)</td>
                  <td>Modified by</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>name</td>
                  <td>ID</td>
                  <td>string (64)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>orgUnit (orgUnitBase)</td>
                  <td>Organizational unit</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>publicLabel</td>
                  <td>Service label</td>
                  <td>string (128)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>start</td>
                  <td>Date de début</td>
                  <td>date </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subLandingPage (landingPageSubscriptionBase)</td>
                  <td>Subscription landing page</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenario (deliveryMCTemplateBase)</td>
                  <td>Subscription confirmation</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subScenarioEventType</td>
                  <td>SubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>subscriptions</td>
                  <td>Abonnements</td>
                  <td>collection </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>targetResource</td>
                  <td>Dimension de ciblage</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>template (service)</td>
                  <td>Service template</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>miniature</td>
                  <td>Miniature</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>title</td>
                  <td>Service</td>
                  <td>string (255)</td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubLandingPage (landingPageUnsubscriptionBase)</td>
                  <td>Unsubscription landing page</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenario (deliveryMCTemplateBase)</td>
                  <td>Unsubscription confirmation</td>
                  <td>link </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>unsubScenarioEventType</td>
                  <td>UnsubScenarioEventType</td>
                  <td>string </td>
                  <td> </td>
               </tr>
               <tr>
                  <td>validityDuration</td>
                  <td>Validity duration</td>
                  <td>number </td>
                  <td> </td>
               </tr>
            </table>

## Filtres

Disponible durant la période donnée (byPlanning)

<table>
    <tr>
    <th>Nom</th>
    <th>Type</th>
    </tr>
    <tr>
    <td>startDate</td>
    <td>date</td>
    </tr>
    <tr>
    <td>endDate</td>
    <td>date</td>
    </tr>
</table>

Par type de canal (byChannel)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>channel</td>
<td>enumeration</td>
</tr>
</table>

Par nom ou libellé (byText)

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

Par ressource de ciblage (byTargetResource)

<table>
<tr>
<th>Nom</th>
<th>Type</th>
</tr>
<tr>
<td>targetResource</td>
<td>string</td>
</tr>
</table>
