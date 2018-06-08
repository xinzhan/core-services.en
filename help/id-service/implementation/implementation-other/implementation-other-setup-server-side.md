---

title: Server-side implementation of ID Service
description: Implementing A4T with mixed server- and client-side implementations of Target, Analytics, and the ID service.
seo-title: Server-side implementation of ID Service
seo-description: Implementing A4T with mixed server- and client-side implementations of Target, Analytics, and the Adobe Experience Cloud ID service.
short-title: Server-side implementation
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

# Server-Side Implementation of the Experience Cloud ID Service

These instructions are for Analytics for Target (A4T) customers with mixed server- and client-side implementations of Target, Analytics, and the ID service. Customers who need to run the ID service in a NodeJS or Rhino environment should also review this information.

This instance of the ID service uses a shortened version the `VisitorAPI.js` code library, which you download and install from Node Package Manager \(NPM\).

Review this section for installation instructions and other configuration requirements.

## Introduction

A4T \(and other customers\) can use this version of the ID service when they need to:

+ Render web page content on their servers and pass it to a browser for final display.
+ Make server-side Target calls.
+ Make client-side \(in-browser\) calls to Analytics.
+ Synchronize separate Target and Analytics IDs to determine if a visitor seen by one solution is the same person as seen by the other solution.

## Code Download and Provided Interfaces

See the [ID service NPM repository](https://www.npmjs.com/package/@adobe-mcid/visitor-js-server) to download the server-side code package and review the interfaces included in the current build.

## Workflow

The diagram and sections below describe what happens, and what you need to configure, in each step of the server-side implementation process.

![Server-side workflow](../../assets/serverside.png)

## Step 1: Request Page

Server-side activity begins when a visitor makes an HTTP request to load a web page. During this step, your server receives this request and checks for the [AMCV cookie](../../getting-started/getting-started-cookies.md). The AMCV cookie contains the visitor's Experience Cloud ID `MID`.

## Step 2: Generate ID Service Payload

Next, you need make a server-side payload request to the ID service. A payload request:

+ Passes the `AMCV` cookie to the ID service.
+ Requests data that is required by Target and Analytics in subsequent steps described below.

>[!NOTE]
>This method requests a single mbox from Target. If you need to request multiple mboxes in a single call, see [generateBatchPayload](https://www.npmjs.com/package/@adobe-mcid/visitor-js-server#generatebatchpayload).

Your payload request should look like following code sample. In the code sample, the `visitor.setCustomerIDs` function is optional. See [Customer IDs and Authentication States](../../reference/reference-authenticated-state.md) for more information.

```javascript
//Import the ID service server package
var Visitor = require("@adobe-mcid/visitor-js-server");

//Pass in your Organization ID to instantiate Visitor
var visitor = new Visitor("Insert Experience Cloud ID here");

//*\(Optional\)* Set a custom customer ID
visitor.setCustomerIDs({
     userid:{
          id:"1234",
          authState: Visitor.AuthState.UNKNOWN //AuthState is a static property of the Visitor class
     }
});

//Parse the visitor's HTTP request for the AMCV cookie
var cookies = cookie.parse(req.headers.cookie || "");
var cookieName = visitor.getCookieName(); // Visitor API that returns the cookie name.
var amcvCookie = cookies[cookieName];

//Generate the payload request pass your mbox name and the AMCV cookie if present
var visitorPayload = visitor.generatePayload({
     mboxName: "bottom-banner-mbox",
     amcvCookie: amcvCookie
});
```

The ID service returns the payload in a JSON object similar to the following example. Payload data is required by Target.

```javascript
{
    "marketingCloudVisitorId": "02111696918527575543455026275721941645",
    "mboxParameters": {
        "mboxAAMB": "abcd1234",
        "mboxMCGLH": "9",
        "mboxMCSDID": "56BE026543F7E211-1CC51BCAAE88F0D2",
        "vst.userid.id": "1234567890",
        "vst.userid.authState": 0
    }
}
```

If your visitor doesn't have an AMCV cookie, the payload omits these key-value pairs:

+ `marketingCloudvisitorId`
+ `mboxAAMB`
+ `mboxMCGLH`

## Step 3: Add Payload to the Target Call

After your server receives payload data from the ID service, you need to instantiate additional code to merge it with data passed in to Target. The final JSON object passed to Target would look similar to this:

```javascript
{
"mbox" : "target-global-mbox",
"marketingCloudVisitorId":"02111696918527575543455026275721941645",
"requestLocation" : {
     "pageURL" : "http://www.domain.com/test/demo.html",
     "host" : "localhost:3000"
     },
"mboxParameters" : {
     "mboxAAMB" : "abcd1234",
     "mboxMCGLH" : "9",
     "mboxMCSDID": "56BE026543F7E211-1CC51BCAAE88F0D2",
     "vst.userid.id": "1234567890",
     "vst.userid.authState": 0,
     }
}
```

## Step 4: Get Server State for the ID Service

Server state data contains information about work that's been done on the server. The client-side ID service code requires this information. Customers who have implemented the ID service through Dynamic Tag Manager \(DTM\) can configure DTM to pass server state data through that tool.

If you've set up the ID service through a non-standard process, you will need to return server state with your own code. The client-side ID service and Analytics code passes state data to Adobe when the page loads.

### Get Server State via DTM

If you have implemented the ID service with DTM, you need to add code to your page and specify a name-value pair in the DTM settings.

**Page Code** Add this code to the `<head>` tag of your HTML page:

 ```javascript
//Get server state
var serverState = visitor.getState();

Response.send("
...
<head>
     <script>
          //Add 'serverState' as a stringified JSON global variable.
          "var serverState = "+ JSON.stringify(serverState) +"; 
     </script>
     <script src = "DTM script (satellite JS)">
     </script>
</head>
...
```

**DTM Settings**
Add these as name-value pairs to the **General \> Settings** section of your ID service instance:

+ **Name:** serverState
+ **Value:** %serverState%

>[!IMPORTANT]
>The value name must match the variable name you set for `serverState` in your page code.

Your configured settings should look like this:

![](../../assets/server_side_dtm.png) 

See also, [Experience Cloud](../implementation-standard/dtm-settings.md).

**Get Server State Without DTM**
If you have a non-standard implementation of the ID service, you must configure this code to run on your server while it assembles the requested page:

```javascript
//Get server state
var serverState = visitor.getState();

Response.send("
...
<head>
     <script src="VisitorAPI.js"></script>
     <script>
          var visitor = Visitor.getInstance(orgID, {
          serverState: serverState 
          ...
     </script>
</head>
...
```

## Step 5: Serve a Page and Return Experience Cloud Data

At this point, the web server sends page content to the visitor's browser. From this point on, the browser \(not the server\) makes all the remaining ID service and Analytics calls. For example, in the browser:

+ The ID service receives state data from the server and passes the SDID to AppMeasurement.
+ AppMeasurement sends data about the page hit to Analytics, including the SDID.
+ Analytics and Target compare SDIDs for this visitor. With an identical SDID, Target and Analytics stitch the server-side call and the client-side call together. At this point, both solutions now recognize this visitor as the same person.