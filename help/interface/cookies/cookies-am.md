---
description: Audience Manager relies on a few simple cookies to perform different functions. These include things like assigning IDs, recording data calls, error tracking, and testing to see if cookies can be set. This section lists and describes the various cookies set by Audience Manager.
keywords: cookies
seo-description: Audience Manager relies on a few simple cookies to perform different functions. These include things like assigning IDs, recording data calls, error tracking, and testing to see if cookies can be set. This section lists and describes the various cookies set by Audience Manager.
seo-title: Audience Manager Cookies
solution: Marketing Cloud,Audience Manager
title: Audience Manager Cookies
uuid: 8b384c38-b85a-4e93-b00e-41a9d3ae2b21
---

# Audience Manager Cookies{#audience-manager-cookies}

Audience Manager relies on a few simple cookies to perform different functions. These include things like assigning IDs, recording data calls, error tracking, and testing to see if cookies can be set. This section lists and describes the various cookies set by Audience Manager.

**demdex Cookie**

<table id="table_1CCF7EA2BC9E421F8DEECA5F611E33F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Purpose</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> sets this cookie to assign a unique ID to a site visitor. The <span class="wintitle"> demdex </span> cookie helps <span class="keyword"> Audience Manger </span> perform basic functions such as visitor identification, ID synchronization, segmentation, modeling, reporting, etc. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Content</b> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> demdex </span> cookie contains a Unique User ID (UUID) as shown in the example below: </p> <p> <span class="codeph"> 06151304227769720433039235178204449977 </span> </p> <p>See also, <a href="https://marketing.adobe.com/resources/help/en_US/aam/ids-in-aam.html" format="https" scope="external"> Index of IDs in Audience Manager </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Other Attributes</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_11291DA87C5045E880034E06C863BCDA"> 
      <li id="li_40C30A06A12449A4A8748621223CA71B">Lifetime: The <span class="wintitle"> demdex </span> cookie has a time-to-live (TTL) interval of 180-days. The TTL is reset to 180-days upon each user interaction with a partner website. The cookie expires if a user does not come back to your site within the TTL interval. </li> 
      <li id="li_A589EDA2198249829207A183872EF1FF">Opt-out: <span class="keyword"> Audience Manager </span> resets the cookie with a <span class="codeph"> Do Not Target </span> string if a user opts-out of data collection. In this case, the cookie TTL is set as 10 years. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**dextp Cookie**

<table id="table_7343C9C9ADD24D3FA693ECC76E4A4045"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Purpose</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> sets this cookie to record the last time it made a data synchronization call. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Content</b> </p> </td> 
   <td colname="col2"> <p>The <span class="wintitle"> dextp </span> cookie contains a data provider name or ID and a UNIX UTC timestamp formatted as pipe-delimited strings. In the examples, <i>italics</i> represents a variable placeholder. </p> <p> 
     <ul id="ul_80D0BC3FCF06470991E12712401D784A"> 
      <li id="li_03747A433CEB4756A26CD866E716B89D">Old style: <span class="codeph"> <span class="varname"> data provider name here </span>-1490307822097| <span class="varname"> data provider name here </span>-1490307822038 </span> </li> 
      <li id="li_79E7000E82DB4ADA9E9887B017343B2D">New style: <span class="codeph"> 21-1-1490307821616|544-1-1490307821793|3-1-1490307821852|420-1-1490307822038| </span> </li> 
     </ul> </p> <p>See also, the dextp data syntax section below. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Other Attributes</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_4922AC2CD55D4C888A6FBEB22F8B889B"> 
      <li id="li_91A68C44E53840379C2ACDED25468735">Lifetime: The <span class="wintitle"> dextp </span> cookie has a time-to-live (TTL) interval of 180-days. </li> 
      <li id="li_6B8C674EFAAC4DABA0A640CF29247F99">Opt-out: <span class="keyword"> Audience Manager </span> resets the cookie with a <span class="codeph"> Do Not Target </span> string if a user opts-out of data collection. In this case, the cookie TTL is set as 10 years. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

dextp Cookie Data Syntax:

The following table lists and defines the elements in a [!DNL dextp] cookie by location in the data string.

