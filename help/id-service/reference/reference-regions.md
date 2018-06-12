---
title: get region and user ids
description: the amcv cookie contains the experience cloud id mid and a region id for your site visitors.
seo-title: get region and user ids from the amcv cookie or the id service
seo-description: the amcv cookie contains the experience cloud id mid and a region id for your site visitors.
short-title: get region and user ids
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false
product: core services id service
cloud: experience cloud
archetype: admin
user-guide: id service admin guide
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/reference/reference-regions.md
git-issue: https://git.corp.adobe.com/AdobeDocs/core-services.en/issues/new
git-repo: https://git.corp.adobe.com/adobedocs/core-services.en
---
<!--Meta Data Values

**Required Meta for search optimization and page data**

title: free text string

description: free text string

seo-title: free text string

seo-description: free text string

**Optional Meta for extended capabilities**

audience:
all (default), admin, developer, end-user
 
index: true (default), false
 
translate:
true (default), false
 
doc-type:
reference (default), tutorials

version:
false (default), Classic, Standard, 6.5, 6.4, 6.3, 6.2
 
private-feature-pack:
false (default), true
 
beta:
false (default), true
 
redirect:
false (default), pathname
-->

# Get Region and User IDs From the AMCV Cookie or the ID Service

The AMCV cookie contains the Experience Cloud ID `MID` and a region ID for your site visitors. These IDs are stored as key-value pairs.

+ The `mid:user` ID holds the visitor's Experience Cloud ID.
+ The `aamlh:region` ID holds the region ID for your site visitors.
+ You can recover this information by parsing the AMCV cookie.

For more information, see [Get User IDs and Regions Through the Experience Cloud ID Service](https://marketing.adobe.com/resources/help/en_US/aam/dcs-mcid-ids.html).

If you're an Audience Manager customer, you can get the region ID from the response sent by the Data Collection Server (DCS). See [Get User IDs and Regions from a DCS Response](https://marketing.adobe.com/resources/help/en_US/aam/dcs-aam-ids.html).

You can also get the region ID with a `GET` method provided by the ID service. See [`getLocationHint`](../id-service-api/id-service-api-methods/id-service-api-methods-getlocationhint.md)

More Information

+ [Cookies and the Experience Cloud ID Service](../getting-started/getting-started-cookies.md)