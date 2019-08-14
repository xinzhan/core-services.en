---
description: Scene7 uses cookies to store helpful information that can be used to delivery dynamic media to the browser.
keywords: cookies;privacy
seo-description: Scene7 uses cookies to store helpful information that can be used to delivery dynamic media to the browser.
seo-title: Scene7 Cookies
solution: Marketing Cloud,Analytics,Target,Social
title: Scene7 Cookies
uuid: f9b9d13a-17e5-4139-8c84-6fe5d22c4196
index: y
internal: n
snippet: y
---

# Scene7 Cookies{#scene-cookies}

Scene7 uses cookies to store helpful information that can be used to delivery dynamic media to the browser.

Scene7 stores information locally for some older AS2 Flash-based viewers.

For AS2 viewers, cookies:

* Track a user's session state, such as current page and image viewed, current zoom level, etc. 
* Determine how long it has been since the user's previous session. The viewer uses this information to decide whether to continue a previous session or start a new one. This information is also sent to the Scene7 servers, but that is not used.

For AS2 Flash eCatalog viewer, cookies:

* Store user-generated content (most notably content entered by the user in the "sticky notes" feature of the ecatalog viewer). This content is restored when the user resumes a session. 
* When the user initiates an email to share the ecatalog with another user, the sticky notes content from the second AS2 viewers bullet is copied to our servers to provide it to the recipient. When the recipient initiates the viewer session, the sticky notes content is retrieved from the server and copied to a cookie. This feature is little-used, so it does not expire and stale content is not removed. At this time it persists on the servers indefinitely.

The newer AS3 viewers do not implement session persistence.

* [Cookie Name: VatLogin.jsp](../cookies/cookies-s7.md#section-03aa90aa7e36427b8cb12dc4a0f0291e) 
* [Cookie Name: s7js.flyout.InfoMessage.displayed.state](../cookies/cookies-s7.md#section-14ad50dfcd7342f9ac80283b1f0d3400) 
* [Cookie Name: s7js.flyout.InfoMessage.displayed_idx.ant](../cookies/cookies-s7.md#section-05d1c52c478541609f4a18a9c1eb032f)

## Cookie Name: VatLogin.jsp {#section-03aa90aa7e36427b8cb12dc4a0f0291e}

|  Attribute  | Description  |
|---|---|
|  Information Stored  | Sets the session cookie. The AuthFilter embedded into IPS ImageServer (IS, IR, and also the SWFs/skins and video contexts) uses the cookie for access authorization. If present, it allows HTTP requests to pass through. Otherwise it returns unauthorized.  |
|  Expiration  | This cookie is a session cookie. Current session expiration is set to 45 minutes in the Scene7 IPS [!DNL web.xml].  |

## Cookie Name: s7js.flyout.InfoMessage.displayed<assetId>.state {#section-14ad50dfcd7342f9ac80283b1f0d3400}

<table id="table_6835D64C5D464A049F576621F2BE3FAD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Information Stored </td> 
   <td colname="col2"> <p>&lt;assetId&gt; is the name of the asset the viewer is working with. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expiration </td> 
   <td colname="col2"> This cookie is a session cookie and expires when the browser is closed. </td> 
  </tr> 
 </tbody> 
</table>

## Cookie Name: s7js.flyout.InfoMessage.displayed<assetId>_idx<id>.ant {#section-05d1c52c478541609f4a18a9c1eb032f}

Browser cookies are used by legacy DHTML viewers for storing state information and sticky notes data. They are also used by the multiscreen DHTML flyout for making message indicator session-specific. 

<table id="table_8F6CC83D32D54BEE99884318AD126C98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attribute </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Information Stored </td> 
   <td colname="col2"> <p> </p> <p> &lt;assetId&gt; is the name of the asset the viewer is working with and &lt;id&gt; is the 0-based sticky note index. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Expiration </td> 
   <td colname="col2"> This cookie is a session cookie and expires when the browser is closed. </td> 
  </tr> 
 </tbody> 
</table>

