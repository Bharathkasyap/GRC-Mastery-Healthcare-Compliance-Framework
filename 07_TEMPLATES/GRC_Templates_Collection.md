# 07_TEMPLATES — GRC Templates Collection
# MediGlobal HealthTech Inc. | Ready-to-Use GRC Templates

> **Document Owner:** GRC Program Director  
> **Last Updated:** Q1 2026  
> **Classification:** INTERNAL — For GRC Team Use  
> **Purpose:** Working templates for real GRC projects — customize with your company's information

---

## TEMPLATE INDEX

1. Business Associate Agreement (BAA) Template
2. Incident Response Checklist — P1 Security Incident
3. Third-Party Risk Questionnaire (50+ questions)
4. Security Awareness Training Acknowledgment Form
5. Risk Acceptance Form
6. Vendor Onboarding Security Checklist
7. GRC Project Kickoff Intake Form
8. ISO 27001 Gap Assessment Template (abbreviated)

---

## TEMPLATE 1: BUSINESS ASSOCIATE AGREEMENT (BAA)

**BUSINESS ASSOCIATE AGREEMENT**

This Business Associate Agreement ("Agreement") is entered into as of [DATE] between:

**Covered Entity:** MediGlobal HealthTech Inc., a healthcare corporation organized under the laws of Delaware, with principal offices at 200 North LaSalle Street, Chicago, IL 60601 ("Covered Entity")

**Business Associate:** [VENDOR COMPANY NAME], organized under the laws of [STATE], with principal offices at [ADDRESS] ("Business Associate")

Collectively referred to as the "Parties."

---

**WHEREAS**, Covered Entity is a Covered Entity as defined under the Health Insurance Portability and Accountability Act of 1996 ("HIPAA") and its implementing regulations at 45 CFR Parts 160 and 164;

**WHEREAS**, Business Associate performs [DESCRIBE SERVICE] on behalf of Covered Entity, which requires Business Associate to access, create, receive, maintain, or transmit Protected Health Information ("PHI") on behalf of Covered Entity;

**NOW, THEREFORE**, the Parties agree as follows:

### ARTICLE 1: DEFINITIONS

**1.1 "Protected Health Information" or "PHI"** shall have the meaning given such term in 45 CFR § 164.103.

**1.2 "Security Incident"** shall have the meaning given such term in 45 CFR § 164.304.

**1.3 "Breach"** shall have the meaning given such term in 45 CFR § 164.402.

**1.4 "Minimum Necessary"** means limiting PHI access to the minimum amount necessary to accomplish the intended purpose, consistent with 45 CFR § 164.502(b).

---

### ARTICLE 2: PERMITTED USES AND DISCLOSURES

**2.1** Business Associate may use and disclose PHI solely to perform the services described in the underlying services agreement between the Parties (the "Services Agreement"), and only to the extent necessary to perform those services.

**2.2** Business Associate shall not use or disclose PHI in any manner that would violate HIPAA if done by Covered Entity.

**2.3** Business Associate may disclose PHI to its subcontractors only if such subcontractors agree in writing to the same restrictions and conditions that apply to Business Associate under this Agreement.

---

### ARTICLE 3: OBLIGATIONS OF BUSINESS ASSOCIATE

**3.1 Safeguards.** Business Associate shall implement and maintain appropriate administrative, physical, and technical safeguards to prevent unauthorized use or disclosure of PHI, including implementing the HIPAA Security Rule safeguards at 45 CFR §§ 164.308, 164.310, and 164.312.

**3.2 Minimum Necessary.** Business Associate shall use and disclose only the minimum necessary PHI required to perform the Services.

**3.3 Reporting.**
   (a) **Breach Notification.** Business Associate shall notify Covered Entity without unreasonable delay, and in no case later than **one (1) business hour** following Business Associate's discovery of a potential or confirmed Breach of Unsecured PHI, as required by 45 CFR § 164.410. Notification shall be made to: GRC@mediglob.com AND CISO@mediglob.com AND Legal@mediglob.com.
   
   (b) **Security Incidents.** Business Associate shall report to Covered Entity any Security Incident of which it becomes aware within **four (4) business hours** of discovery.
   
   (c) **Non-permitted Uses.** Business Associate shall report any use or disclosure of PHI not provided for by this Agreement within **twenty-four (24) hours**.

