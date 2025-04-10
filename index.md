---

<img src="./aged_vuln.jpg?raw=true" width=250 height=300/>

---

## Investigate & Remediate Aged (>60days) Vulnerabilties 


### Problem Statement

Despite the organization's security policy mandating the resolution of all severity 4 and 5 vulnerabilities within 60 days, aged vulnerabilities older than 60 days persist within the environment. The presence of these unresolved vulnerabilities increases the organization’s exposure to security threats, non-compliance with internal policies, and potential regulatory repercussions. An investigation is required to determine the root causes behind this non-compliance and to propose remedial actions.

### Project Objectives

* Identify and analyze the key reasons for the persistence of vulnerabilities older than 60 days.
* Assess adherence to security policy and determine process gaps.
* Evaluate the effectiveness of current vulnerability management and remediation processes.
* Identify resource, technical, and procedural constraints contributing to the delays.
* Provide actionable recommendations to improve the remediation process and ensure policy compliance.

### Scope

* Review all severity 4 and 5 vulnerabilities recorded in the vulnerability management system over the past 12 months.
* Investigate cases where vulnerabilities exceeded the 60-day remediation timeline.
* Assess team responsibilities, workflows, and escalation procedures.
* Engage stakeholders to gather insights on challenges in the remediation process.
* Provide a comprehensive report with findings and recommendations.

### Out of Scope

* Investigation of vulnerabilities with lower severity levels (Severity 1-3). (BAU responsibility!)
* Real-time penetration testing or active threat exploitation.
* Any systems or vulnerabilities outside the organization's direct management.

### Methodology

* **Data Collection:** Gather vulnerability scan reports, patching records, and remediation logs.
* **Stakeholder Interviews:** Engage with IT, security, and application teams to understand roadblocks.
* **Process Analysis:** Examine existing workflows for identifying, tracking, and resolving vulnerabilities.
* **Root Cause Analysis:** Identify recurring themes, systemic failures, and areas for improvement.
* **Recommendations & Remediation Plan:** Propose policy enhancements, process optimizations, and accountability measures.

### Key Deliverables

* Root Cause Analysis (RCA) Report
* Process Gap Assessment
* Compliance and Policy Adherence Report
* Recommendations for Improving Vulnerability Management
* Action Plan for Addressing Identified Issues

### Assumptions

* All relevant teams will collaborate and provide necessary data and insights.
* Security tools and reports will provide accurate and up-to-date vulnerability information.
* The organization is committed to implementing recommendations to improve compliance.

### Constraints

* Limited resources and competing IT/Business priorities.
* Possible resistance to change in remediation workflows.
* Dependency on third-party vendors for certain patches or fixes.
* Ownership of systems not clearly defined

### Seccess Criteria

* Identification of key failure points in the remediation process.
* Implementation of process improvements that reduce aged vulnerabilities by at least 80%.
* Enhanced accountability and tracking mechanisms.
* Improved compliance with the 60-day vulnerability resolution policy.

### Project Timeline

* Week 1-2: Data Collection and Initial Assessment
* Week 3-4: Stakeholder Interviews and Process Analysis
* Week 5-6: Root Cause Analysis and Findings Compilation
* Week 7-8: Recommendations and Final Report Submission
  
### Risks and Mitigation Strategies

| Risk  | Likelihood | Impact | Mitigation Strategy |
|-------|------------|--------|---------------------|
| Lackof stakeholder engagement | Medium | High | Secure Executive sponsoirship and mandate participation |
| Incomplete of inaccurate data | High | High | Validate data from multiple sources |
| Resistance to process change | Medium | Medium | Provide clear justification ad involve teams in solution design process |
| Competing priorities with IT teams | High | High | Align project with bussiness and security objectives to ensure prioritisation |

### Approval & Signoff

* Executive Sponsor : CTO
* Project Owner : Information Security Manager
* Security Leadership: Regional Information Security Officer
* IT Leadership: Regional CIO  

### Conclusion


