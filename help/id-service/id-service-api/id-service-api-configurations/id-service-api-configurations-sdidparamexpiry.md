---
title: api configurations - sdidparamexpiry
description: sdidparamexpiry configurations for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api configurations - sdidparamexpiry
seo-description: sdidparamexpiry configurations for the adobe experience cloud id service api
short-title: sdidparamexpiry
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-configurations/id-service-api-configurations-sdidparamexpiry.md
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

# sdidParamExpiry

This configuration lets you override the default Supplemental Data ID \(`SDID`\) expiration interval when passing that ID from one page to another using the `appendSupplementalDataIDTo` helper function.

>[!IMPORTANT]
>By default, the ID service code on the receiving page has 30 seconds to get the `SDID` from the URL sent by the referring page. If the ID service code on the receiving page can't retrieve the `SDID` in less than 30 seconds it requests a new `SDID`. This functionality is mainly for A4T customers who need to pass the `SDID` from one page to another and want control over this timeout interval.

## Override the SDID Timeout

If you need to change the default SDID timeout, add `sdidParamExpiry` to the `Visitor.getInstance` function with the following syntax:

## Syntax

`sdidParamExpiry: time in seconds`

## Code Sample

When configured, your ID service code could look similar to this sample. This sample sets the SDID timeout to 15 seconds. This configuration works with the [appendSupplementalDataIDTo](../id-service-api-methods/id-service-api-methods-appendsupplementaldataidto.md) helper method.

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   ...
   //Change the default SDID timeout to 15 seconds
   sdidParamExpiry: 15
});

//Call helper method to append SDID to the Page B URL from Page A
var pageB = "www.domain.com/pageB";
var pageBWithSdid = visitor.appendSupplementalDataIDTo(pageB, "67987653465787219");

```