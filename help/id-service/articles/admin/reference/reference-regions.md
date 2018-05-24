---

title:  Get region and user IDs
description: 
SEO title: Get Region and User IDs From the AMCV Cookie or the ID Service
SEO description: 
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: Reference
guide subtopic 1: 
guide subtopic 2: 

---

# Get Region and User IDs From the AMCV Cookie or the ID Service

The AMCV cookie contains the Experience Cloud ID `MID` and a region ID for your site visitors. These IDs are stored as key-value pairs. 

+ The `mid:user` ID holds the visitor's Experience Cloud ID. 
+ The `aamlh:region` ID holds the region ID for your site visitors. 
+ You can recover this information by parsing the AMCV cookie.

For more information, see [Get User IDs and Regions Through the Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/aam/dcs-mcid-ids.html).

If you're an Audience Manager customer, you can get the region ID from the response sent by the Data Collection Server (DCS). See [Get User IDs and Regions from a DCS Response](https://marketing.adobe.com/resources/help/en_US/aam/dcs-aam-ids.html).

You can also get the region ID with a `GET` method provided by the ID service. See [`getLocationHint`](../id-service-api/id-service-api-methods/id-service-api-methods-getlocationhint.md)

[MORE!]

+ [Cookies and the Experience Cloud ID Service](../getting-started/getting-started-cookies.md)

[!END]