**3.4 Subcontractors.** Business Associate shall ensure that any subcontractor handling PHI executes a written agreement with Business Associate imposing substantially similar requirements to this Agreement.

**3.5 Access to Records.** Business Associate shall make its internal practices, books, and records relating to the use and disclosure of PHI available to the Secretary of HHS and to Covered Entity for purposes of determining compliance with HIPAA.

**3.6 Audit Rights.** Covered Entity shall have the right to audit Business Associate's security practices no more than once per calendar year, upon 30 days' written notice, at Covered Entity's expense.

**3.7 Return/Destruction of PHI.** Upon termination of this Agreement, Business Associate shall destroy or return all PHI received from or created on behalf of Covered Entity. If return or destruction is not feasible, Business Associate shall extend the protections of this Agreement to the PHI and limit further uses and disclosures to those purposes that make return or destruction infeasible.

**3.8 Log Retention.** Business Associate shall retain audit logs, access logs, and security event logs for a minimum of **seven (7) years** from the date of creation, or for such longer period as required by applicable law.

**3.9 Annual Security Assessment.** Business Associate shall complete Covered Entity's security assessment questionnaire annually and provide supporting documentation within **thirty (30) days** of request.

**3.10 Sub-processor Disclosure.** Business Associate shall maintain and provide to Covered Entity a current list of all sub-processors that handle PHI within **five (5) business days** of request.

---

### ARTICLE 4: TERM AND TERMINATION

**4.1** This Agreement shall be effective as of the date first written above and shall remain in effect until the termination of the Services Agreement, unless earlier terminated under this Article.

**4.2** Either Party may terminate this Agreement upon thirty (30) days' written notice.

**4.3** Covered Entity may terminate this Agreement immediately upon written notice if Business Associate has materially violated any provision of this Agreement.

**4.4** Obligations under Section 3.7 (Return/Destruction of PHI) and Section 3.8 (Log Retention) shall survive termination.

---

### ARTICLE 5: MISCELLANEOUS

**5.1 Governing Law.** This Agreement shall be governed by the laws of the State of Illinois.

**5.2 Amendment.** This Agreement may be amended only by written agreement signed by authorized representatives of both Parties.

**5.3 Entire Agreement.** This Agreement, together with the Services Agreement, constitutes the entire agreement of the Parties regarding the subject matter hereof.

---

**COVERED ENTITY:** MediGlobal HealthTech Inc.

Signature: _________________________ Date: ___________
Name: Sarah Patel
Title: Chief Compliance Officer

**BUSINESS ASSOCIATE:** [VENDOR NAME]

Signature: _________________________ Date: ___________
Name: _________________________
Title: _________________________

---

## TEMPLATE 2: INCIDENT RESPONSE CHECKLIST — P1 SECURITY INCIDENT

**MEDIGLOBAL HEALTHTECH INC. — P1 INCIDENT RESPONSE CHECKLIST**
**Incident ID:** INC-[YEAR]-[NUMBER]
**Incident Declared:** [DATE/TIME]
**Completed by:** [GRC ANALYST NAME]

---

### PHASE 1: IDENTIFICATION (0–30 minutes)

- [ ] **T+0:** P1 incident declared — note exact time: __________
- [ ] **T+5:** Page CISO (James Nakamura — cell: on-call roster) — note time paged: __________
- [ ] **T+10:** Page Incident Response Lead — note time paged: __________
- [ ] **T+15:** Open ServiceNow INC ticket — ticket number: __________
- [ ] **T+15:** Set ticket access restriction if sensitive investigation (HR/Legal)
- [ ] **T+20:** Notify Privacy Officer (Priya Sharma) if PHI potentially involved
- [ ] **T+25:** Notify Legal (Jennifer Wu, General Counsel) — invoke attorney-client privilege
- [ ] **T+30:** Confirm War Room location or Teams bridge: __________

**Initial Scope Assessment:**
- Systems affected: ______________________________________
- Data types involved: ____ PHI ____ PII ____ Financial ____ IP ____ None confirmed yet
- Estimated number of individuals potentially affected: ______
- Geographic scope: ____________________________________

---

