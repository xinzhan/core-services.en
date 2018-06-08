---

title: API Methods - setCustomerIDs
description: setCustomerIDs method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - setCustomerIDs
seo-description: setCustomerIDs method for the Adobe Experience Cloud ID Service API
short-title: setCustomerIDs
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false

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