**Adobe Analytics: Simple Hacks for Greater Efficiency and Self-Service**

**[Part 1: Outside the UI]**

In this article we&#39;ll discuss key challenges analytics teams face today and our recommendations to overcome them using strategies outside the Adobe Analytics UI. For more information on in-tool strategies / live demo, click here: [link to demo or additional article with in-tool strategies]

**Key Challenges for Analytics Teams**

Many Analytics teams find themselves with an imbalanced distribution of work. Instead of a mix of 80% analysis and 20% implementation, numerous organizations find themselves in the inverse of that, with the majority of their efforts spent setting up, reporting, and providing support as opposed to producing analysis that drives high value insights.

Analytics teams are finding their productivity and efficiency drained for a number of reasons: the ever-changing and evolving implementations, trying to maintain organizational trust in the data, and reducing analyst turnover to avoid the lengthy process of training new team members on unfamiliar, custom-implementation tools.

Other key challenges analysts face:

- **Competition -** online and multi-channel retail businesses grow more competitive
- **Customer expectations -** customer experiences and marketing strategies become more complex
- **Data Value -** the value of accurate data and insights to drive a competitive advantage grows more important
- **Stakeholder expectations -** business partners, stakeholders, and executives increasingly request data before approval
- **Project management -** the analytics team drowns in requests to implement data collection for a never-ending stream of new features, while producing accurate reports, onboarding new analysts, and uncovering the next new insight

**Keys to Efficiency: Outside the UI**

1. Keep your Solution Design Reference (SDR) up to date
  1. The SDR is the primary source of truth for the definition and intended use of all variables within your analytics implementation
  2. The SDR is the main reference that direct users will need to be familiar with to get value out of your Adobe Analytics UI
  3. Keeping it updated and versioned (a simple date format can be used) is highly important

1. Data Collection Documentation and Governance - Tech Specs

The Tech Spec has a more limited audience than the SDR but is as important, if not more, for a fully functional implementation. A good tech spec should be all the development, QA, and tag tag management resources needed to implement the solution. Be sure to maintain as many documents as are needed to accommodate unique implementation architectures.

Tech Spec:

  1. Use Case: Instructions describing how to construct scripts for data collection
  2. Primary Users: Developers
  3. Other Notes:
    1. Highly technical document built specifically for your deployment environments
    2. Useful for both initial implementation and subsequent maintenance/reference
    3. Organized by solution type (e.g. campaign tracking, page metadata, etc.)
    4. Primary document needs to be updated and maintained as SDR changes are made
    5. Central repository
    6. Synchronized version numbers for SDR and Tech Spec

1. Communicate and document solution design intent on launch
  1. Communicate with the user in mind
  2. When launching or enhancing data collection, create simple summaries that can be shared with stakeholders.
  3. Reinforce proper variable use out of the gate
  4. Send a summary launch announcement email to the main stakeholders and analysts
  5. Create a library that can be used in support of office hours, team enablement sessions, or for team-specific onboarding

1. Data collection documentation, governance, and data hygiene - AHD

The Analytics Health Dashboard (AHD) dives deep into a _single_ report suite and

provides a view into data collected in every component (eVar, prop, and event). This can

help point out if data has stopped collecting into a component so you can take action to correct the issue. You can run this dashboard at any time in the future for any report suite.

Analytics Health Dashboard (AHD):

1. Use Case: Snapshot of every metric and dimension being captured by a single report suite
2. Primary Users: Lead Analytics SME and/or Dev
3. Other Notes:
  1. Delivered through Excel using a custom integration of the Adobe Reporting API
  2. Users must have Analytics web services API access
  3. Options to semi-automate exist

5. Win through expanding the world of SMEs

1. Establish SMEs within the various teams in the organization
2. Build their presence by helping socialize releases and wins
3. Leverage regular office hours to help train the trainers and cut down on ad-hoc asks

In this article we have reviewed ways to improve efficiency outside the UI of Adobe Analytics. For more information on in-tool strategies, click here: [link to demo or additional article with in-tool strategies]