### PHASE 2: CONTAINMENT (30 minutes – 4 hours)

- [ ] Isolate affected systems (if applicable — confirm with CISO before acting)
- [ ] Preserve evidence BEFORE taking containment actions (check with Legal/IR Lead)
- [ ] Block attacker/threat source at firewall (if applicable)
- [ ] Revoke compromised credentials (if applicable)
- [ ] Preserve forensic evidence — note all evidence collected:

| Evidence Item | Date/Time Collected | Collected By | Hash (SHA-256) |
|--------------|---------------------|-------------|----------------|
| | | | |
| | | | |

- [ ] Engage external forensic firm if needed (Mandiant — pre-authorized retainer)
- [ ] Notify Cyber Insurance (AIG — contact in incident response playbook)

---

### PHASE 3: HIPAA BREACH ASSESSMENT (Within 24 hours)

- [ ] **Start HIPAA 60-day clock:** Discovery date = __________ | Deadline = __________
- [ ] Complete HIPAA breach risk assessment (4-factor test):

| Factor | Analysis | High/Low Risk? |
|--------|---------|----------------|
| Nature and extent of PHI | | |
| Who accessed/used the PHI | | |
| Was PHI actually acquired? | | |
| Was risk mitigated? | | |

- [ ] **Breach determination:** ☐ Breach confirmed ☐ Not a breach ☐ Still assessing
- [ ] If breach confirmed: assign patient notification lead
- [ ] If >500 patients: trigger OCR notification process (Deputy Privacy Officer)

---

### PHASE 4: NOTIFICATION (Timeline depends on breach determination)

**Internal Notifications:**
- [ ] CEO notified by: __________ at __________ (time)
- [ ] Board Chair pre-briefed (if material): __________
- [ ] All department heads notified: __________ (confidential — restricted)
- [ ] Hospital CMOs notified (if clinical impact): __________

**Regulatory Notifications (if HIPAA breach confirmed):**
- [ ] Individual patients by: __________ (60 days from discovery)
- [ ] HHS OCR by: __________ (60 days, or 72 hours if media notice required)
- [ ] State AGs — identify relevant states: __________________________
- [ ] Media notice (if >500 patients in single state): __________

---

### PHASE 5: RECOVERY AND LESSONS LEARNED

- [ ] Systems restored and verified secure: Date: __________
- [ ] Monitoring enhanced for 30 days post-incident
- [ ] Lessons learned meeting scheduled: Date: __________
- [ ] Post-incident report drafted: Date: __________
- [ ] Risk register updated with new/modified risk entries
- [ ] ISO 27001 audit evidence gathered (incident management — A.5.26)

**Lessons Learned (complete within 5 business days of incident close):**
1. What worked well?
2. What didn't work? Root cause?
3. What controls need to be added or improved?
4. What policy/procedure needs to be updated?

---

## TEMPLATE 3: THIRD-PARTY RISK QUESTIONNAIRE (ABBREVIATED — 50+ QUESTIONS)

**MEDIGLOBAL HEALTHTECH INC. — VENDOR SECURITY ASSESSMENT**
**Vendor Name:** ___________________________
**Assessment Date:** ___________________________
**Vendor Contact:** ___________________________
**Tier Classification:** ☐ Tier 1 (PHI access) ☐ Tier 2 (Limited data) ☐ Tier 3 (No sensitive data)

---

### SECTION A: ORGANIZATIONAL SECURITY (10 questions)

A1. Does your organization have a documented information security program? ☐ Yes ☐ No
   If yes, attach your Information Security Policy (required for Tier 1 vendors).

A2. Does your organization have a designated CISO or equivalent security leader? ☐ Yes ☐ No
   Name and contact: ___________________________

A3. Has your organization achieved ISO 27001 certification? ☐ Yes ☐ No ☐ In Progress
   If yes, provide certificate and scope: ___________________________

A4. Does your organization have a current SOC 2 Type II report? ☐ Yes ☐ No
   If yes, provide report (or NDA-protected summary): ___________________________

A5. Has your organization undergone a penetration test in the last 12 months? ☐ Yes ☐ No
   If yes, provide executive summary with findings and remediation status.

A6. Does your organization conduct annual security awareness training for all employees? ☐ Yes ☐ No
   Current completion rate: _______% Date last completed: _______________

