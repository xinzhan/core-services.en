---
title: api methods - appendsupplementaldataidto
description: appendsupplementaldataidto helper method for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api methods - appendsupplementaldataidto
seo-description: appendsupplementaldataidto helper method for the adobe experience cloud id service api
short-title: appendsupplementaldataidto
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/reference/reference-authenticated-state.md
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

# Customer IDs and Authentication States

Along with the Experience Cloud visitor ID, you can associate additional customer IDs and an authentication status with each visitor.

## Authentication States
The setCustomerIDs method accepts multiple customer IDs for the same visitor. This helps you identify or target an individual user across different devices. For example, you can upload these IDs as customer attributes to the Experience Cloud and access this data across the different solutions.

>[!IMPORTANT]
>
>`setCustomerIDs` (customer ID synchronization) is required by customer attributes and core services functionality. Synching customer IDs is an optional identification method for Analytics. Target requires `Visitor.AuthState.AUTHENTICATED` for Customer Attributes to work.

Beginning with Experience Cloud ID service v1.5+, `setCustomerIDs` includes the optional `AuthState` object. `AuthState` identifies visitors according to their authentication status (e.g., logged in, logged out). You set the authentication state with a status value listed in the table. Authentication status is returned as an integer.

## Set Customer IDs and Authenticated States
Customer IDs can include combinations of IDs and authenticated states as shown in the following examples.

>[!IMPORTANT]
>
>+ IDs are case-sensitive.
>+ Only use un-encoded values for your IDs.
>+ Customer IDs and authentication states are not stored in the visitor ID cookie. They must be set for every page or application context.
>+ You should not include any Personally Identifiable Information (PII) in the customer IDs. If you are using PII to identify a visitor (such as an email address), we recommend storing a hashed or encrypted version of the information instead.

```javascript
// Single ID with a single authentication state
visitor.setCustomerIDs({
    "userid":{
        "id":"67312378756723456",
        "authState":Visitor.AuthState.AUTHENTICATED
    }
});

/* 
Multiple IDs with only the first ID explicitly assigned an authentication state.
The second ID is not explicitly assigned an authentication state and is implicitly
assigned Visitor.AuthState.Unknown by default.
*/
visitor.setCustomerIDs({
    "userid":{
        "id":"67312378756723456",
        "authState":Visitor.AuthState.AUTHENTICATED
    },
    "puuid":"550e8400-e29b-41d4-a716-446655440000"
});

// Multiple IDs with identical authentication states
visitor.setCustomerIDs({
    "userid":{
        "id":"67312378756723456",
        "authState":Visitor.AuthState.AUTHENTICATED
    },
    "puuid":{
        "id":"550e8400-e29b-41d4-a716-446655440000",
        "authState":Visitor.AuthState.AUTHENTICATED
    }
});

// Multiple IDs with different authentication states
visitor.setCustomerIDs({
    "userid":{
        "id":"67312378756723456",
        "authState":Visitor.AuthState.AUTHENTICATED
    },
    "puuid":{
        "id":"550e8400-e29b-41d4-a716-446655440000",
        "authState":Visitor.AuthState.LOGGED_OUT
    }
});
```

## Return Customer IDs and Authenticated States

Use getCustomerIDs to return customer IDs and related authenticated states. This method returns a visitor's authenticated state as an integer.

### Syntax

`getCustomerIDs` returns data with the following syntax.

```javascript
{
    [customerIDType1]:{
        "id":[customerID1],
        "authState":[authState1]
    },
    [customerIDType2]:{
        "id":[customerID2],
        "authState":[authState2]
    }
    ...
}
```

### Examples

Returned customer IDs and authentication state data should look similar to the following examples.

```javascript
Object customerIDs = visitor.getCustomerIDs();
 
// No setCustomerIDs call on this instance
{}
 
// setCustomerIDs call on this instance with {"userid":{"id":"67312378756723456"}}
{
    "userid":{
        "id":"67312378756723456",
        "authState":0
    }
}
 
// setCustomerIDs call on this instance with {"userid":{"id":"67312378756723456","authState":Visitor.AuthState.AUTHENTICATED}}
{
    "userid":{
        "id":"67312378756723456",
        "authState":1
    }
}
 
// setCustomerIDs call on this instance with {"userid":{"authState":Visitor.AuthState.LOGGED_OUT}}
{
    "userid":{
        "authState":2
    }
}
 
// setCustomerIDs call on this instance with {"userid":{"authState":Visitor.AuthState.LOGGED_OUT},"puuid":{"id":"550e8400-e29b-41d4-a716-446655440000"}}
{
    "userid":{
        "authState":2
    },
    "puuid":{
        "id":"550e8400-e29b-41d4-a716-446655440000",
        "authState":0
    }
 }
```

## SDK Support
The Experience Cloud ID service supports customer IDs and authentication states in our Android and iOS SKD code. See the following code libraries:

+ Android SDK methods
+ iOS SDK methods

## Notice for Analytics and Audience Manager Customers
If you're passing declared IDs to Audience Manager, the userid object needs to match the integration code associated with a data source. For more information, see the Visitor ID Service section in the Configure Merge Rules Code documentation.