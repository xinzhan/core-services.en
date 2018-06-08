---

title: API Methods - getLocationHint
description: getLocationHint method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - getLocationHint
seo-description: getLocationHint method for the Adobe Experience Cloud ID Service API
short-title: getLocationHint
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

# getLocationHint

Returns the Experience Cloud ID service `region ID`. A `region ID` \(or location hint\), is a numeric identifier for the geographic location of a particular ID service data center. You need the `region ID` in order to make server-side API calls to Audience Manager.

## Syntax

`var variable name = visitor.getLocationHint()` 

>[!NOTE]
>For a list of region IDs and corresponding locations, see [DCS Region IDs, Locations, and Host Names](https://marketing.adobe.com/resources/help/en_US/aam/dcs-regions.html).

## Code Sample

The location hint function reads the region ID from the `AMCV` cookie. If the region ID is already set in the `AMCV` cookie, then the callback happens immediately. If the `region ID` is not set, the function will wait for a response from the server before passing the `region ID` to the callback.

Your code could look similar to the following example:

```javascript
//callback function
var callback = function (*region ID here*){
//do whatever your function does with the region ID
};

//Get the region ID
visitor.getLocationHint(callback, true);

```