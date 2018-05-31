---

title: Order of Operations for Analytics IDs
description: Order of Operations for Analytics IDs when using Adobe Experience Cloud ID ServiceI
SEO title: Order of Operations for Analytics IDs when using Adobe Experience Cloud ID Service
SEO description: Order of Operations for Analytics IDs when using Adobe Experience Cloud ID Service
author: gipaul
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: Reference
guide subtopic 1: Reference Analytics
guide subtopic 2:

---

# Order of Operations for Analytics IDs

After you deploy the visitor ID service, there are five ways a visitor can be identified in Analytics. In many scenarios you might see two or three different IDs on a call, but Analytics will use the first ID present from that list as the official Experience Cloud ID. 

For example, if you are setting a custom visitor ID (included in the `vid` query parameter), that ID will be used before other IDs that might be present on that same hit. See [Setting Analytics and Experience Cloud IDs](reference-analytics-ids.md) for more information.

[!PROCEDURE Title="Order of Operations"]
1. **vid (s.visitorID)**\
*Present when*: The `s.visitorID` is set.

2. **aid (s_vi cookie)**\
*Present when*: The visitor had an existing `s_vi` cookie before you deployed the Experience Cloud ID service, or you have a grace period configured.

3. **Experience Cloud ID (MID)**\
*Present when*: The visitor's browser accepts first-party cookies. This is set by the `AMCV` cookie.

4. **fid (fallback cookie on H.25.3 or newer, or AppMeasurement for JavaScript)**\
*Present when*: A browser doesn't accept third-party cookies and the Analytics tracking server is set up as a third-party tracking server.

    [!NOTE]
    The `fid` is a legacy identifier and is not used if you've implemented the ID service on your site. In this case, the `fid` is not needed because the first-party, `AMCV` cookie makes it obsolete. It has been retained to support legacy code and for historic reasons.
    [!END]

5. **IP Address, User Agent, Gateway IP Address**\
*Present when*: The visitor's browser does not accept cookies.
[!END]
