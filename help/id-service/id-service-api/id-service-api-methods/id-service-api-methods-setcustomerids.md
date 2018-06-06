---

title: API Methods - setCustomerIDs
description: setCustomerIDs method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - setCustomerIDs
SEO description: setCustomerIDs method for the Adobe Experience Cloud ID Service API
short-title: free text
doc-type: article
audience: 
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

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
