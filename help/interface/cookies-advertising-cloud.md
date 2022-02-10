---
description: Learn about Adobe Ad Cloud cookies for mapping ad engagement events to conversion events and, potentially, to use that information to optimize ad bids.
title: Advertising Cloud Cookies 
uuid: 2eec48a3-3e81-488e-8e30-5fd62885de0b
feature: Cookies
topic: Administration
role: Admin
level: Experienced
exl-id: 6818edea-31b1-49fc-bca2-32828c7ca78d
---
# Advertising Cloud Cookies{#advertising-cloud-cookies}

Advertising Cloud uses cookies to map ad engagement events to conversion events and, potentially, to use that information to optimize ad bids.

>[!NOTE]
>
>The beta Advertising Cloud Javascript tag that uses the [Adobe Experience Cloud ID (ECID) Service](https://experienceleague.adobe.com/docs/id-service/using/intro/overview.html) creates [first-party Experience Cloud s_ecid cookies](cookies-first-party.md), not Advertising Cloud cookies.

## Cookie Name: _lcc

<table id="table_821F8EBE91F244CBA72B0975B961B908"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>IDs and time stamps (in the format yyyymmdd) of display clicks</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>15 minutes</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>A third-party cookie used to determine if a click event on a display ad applies to an Adobe Analytics hit </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>everesttech.net </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>52 bytes </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: _tmae 

<table id="table_28C2B62595E240D5A3C3E0BE147748C1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>Encoded IDs and time stamps for ad engagements using Advertising Cloud DSP tracking </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>1 year </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>A third-party cookie that stores user engagements with ads, such as “last seen ad xyz123 on June 30, 2016” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>everesttech.net </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>Variable; data is encoded and typically less than 1 KB </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: adcloud 

<table id="table_D7CD238736BC4571883F92F47673F57C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>The timestamps of the surfer's last visit to the advertiser’s website and the surfer's last search click, and the ef_id that was created when the user clicked an ad</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>Cookies set on 24 February 2021 or earlier expire after 730 days. Cookies set on 25 February 2021 or later expire after 364 days.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>A first-party cookie that associates the surfer ID with relevant audience segments and conversions </p> <p> Information about the last visit is used to optimize page load times by avoiding unnecessary requests to Adobe servers. </p> <p>Information about the last search click helps determine if a conversion event was the result of a click or a view-through (conversion resulting from impressions but no clicks). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>The advertiser's top-level domain (such as example.com) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>Variable, but typically 50-150 bytes </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: ev_sync_&#42;

(ev_sync_ax, ev_sync_bk, ev_sync_dd, ev_sync_fs, ev_sync_ix, ev_sync_nx, ev_sync_ox, ev_sync_pm, ev_sync_rc, ev_sync_tm, ev_sync_yh) 

<table id="table_A05C02AB261946E0AABAD78259392D81"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>The date when synchronization is performed, in the format yyyymmdd </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>The date when synchronization is performed, in the format yyyymmdd </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>A third-party, ad exchange-specific cookie that syncs the Advertising Cloud surfer ID with the partner ad exchange. It's created for new surfers and sends a synchronization request when it's expired. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>everesttech.net </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>8 characters </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: everest_g_v2 

<table id="table_04043292A43B41B69EAF17AF4E217C69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>The browser and surfer ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>2 years </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>Created after a user initially clicks a client's ad, and used to map the current and subsequent clicks with other events on the client's website </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>everesttech.net </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>~27 characters </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: everest_session_v2 

<table id="table_1A3AE4CA71304ADB943CB1F64BE695F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>The session ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>When the browser is closed </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>A third-party browser session cookie; one cookie is used for all accounts </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>everesttech.net </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>~16 characters </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: ev_tm 

<table id="table_6C4D9DCFA4BF4FB2BD445E027550955F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>Advertising Cloud DSP (Demand Side Platform) ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>2 years </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>A third-party cookie that stores the DSP ID that corresponds to the surfer ID in the everest_g_v2 cookie </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>everesttech.net </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>~20 bytes </p> </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: id_adcloud 

<table> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Information Stored </p> </td> 
   <td colname="col2"> <p>The surfer ID </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expiration </p> </td> 
   <td colname="col2"> <p>91 days </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usage </p> </td> 
   <td colname="col2"> <p>The cookie is set in the first-party domain but isn't used yet </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Location </p> </td> 
   <td colname="col2"> <p>The advertiser's top-level domain (such as example.com) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Size </p> </td> 
   <td colname="col2"> <p>16 bytes </p> </td> 
  </tr> 
 </tbody> 
</table>
