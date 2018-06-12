---

title: ID Service and Analtyics FAQs
description: FAQs for ID Service and Analtyics
seo-title: Adobe ID Service and Analtyics Frequently Asked Questions
seo-description: Adobe ID Service and Analtyics Frequently Asked Questions
short-title: FAQs
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

# FAQs for ID Service and Analtyics

Frequently Asked Questions about features, functionality, and issues related to using Analytics with the ID service.

## Tracking Servers

**How do I find my tracking server information**

Every properly configured piece of `AppMeasurement` code contains your tracking server information.

However, sometimes, customers may break up their Analytics `AppMeasurement` file into separate files. 

For example, some customers may put configuration variables in one file, use a second file for plug-ins, and then put AppMeasurement code in a third file. This is not recommended.

If you can't find your tracking server information then your Analytics instance may not be configured properly. Contact Customer Care if you cannot find your tracking server information.

Nothing will change for users who have already been identified by the ID service. Legacy visitors who have not been migrated to the ID service and are still identified with an Analytics cookie would be cliffed.

The amount of users affected would depend on how long the ID service has been active. For example, an implementation where the ID service has been active for one week may have more legacy users than an implementation where ID service has been active for 6 months because users returning to the site would have been migrated.