A7. Does your organization have a documented incident response plan? ☐ Yes ☐ No
   When was it last tested? ___________________________

A8. Does your organization carry cyber liability insurance? ☐ Yes ☐ No
   If yes, coverage amount: $________________________

A9. How many employees have access to MediGlobal data? ___________________________
   How many of those have privileged/administrative access? ___________________________

A10. Describe your process for background screening of employees with access to PHI:
___________________________________________________________________

---

### SECTION B: ACCESS CONTROL (8 questions)

B1. Do you enforce Multi-Factor Authentication (MFA) for all users accessing systems with PHI? ☐ Yes ☐ Partial ☐ No
   Which systems have MFA gaps? ___________________________

B2. Is privileged access (admin accounts) segregated from standard user accounts? ☐ Yes ☐ No
   Describe your Privileged Access Management (PAM) approach:

B3. How frequently do you review and recertify user access rights? 
   ☐ Monthly ☐ Quarterly ☐ Semi-annually ☐ Annually ☐ Never

B4. Do you have a formal offboarding procedure to revoke all access within __ hours of employee termination?
   Timeframe: __________ hours. Attach procedure if Tier 1.

B5. Do you use role-based access control (RBAC)? ☐ Yes ☐ No
   Are access roles documented and reviewed? ☐ Yes ☐ No

B6. Are all administrative actions (privileged access) logged and monitored? ☐ Yes ☐ No
   Log retention period: _____ months/years

B7. Do you have a documented "minimum necessary" policy for data access? ☐ Yes ☐ No

B8. Are shared accounts/credentials prohibited in your environment? ☐ Yes ☐ No
   If no, explain exceptions: ___________________________

---

### SECTION C: VULNERABILITY MANAGEMENT AND PATCHING (8 questions)

C1. Do you conduct regular vulnerability scans of all systems in scope for MediGlobal data? ☐ Yes ☐ No
   Scan frequency: ___________________________

C2. What is your patching SLA for critical vulnerabilities (CVSS 9.0+)?
   ☐ 24 hours ☐ 72 hours ☐ 7 days ☐ 30 days ☐ No formal SLA

C3. Do you have a formal patch management policy? ☐ Yes ☐ No
   Provide policy or summary: ___________________________

C4. **[POST-BREACH ADDITION]** List all Java-based applications in your production environment and confirm Log4j2 version:

| Application Name | Java Version | Log4j2 Version | Patch Status |
|----------------|-------------|----------------|-------------|
| | | | |

C5. Do you have end-of-life (EOL) operating systems or applications in your environment? ☐ Yes ☐ No
   If yes, list them and describe compensating controls: ___________________________

C6. Are all systems in scope for MediGlobal data included in your vulnerability management program? ☐ Yes ☐ No
   Are there exceptions? If yes, describe: ___________________________

C7. Do you use a vulnerability management tool (e.g., Qualys, Tenable, Rapid7)? ☐ Yes ☐ No
   Tool name: ___________________________

C8. How do you prioritize vulnerability remediation? Describe your risk-based approach:
___________________________________________________________________

---

### SECTION D: DATA PROTECTION AND ENCRYPTION (7 questions)

D1. Is PHI encrypted at rest using AES-256 or equivalent? ☐ Yes ☐ No ☐ Partial
   Which systems are NOT encrypted at rest? ___________________________

D2. Is PHI encrypted in transit using TLS 1.2 or higher? ☐ Yes ☐ No ☐ Partial
   Are any systems using TLS 1.0 or SSL? ☐ Yes ☐ No

D3. Is mobile device storage encrypted for devices that can access PHI? ☐ Yes ☐ No

D4. Do you have a documented data classification policy? ☐ Yes ☐ No
   Is PHI/sensitive data classified and labeled? ☐ Yes ☐ No

D5. Do you use Data Loss Prevention (DLP) tools? ☐ Yes ☐ No
   Coverage: ☐ Email ☐ Endpoint ☐ Network ☐ Cloud ☐ None

D6. What is your data retention policy for MediGlobal PHI? 
   Retention period: _____ years | Disposal method: ___________________________

D7. Do you have controls preventing PHI from being stored on personal devices or unauthorized cloud storage? ☐ Yes ☐ No

