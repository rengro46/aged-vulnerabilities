

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


