---

title: FAQs for Analytics and ID Service
description: 
SEO title: 
SEO description: 
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: FAQs
guide subtopic 1: 
guide subtopic 2:

---

# FAQs for ID Service and Analtyics

Frequently asked questions about features, functionality, and issues related to using Analytics with the ID service.

## Tracking Servers

[!ACCORDION]

[!STEP Title="How do I find my tracking server information?"]

Every properly configured piece of AppMeasurement code contains your tracking server information.

However, sometimes, customers may break up their Analytics `AppMeasurement` file into separate files. For example, some customers may put configuration variables in one file, use a second file for plug-ins, and then put AppMeasurement code in a third file. This is not recommended.

If you can't find your tracking server information then your Analytics instance may not be configured properly. Contact Customer Care if you cannot find your tracking server information.

[!END]
[!STEP Title="What happens if I am using the ID service and change my tracking server?"]

Nothing will change for users who have already been identified by the ID service. Legacy visitors who have not been migrated to the ID service and are still identified with an Analytics cookie would be cliffed. 

The amount of users affected would depend on how long the ID service has been active. For example, an implementation where the ID service has been active for one week may have more legacy users than an implementation where ID service has been active for 6 months because users returning to the site would have been migrated.

[!END]