<table id="table_BE00604B97F24F5A94AA4F566063D785"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable Position </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>First or Second</b> </p> </td> 
   <td colname="col2"> <p>The position of the data provider name or ID varies depending on if the cookie uses the new or old style formatting. </p> <p> <b>Old style formatting:</b> </p> <p> 
     <ul id="ul_5BFBF40E3FE849CA859030F2D070FDF6"> 
      <li id="li_E8F4DC0CB15B472ABE9892B3A61D7F77">Syntax: <span class="codeph"> <span class="varname"> data provider name </span> - <span class="varname"> UNIX UTC timestamp </span> </span> </li> 
      <li id="li_7CD8B101156140F49EA97B18E9591402">Example: <span class="codeph"> dataProvider1 - 1490307822038 </span> </li> 
     </ul> </p> <p>The old style cookie identifies the data provider with a readable name. </p> <p> <b>New style formatting:</b> </p> <p> 
     <ul id="ul_AC6225CA781746148C125F21DFED1ED9"> 
      <li id="li_29C4B52E398B4EA28944980A15B05A57">Syntax: <span class="codeph"> <span class="varname"> data provider ID </span> - 1|2 - <span class="varname"> UNIX UTC timestamp </span> </span> </li> 
      <li id="li_3BF30CA5FED242DF96E0B54AFC64B06F">Example: <span class="codeph"> 123345 - 1 - 1490307822038 </span> </li> 
     </ul> </p> <p>The new style cookie: </p> <p> 
     <ul id="ul_F05A91A455FA44C7A71186C0C9E31630"> 
      <li id="li_A8C9638173684359BABC4207845A4F48">Replaces the readable data provider name with a numeric ID. </li> 
      <li id="li_28F1E2DB24904E53BE9718AD788CE61E">Identifies the call type with ID 1 or ID 2. ID 1 represents an ID synchronization call. ID 2 represents a deprecated call that is no longer used. You should not see many (or any) dextp cookies with ID 2. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Last</b> </p> </td> 
   <td colname="col2"> <p>The last position contains a UNIX UTC timestamp. </p> </td> 
  </tr> 
 </tbody> 
</table>

**dst Cookie**

<table id="table_83AE9B6350C6408BAECD9FCF33022B98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Purpose</b> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"> Audience Manager </span> sets this cookie when there's an error sending data to a <a href="https://marketing.adobe.com/resources/help/en_US/aam/c_destinations.html" format="https" scope="external"> destination </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Content</b> </p> </td> 
   <td colname="col2"> <p> The <span class="wintitle"> DST </span> cookie contains sets of destination IDs and UNIX time-stamps formatted as pipe-delimited strings. In the examples, <i>italics</i> represents a variable placeholder. </p> <p> 
     <ul id="ul_CE98076A02DA413486C1D341E9806889"> 
      <li id="li_850209D956644749B98C7A208C825C15">Syntax: <span class="codeph"> <span class="varname"> destination ID </span> - <span class="varname"> UNIX UTC timestamp </span> </span> </li> 
      <li id="li_4A22152C70844733982230EBF7B9EB78">Example: <span class="codeph"> 067797-1490349684|1010788-1490349692|1067797-1490349692 </span> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Other Attributes</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_5D13DD701B484B51BF2808A69A919106"> 
      <li id="li_4E665114C63246FBA32A4E19984D2693">Lifetime: The <span class="wintitle"> dst </span> cookie has a time-to-live (TTL) interval of 180-days. </li> 
      <li id="li_A682B566704F43D2AB72487EFF212474">Opt-out: <span class="keyword"> Audience Manager </span> resets the cookie with a <span class="codeph"> Do Not Target </span> string if a user opts-out of data collection. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**_dp Cookie**

This is a temporary cookie. [!DNL Audience Manager] tries to set the [!DNL _dp] cookie to determine if it can set other cookies in the demdex.net domain in a third-party context. When [!DNL _dp] is set it contains a value of 1. [!DNL Audience Manager] reads this value and immediately removes the cookie. If the [!DNL _dp] cookie is not present, [!DNL Audience Manager] knows it cannot set cookies.