---

### SECTION E: INCIDENT RESPONSE (5 questions)

E1. What is your incident notification procedure for a breach involving MediGlobal data?
   Under this BAA, MediGlobal requires notification within 1 business hour of discovery. Confirm you can meet this requirement: ☐ Yes ☐ No
   Describe your notification process: ___________________________

E2. Who is your primary security contact for breach notifications?
   Name: ___________________________ | Phone: ___________________________ | Email: ___________________________

E3. Who is your 24/7 emergency security contact?
   Name: ___________________________ | Cell: ___________________________

E4. Have you experienced a data breach in the last 3 years? ☐ Yes ☐ No
   If yes, describe the incident and outcome: ___________________________

E5. Do you conduct annual tabletop exercises for breach response? ☐ Yes ☐ No

---

### SECTION F: PHYSICAL SECURITY (5 questions)

F1. Is physical access to facilities where MediGlobal data is processed controlled and logged? ☐ Yes ☐ No

F2. Are server rooms and data centers secured with multi-factor physical access controls? ☐ Yes ☐ No

F3. Are visitors required to sign in and be escorted in areas where PHI is processed? ☐ Yes ☐ No

F4. Are clean desk policies enforced (no PHI left unattended)? ☐ Yes ☐ No

F5. Is physical media (hard drives, USB drives) containing PHI destroyed using NIST 800-88 standards? ☐ Yes ☐ No

---

### SECTION G: CLOUD AND THIRD-PARTY (7 questions)

G1. Is MediGlobal data processed or stored in a cloud environment? ☐ Yes ☐ No
   If yes, which provider(s): ☐ AWS ☐ Azure ☐ GCP ☐ Other: ___________
   Confirm data residency region: ___________________________

G2. Do you have a list of all sub-processors (fourth parties) that handle MediGlobal data? ☐ Yes ☐ No
   Provide the list as an attachment.

G3. Have all sub-processors who handle MediGlobal PHI signed BAAs with you? ☐ Yes ☐ No
   % sub-processors with signed BAAs: _______%

G4. Do you notify MediGlobal before adding new sub-processors? ☐ Yes ☐ No
   Notice period: _____ days

G5. Do you assess your sub-processors' security before engaging them? ☐ Yes ☐ No

G6. Is your cloud environment configured per CIS Benchmarks or equivalent? ☐ Yes ☐ No

G7. Do you have a Cloud Security Posture Management (CSPM) tool? ☐ Yes ☐ No
   Tool name: ___________________________

---

### VENDOR CERTIFICATION

I certify that the responses provided in this questionnaire are accurate and complete to the best of my knowledge. I understand that MediGlobal HealthTech Inc. may request supporting documentation for any of the above responses.

Name: ___________________________  
Title: ___________________________  
Signature: ___________________________  
Date: ___________________________  
Company: ___________________________

---

## TEMPLATE 4: SECURITY AWARENESS TRAINING ACKNOWLEDGMENT

**MEDIGLOBAL HEALTHTECH INC.**
**Annual Security Awareness Training Acknowledgment**

I, _________________________ [Employee Full Name], Employee ID: _____________, 
Department: _________________________, 

acknowledge that I have:

☐ Completed the MediGlobal Annual Security Awareness Training (Course ID: SAT-2026-01) on [DATE]

☐ Reviewed and understood the MediGlobal Information Security Policy (v3.2, effective January 1, 2026)

☐ Reviewed and understood the MediGlobal Acceptable Use Policy (v2.8, effective January 1, 2026)

☐ Reviewed and understood the MediGlobal HIPAA Privacy and Security Training

I understand and agree to the following:

1. **Minimum Necessary Access:** I will only access patient information necessary for my specific job duties, and no more.

2. **Credential Security:** I will not share my login credentials with any other person, including supervisors, IT staff, or contractors.

3. **PHI Handling:** I will handle Protected Health Information (PHI) in accordance with HIPAA regulations and MediGlobal policies.

4. **Device Security:** I will use only approved, encrypted MediGlobal devices for work tasks involving PHI. I will not store PHI on personal devices or unauthorized cloud storage (e.g., personal Google Drive, Dropbox, iCloud).

