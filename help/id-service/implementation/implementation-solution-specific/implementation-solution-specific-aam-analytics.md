---

title: Implement ID Service for Analytics and Audience Manager
description: These instructions are for Analytics and Audience Manager customers who want to use the ID service and do not use Dynamic Tag Management
seo-title: Implement the Adobe Experience Cloud ID Service for Analytics and Audience Manager
seo-description: These instructions are for Analytics and Audience Manager customers who want to use the ID service and do not use Dynamic Tag Management
short-title: 
doc-type: article
audience: 
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# Implement the Experience Cloud ID Service for Analytics and Audience Manager

These instructions are for Analytics and Audience Manager customers who want to use the Experience Cloud ID service and do not use Dynamic Tag Management \(DTM\). However, we strongly recommend that you use DTM to implement the ID service. DTM streamlines the implementation workflow and automatically ensures the correct code placement and sequencing.

>[!IMPORTANT]
>+ [Read the requirements](../../reference/reference-requirements.md) before you begin.
>+ This procedure requires AppMeasurement. Customers using `s\_code` cannot complete this procedure.
>+ Configure and test this code in a development environment before implementing it in production.

## Step 1: Plan for Server-side Forwarding

In addition to the steps described here, customers who use Analytics and Audience Manager should migrate to server-side forwarding. Server-side forwarding lets you remove DIL \(Audience Manager's data collection code\) and replace it with the [Audience Management Module](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html). See the [server-side forwarding documentation](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/ssf.html) for more information.

Migrating to server-side forwarding requires planning and coordination. This process involves external changes to your site code and internal steps that Adobe must take to provision your account. In fact, many of these migration procedures need to happen in parallel and get released together. Your implementation path should follow this sequence of events:

1. Work with your Analytics and Audience Manager contacts to plan your ID service and server-side forwarding migration. Make selecting a tracking server an important part of this plan.
1. Get provisioned for Profiles & Audiences. Complete the form on the [integrations and provisioning site](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES) to get started.
1. Implement the ID service and the Audience Management Module simultaneously. To work properly, the Audience Management Module \(server-side forwarding\) and the ID service must be released for the same set of pages and at the same time.

## Step 2: Download the ID Service Code

The ID Service requires the `VisitorAPI.js` code library. To download this code library:

1. Go to `Admin \> Code Manager`.
1. In Code Manager, click either `JavaScrpt \(New\)` or `JavaScript \(Legacy\`. This downloads compressed code libraries.
1. Decompress the code file and open the `VisitorAPI.js` file.

## Step 3: Add the Visitor.getInstance Function to the ID Service Code

>[!IMPORTANT]
>+ Previous versions of the ID service API placed this function in a different location and required a different syntax. If you are migrating from a version prior to [version 1.4](mcvid-notes-2015.html#section_F5C596F355B14DA28F45C798DF513572), note the new placement and syntax documented here.
>+ Code in ALL CAPS is a placeholder for actual values. Replace this text with your Organization ID, tracking server URL, or other named value.

### Part 1: Copy the Visitor.getInstance function below

```javascript
var visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ORGANIZATION ID-HERE", {
     trackingServer: "INSERT-TRACKING-SERVER-HERE", // same as s.trackingServer
     trackingServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE", // same as s.trackingServerSecure

     // To enable CNAME support, add the following configuration variables
     // If you are not using CNAME, DO NOT include these variables
     marketingCloudServer: "INSERT-TRACKING-SERVER-HERE",
     marketingCloudServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE" // same as s.trackingServerSecure
});

```

### Part 2: Add function code to the Visitor API.js file

Place the `Visitor.getInstance` function at the end of the file after the code block. Your edited file should look like this:

```javascript
/*
========== DO NOT ALTER ANYTHING BELOW THIS LINE ==========
Version and copyright section
*/

// Visitor API code library section

// Put Visitor.getInstance at the end of the file, after the code library

var visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ORGANIZATION ID-HERE", {
     trackingServer: "INSERT-TRACKING-SERVER-HERE", // same as s.trackingServer
     trackingServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE", // same as s.trackingServerSecure

     // To enable CNAME support, add the following configuration variables
     // If you are not using CNAME, DO NOT include these variables
     marketingCloudServer: "INSERT-TRACKING-SERVER-HERE",
     marketingCloudServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE" // same as s.trackingServerSecure
});

