---
description: Learn how to enable privacy settings for browser cookies. You can remove users who blocked all cookies on desktop and mobile browsers.
keywords: cookies;privacy
solution: Experience Cloud, Analytics, Target, Social
title: Privacy settings for browser cookies 
uuid: f6a56e8b-b021-49db-8eb4-6c14af0c7243
feature: Cookies
topic: Administration
role: Administrator
level: Experienced
---

# Enable privacy settings for browser cookies{#enable-privacy-settings-for-browser-cookies}

You can remove users who blocked all cookies on desktop and mobile browsers. This feature is a privacy setting that excludes users who opt out of data collection, enabling you to respect a user's intention to stop Analtyics processing.

**To enable privacy settings for browser cookies**

1. Navigate to **[!UICONTROL Admin Tools]** > **[!UICONTROL Report Suites]**. 
1. Click **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Privacy Settings]**. 
1. Enable **[!UICONTROL Privacy Settings]** (for desktop or mobile).

>[!IMPORTANT]
>
>Be aware that many mobile apps (such as the in-app browser for Facebook or Twitter) can appear as a standard mobile browser but do not allow all cookies. Enabling this feature could exclude a high proportion of mobile traffic from Analytics reports.

**About Browser Privacy Settings**

Laws and regulatory guidance have expressed that a user's action to block cookies is the same as a user's action to opt out of profiling. By enabling this feature, data collected from desktop browsers, where the user has set the browser to block all cookies, will be excluded from Analytics reports. If Adobe cannot recognize the web browser, data will be included in Analytics reports.

Lawmakers around the world have stated (both in guidance and in settlements) that cookie browser settings are an indication of user preference to opt out of profiling. Specifically, these lawmakers have stated that the browser setting to block third-party cookies is an opt-out request from third-party (cross-site) tracking. Blocking out all cookies is an opt-out request for all tracking. While server-side identifiers (such as IP address or user agent) may be a desirable option that bypasses cookie browser settings, some lawmakers view them as a circumvention of user choice.