5. **Incident Reporting:** I will immediately report any suspected security incident, data breach, or policy violation to my manager AND the GRC team at GRC@mediglob.com or the security hotline: 1-800-555-SECURE.

6. **Phishing Awareness:** I understand that I must not click suspicious links, open unexpected email attachments, or provide credentials in response to emails, even if they appear to come from MediGlobal IT or management.

7. **Physical Security:** I will not leave PHI unattended, will lock my workstation when stepping away, and will challenge unknown individuals in secure areas.

8. **Policy Violations:** I understand that violations of MediGlobal security policies may result in disciplinary action up to and including termination of employment.

9. **Monitoring Acknowledgment:** I understand that MediGlobal may monitor all activity on company-owned systems, networks, and devices for security purposes. I have no expectation of privacy on company systems.

10. **Annual Obligation:** I understand that completing this training is required annually by March 31st. Failure to complete may result in system access restrictions.

**Employee Signature:** ___________________________  
**Date:** ___________________________  
**Manager Signature:** ___________________________  
**Date:** ___________________________

*Retain original in employee file. Copy to GRC team by March 31.*

---

## TEMPLATE 5: RISK ACCEPTANCE FORM

**MEDIGLOBAL HEALTHTECH INC. — RISK ACCEPTANCE FORM**
**Risk ID (ServiceNow):** ___________________________
**Date:** ___________________________

### Risk Description
**Risk Title:** ___________________________  
**Risk Category:** ___________________________  
**Risk Owner:** ___________________________  
**Risk Rating:** ☐ Critical (15–25) ☐ High (8–14) ☐ Medium (4–7) ☐ Low (1–3)  
**Inherent Risk Score:** _______ (Likelihood ___ × Impact ___)  
**Residual Risk Score (with compensating controls):** _______

**Description of the Risk:**
___________________________________________________________________

**Why Cannot Be Fully Mitigated:**
___________________________________________________________________

**Compensating Controls in Place:**
1. ___________________________
2. ___________________________
3. ___________________________

**Business Justification for Acceptance:**
___________________________________________________________________

### Risk Acceptance Period
- **Start Date:** ___________________________
- **End Date:** ___________________________ (maximum 12 months for High; 3 months for Critical)
- **Review Date:** ___________________________

### Impact of Not Accepting (Cost to Fully Mitigate)
**Estimated cost to fully remediate:** $________________________  
**Operational impact if remediated now:** ___________________________

### Approvals Required

| Risk Score | Approvals Required |
|-----------|-------------------|
| Low (1–3) | Risk Owner |
| Medium (4–7) | Risk Owner + GRC Director |
| High (8–14) | Risk Owner + GRC Director + CISO |
| Critical (15–25) | Risk Owner + CISO + CCO + CEO |

**Risk Owner:** _________________________ Date: _______  
**GRC Director:** _________________________ Date: _______  
**CISO (if High/Critical):** _________________________ Date: _______  
**CCO (if Critical):** _________________________ Date: _______  
**CEO (if Critical):** _________________________ Date: _______

*Note: Acceptance of a Critical risk without CEO/CCO sign-off is not permitted under MediGlobal Risk Management Policy Section 4.3.*

---

## TEMPLATE 6: VENDOR ONBOARDING SECURITY CHECKLIST

**MEDIGLOBAL HEALTHTECH INC. — VENDOR ONBOARDING CHECKLIST**
**Vendor Name:** ___________________________  
**Service Description:** ___________________________  
**Onboarding Date:** ___________________________  
**Vendor Tier:** ☐ Tier 1 ☐ Tier 2 ☐ Tier 3  
**PHI Access Required:** ☐ Yes ☐ No  
**GRC Reviewer:** ___________________________

---

### PRE-CONTRACT CHECKLIST

**Legal/Contractual:**
- [ ] Master Services Agreement (MSA) reviewed by Legal
- [ ] BAA signed (REQUIRED for any vendor with PHI access)
- [ ] Data Processing Agreement (DPA) signed (REQUIRED for EU data — GDPR)
- [ ] Non-Disclosure Agreement (NDA) in place
- [ ] Contract includes: liability caps, indemnification, audit rights, security requirements
- [ ] Sub-processor list obtained from vendor

