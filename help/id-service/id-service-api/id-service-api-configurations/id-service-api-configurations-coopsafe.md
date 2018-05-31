---

title: API Configurations - isCoopSafe
description: isCoopSafe configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - isCoopSafe
SEO description: isCoopSafe configurations for the Adobe Experience Cloud ID Service API
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Configurations
guide subtopic 2:

---

# isCoopSafe

An optional, Boolean configuration that determines if the ID service sends \(or does not send\) data to the Adobe Experience Cloud Device Co-op.

## Requirements

To use `isCoopSafe` you must:

+ Use ID service code version 2.4, or higher.
+ Participate in the [Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/). 
    + Prospective co-op members should also review this documentation to determine if `isCoopSafe` addresses possible concerns about how data is used to create the device graph.
+ Work with your Adobe consultant to set a whitelist or a blacklist flag on your Device Co-op account. There is no self-service path to enabling these flags.

## Use Cases

`isCoopSafe` helps resolve 2 use cases related to data collection by current or prospective members of the Device Co-op. These use cases relate to how site visitor data is passed on to the Device co-op to help build the device graph. 

The following table describes how `isCoopSafe` works with these use cases to block or send data to the device graph

| Use Case                     | Description                                                                                                                                                                                                                                                             |
| ---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Authenticated Visitors**   | Add `isCoopSafe` to your ID service code to control how data for authenticated visitors who have or have not accepted term-of-use agreements is used by the Device Co-op to build the device graph.                                                                     |
| **DIL on Third-Party Sites** | Add 'isCoopSafe' to your ID service code for use on third-party sites where you:\  + Cannot ensure that authenticated visitors have or have not accepted term-of-use agreements.\   + Need to control how that data is used by the Device Co-op to build the device graph. |


## Syntax and Code Sample

 **Syntax:** `isCoopSafe: true | false` 

The Boolean options determine how customer data is or is not used by the Device Co-op.

+ `isCoopSafe: true`: Visitor data collected by a mobile SDK or website *can* be used to help build the device graph.
+ `isCoopSafe: false`: Visitor data collected by a mobile SDK or website *cannot* be used to help build the device graph.

 **Code Sample** 

Set this when your ID service code instantiates:

```javascript
var visitor = Visitor.getInstance("Insert Experience Cloud organization ID here",{
     ...
     isCoopSafe: true
});
```

## Event Call POST Parameters

Depending on the flag you set \(`true` or `false`\), the ID service translates `isCoopSafe` into these POST parameters and sends them to Adobe in an event call:

+ `d_coop_safe=1` 
+ `d_coop_unsafe=1` 

The POST parameters tell the Experience Cloud Device Co-op if it can or cannot include user data in the device graph. 

The table below defines the relationship between the `isCoopSafe` Boolean flags and the POST parameters passed in on an event call. If you don't use `isCoopSafe`, neither of these are passed in an event call.

| API                 | Description                                                                                |
| ------------------- | ------------------------------------------------------------------------------------------ |
| `isCoopSafe: true`  | `d_coop_safe=1` The Device Co-op can use visitor data to help build the device graph.      |
| `isCoopSafe: false` | `d_coop_unsafe=1` The Device Co-op cannot use visitor data to help build the device graph. |

## Post-Instantiation APIs

These APIs allow you to override the `isCoopSafe` status. These are necessary because they let you change a visitor's post-instantiation/post-login status on a site or in a single page app where the page does not refresh. 

For example, you would need to call these APIs if a user authenticates to your site or app and later accepts a terms-of-use policy that allows the Device Co-op to use their data.

| API                          | Description                                                          |
| ---------------------------- | -------------------------------------------------------------------- |
| `visitor.setAsCoopSafe();`   | Sets POST parameter `d_coop_safe=1` in all subsequent event calls.   |
| `visitor.setAsCoopUnsafe();` | Sets POST parameter `d_coop_unsafe=1` in all subsequent event calls. |

 

**Parent topic:** [Configurations](mcvid-function-vars.html)

[!MORE]
[DIL isCoopSafe](https://marketing.adobe.com/resources/help/en_US/aam/dil-coopsafe.html)
[!END]
