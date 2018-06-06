# Direct Integration with the Experience Cloud ID Service

This implementation lets customers use the ID service on devices that cannot accept or work with our JavaScript or SDK code. This includes devices such as gaming consoles, smart TVs, or other Internet-enabled appliances. Refer to this section for syntax, code samples, and definitions.

## Syntax

Devices that cannot use the `VisitorAPI.js` or SDK code libraries can make calls directly to the data collection servers \(DCS\) used by the ID service. To do this, you would call `dpm.demdex.net` and format your request as shown below. *Italics* indicates a variable placeholder.

![](../../assets/directSyntax.png) 

In this syntax example, the `d_` prefix identifies the key-value pairs in the call as a system-level variable. You can pass quite a few `d_` parameters to the ID service, but stay focused on the key-value pairs as shown in the code above. For more information about other variables, see [Supported Attributes for DCS API calls](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

The ID service supports HTTP and HTTPS calls. Use HTTPS to pass data from a secure page.

## Sample Request

Your request could look similar to the sample shown below. Long variables have been shortened.

![](../../assets/directExample.png) 

## Sample Response

The ID service returns data in a JSON object as shown below. Your response may be different.

```javascript
{
     "d_mid":"12345",
     "dcs_region":"6",
     "id_sync_ttl":"604800",
     "d_blob":"wxyz5432"
}
```

## Request and Response Parameters Defined

 **Request Parameters** 

|Parameter|Description|
|---------|-----------|
|  `dpm.demdex.net` 

 | A legacy domain controlled by Adobe. See [Understanding Calls to the Demdex Domain](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html).

 |
|  `d_mid` 

 | The Experience Cloud visitor ID. See [Cookies and the Experience Cloud ID Service](mcvid_cookies.html#).

 |
|  `d_orgid` 

 | Your Experience Cloud Organization ID. For help with finding this ID see, [Requirements for the Experience Cloud ID Service](mcvid-requirements.html#).

 |
|  `d_cid` 

 | An optional parameter that passes the Data Provider ID \(DPID\), the Unique User ID \(DPUUID\), and an [authenticated state ID](mcvid-authenticated-state.html#) to the ID service. As shown in the code sample, separate the DPID and DPUUID with the non-printing control character, `%01`.

  **DPID and DPUUID** 

 In the `d_cid` parameter, assign each related DPID and DPUUID combination to the same `d_cid` parameter. This lets you return multiple ID sets in a single request. Also, separate the DPID, DPUUID, and optional authentication flag with the non-printing control character, `%01`. In the examples below, the provider and user IDs are highlighted in **bold** text.

+ Syntax: `...d_cid=**DPID**%01**DPUUID**%01authentication state...` 
+ Example: `...d_cid=**123**%01**456**%011...` 

  **Authentication State** 

This is an optional ID in the `d_cid` parameter. Expressed as an integer, it identifies users according to their authentication status as shown below:

+ `0` \(Unknown\)
+ `1` \(Authenticated\)
+ `2` \(Logged out\)

To specify an authentication state, you set this flag after the user ID \(UUID\) variable. Separate the UUID and authentication flag with the non-printing control character, `%01`. In the examples below, the authentication IDs are highlighted in **bold** text.

Syntax: `...d_cid=DPID%01DPUUID%01**authentication state**` 

Examples:

+ Unknown: `...d_cid=123%01456%01**0**...` 
+ Authenticated: `...d_cid=123%01456%01**1**...` 
+ Logged out: `...d_cid=123%01456%01**2**...` 

 |
|  `dcs_region` 

 | The ID service is a geographically distributed and load-balanced system. The ID identifies the region of the data center handling the call. See [DCS Region IDs, Locations, and Host Names](https://marketing.adobe.com/resources/help/en_US/aam/dcs-regions.html).

 |
|  `d_cb` 

 |  *\(Optional\)* A callback parameter that lets you execute a JavaScript function in the request body.

 |
|  `d_blob` 

 | An encrypted chunk of JavaScript metadata. Size constraints limit the blob to 512 bytes or less.

 |
|  `d_ver` 

 | Required. This sets the API version number. Leave this set as `d_ver=2`.

 |

 **Response Parameters** 

Some response parameters are part of the request and have been defined in the section above.

| Parameter     | Description                                                                                              |
| ------------- | -------------------------------------------------------------------------------------------------------- |
| `id_sync_ttl` | The re-synchronization interval, specified in seconds. The default interval is 604,800 seconds (7-days). |
