---
description: Learn how Adobe Analytics uses cookies to provide information on variables and components that do not persist between image requests and browser sessions.
keywords: cookies;privacy
solution: Experience Cloud,Analytics
title: "First-party cookies "
index: y
snippet: y
feature: Cookies
topic: Administration
role: Admin
level: Experienced
exl-id: e15abde5-8027-4aed-a0c1-8a6fc248db5e
---
# About first-party cookies

Analytics uses cookies to provide information on variables and components that do not persist between image requests and browser sessions. Where possible Adobe uses first-party cookies to record activities on your site. To record activity on different sites such as other domains you may own, third-party cookies are required.

Many browsers and anti-spyware applications are designed to reject and delete third-party cookies. Adobe ensures that cookies can always we set even if third-party cookies are blocked. The specific behavior varies depending on whether you are using the Experience Platform Identity Service (ECID Service) or Analytics’ legacy identifiers (aka the s_vi cookie):

* The [Experience Platform Identity Service (ECID Service)](https://experienceleague.adobe.com/docs/id-service/using/intro/overview.html?lang=en) will automatically set first-party cookies regardless of whether your collection domain matches your site domain. If they do not match, the Identity Service will use JavaScript to set cookies in your site’s domain.
* If you are using [Analytics legacy identifiers](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-analytics.html?lang=en) (aka the `s_vi` cookie) it depends on how you have configured your data collection server. If the data collection server matches your site's domain, then cookies are set as first-party. If the collection server does not match your current domain, then cookies are set as third party. In this case, if third-party cookies are blocked, Analytics sets a first-party [fallback id (s_fid)](cookies-analytics.md) instead of the standard "s_vi" cookie.

If you would like to ensure your collection server matches your site’s domain, you can use a CNAME implementation which will enable forwarding from a custom domain specified in your CNAME implementation to Adobe’s collection servers. This involves changes to your company’s DNS settings to configure a CNAME alias to pointing to an Adobe hosted domain. Please note that while various Adobe products support using a CNAME, in all cases the CNAME is used to a create a trusted first-party endpoint for a specific customer and is owned by that customer. If you control multiple domains, they may use a single CNAME endpoint to track users across their domains, but wherever the site domain does not match the CNAME domain cookies is set as third party.

>[!NOTE]
>
>Regardless of whether your collection domain matches your site domain, Apple’s Intelligent Tracking Prevention (ITP) program makes the first-party cookies set by Adboe short-lived on browsers that are governed by ITP, which include Safari on macOS and all browsers on iOS and iPadOS. As of November 2020, cookies set via CNAME also have the same expiry as cookies set via JavaScript. This expiry is subject to change.

If you want to establish a CNAME for data collection and if your site has secure pages using the HTTPS protocol, you can work with Adobe to obtain an SSL certificate.

The SSL certificate issuance process can often be confusing and time consuming. As a result, Adobe established a partnership with DigiCert, an industry-leading Certificate Authority (CA), and developed an integrated process by which the purchase and management of these certificates is automated.

With your permission, we work with CA to issue, deploy, and manage a new SHA-2 SSL certificate for you. Adobe continues to manage this certificate and ensure that an unexpected expiration, revocation, or security concern, does not threaten the availability of your organization's secure collection.

## Adobe-Managed Certificate Program

The Adobe Managed Certificate Program is the recommended process for setting up the first-party SSL certificate needed for a CNAME implementation which ensures your Adobe collection server matches your site domain. 

The Adobe Managed Certificate program lets you implement a new first-party SSL certificate at no additional cost (for your first 100 CNAMEs). If you currently have your own Customer-Managed SSL certificate, speak with Adobe Customer Care about migrating to the Adobe-Managed Certificate Program.

### Implement

Here is how you implement a new first-party SSL certificate for first-party data collection:

1. Fill out the [First-party domain request form](/help/interface/cookies/assets/First_Part_Domain_Request_Form.xlsx) and open a ticket with Customer Care requesting to set up first-party data collection on the Adobe-Managed program. Each field is described within the document with examples.

2. Create CNAME records (see instructions below).

    Upon receiving the ticket, a customer care representative should provide you with a CNAME record. These records must be configured on your company's DNS server before Adobe can purchase the certificate on your behalf. The CNAME is similar to the following: 

    **Secure** - For example, the hostname `smetrics.example.com` points to: `example.com.adobedc.net`.

>[!NOTE]
> In the past, Adobe recommended that customers setup two CNAME, one for HTTPS and one for HTTP. Since it is a best practice to encrypt traffic and most browsers are strongly discouraging HTTP, we no longer recommend setting up a CNAME for HTTP. If you need to configure your CNAME for HTTP, please reach out to Adobe Customer Care. 

1. When the CNAME is in place, Adobe works with DigiCert to purchase and install a certificate on Adobe's production servers.

    If you have an existing implementation, you should consider visitor migration to maintain your existing visitors. After the certificate has been pushed live to Adobe’s production environment, you can update your tracking server variables to the new hostnames. Meaning, if the site is not secure (HTTP), update the `s.trackingServer`. If the site is secure (HTTPS), update both `s.trackingServer` and `s.trackingServerSecure` variables.

2. [Validate hostname forwarding](#validate) (see below).

3. [Update Implementation Code](#update) (see below).

### Maintenance and Renewals

SSL certificates expire each year, meaning Adobe must purchase a new certificate for each implementation on a yearly basis. All supported users within your organization receive an email notification each time an implementation is close to expiration. For Adobe to renew your hostname, one supported user must reply to the email from Adobe and indicate that you plan to continue using the expiring hostname for data collection. At that point, Adobe automatically purchases and installs a new certificate.

### Frequently Asked Questions

|Question|Answer|
|---|---|
|**Is this process secure?**|Yes, the Adobe-Managed program is more secure than our legacy method as no certificate or private key changes hands outside of Adobe and the issuing certificate authority.|
|**How can Adobe purchase a certificate for our domain?**|The certificate can only be purchased when you have pointed the specified hostname (for example, `telemetry.example.com`) to an Adobe owned hostname. This is essentially delegating this hostname to Adobe and allows Adobe to purchase the certificate on your behalf.|
|**Can I request that the certificate be revoked?**|Yes, as the owner of the domain, you are entitled to request we have the certificate revoked. You will only need to open a ticket with Customer Care to have this completed.|
|**Will this certificate be using SHA-2 encryption?**|Yes, Adobe will work with DigiCert to issue a SHA-2 certificate.|
|**Does this incur any additional cost?**|No, Adobe is offering this service to all current Adobe Digital Experience customers at no additional cost.|

{style="table-layout:auto"}

## Create CNAME records

Your organization's network operations team should configure your DNS servers by creating CNAME records. Each hostname forwards data to Adobe's data collection servers.

The FPC specialist provides you with the configured hostname and what CNAME they are to be pointed to. For example:

* **SSL Hostname**:`smetrics.mysite.com`
* **SSL CNAME**:`mysite.com.adobedc.net`

>[!NOTE]
> If you still use non-secure, it will look like this:
> * **Non-SSL Hostname**:`metrics.mysite.com`
> * **Non-SSL CNAME**:`mysite.com.adobedc.net`

As long as implementation code is not altered, this step will not affect data collection and can be done at any time after updating implementation code.

## Validate hostname forwarding {#validate}

The following methods are available for validation:

### Validate using a browser

If you have a CNAME set up and the certificate installed, you can use the browser for validation:

`https://smetrics.adobe.com/_check`

>[!NOTE]
>
>You are issued a security warning if a certificate is not installed.

### Validate using [!DNL curl]

Adobe recommends using [[!DNL curl]](https://curl.se/) from the command line. ([!DNL Windows] users can install [!DNL curl] from: <https://curl.se/windows/>)

If you have a CNAME but no certificate is installed, run: 
`curl -k https://smetrics.adobe.com/_check`
Response: `SUCCESS` 

(The `-k` value disables the security warning.)

If you have a CNAME set up and the certificate is installed, run:
`curl https://smetrics.adobe.com/_check`
Response: `SUCCESS`

### Validate using [!DNL nslookup]

You can use `nslookup` for validation. Using `smetrics.adobe.com`as an example, open a command prompt and type `nslookup smetrics.adobe.com`

If everything is successfully set up, you see a return similar to:

```
nslookup smetrics.adobe.com
Server:             10.30.7.247
Address:     10.30.7.247#53

smetrics.adobe.com    canonical name = adobe.com.ssl.d1.sc.omtrdc.net.
Name:  adobe.com.ssl.d1.sc.omtrdc.net
Address: 54.218.180.161
Name:  adobe.com.ssl.d1.sc.omtrdc.net
Address: 52.39.8.230
Name:  adobe.com.ssl.d1.sc.omtrdc.net
Address: 54.187.216.46
```

## Update implementation code {#update}

Before you edit code on your site to use first-party data collection, complete these prerequisites:

* Request an SSL certificate, by following the steps described above in the *Implement* section of the [Adobe-Managed Certificate Program](#adobe-managed-certificate-program).
* Create CNAME records (see above).
* Validate the hostnames (see above).

After you have verified your hostnames are responding and forwarding to Adobe data collection servers, you can alter your implementation to point to your own data collection hostnames.

1. Open your core JavaScript file (`s_code.js/AppMeasurement.js`).
1. If you want to update your code version, replace your entire `s_code.js/AppMeasurement.js` file with the newer version and replace any plugins or customizations (if any). **Or**, if you want to update the code only pertinent to first-party data collection, locate the s.trackingServer and s.trackingServerSecure (if using SSL) variables, and point them to your new data collection hostnames. Using mysite.com as an example:`s.trackingServer = "metrics.mysite.com"` `s.trackingServerSecure = "smetrics.mysite.com"`

1. Upload the updated core JavaScript file to your site.

1. If you are moving to first-party data collection from a long-standing implementation, or changing to a different first-party collection hostname, Adobe recommends migrating visitors from the previous domain to the new domain.

See [Visitor Migration](https://experienceleague.adobe.com/docs/analytics/technotes/visitor-migration.html?lang=en) in the Analytics Implementation Guide.

After you have uploaded the JavaScript file, everything is configured for first-party data collection. Adobe recommends that you monitor Analytics reporting for the next several hours to ensure that data collection continues as normal. If it does not, verify that all above steps have been completed and have one of your organization's supported users contact Customer Care.
