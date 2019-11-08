---
description: Learn about solution data sources and configuring subscriptions. Subscriptions enable the customer attribute data flow between the Experience Cloud and solutions (Analytics and Target).
keywords: customer attributes;core services
seo-description: Learn about solution data sources and configuring subscriptions. Subscriptions enable the customer attribute data flow between the Experience Cloud and solutions (Analytics and Target).
seo-title: Configure subscriptions
solution: Experience Cloud
title: Configure subscriptions
uuid: f74a8155-0a21-46b3-9b1e-4c838f72f24f
---

# Configure subscriptions

Learn about solution data sources and configuring subscriptions. Subscriptions enable the customer attribute data flow between the Experience Cloud and solutions (Analytics and Target).

For example, an Adobe Analytics subscription enables attribute data in reports. If you use Adobe Target, you can upload customer attributes for targeting and segmentation. 

**[!UICONTROL Customer Attribute Source]** > **[!UICONTROL Create New Customer Attribute Source]** > **[!UICONTROL New]** 

![](assets/configure_subscription_page.png) 

| Element | Description |
|--- |--- |
|Solution|**Adobe Analytics**<br>Select Analytics, specify the report suites to that you want to receive attribute data, and the attributes to include.<br>**Adobe Target**<br>You can upload customer attributes for targeting and segmentation. This feature is useful if want to target a test based on attribute data, or make the data available for segmentation in Analytics.<br>Uploaded customer attribute data for a visitor is available at login, in **Target** > **Audiences**.<br>Multiple data sources are supported. When you  [set customer IDs](../core-services/core-services.md) on your website, verify that at least one of the aliases is subscribed to Target.|
|Report Suite (Analytics)|The report suites from Analytics.<br>You cannot add more than a total of 10 report suites to the Analytics subscriptions within a single attribute source. When choosing which report suites to include, consider the following suggestions:<ul><li>Choose report suites that have a common set of authenticated customers. If the authenticated customers in one report suite do not overlap with the authenticated customers in another report suite, separate these report suites into different attribute sources.</li><li>If possible, the report suites included in an attribute source should have similar traffic volume.</li></ul><br>If you have more than 10 report suites that have a common set of authenticated customers, you can configure additional customer attribute sources, each with up to 10 report suites.|
|Attributes to Include (Analytics and Target)|The attributes, _per report suite_, that you want to send to the solution. <br>When configuring subscriptions and selecting attributes, the following limits apply, depending on the solutions you own:<ul><li>Foundation: 0</li><li>Select: 3</li><li>Prime: 15</li><li>Ultimate: 200</li><li>Standard: 3 total</li><li>Premium: 200 per report suite</li><li>Target Standard: 5</li><li>Target Premium: 200</li></ul><br>**Note:** When you upgrade to Analytics Premium, there is a 24-hour delay before additional attributes are available. You may see an Attribute Subscription Max error issued during this delay.|
