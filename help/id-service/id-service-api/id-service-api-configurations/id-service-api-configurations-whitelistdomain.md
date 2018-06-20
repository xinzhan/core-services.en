---
title: api configurations - whitelistparentdomain and whitelistiframedomains
description: whitelistparentdomain and whitelistiframedomains configurations for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api configurations - whitelistparentdomain and whitelistiframedomains
seo-description: whitelistparentdomain and whitelistiframedomains configurations for the adobe experience cloud id service api
short-title: whitelistparentdomain
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-configurations/id-service-api-configurations-whitelistdomain.md
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

# whitelistParentDomain and whitelistIframeDomains

These configurations let different instances of ID service code implemented in an iFrame and on the parent page communicate with each other. They're designed to help resolve problems with two specific use cases where you may or may not control the parent page/domain and you have ID service code loading in the iFrame of a domain that you do control.

They are available in `VisitorAPI.js` code version 2.2, or higher.

## Syntax

Both configuration elements are required when you use this code.

| Configuration Syntax                                                        | Description                                                    |
| --------------------------------------------------------------------------- | -------------------------------------------------------------- |
| `whitelistParentDomain: "Domain name of parent page"`                       | Accepts a single domain name passed in as a string.            |
| `whitelistIframeDomains: ["iFrame domain","iFrame domain","iFrame domain"]` | Accepts one or more iFrame domain names passed in as an array. |

## Code Sample

Your configured ID service code could look similar to this example.

```javascript
//Instantiate Visitor
var visitor = Visitor.getInstance("Insert Experience Cloud Organization ID here",{
	...
	//Add parent page domain name and iFrame domain names
	whitelistParentDomain: "parentpageA.com",
	whitelistIframeDomains: ["iFrameDomain1.com","iFrameDomain2.com"],
	...
	}
);
```

## Use Cases

These configurations help solve the problem of setting an ID service cookie and assigning a visitor ID when browsers block third-party cookies and if either of these conditions apply:

+ You do or do not control the parent page/domain.
+ ID service code is not installed on the parent page, but is implemented in an iFrame.

>[!NOTE]
>You may also want to implement these configurations when you're serving video in an iFrame with [Video Heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/). Video Heartbeat needs an ID service ID \(the 'MID'\) to work properly.

### Use Case 1: The Browser Blocks Third-Party Cookies and the ID Service is Implemented on the iFrame and Parent Page

**Conditions**
This use case includes the following conditions:

+ Company A implements the ID service on their home page.
+ Company A implements the ID service in iFrame on their home page.
+ Company A owns the parent page and the iFrame and have implemented the ID service in both places.
+ A customer loads the parent page in a browser that blocks third-party cookies.

**Results**

Given these conditions, the ID service:

+ Works properly on the parent page. 
    + It requests and sets the AMCV cookie and assigns a unique ID to the site visitor.
+ Does not work in the iFrame. 
    + This is because the browser sees the iFrame as a third-party domain and prevents the ID service from setting the AMCV cookie.

**Solution**

+ Modify the ID service `Visitor.getInstance` function in the iFrame with these white list configurations. 
    + Specify the parent and child domains in the code. These configurations let the ID service code in the iFrame check the ID service code on the parent page for a visitor ID.
+ If the ID service code in the iFrame doesn't receive a response parent page, these configurations generate a local visitor ID.

### Use Case 2: Requesting an ID from an iFrame embedded in a parent page you do not control or that does not use the ID service

**Conditions**

This use case includes the following conditions:

+ Company A does not use the ID service.
+ Company A loads an iFrame on the page. 
    + This iFrame is owned by Company B and loads in a separate domain than Company A.
+ The browser blocks third-party cookies.

**Results**

Given these conditions, the ID service:

+ Does not work in the iFrame. This is because the browser sees the iFrame as a third-party domain and prevents the ID service from setting the `AMCV` cookie.
+ Can't get a visitor ID from the parent page because Company A doesn't use this service.

**Solution**

Modify the ID service `Visitor.getInstance` function in the iFrame with these white list configurations. Specify the parent and child domains in the code. These configurations let the ID service code in the iFrame check the ID service code on the parent page for a visitor ID.

If the ID service code in the iFrame doesn't receive a response parent page, these configurations generate a local visitor ID.

## Configuration Safety and Security

You can implement these configurations safely because:

+ The ID service implemented on parent domain and the iFrame domain must use the same organization ID. These white list configurations will not work when the organization IDs on the parent or in the iFrame are different.
+ These configurations only communicate with the domain and iFrames specified in the code.
+ The communication between the iFrame and the parent page follows a specific format. If the ID service on the parent page does not receive a request in the expected format this sharing process will fail.

## Supported Visitor API Methods

The ID service supports a limited set of public API methods when you implement these white list configurations. The supported methods vary according to the use case scenarios described above.

**Case 1**

+ `getMarketingCloudID`
+ `getAudienceManagerLocationHint`
+ `getAudienceManagerBlob`
+ `getSupplementalDataID`
+ `getCustomerIDs`

**Case 2**

+ `getSupplementalDataID`
+ `getMarketingCloudVisitorID`