---

title: Experience Cloud ID Service Migration Scenarios
description: Migration scenarios for the Adobe Experience Cloud ID Service
SEO title: Adobe Experience Cloud ID Service Migration Scenarios
SEO description: Migration scenarios for the Adobe Experience Cloud ID Service
short-title: free text
doc-type: article
author: name
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# Experience Cloud ID Service Migration Scenarios

Contains server example configurations and the required migration steps.

## Single Web Property

+ **Customer**: Example Company Inc.
+ **Experience Cloud enabled**: No
+ **Web Properties**: example.com
+ **Data collection servers**: metrics.example.com, smetrics.example.com
+ **Analytics JavaScript file**: A single file for all site pages

Firstly, this customer should get enabled for the Experience Cloud \(see the [requirements](../reference-requirements.md)\). And, because they have a single JavaScript file, this customer does not need a grace period. This customer will also set up visitor migration and then migrate away from their data collection `CNAME`, which is not necessary.

## Multiple JavaScript Files, hard-coded image tags

+ **Customer**: Another Example Company Inc.
+ **Experience Cloud enabled**: Yes
+ **Web Properties**: anotherexample.com
+ **Data collection servers**: anotherexampleco.112.2o7.net
+ **Analytics JavaScript file**: Multiple JavaScript files. One file for their main site, another file for their support section that is maintained in a separate CMS.
+ **Other data collection methods**: Hard-coded image tags on one site section

Firstly, this customer should find their Adobe Experience Cloud Organization ID \(see the [requirements](../reference-requirements.md)\). Next, they should configure a migration grace period because they are using multiple JavaScript files. This customer will also set up visitor migration and then migrate from `*.2o7.net` to `*.sc.omtrdc.net`.

When this customer updates to the latest Analytics JavaScript code in preparation for the Experience Cloud ID service rollout, they will also update all hard-coded image tags to use JavaScript instead.

## Multiple Web Properties, Multiple JavaScript Files and a Flash-based Video Player

+ **Customer**: A Good Customer LLC
+ **Experience Cloud enabled**: Yes
+ **Web Properties**: mymainsite.com, myothersiteA.com, myothersiteB.com
+ **Data collection servers**: metrics.mymainsite.com, smetrics.mymainsite.com
+ **Analytics JavaScript file**: Multiple JavaScript files. One file for each web property.
+ **Other data collection methods**: A Flash-based video player

Firstly, this customer should find their Adobe Experience Cloud Organization ID \(see the [requirements](../reference-requirements.md)\). Next, they should configure a migration grace period because they are using multiple JavaScript files. This customer tracks visitors between their primary domain and their sub-domains, so they will continue to use their data collection CNAME with the visitor ID service.

When this customer updates to the latest Analytics JavaScript code in preparation for the Experience Cloud ID service rollout, they will also update their Flash-based video player to the latest version of AppMeasurement for Flash.
