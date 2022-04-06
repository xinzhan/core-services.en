**Optimizing Your Adobe Target Implementation**

If you are new to your organization and want to become familiar with what is in place from a testing and optimization practice, this article with guide you in where to begin. We&#39;ll begin with an overview of Adobe Target implementation and structure. You&#39;ll learn how to understand and audit your organization&#39;s set up. Finally, we&#39;ll discuss common troubleshooting techniques and tips on creating a knowledge repository for your team.

Adobe Target is a tool that allows testing and targeting of unique content to different visitors. For an overview of the features available, [visit this guide](https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en).

**Target Implementation and Structure**

Before we dive into the implementation process for Adobe Target or how it is structured, it&#39;s helpful to first understand some fundamentals about the software.

Adobe Target is a tool that allows testing and targeting of unique content to different visitors without changing the native website code. Target temporarily changes the end user experience, as well as tracks the behavior of users after seeing the change. Target also offers the ability to alter the experience for end users based on profile information or previous actions.

There are three Target fundamental activity types:

1. A/B Test
2. Multi-Variate Testing (MVT)
3. Experience Testing

**The A/B Test** compares two or more experiences to see which best improves conversions throughout a pre-specified test period. The A/B test is a highly controlled experiment with traffic measurements, split by percentages rather than by a rule, allowing you:

- to analyze the test data.
- to glean insights about your audience.
- to determine which experience performs the best.

**Multi-Variate Testing** (MVT) compares combinations of offers among elements on a page to see which combination performs the best for a specific audience. This test also identifies which element of the page best improves conversions throughout a pre-specified test period. MVT provides:

- A way to display multiple offers in multiple elements.
- A method to test the resulting unique experience against a specific goal.
- Insight as to which elements have the greatest negative or positive impact on visitor interactions.

**Experience Testing** (Experienced Targeting) delivers content to a specific audience based on a set of marketer-defined rules and criteria. This method provides a way to target specific content to a specific audience based on a set of defined allocation rules.

How does Target work?

Here is a high-level example of how Target works:

1. A visitor requests a page from your server, and it displays in the browser.
2. A first party cookie is set in the visitor&#39;s browser to store behavior.
3. The page then calls Adobe Target.
4. The content displays based on the rules of the user&#39;s activity.
5. Adobe Target captures specific metrics as defined in the activity configuration to gauge the impact of the test experiences.

Target is built on an &quot;global Mbox&quot; that provides the ability to impact anything on the page. This feature deploys on page load either as a hardcoded link to the at.js file or it is delivered using a Tag Manager like Adobe Launch.

**Understand Your Current Implementation**

To understand your current Implementation, Adobe recommends that you review your Target User Interface implementation along with your Tag Manager and Page Load implementation.

1.

To Review your Target User Interface:

1. Begin your review on the Target UI:
  - Review the Target technology stack
  - Confirm the available features
  - Identify where the deployment is live
2. Review activities for Best Practices:

- Review historical Campaigns for program maturity

1. Deactivate Old Activities:
  - Archive and clean up Target Asset that no longer have current or future use
2. Review Audiences
3. Review environment definitions and associated domains
4. Review profile scripts for applicability
  - All profile scripts run on every target call
  - Maintain call efficiency by removing non applicable scripts

To Review the Tag Manager and Page Load:

1. Confirm the following in Tag Manager:
  - The deployment of the expected Target JavaScript code
  - The appropriate content hiding solution
  - Set Necessary rules to populate the Target calls with the expected parameters
2. Confirm the following during page load:
  - Matching version numbers for the Request URL and Target Request URL
  - Populated Experienced Cloud ID value (Cloud Body)
  - Present Expected Integration values (Cloud Body)
  - Populated Target Parameters on the appropriate pages

**Target Audit Activities**

To avoid manually going through each page to audit Target activities, use the Adobe Auditor to help with understanding the current technical state of your implementation. Adobe Auditor is powered by ObservePoint and can be set up to run at a manual level, to identify high level implementation issues on your site.

The Adobe Auditor provides:

- A high site health
- Quick call outs for implementation issues

Adobe recommends performing monthly manual audits to:

- Identify untagged pages
- Identify inconsistent versions
- Find out-of-date versions
- Provide detailed information that can be exported

**Common Troubleshooting**

**General Note:** Adobe recommends installing the Adobe Experience Platform Debugger.

The following are general troubleshooting tips when entering the Experience:

**Cache and Cookies**

- Clearing Cache and cookies
- Be careful using Private mode (for example: Private mode in Firefox can block Target)

**Are you qualified for the activity?**

- Check that you have performed the same steps that the audience used in the activity
- Use mboxTrace or response tokens to check profile and segment values

**The following are general troubleshooting tips when validating visual/ functional:**

If are in the Target experience and you do not see the expected visual experience:

Check the Target response:

- If the code is not executed:

1. Check conflicting activities
2. Contact Client Care

- If the code is executed:

1. Re-work the code in that scenario

**Maintaining a Knowledge Repository**

A Knowledge Repository is an online platform used for documenting and sharing information. The Knowledge Repository contains information specific to your implementation and can contain team specific information.

Ideally, the repository should allow editing and auto saving within the platform. Once it is initially configured, it is easy to maintain and keep up to date. Content within the Knowledge Repository is curated based on user roles.

Typical documents in a Knowledge Repository include:

- **Overview document** – a document used to clearly explain program goals, objectives, processes and structure
- **Ideation Repository** – a document used to manage and prioritize potential ideas that are not ready for the testing process
- **Program Roadmap** – a document used to manage all aspects of testing activities once ideas are ready to start the testing process
- **Activity Plan Document** – a document used to outline information needed to build and launch activities
- **Activity Plan Document** – a document used to communicate results and recommended next steps to stakeholders
- **Program Dashboard** – a document used to track program performance, cadence, and revenue benefits over time.

For more information, review our webinar with Senior Consultant, Wilder Freed: [https://adobecustomersuccess.adobeconnect.com/p4p7xlp7dh42mp4/](https://adobecustomersuccess.adobeconnect.com/p4p7xlp7dh42mp4/)