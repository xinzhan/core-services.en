---

title: Experience Cloud ID Service Migration Decision Points
description:  Understanding how the Adobe Experience Cloud ID Service affects visitor tracking on multiple domains and potential issues if you are collecting data with different methods or through JavaScript files
SEO title: Experience Cloud ID Service Migration Decision Points
SEO description: Understanding how the Adobe Experience Cloud ID Service affects visitor tracking on multiple domains and potential issues if you are collecting data with different methods or through JavaScript files
short-title:
doc-type: article
audience:
author:
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# Experience Cloud ID Service Migration Decision Points

Before deploying the Experience Cloud ID service, you should understand how this service affects visitor tracking on multiple domains and potential issues if you are collecting data with different methods or through JavaScript files.

Answers to the questions in this section help determine any additional migration steps you should take.

+ [Do you have a data collection CNAME?](mcvid-migration-decisions.md)
+ [If you have a data collection CNAME, do you have multiple domains?](mcvid-migration-decisions.html#section_69EB55192F8B40A5833DA41AAFF5BFC0) 
+ [If you are keeping your data collection CNAME, is it mapped to omtrdc.net?](mcvid-migration-decisions.html#section_C9009CBF58594746A5B78BBF44ACAFBD) 
+ [If you do not have a data collection CNAME, is your data collection server \*.2o7.net or \*.sc.omtrdc.net?](mcvid-migration-decisions.html#section_34DABDE7780E4A339F134C0CA7768961) 
+ [Do you have multiple Analytics JavaScript files, or are you tracking Flash applications or videos?](mcvid-migration-decisions.html#section_943A04529F3D456AB608252D146658B3) 
+ [Are you using unsupported data collection methods?](mcvid-migration-decisions.html#section_6AF5FF728C054A3F8D27BA073E5B268B) 

## Do you have a data collection CNAME?

Many customers can migrate away from a data collection `CNAME` as part of the ID service migration.

| Data Collection Method | Description                                                                                                          |
| ---------------------- | -------------------------------------------------------------------------------------------------------------------- |
| With a `CNAME`         | See the next question to decide if you should migrate away from a data collection `CNAME`.                             |
| Without a `CNAME`      | Skip to *If you do not have a data collection `CNAME`, is your data collection server \*.2o7.net or \*.sc.omtrdc.net?* |

## If you have a data collection CNAME, do you have multiple domains?

If you have multiple domains that send data to the *same report suite*, then we recommend data collection with a `CNAME`. This helps you track visitors across domains. If you are collecting data on a single domain, there is no advantage to maintaining a data collection `CNAME`.

### Multiple Domains

+ If you are tracking visitors across multiple domains, and you also have a main entry site where customers can be identified before they visit other domains, then you should continue to use your data collection `CNAME`. See [Data Collection CNAMES and Cross Domain Tracking](mcvid_cname.html#) for a detailed explanation.

>[!NOTE]
>Note that you need to specify two additional tracking-server parameters, `visitor.marketingCloudServer` and `visitor.marketingCloudServerSecure`, to configure a `CNAME` with the ID service.

### A Single Domain

Working with a single domain means you can migrate away from a data collection `CNAME` if you no longer wish to manage it. However, there's no requirement to change if your `CNAME` is working.

If you do remove the `CNAME`:

+ Make sure your new tracking server is [RDC compliant](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/).
+ Move from the `CNAME` to an RDC tracking server a few months in advance of your migration to the Experience Cloud ID service.
+ *Do not* use a `*.2o7.net` tracking server.
+ Contact [Customer Care](https://helpx.adobe.com/marketing-cloud/contact-support.html) to set up a visitor migration. This helps ensure consistent visitor counts.

## If you are keeping your data collection CNAME, is it mapped to omtrdc.net?

If you decided to keep your `CNAME`, open a command prompt and ping your `CNAME`:

```
$: ping metrics.example.com
PING example.com.d1.sc.omtrdc.net (66.235.139.256)
```

| `CNAME` Resolves to                     | Required Action                                                                                                             |
| ------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| `*.omtrdc.net`                        | Your `CNAME` is configured correctly. No additional action is necessary.                                                      |
| Destination other than `*.omtrdc.net` | Update the `CNAME` record to point to your [RDC hostname](https://marketing.adobe.com/resources/help/en_US/whitepapers/rdc/). |

## If you do not have a data collection CNAME, is your data collection server \*.2o7.net or \*.sc.omtrdc.net?
| Server Address | Required Action                                                                                                                                                                                                                                                                                                                                              |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `*.2o7.net`    | If you are using `*.2o7.net`, migrate to the RDC data collection domain, `*.sc.omtrdc.net`.                                                                                                                                                                                                                                                                  |
|                | To make this migration, configure visitor migration from `*.2o7.net` to `*.sc.omtrdc.net`, and then update `s.trackingServer` to `[namespace].sc.omtrdc.net` when you update your Analytics JavaScript code later as part of the implementation process. |
| `*.sc.omtrdc`  | Continue to use your current data collection server.     |                                                 

If you have any questions at all about the hostname of your tracking server, contact Customer Care.

## Do you have multiple Analytics JavaScript files, or are you tracking Flash applications or videos?

If you have multiple Analytics JavaScript files or Flash applications or videos across your site that send data to the *same report suite*, You should configure a grace period so that visitors continue to be identified by an Analytics ID while you roll out the Experience Cloud ID service.

| Data Collection using                                                | Required Action                                                                                                                                                                                  |
| -------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Multiple Analytics Javascript files or other data collection methods | You should configure a visitor ID service grace period so that you can roll out the visitor ID service to each JavaScript file and other data collection libraries. See ID Service Grace Period. |
| A single Analytics JavaScript file                                   | You can update your single JavaScript file to use the visitor ID service without a grace period.                                                                                                 |
## Are you using unsupported data collection methods?

You might need to update the way you track links or migrate away from Sliverlight.

| Data Collection using   | Required Action                                                                                                                                                                                                                                                                                                                           |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| JavaScript and/or Flash | None. The Experience Cloud ID service supports these data collection methods.                                                                                                                                                                                                                                                             |
| Silverlight             | You need to migrate away from Silverlight if visitors can access Silverlight content and other sections of your site that use the Experience Cloud ID service. Silverlight is not supported by the ID service. If you are tracking a Silverlight-based video player, the vendor likely provides JavaScript APIs that you can use instead. |
| Hard-coded image tags   | Update hard-coded links to use JavaScript.                                                                                                                                                                                                                                                                                                |
