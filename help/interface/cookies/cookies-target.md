---
description: Learn how Adobe Target uses cookies to give website operators the ability to test which online content and offers are more relevant to visitors.
keywords: cookies;privacy
solution: Experience Cloud,Analytics,Target,Social
title: Adobe Target Cookies 
uuid: 44f7e32e-8d99-4682-8b54-8364d001b403
feature: Cookies
topic: Administration
role: Administrator
level: Experienced
exl-id: c4399cc0-8333-47b8-b830-2ba7359f464a
---
# Adobe Target Cookies{#target-cookies}

Adobe Target uses cookies to give website operators the ability to test which online content and offers are more relevant to visitors.

You can change these settings if needed, except for the cookie duration. Consult your account representative when changing cookie settings.

>[!NOTE]
>
>Adobe Target users can also create customized third-party cookies.

|Setting|Information|
| --- | --- |
|Cookie name|mbox.|
|Cookie domain|The second and top levels of the domains from which you serve the mbox. Because it is served from your company's domain, the cookie is a first party cookie. Example: `mycompany.com`.|
|Server domain|`clientcode.tt.omtrdc.net`, using the client code for your [!DNL Adobe Target] account.|
|Cookie duration|The cookie remains on the visitor's browser two years from his or her last login. You cannot change the cookie duration.|



>[!NOTE]
>
>If any of your domain names include a country code, such as `mycompany.co.uk`, work with your Client Services to configure your [!DNL at.js] to support this.

The cookie keeps a number of values to manage how your visitors experience Adobe Target campaigns:

|Value|Definition|
| --- | --- |
|session ID|A unique identifier for a given user session. By default the session expires after 30 minutes of inactivity. If you are generating sessionId yourself (for example, for server-side implementations), ensure following:<ul><li>The Session ID can be any printable string except a space, question mark ( ? ), or a forward slash ( / ).</li><li>* The Session ID should be between 1 and 128 characters in length.</li><li>For a particular session, its value must stay the same across multiple requests</li><li>You should never have parallel sessions (distinct sessionIds) for a given visitor at any point in time.</li></ul>Routing to a particular node in the edge cluster is done using Session ID.<ul><li>The session is active for 30 minutes on the server side. Therefore, you shouldn’t use a different Session Id for a particular `tntId/thirdPartyId` within 30 minutes of the last request made with the `tntId/thirdPartyId`. Otherwise, changes to the profile could be inconsistent and unpredictable.</li><li>Using the same Session ID with multiple `tntIds/thirdPartyIds` can cause unpredictable changes to the profiles identified by the `tntId/thirdPartyIDs`.</li></ul>**Note**: See [limit on number of concurrent requests](https://experienceleague.adobe.com/docs/target/using/troubleshoot/target-limits.html?lang=en#content-delivery) for a given session ID.|
|pc ID|A semi-permanent ID for a visitor's browser. Lasts until cookies are manually deleted.|
|check|A simple test value used to determine if a visitor supports cookies. Set each time a visitor requests a page.|
|disable|Set if visitor's load time exceeds the timeout configured in the at.js file. By default, this lasts 1 hour.|

