---

title: API Methods - getLocationHint
description: getLocationHint method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - getLocationHint
SEO description: getLocationHint method for the Adobe Experience Cloud ID Service API
short-title: free text
doc-type: article
author: name
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

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
