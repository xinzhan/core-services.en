---

title: audienceManagerServer and audienceManagerServerSecure
description: ID Service API configuration for audienceManagerServer and audienceManagerServerSecure
seo-title: audienceManagerServer and audienceManagerServerSecure
seo-description: Adobe ID Service API configuration for audienceManagerServer and audienceManagerServerSecure
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

# audienceManagerServer and audienceManagerServerSecure

Change the default domain name used by calls to the Experience Cloud ID service to your own subdomain name with these configurations.

## Syntax:

+ `audienceManagerServer: "your subdomain name.demdex.net"`
+ `audienceManagerServerSecure: "your subdomain name.demdex.net"`

## Purpose

Normally, the Experience Cloud ID service makes calls to Adobe at dpm.demdex.net. Sometimes you may not want to make calls to this destination because it looks too generic or "third-party." To make the ID service call look more like a first-party call, use these configurations to add your Audience Manager subdomain name to demdex.net as shown below. For more information about the `dpm.demdex.net` call, see Understanding Calls to the Demdex Domain.

## Requirements

These configurations require that you use:

+ The Audience Manager subdomain name of record for your company. Verify or get this name from your consultant.
+ The subdomain name associated with your Organization ID.
+ Both configuration parameters with the same subdomain name.

## Code Sample

In this example, let's say we have a media entertainment company that has expressed legal concerns with making calls to `dpm.demdex.net`. In Audience Manager, the company subdomain name of record is Music1. The following code sample demonstrates how to brand the ID service data call with this customer-specific subdomain name.

```javascript
//Instantiate Visitor
var visitor = Visitor.getInstance("Insert Experience Cloud Organization ID here",{
     ...
     //Configure ID service call
     audienceManagerServer: "Music1.demdex.net",
     audienceManagerServerSecure: "Music1.demdex.net"
     }
);
```
