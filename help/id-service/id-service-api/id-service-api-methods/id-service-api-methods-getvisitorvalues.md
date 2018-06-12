---
title: api methods - getvisitorvalues
description: getvisitorvalues method for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api methods - getvisitorvalues
seo-description: getvisitorvalues helper method for the adobe experience cloud id service api
short-title: getvisitorvalues
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-methods/id-service-api-methods-getvisitorvalues.md
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

# getVisitorValues

This is an asynchronous API that returns identifiers for Analytics, the ID service, data collection opt-out, geographic location, and metadata "blob" content by default. Also, you can control which IDs you want to return with the optional `visitor.FIELDS` enum.

## Syntax

This function uses the following syntax \(italics represents a placeholder for a variable\): `var values = visitor.getVisitorValues (callback, [visitor.FIELDS.ID type, visitor.FIELDS.ID type]);`

In the function parameters:

+ `callback` represents your own callback code that receives the returned IDs.
+ *\(Optional\)* `visitor.FIELDS.ID type` is an enum that lets you specify which `getvisitorvalues` you want this function to return.

See the following use cases and definitions for more information.

### Use Case 1: Request the Default Data Set
This code returns the standard data set. Your request and response could look similar to the following examples.

```javascript
//Call the ID service
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{...});
  
//Add your callback to the GET method to return IDs and data.
visitor.getVisitorValues(visitorIdsCallback);
```

In the default sample response, some values have been shortened for demonstration purposes.

```javascript
//Formatted IDs in JSON response
{
    MCMID: 'mid-1234',
    MCOPTOUT: 'isoptedout-true',
    MCAID: 'aid-1234',
    MCAAMLH: 7,
    MCAAMB: 'hgfe54236786oygj'
}
```

### Use Case 2: Request a Custom Data Set
This code uses an optional array to return a specific set of IDs using the `visitor.FIELDS` enum. In this case, we only want the visitor's Experience Cloud ID \(MCID\) and Analytics ID \(MCAID\). Your request and response could look similar to the following examples.

```javascript
//Call the ID service
var visitor = Visitor.getInstance("Insert Experience Cloud organization ID here", { ... });
  
  
// Add an optional array to specify which IDs you want to return.
visitor.getVisitorValues(visitorIdsCallback, [visitor.FIELDS.MCMID, visitor.FIELDS.MCAID]);
```

The customized sample response returns only those IDs specified in the request.

```javascript
//Formatted IDs in JSON response
{
    MCMID: 'mid-1234',
    MCAID: 'aid-4321'
}
```

## Response Parameters Defined

The following table lists and defines the response parameters. These are also all the values in the `visitor.FIELDS` enum. Note, this method returns and empty string if there are no values for a particular variable.

| Value      | Description                                                                                                                                                                                                             |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `MCAAMB`   | Encrypted Audience Manager metadata known as "the blob."                                                                                                                                                                |
| `MCAAMLH`  | The data collection region ID. This is a numeric identifier for the geographic location of a particular ID service data center.                                                                                         |
| `MCAID`    | The visitor's Analytics ID.                                                                                                                                                                                             |
| `MCMID`    | The visitor's Experience Cloud ID. See Cookies and the Experience Cloud ID Service.                                                                                                                                     |
| `MCOPTOUT` | A flag that indicates if a visitor has opted out of data collection. Values include: `isoptedout-true`: A visitor has opted out of data collection. `isoptedout-false`: A visitor has not opted out of data collection. |