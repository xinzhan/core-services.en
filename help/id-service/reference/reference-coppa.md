---

title: API Methods - appendSupplementalDataIDTo
description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - appendSupplementalDataIDTo
SEO description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
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

# COPPA Support in the Experience Cloud ID Service

The Children’s Online Privacy Protection Act (COPPA) prohibits the online collection of personal information from children under 13 years old without verifiable parental consent. Customers concerned about COPPA can add an optional variable to their Experience Cloud ID service code that prevents it from setting cookies in the third-party domain of a browser.

[!NOTE] 

For version 1.5.3 or greater.

[!END]

## Cookies and Tracking

When a web page loads, the Experience Cloud ID service calls an Adobe data collection server (DCS). The DCS response includes a Experience Cloud cookie and a `demdex.net` cookie.

The Experience Cloud cookie is set in the first party domain. It cannot be used to track visitors across different domains, unless those domains work together to allow access.

The `demdex.net` cookie is set in the third-party domain. It contains a unique identifier that can be used to track visitors across different domains.

## Cookies and COPPA Compliance

Third-party cookies that track visitors across different domains on websites directed to (or primarily for) children trigger COPPA parental consent requirements. To more easily comply with COPPA for internal website analytics, add the variable `idSyncDisable3rdPartySyncing:true` to the `Visitor.getInstance` function as shown below.

```javascript 
var visitor = Visitor.getInstance("insert marketing cloud ID here", {
    idSyncDisable3rdPartySyncing: true
    ...
});
```

When set to true, the `idSyncDisable3rdPartySyncing` object stops the DCS from returning the third-party, `demdex.net` cookie. 

If a site visitor already has this cookie in their browser, the ID service won't use it to create a new Experience Cloud ID or return an existing ID. Instead, the Experience Cloud ID service creates a new, random ID in the first-party cookie. Once enabled, you can collect data with the ID service and share it across different Experience Cloud solutions, including other internal operations allowed by COPPA.

[!MORE]

+ [Adobe Privacy Center](https://www.adobe.com/privacy.html)
+ [What is COPPA?](http://www.consumer.ftc.gov/articles/0031-protecting-your-childs-privacy-online#whatis)

[!END]
