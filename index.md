

---

## Remediation of Aged (>60days) Vulnerabilties 

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

#### Identify Assets associated with insecure communication encryption protocols in use:

Due to a number of legacy Operating systems existing in the environment (Windows 2012, CentOs6.x, Ubuntu 12,14,16 and 18, Debian 8) still in use throughout the organisation, it was decided to check for the existance of depracated encryption protocols including:
- SSL 2.0 and SSL 3.0 and
- TLS 1.0 and TLS 1.1

Using tools like NMAP and SSLSCan in a limited scope evironment identified for a POC, a detailed understanding of how to enumerate and interrogate ports using encryted communication was achieved.
This investigation helped with the identification of all of the QID's associated with SSL1, SSL2, SSL3, TLS 1.0 and TLS 1.1 In addition, a list of encryption protocols, already deemed insecure by the Security industry was compiled, and QID's associated with each of these depracated encryption algo's were identified and appended to the initial list of QID's identified for insecure transport protocols.
Using the complete list of QID's identified, a custom asset report was created in Qualys Asset module, to extract a list of assets with any of the associated QID’s identified. The resulting asset report was then used as the basis for the remediation plan to address those items found lacking ito secure communication protocols, insecure encryption algo’s and the directive received from CISO.

#### Identify Assets associated with insecure disk encryption protocols in use:

The encryption status of disks across the organisation was approached in a simple categorisation method.
All server disks on premise were interrogated with a script based approach, including Powershell for Windows based servers, and python for Linux based server platforms. A number of challenges were experienced, some around the specifics of python regarding the linux distributions but mainly around firewall access to specific systems. Once this was resolved, the disk encryption status results were written into a database, with the intent of using the database for analysis and reporting. The extraction of all cloud based disk partition encryption status (incl. Azure and AWS) was done using their respective CLI’s, with results written to same database as used for on-prem data disks info
A summary report was compiled to portray the full picture of the entire organisation’s disk encryption status, and subsequently published to a WEB page.

#### Identify Assets associated with insecure SSL certificates in use:

Collection of information regarding SSL certificate in use for on-prem servers, was done using a combination of Qualys Certificate Store, New Qualys Agents Scans and Qualys Network scan results, some python scripts and some Powershell scripts to extract info from windows server registry entries.
Extraction of Cloud based certificate info included Azure Entra, Powershell scripts, Azure Key Vault, AWS Certificate Manager, Qualys Certificate Store and Python scripts for 3rd party certificates, results were written to the previously created database.

A custom report was created to:
- Show disk volumes which did not have encryption enabled and
- Those disk volumes using insecure encryption algo’s already identified previously

This report was published to the same website as used previously for the comms protocol info. The entire process to collect, collate and publish this comms, diskand certificate encryption information was automated and implemented as a live data report for use by the organisations Information Security Manager as well as the Regional Information Security Officer going forward.

This concluded the assessment/investigation phase.


---

### Remediation Phase

---

Once the assessment info was published and shared with the operational teams responsible for supporting and updating these platforms, the Remediation initiative was kicked off.
A detailed extract of all server information, including operating systems and versions was provided to each of the technical engineering teams to review and provide feedback.
Upon receiving feedback it became clear that all of the platforms still running End of Life operating systems were constrained by the legacy applications hosted on those systems. A Large number of application owners were contacted and a process was started to either sunset, redevelop or re-host the current set of legacy applications.
Those applications for which the owners could not be found was escalated to the Regional CIO for a decision on how to proceed. An evaluation was made by the regional CIO of the usage of these legacy apps for which owners could not be found. Around 20 of the 25 apps for which owners could not be found were deemed unsuitable for future use and were retired via a Change management process. The other 5, for which the code was still available in the organisational code repo was earmarked for being migrated/replatformed into docker containers
The remaining 67 legacy applications were earmarked for either redevelopment, replatforming of retain status, till their functionality could either be retired or incorporated into one of the applications identified to be redeveloped. This retain period was capped at a maximum of 6 months from the date of decision.

This remediation phase was intended to be completed within 10 months in total, some external factors caused some delays, and was eventually signed off by Exco as complete after a periond of 12 months.

---
