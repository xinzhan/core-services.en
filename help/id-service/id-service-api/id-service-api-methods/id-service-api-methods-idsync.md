---

title: API Methods - ID Synchronization by URL or Data Source
description: ID Synchronization by URL or Data Source for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - ID Synchronization by URL or Data Source
SEO description: ID Synchronization by URL or Data Source for the Adobe Experience Cloud ID Service API
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

# ID Synchronization by URL or Data Source

The ID service functions `idSyncByURL` and `idSyncByDataSource` let you manually implement an ID sync in the Destination Publishing iFrame. These are available in `VisitorAPI.js` versions 1.10, or higher.


## Syntax

| Code                            | Synchronized User IDs                                                                                                 |
| ------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| `visitor.idSyncByURL();`        | Between different data partners and Audience Manager by using a custom ID sync URL.                                   |
| `visitor.idSyncByDataSource();` | When you already know the DPID and DPUUID and want to send it to Audience Manager in the standard ID sync URL format. |

## Properties

The following table lists and defines the properties available to both functions.

| Name            | Type   | Description                                                                                           |
| --------------- | ------ | ----------------------------------------------------------------------------------------------------- |
| `dpid`          | String | Data provider ID assigned by Audience Manager.                                                        |
| `dpuuid`        | String | The data provider's unique ID for the user.                                                           |
| `minutesToLive` | Number | \(Optional\) Sets the cookie expiration time. Must be an integer. Default is 20160 minutes (14 days). |
| `url`           | String | Destination URL.                                                                                      |

## Macros

Both functions accept the following macros:

+ `%TIMESTAMP%`: Generates a timestamp \(in milliseconds\). Used for cache busting.
+ `%DID%`: Inserts the Audience Manager ID for the user.
+ `%HTTP_PROTO%`: Sets the communication protocol \(`http` or `https`\).

## Sample Code and Output

Both functions return `Successfully queued` if successful. They return an error message string if not.

### visitor.idSyncByURL

*Sample Code*

```javascript
//Instatiate Visitor
var visitor = Visitor.getInstance("MARKETING-CLOUD-ORG-ID-HERE",{});

// Fires url with macros replaced
visitor.idSyncByURL({
	dpid: '24', // must be a string
	url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D',
	minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days) 
});
```
*Sample Output*

`http://su.addthis.com/red/usync?pid=16&puid=28777806459181003670799219185178493848&url=http%3A%2F%2Fdpm.demdex.net%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D`

---

### visitor.idSyncByDataSource

*Sample Code*

```javascript
//Instantiate Visitor
var visitor = Visitor.getInstance("MARKETING-CLOUD-ORG-ID-HERE",{});
// Fires 'http:/https:' + '//dpm.demdex.net/ibs:dpid=<dpid>&dpuuid=<dpuuid>'
visitor.idSyncByDataSource({
	dpid: '24', // must be a string
	dpuuid: '98765', // must be a string
	minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days) 
});
```

*Sample Output*
`http://dpm.demdex.net/ibs:dpid=24&dpuuid=98765`


For more see [DIL idSync](https://marketing.adobe.com/resources/help/en_US/aam/r_dil_idsync.html)
