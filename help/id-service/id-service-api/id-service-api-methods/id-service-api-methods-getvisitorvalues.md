---

title: API Methods - getVisitorValues
description: getVisitorValues method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - getVisitorValues
SEO description: getVisitorValues helper method for the Adobe Experience Cloud ID Service API
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

# getVisitorValues

This is an asynchronous API that returns identifiers for Analytics, the ID service, data collection opt-out, geographic location, and metadata "blob" content by default. Also, you can control which IDs you want to return with the optional `visitor.FIELDS` enum.

## Syntax

This function uses the following syntax \(italics represents a placeholder for a variable\): `var values = visitor.getVisitorValues (callback, [visitor.FIELDS.ID type, visitor.FIELDS.ID type]);` 

In the function parameters:

+ `callback` represents your own callback code that receives the returned IDs.
+ *\(Optional\)* `visitor.FIELDS.ID type` is an enum that lets you specify which [ID values](mcvid-getvisitorvalues.html#section_4C4C300167694C6FBFF1D6C612F372B5) you want this function to return.

See the following use cases and definitions for more information.

## Use Case 1: Request the Default Data Set

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

## Use Case 2: Request a Custom Data Set

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
