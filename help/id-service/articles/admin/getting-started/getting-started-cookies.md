---

title: Cookies and the Experience Cloud ID Service
description: The role of the Experience Cloud ID service in the Adobe Experience Cloud.
SEO title: Cookies and the Adobe Experience Cloud ID Service
SEO description: How the Adobe Experience Cloud ID Services uses and interacts with cookies.
author: giurgiu

---

# Cookies and the Experience Cloud ID Service

The ID service uses your organization ID, the Experience Cloud `AMCV` cookie, and demdex cookie to create and store unique, persistent identifiers for your site visitors. These cookies let the ID service track visitors across your different domains and enable data sharing among different Experience Cloud solutions.

## Understanding ID Service Cookies

The ID service relies on the `AMCV` and demdex cookies to help it work properly. These cookies are just files that store data used by the ID service. ID service cookies are not dangerous, malicious, or somehow different from any other first- or third-party cookies stored set by a website or service and stored in your browser. 

In fact, ID service cookies follow the same rules that govern other first- and third-party cookies. Refer to the following table and the separate sections below for more information about cookies used by the ID service.

## Things ID Service Cookies Can Do

+ Set and store a unique ID for your site visitors (the `MID`).
+ Persist this unique ID so the ID service can collect and share data with other Experience Cloud solutions.
+ Track users across your domains. But this requires that you own those other domains and have ID service code deployed on them.

## Things ID Service Cookies Cannot Do

+ Store, transmit, or execute computer viruses.
+ Access or store personally identifiable information \(PII\) like your email address.
+ Control computer hardware or software.
+ Make computers unstable or cause performance problems.
+ Track users on sites that do not use the ID service.

## The Adobe Experience Cloud Visitor \(AMCV\) Cookie

The following table lists and defines some important attributes of the AMCV cookie.

>[!NOTE]
>*italics* indicates placeholder text for a variable.

| Attribute    | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| ------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Name**     | The `AMCV` cookie name follows the syntax `AMCV_####@AdobeOrg`. In the name, the `####` elements are placeholders for part of your Experience Cloud organization ID. This ID is passed in to the DCS by the `Visitor.getInstance` function in the ID service code. A fully formed cookie name would look similar to this:  `AMCV_1FD6776A524453CC0A490D44%40AdobeOrg`                                                                                                                                                                                          |
| **Contents** | The AMCV cookie contains the Experience Cloud visitor ID or `MID`. The `MID` is stored in a key-value pair that follows this syntax, `mid\|Experience Cloud ID`. A fully formed key-value pair would look similar to this: `mid\|20265673158980419722735089753036633573`  This persistent identifier enables cross-solution data sharing.                                                                                                                                                                                                                                                                                                                                                 |
| **Domain**   | The `AMCV` cookie is set in the first-party domain in a browser. This means it is set in the domain of the site currently visited by a user. As such, ID service code and other Experience Cloud code libraries can read the `MID` stored in the `AMCV` cookie.  However, because the `AMCV` cookie is set in the first-party domain, it cannot be used to track and identify users across different domains. Instead, the ID service relies on the organization ID and the demdex ID to return the correct `MID` when a site visitor navigates to a different domain. |

## The demdex Cookie

The following table lists and defines some important attributes of the demdex cookie.

| Attribute    | Description                                                                                                                                                                                                                                                                                                                                                                                                 |
| ------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Name**     | The cookie name is `demdex`                                                                                                                                                                                                                                                                                                                                                                                 |
| **Contents** | The demdex cookie contains the demdex ID, which is generated by the DCS.                                                                                                                                                                                                                                                                                                                                    |
| **Domain**   | The demdex cookie is set in the third-party, `demdex.net` domain in the browser. This domain is separate from the site currently visited by a user. Unlike the first-party, `AMCV` cookie, the demdex cookie and ID persists across different domains. The demdex ID and your organization ID are the common values that allows the ID service to return and identify a site visitor with the right visitor ID. |

For related information, see also [Understanding Calls to the Demdex Domain](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html).

## Generating the Experience Cloud ID

The Experience Cloud ID `MID` is derived mathematically from your organization ID and the demdex ID. As long as these IDs remain constant generating the right `MID` for a specific user is simply a math problem. With the same organization ID and demdex ID you get the same `MID` value every time. This allows the ID service to track visitors across domains that you control and have configured with ID service code.

The ID service starts to create a MID as your page loads. During this process, code provided by the `visitorAPI.js` code library sends your organization ID in an event call to the ID service. The ID service creates and returns the `MID` and a `demdex` ID in the `AMCV` and `demdex` cookies respectively.

+ [How the Experience Cloud ID Service Requests and Sets IDs](getting-started-id-request.md)