```

## Step 4: Add Your Experience Cloud Organization ID to Visitor.getInstance

In the `Visitor.getInstance` function, replace `INSERT-MARKETING-CLOUD-ORGANIZATION ID-HERE` with your Experience Cloud organization ID. If you do not know your organization ID, you can find it on the Experience Cloud administration page. Your edited function could look similar to the example below.

 `var visitor = Visitor.getInstance("1234567ABC@AdobeOrg", { ...` 

>[!IMPORTANT]
>*Do not* change the case of the characters in your organization ID. The ID is case-sensitive and must be used exactly as provided.

## Step 5: Add Your Tracking Servers to `Visitor.getInstance`

Analytics uses tracking servers for data collection.

### Part 1: Find your tracking server URLs

Check your `s_code.js` or `AppMeasurement.js` files to find the tracking server URLs. You'll want the URLs specified by these variables:

+ `s.trackingServer` 
+ `s.trackingServerSecure` 

### Part 2: Set tracking server variables

To determine which tracking server variables to use:

1. Answer the questions in the decision matrix below. Use the variables that correspond to your answers.
1. Replace the tracking server placeholders with your tracking server URLs.
1. Remove unused tracking server and Experience Cloud server variables from the code.

 ![](../../assets//tracking-server-matrix.png) 

>[!NOTE]
>When used, match the Experience Cloud server URLs to their corresponding tracking server URLs like this:
>+ Experience Cloud server URL = tracking server URL
>+ Experience Cloud server secure URL = tracking server secure URL

If you're not sure how to find your tracking server see the [FAQ](../../faqs/faqs-id-service.md) and [Correctly Populate the trackingServer and trackingServerSecure variables](https://helpx.adobe.com/analytics/kb/determining-data-center.html).

## Step 6: Update Your AppMeasurement.js File

This step requires AppMeasurement. You cannot continue if you're still using `s\_code`.

Add the `Visitor.getInstance` function shown below to your `AppMeasurement.js` file. Place it in the section that contains configurations such as `linkInternalFilters`, `charSet`, `trackDownloads`, etc. :

`s.visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ORGANIZATION ID-HERE");` 

>[!IMPORTANT]
>At this point, you should remove the Audience Manager DIL code and replace it with the Audience Management Module. See [Implement Server-Side Forwarding](https://marketing.adobe.com/resources/help/en_US/aam/ssf.html) for instructions.

** *\(Optional, but recommended\)* Create a custom prop** 

Set a custom prop in `AppMeasurement.js` to measure coverage. Add this custom prop to the `doPlugins` function of your `AppMeasurement.js` file:

```javascript
// prop1 is used as an example only. Choose any available prop.
s.prop1 = (typeof(Visitor) != "undefined" ? "VisitorAPI Present" : "VisitorAPI Missing");
```

## Step 7: Add Visitor API Code to the Page

Place the `VisitorAPI.js` file within the `<head>` tags on each page. When you the `VisitorAPI.js` file to your page:

+ Put it at the beginning of the `<head>` section to it appears before other solution tags.
+ It must execute before AppMeasurement and the code for other Experience Cloud solutions.

## Step 8: *\(Optional\)* Configure a Grace Period

If any of these use cases apply to your situation, ask [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) to set up a temporary [grace period](../../reference/reference-analytics/reference-analytics-grace.md). Grace periods can run for up to 180-days. You can renew a grace period if required.


### Partial Implementation Use Case
You need a grace period if you have some pages that use the ID service and some pages that do not, and they all report into the same Analytics report suite. This is common if you have a global report suite that reports across domains.

Discontinue the grace period after the ID service is deployed on all your web pages that report into the same report suite.

### s\_vi Cookie Requirements 
You need a grace period if you require new visitors to have an s\_vi cookie after migrating to the ID service. This is common if your implementation reads the s\_vi cookie and stores it in a variable.

Discontinue the grace period after your implementation can capture the MID instead of reading the s\_vi cookie.

See also, [Cookies and the Experience Cloud ID Service](../../getting-started/getting-started-cookies.md).

### Clickstream Data Integration
You need a grace period if you send data to an internal system from a Clickstream data feed and that processes uses the `visid_high` and `visid_low` columns.

Discontinue the grace period after your data ingestion process can use the `post_visid_high` and `post_visid_low` columns.

See also, [Clickstream Data Column Reference](https://marketing.adobe.com/resources/help/en_US/sc/clickstream/datafeeds_reference.html).

## Step 9: Test and Deploy ID Service Code

### Test and Verify
To test your ID service implementation, check for the:

+ [AMCV cookie](../../getting-started/getting-started-cookies.md) in the domain where you pages is hosted.
+ MID value in the Analytics image request with the [Adobe debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html).
+ See also, [Test and Verify the Experience Cloud ID Service](../../implementation/implementation-standard/test-verify.md).

To test server-side forwarding, see:

+ [How to Determine if Your Account is Ready to Receive Forwarded Data](https://marketing.adobe.com/resources/help/en_US/aam/ssf-success.html) 
+ [How to Determine if Your Account is not Ready to Receive Forwarded Data](https://marketing.adobe.com/resources/help/en_US/aam/ssf-fail.html) 

### Deployment
Deploy your code after it passes testing.

>[!NOTE]
>If you enabled a grace period:
>+ Ensure the Analytics ID \(AID\) and `MID` are in the image request.
>+ Remember to disable the grace period once you meet the criteria for discontinuation.