This project aims to enhance the organization’s cybersecurity posture by identifying and addressing the reasons for aged vulnerabilities exceeding the 60-day resolution timeline. By implementing process improvements, we will mitigate security risks, improve compliance, and strengthen overall vulnerability management practices.

---

## Project Execution
Investigate the reasons for aged (>60days) vulnerabilities to still exist, identify the reasons for these vulnerabilities to still exist, and compile a remediation plan for those addressable with priorities and categorisationsChecking the current set of communication encryption algorithms in use (Data in Transit) as well as the encryption status of disk volumes (Data at Rest). Finally to compare compliance of the encryption algos in use to the published company standard and generating exception based reporting in PowerBI dashboard

---

### Review and Categorisation of Aged vulnerabilities

Vulnerabilities are categorised as either addressable or a non-addressable:
Addressable vulnerabilities needs to be actioned and remediated ASAP.

Company policy states that:

- All severity 4 & 5 vulnerabilities needs to be resolved within 30days

- Any severity 1-3 vulnerabilties needs to be resolved within 30 – 60 days.

Non-addressable vulnerabilities needs to be highlighted and formally logged under an InfoSec Risk and presented to business as part of a Risk Acceptance document. Business will then decide whether it will continue to tolerate the identified risk or enable some funds for investment to mitigate/eliminate the risk identified.

---

### Identification and classification of aged vulnerabilties

All aged vulnerabilities of severity 4 & 5 were identified, sorted and placed into buckets for each technical support team.

A large number (32%) of these severity 4 & 5 vulnerabilities were found to be associated with one specific business system which was still using CentOs 6.x and Ubuntu 12, 14 and 16 as the operating systems in use by this specific business system. Since there was another project already underway to rewrite the specific business application and transform it into a containerised application, these vulnerabilities were placed in a seperate remediation stream and progress tracked and reported on a weekly basis. Once the containerisation project was completed, the legacy system in use, as well as all of the CentOS 6.x and those deprecated Ubuntu platforms (12,14, 16 & 18)were decommissioned.

The remainder of these aged severity 4 and 5 vulnerabilties were associated with specific business systems and their associated platforms.

Results were as follows:

| Buss System				| Operating System	| Qty		| %Aged |
| ------------------------------------- | --------------------- | ------------- | ----- |
| System 1 (NMS - Network Monitor)	| Windows 2008		| 2		| 13    |
|					| Windows 2012		| 14		| 5     |
|                			| CentOS 6		| 17		| 16    | 
| System 2 (Hosted Xchange)		| Windows 2012		| 27		| 15    |
| System 3 (DNS Proxy)			| CentOS 6		| 8		| 9     |
| System 4 (VPN Access)			| Debian 8.x		| 8		| 2     |
| System 5 (Trafficker)			| CentOs 6		| 4		| 5     |
| System 6 (Legacy SAP)			| Windows 2012		| 9		| 7     |
| System 7 (HR Sharepoint Records)	| Windows 2012		| 8		| 5     |
| System 8 (containerisation)		| CentOS 6, Ubuntu	| 23		| 32    |
| 								|TOTAL		| 100   |

---

### Remediation of remainder of Aged Vulnerabilty Systems

Each of the identified applications was discussed with their respective owners as being out of compliance. It was made clear to them and the regional CIO that urgent steps will need to be taken to reduce the risk to the organisation by remediating the severity 4 & 5 vulnerabilties ASAP. It was made very clear that these applications are long overdue for either redevelopment/rehosting and or replatforming required. 

A remediation plan with an associated timeline was compiled with each of these application owners. This was used to construct high level program and project plans in order to compile budgetrequirements for these remediation efforts w.r.t. overtime to be worked as well a contractor resources to be brought on-board for the duration of the remediation period. All of these documents were presented to InfoSec Exco for approval. Each of these identified applications was registered as a remediation stream and tracked through daily standups, bi-weekly reviews and quarterly Exco feedback sessions

---
