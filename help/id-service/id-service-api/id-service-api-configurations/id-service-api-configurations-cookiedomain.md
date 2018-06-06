---

title: API Configurations - cookieDomain
description: cookieDomain configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - cookieDomain
SEO description: cookieDomain configurations for the Adobe Experience Cloud ID Service API
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

# cookieDomain

Required for multi-part, top-level domains where either of the last two parts of the URL are *greater than* 2 characters.

## Syntax:
`cookieDomain: "URL"` \(The `www` prefix is not required.\)

## Use Case

+ Required: `www.example.com.uk`
+ Not required: `www.example.co.uk`

## Code Sample 

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable
   cookieDomain:"example.com.uk"
});
```
