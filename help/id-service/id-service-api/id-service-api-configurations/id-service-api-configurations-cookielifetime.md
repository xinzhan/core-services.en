---

title: cookieLifetime for ID Service
description: This variable lets you override the default lifetime interval for the AMCV cookie
seo-title: cookieLifetime for Adobe Experience Cloud ID Service
seo-description: This variable lets you override the default lifetime interval for the AMCV cookie
short-title: cookieLifetime
doc-type: article
audience: 
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# cookieLifetime

This variable lets you override the default lifetime interval for the AMCV cookie. By default, Experience Cloud ID service cookies expire after 24-months. Set the time interval in seconds.

## Syntax

*cookieLifetime:lifetime in seconds*

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable. Example changes expiration period to 12-months.
   cookieLifetime:31536000
});
```
