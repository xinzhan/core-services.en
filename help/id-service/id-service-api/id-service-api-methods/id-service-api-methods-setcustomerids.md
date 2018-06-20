---
title: api methods - setcustomerids
description: setcustomerids method for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api methods - setcustomerids
seo-description: setcustomerids method for the adobe experience cloud id service api
short-title: setcustomerids
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-methods/id-service-api-methods-setcustomerids.md
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

# setCustomerIDs

`setCustomerIDs` sets 1 or more key-value pairs that define customer IDs and their authentication state.

## Syntax

`visitor.setCustomerIDs()`

## Sample Code

You can set single or multiple IDs as shown in the code sample below. See [Customer IDs and Authentication States](mcvid-authenticated-state.html#) for more information and examples.

```javascript
// Single ID with a single authentication state
visitor.setCustomerIDs({
    "userid":{
        "id":"67312378756723456",
        "authState":Visitor.AuthState.AUTHENTICATED
    }
});

//Multiple IDs with a single authentication state
visitor.setCustomerIDs({
    "userid":{
        "id":"67312378756723456",
        "authState":Visitor.AuthState.AUTHENTICATED
    },
    "puuid":"550e8400-e29b-41d4-a716-446655440000"
});
```