**Security Assessment:**
- [ ] Vendor security questionnaire completed (see Template 3)
- [ ] Security questionnaire reviewed and risk-rated by GRC
- [ ] SOC 2 Type II report obtained and reviewed (Tier 1 required)
- [ ] Penetration test summary obtained (Tier 1 required if annual test was performed)
- [ ] ISO 27001 certificate verified, if applicable
- [ ] SecurityScorecard baseline score obtained: ____/100

**Risk Assessment:**
- [ ] Vendor entered in ServiceNow (vendor record created)
- [ ] Initial risk score assigned: ___________________________
- [ ] Tier classification confirmed and documented

---

### TECHNICAL ACCESS PROVISIONING

**Tier 1 (PHI access) Additional Requirements:**
- [ ] MFA enforced on all vendor accounts accessing MediGlobal systems
- [ ] Vendor access uses named accounts (no shared accounts)
- [ ] Access limited to minimum necessary systems/data
- [ ] Access scope documented: which systems, which data types, which patient populations
- [ ] Vendor accounts created in Okta with appropriate role/group assignment
- [ ] API integration: API key generated with least-privilege permissions; key stored in secrets manager
- [ ] IP allowlist (whitelist) configured for vendor's access
- [ ] Time-limited access: automatic expiration date set if applicable

**Monitoring Setup:**
- [ ] Vendor access logs flowing into Rapid7 SIEM
- [ ] SecurityScorecard continuous monitoring activated for this vendor
- [ ] ServiceNow alert configured for score drops below threshold

---

### ONGOING VENDOR MANAGEMENT

**Recurring Tasks (GRC Analyst to schedule in ServiceNow):**
- [ ] Annual reassessment scheduled: ___________________________
- [ ] BAA renewal reminder set: ___________________________
- [ ] Quarterly security score review in SecurityScorecard
- [ ] Vendor added to monthly Vendor Risk Meeting agenda (Tier 1 only)

**Offboarding Pre-Planning:**
- [ ] Data return/destruction procedure documented
- [ ] Contact list for emergency communications maintained

**Checklist Sign-off:**

GRC Analyst: _________________________ Date: _______  
Third-Party Risk Manager: _________________________ Date: _______  
IT Security (for technical access): _________________________ Date: _______  
Legal (BAA confirmed): _________________________ Date: _______

---

## TEMPLATE 7: GRC PROJECT KICKOFF INTAKE FORM

**MEDIGLOBAL HEALTHTECH INC. — GRC PROJECT INTAKE**
**Project Name:** ___________________________  
**Requestor:** ___________________________ | Department: ___________________________  
**Date Submitted:** ___________________________

---

**What type of GRC support is needed?**
☐ Risk Assessment | ☐ Policy Development | ☐ Compliance Gap Assessment  
☐ Vendor Assessment | ☐ Audit Support | ☐ Incident Response Support  
☐ New Technology Review | ☐ Other: ___________________________

**Business Objective:**
___________________________________________________________________

**Data Types Involved:**
☐ PHI | ☐ PII | ☐ Financial | ☐ Intellectual Property | ☐ Public | ☐ None

**Systems Involved:**
___________________________________________________________________

**Regulatory Requirements (check all that apply):**
☐ HIPAA | ☐ GDPR | ☐ SOX | ☐ ISO 27001 | ☐ State Law | ☐ Other: ___

**Requested Completion Date:** ___________________________  
**Priority:** ☐ Critical ☐ High ☐ Medium ☐ Low  

**Budget Available:** $________________________

**Key Stakeholders:**
| Name | Role | Department | Availability |
|------|------|-----------|-------------|
| | | | |

**GRC Lead Assigned:** ___________________________  
**Estimated Hours:** ___________________________

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2024-01-15 | GRC Program Director | Initial templates |
| 1.5 | 2024-07-01 | GRC Team | Added vendor onboarding checklist |
| 2.0 | 2025-06-15 | GRC Program Director | Added Log4j questions to vendor questionnaire post-incident |
| 2.1 | 2026-01-10 | GRC Analyst | Updated BAA notification language to 1-hour requirement |

---
*End of GRC Templates Collection — MediGlobal HealthTech Inc.*
*These templates are living documents — update them after every incident and every audit finding.*
