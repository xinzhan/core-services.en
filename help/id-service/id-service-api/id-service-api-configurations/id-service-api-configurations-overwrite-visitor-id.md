---

title: API Configurations - overwriteCrossDomainMCIDAndAID
description: overwriteCrossDomainMCIDAndAID configurations for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Configurations - overwriteCrossDomainMCIDAndAID
seo-description: overwriteCrossDomainMCIDAndAID configurations for the Adobe Experience Cloud ID Service API
short-title: overwriteCrossDomainMCIDAndAID
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

# overwriteCrossDomainMCIDAndAID

This property overwrites a visitor's Experience Cloud and Analytics IDs as they navigate from one domain to a second domain. 

>[!IMPORTANT]
>To overwrite an ID, you must own and have implemented the ID service on each domain. This code does not let you overwrite IDs on domains you do not control.

## Syntax
`Visitor.overwriteCrossDomainMCIDAndAID: true|false` \(default is `false`\)

## Code Sample

Your JavaScript code could look similar to the following example.

```javascript
//Call the ID service
var visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ID-HERE", {
     ...

     //Set overwrite property
     overwriteCrossDomainMCIDAndAID: true
});
```

## Use Cases

To track site visitors, the ID service writes a Experience Cloud ID \(or `MID`\) to a browser cookie. The following table lists and describes the common use cases where you might want to overwrite an existing `MID` set by the ID service in another domain.

### Identify visitors on different domain landing pages 
Let's say you own Domains A and B. In this case you can set `Visitor.overwriteCrossDomainMCIDAndAID: true` when:

+ Each domain has it's own landing page.
+ A visitor already has a cookie \(and a `MID`\) set from a previous visit to Domain B.
+ You want to consistently identify a visitor if they come to Domain B from Domain A.

### Identify visitors across landing and conversion pages
Let's say you own Domains A and B. In this case, you can set `Visitor.overwriteCrossDomainMCIDAndAID: true` when:
+ Domain A is a landing page.
+ Domain B is a separate conversion, booking, or other end-of-workflow page.
+ A visitor already has a cookie \(and a `MID`\) set from a previous visit to Domain B and you know these are less desirable client-side `MID`s rather than server-side `MID`s.
+ You want to consistently identify a visitor if they come to Domain B from Domain A.

### Identify visitors from mobile apps to web browsers
This use case is slightly different. It involves identifying users as they move from a mobile app to your website. In this case, your visitor already has a `MID` set locally by a mobile app and they have a different `MID` set in a cookie on your website.
You can set `Visitor.overwriteCrossDomainMCIDAndAID: true` to overwrite the `MI`D set in the browser cookie with the `MID` set by the mobile app.