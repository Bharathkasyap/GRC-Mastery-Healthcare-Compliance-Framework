# 05_GRC_TOOLS_INTEGRATION — GRC Tools Deep Dive
# MediGlobal HealthTech Inc. | ServiceNow GRC + OneTrust + Archer + Supporting Tools

> **Document Owner:** GRC Technology Lead  
> **Last Updated:** Q1 2026  
> **Classification:** INTERNAL  
> **Purpose:** Technical guide for GRC analysts to use market-leading tools effectively

---

## OVERVIEW OF MEDIGLOBAL'S GRC TOOL STACK

MediGlobal HealthTech Inc. uses a layered GRC technology stack to manage its compliance program across 8 countries, 847 vendors, 15,000 employees, and 93 ISO 27001 controls.

| Tool | Primary Use | License Type | Cost/Year |
|------|------------|--------------|-----------|
| **ServiceNow GRC** | Risk management, policy management, audit management | Enterprise | $1.2M |
| **OneTrust** | Privacy management, vendor assessments, consent management | Enterprise | $380K |
| **Archer GRC** | Advanced risk quantification, board reporting | Enterprise | $290K |
| **Qualys** | Vulnerability management, compliance scanning | Enterprise | $220K |
| **SecurityScorecard** | Continuous vendor security monitoring | Enterprise | $95K |
| **Tenable.io** | Cloud security posture management | Enterprise | $180K |
| **Rapid7 InsightIDR** | SIEM + incident detection | Enterprise | $310K |
| **Splunk UBA** | User behavior analytics (insider threat) | Enterprise | $260K |
| **Okta** | Identity and access management | Enterprise | $450K |
| **CrowdStrike Falcon** | Endpoint detection and response | Enterprise | $380K |

---

## PART 1: SERVICENOW GRC — COMPREHENSIVE GUIDE

### What is ServiceNow GRC?

ServiceNow GRC (Governance, Risk, and Compliance) is a cloud-based platform that centralizes risk management, policy management, audit management, and compliance activities in a single system. It is one of the most widely used GRC platforms in healthcare and financial services.

**Key Modules in ServiceNow GRC:**
- **Policy and Compliance Management** — Create, manage, and track policies
- **Risk Management** — Risk register, risk assessments, risk monitoring
- **Audit Management** — Internal and external audit planning, evidence collection
- **Issue Management** — Track findings and remediation
- **Vendor Risk Management** — Third-party assessments, BAA tracking
- **Business Continuity Management** — BCP/DR planning

---

### 1.1 ServiceNow GRC — POLICY AND COMPLIANCE MODULE

#### Setting Up a Policy in ServiceNow

**Navigation:** GRC > Policy and Compliance > Policies

**Step-by-step at MediGlobal:**

1. **Create a Policy Record**
   - Go to Policy and Compliance > Policies > New
   - Fields to complete:
     - Name: "HIPAA Minimum Necessary Policy"
     - Owner: CCO — Sarah Patel
     - Effective Date: 2025-01-01
     - Review Date: 2026-01-01
     - Status: Published
     - Regulation: HIPAA 45 CFR 164.502(b)
     - ISO 27001 Reference: A.8.3 (Information access restriction)

2. **Link Controls to the Policy**
   - In the Policy record, scroll to "Controls" related list
   - Add Control: "EHR Access Review — Quarterly"
   - Add Control: "Minimum Necessary Access Training — Annual"
   - Add Control: "DLP Export Monitoring — Continuous"

3. **Assign Policy Attestation**
   - Go to Policy Attestation > Create Campaign
   - Select Policy: HIPAA Minimum Necessary Policy
   - Audience: All employees with EHR access (15,000 employees minus IT staff = ~12,000)
   - Frequency: Annual
   - Due Date: March 31 (fiscal year deadline)
   - Escalation: Auto-escalate to manager if not completed within 14 days

**Screenshot Description:**
*[ServiceNow Policy Record Screen — Shows policy name, owner, status (Published), linked controls, and attestation campaign. The left navigation panel shows GRC > Policy and Compliance. The policy list shows 47 active policies with compliance percentages.]*

**GRC Analyst Effectiveness Tips:**
- Always link policies to specific regulatory requirements (45 CFR references, ISO control numbers) — this creates automatic audit evidence
- Set review reminders 90 days before policy expiration — gives time to review without rushing
- Use ServiceNow's "Policy Exception" workflow for any deviations — document them so auditors see controlled exceptions, not hidden violations
- Run the "Policy Compliance Dashboard" weekly to identify employees who haven't attested

---

#### Control Testing in ServiceNow

**Navigation:** GRC > Policy and Compliance > Controls

**What MediGlobal tests (sample):**

| Control ID | Control Name | Testing Frequency | Evidence Type |
|-----------|--------------|-------------------|--------------|
| CTL-001 | Multi-Factor Authentication | Monthly | Screenshot of MFA enrollment report from Okta |
| CTL-002 | Quarterly Access Review | Quarterly | Access review sign-off from department heads |
| CTL-003 | Backup Verification Test | Monthly | Backup success report from Veeam |
| CTL-004 | Security Awareness Training | Annual | LMS completion report (98.3% completion) |
| CTL-005 | Penetration Test | Bi-annual | External pentest report from Bishop Fox |
| CTL-006 | Vendor BAA on File | Continuous | ServiceNow vendor record — BAA attachment |

**Control Testing Workflow in ServiceNow:**
1. Open Control Test record
2. Select testing period
3. Upload evidence files (drag-and-drop into Evidence field)
4. Set test result: Effective / Partially Effective / Ineffective
5. If Ineffective: create Issue record automatically (linked to control)
6. Submit for reviewer approval
7. Reviewer approves → Control test record moves to "Closed — Pass/Fail"

**Screenshot Description:**
*[ServiceNow Control Testing Screen — Shows control "Multi-Factor Authentication" with test status "In Progress," evidence attachment area, and test result dropdown showing "Effective." A timeline shows the last 4 testing periods with green/red status indicators.]*

---

### 1.2 ServiceNow GRC — RISK MANAGEMENT MODULE

**Navigation:** GRC > Risk Management > Risks

#### Risk Register Management

**MediGlobal's Risk Register Configuration:**

**Risk Rating Matrix (5x5):**
| | Very Low (1) | Low (2) | Medium (3) | High (4) | Very High (5) |
|---|---|---|---|---|---|
| **Very High (5)** | 5 | 10 | 15 | 20 | 25 |
| **High (4)** | 4 | 8 | 12 | 16 | 20 |
| **Medium (3)** | 3 | 6 | 9 | 12 | 15 |
| **Low (2)** | 2 | 4 | 6 | 8 | 10 |
| **Very Low (1)** | 1 | 2 | 3 | 4 | 5 |

Scores 15–25 = Critical | 8–14 = High | 4–7 = Medium | 1–3 = Low

**Creating a Risk Record:**

1. **GRC > Risk Management > Risks > New**
2. Complete fields:
   - Risk Title: "Third-Party Vendor PHI Breach via API Integration"
   - Risk Category: Information Security
   - Risk Owner: Third-Party Risk Manager (Priya Krishnamurthy)
   - Likelihood: 3 (Medium — occurred once in 2025)
   - Impact: 5 (Very High — PHI breach affects 2.3M patient population)
   - Inherent Risk Score: 15 (Critical)
   - Controls in place: Vendor assessments, BAA, API monitoring
   - Residual Risk Score: 9 (High — even with controls, risk remains elevated)
   - Risk Response: Mitigate
   - Treatment plan: Deploy SecurityScorecard, annual pen testing for Tier-1 vendors

3. **Link to Control Deficiencies:**
   - Link to CTL-006 (Vendor BAA on File) — 86.3% compliance, gaps exist
   - Link to CTL-NEW (Vendor Continuous Monitoring) — newly implemented post-breach

4. **Set Review Cadence:**
   - Quarterly review for Critical risks
   - Monthly review for High risks
   - ServiceNow will auto-create review tasks and assign to Risk Owner

**Screenshot Description:**
*[ServiceNow Risk Detail Screen — Shows risk "Third-Party Vendor PHI Breach via API Integration" with a heat map visualization in the top right showing a red dot at position (3,5). The risk timeline shows Inherent: 15 (Critical) → Residual: 9 (High) after controls. Related controls and issues listed at the bottom.]*

**Risk Dashboard KPIs (visible in ServiceNow Risk Dashboard):**
- Total risks: 287 (23 Critical, 89 High, 118 Medium, 57 Low)
- Risks past due for review: 7 (flagged in red)
- New risks added this quarter: 14
- Risks closed this quarter: 8
- Average time to remediate High risks: 47 days (target: 30 days)

**GRC Analyst Effectiveness Tips:**
- Use ServiceNow's Monte Carlo simulation for quantifying financial risk impact — much more convincing to the board than "High/Medium/Low" labels
- Set up automated alerts: any risk that changes from Medium to High sends an email to the Risk Owner and GRC Director
- The Risk Register is your single source of truth — everything must be in ServiceNow, not in Excel spreadsheets. If an auditor asks "where's your risk register?" and you point to a spreadsheet, that's a finding.
- Link every risk to at least one control — risks without controls will be flagged in an ISO 27001 audit

---

### 1.3 ServiceNow GRC — AUDIT MANAGEMENT MODULE

**Navigation:** GRC > Audit Management > Engagements

#### ISO 27001 Internal Audit Workflow at MediGlobal

**Annual Internal Audit Schedule:**
- January: Audit planning and scoping
- February–April: Evidence collection and control testing
- May: Audit interviews with control owners
- June: Draft audit report
- July: Management responses
- August: Final audit report issued

**Creating an Audit Engagement in ServiceNow:**

1. **GRC > Audit Management > Engagements > New**
2. Fields:
   - Engagement Type: Internal Audit
   - Scope: ISO 27001:2022 — All 93 Controls
   - Audit Period: January 1 – December 31, 2025
   - Lead Auditor: Director of Internal Audit
   - Audit Team: 3 internal GRC analysts + 1 external advisor (KPMG)

3. **Create Control Test Plans:**
   - ServiceNow auto-generates test plans for all controls linked to the audit scope
   - Each test plan includes: test procedure, evidence required, responsible party, due date
   - MediGlobal: 93 controls × 1.3 tests each = ~121 control tests

4. **Evidence Collection:**
   - Assign each test to the appropriate GRC analyst
   - Each analyst uploads evidence to their assigned test records
   - Evidence review queue managed by Lead Auditor

5. **Issue Management:**
   - Deficiencies automatically create Issue records
   - Issues have: finding title, severity (Critical/High/Medium/Low), root cause, recommendation, management response, remediation owner, due date
   - Issues linked back to controls, risks, and regulatory requirements

**Screenshot Description:**
*[ServiceNow Audit Engagement Dashboard — Shows the ISO 27001 2025 Internal Audit with a progress bar at 67% complete. A Gantt chart shows audit phases. The control test summary shows: 82 tests complete, 39 in progress, 0 not started. Issues created: 12 (2 High, 7 Medium, 3 Low).]*

**GRC Analyst Effectiveness Tips:**
- Start the audit engagement in ServiceNow 3 months before fieldwork begins — this gives time to populate test plans, assign owners, and collect preliminary evidence
- Use ServiceNow's "Request for Information" (RFI) feature to formally request evidence from business units — creates a documented request trail
- When an auditor finds a deficiency, open the Issue in ServiceNow immediately and tag the relevant control owner — don't wait until the end of fieldwork
- The audit report should directly reference ServiceNow Issue IDs — auditors love seeing a systematic, traceable process

---

### 1.4 ServiceNow GRC — VENDOR RISK MANAGEMENT MODULE

**Navigation:** GRC > Vendor Risk Management > Vendors

#### MediGlobal's Vendor Assessment Workflow

**Vendor Tiers in ServiceNow:**
- **Tier 1 (Critical):** 147 vendors — access to PHI, critical systems. Annual full assessment.
- **Tier 2 (Standard):** 350 vendors — limited data access. Bi-annual abbreviated assessment.
- **Tier 3 (Low):** 350 vendors — no sensitive data. 3-year assessment cycle.

**Tier-1 Vendor Assessment Process:**

1. **Create Vendor Assessment Record:**
   - GRC > Vendor Risk Management > Assessments > New
   - Vendor: MedSync Solutions LLC
   - Assessment Type: Tier-1 Annual Assessment
   - Questionnaire: MediGlobal TPRM Questionnaire v4.2 (ISO 27001 + HIPAA aligned)
   - Due Date: 30 days from send date

2. **Send Questionnaire to Vendor:**
   - ServiceNow sends automated email to vendor contact
   - Vendor accesses a secure portal to complete the questionnaire
   - Questionnaire includes 127 questions across 12 domains:
     - Access Control (ISO A.5.15, HIPAA 164.308(a)(3))
     - Vulnerability Management (ISO A.8.8)
     - Incident Response (ISO A.5.26, HIPAA 164.308(a)(6))
     - Business Continuity (ISO A.5.30)
     - Data Protection (ISO A.8.11, HIPAA 164.312(a)(2)(iv))
     - Physical Security (ISO A.7.1–A.7.14)
     - Encryption (HIPAA 164.312(a)(2)(iv))
     - Patch Management (ISO A.8.8) ← **Added post-MedSync breach**
     - Java/Log4j CVE status ← **Added post-MedSync breach**
     - Third-party sub-processors
     - SOC 2 Type II report availability
     - Penetration test results

3. **Score and Rate the Assessment:**
   - ServiceNow auto-scores responses using pre-defined risk weights
   - Each question has a risk weight (1–5) based on criticality
   - Total score generates a risk rating: Low/Medium/High/Critical
   - GRC analyst reviews auto-score and can adjust with justification

4. **Generate Risk Findings:**
   - Findings automatically create Issues linked to the vendor record
   - Each finding has: severity, recommendation, remediation deadline
   - Vendors can submit remediation evidence directly through the portal

**Screenshot Description:**
*[ServiceNow Vendor Assessment Portal — Shows MedSync Solutions LLC assessment at 87% complete. The questionnaire section "Vulnerability Management" shows question "List all Java-based middleware applications and confirm Log4j2 CVE status" with status OPEN (red). The vendor's previous responses appear on the left for comparison.]*

**BAA Tracking in ServiceNow:**
- Every vendor with PHI access has a BAA record in ServiceNow
- BAA fields: vendor name, effective date, expiration date, key contact, PHI types, sub-processor list
- ServiceNow sends automated reminders 90 days, 60 days, 30 days before BAA expiration
- Current status at MediGlobal: 731/847 BAAs current | 23 overdue | 93 new vendors in process

---

### 1.5 ServiceNow GRC — INCIDENT MANAGEMENT MODULE

**Navigation:** Incident > All Incidents (or IRM Incidents for GRC team)

**Incident Record Key Fields (GRC-relevant):**
- Incident Number (e.g., INC-2025-0047)
- Category: Data Breach / Security Incident / Vendor Incident / Insider Threat
- Severity: P1/P2/P3/P4
- HIPAA Breach Indicator: Yes/No/TBD
- HIPAA 60-Day Deadline: Auto-calculated from "Date of Discovery"
- Notification Status: Not Required / Required — Not Yet Sent / Sent — OCR Confirmed
- Evidence Log: Attachment list with hash values
- Investigation Team: Access-restricted field

**HIPAA Clock Tracking:**
ServiceNow automatically calculates:
- Day 0: Date of Discovery = June 3, 2025
- Day 60: August 2, 2025 (notification deadline — highlighted in red when T-14 days)
- Day 45: Warning notification sent to GRC Director and Privacy Officer
- Day 55: Escalation to CISO if notification not yet sent

**GRC Analyst Effectiveness Tips:**
- Open the IRM incident record within 30 minutes of a P1 declaration — not after the war room call
- Set the access restriction on sensitive incidents (insider threats, investigations) before entering any details
- Use ServiceNow's "Legal Hold" flag — when toggled, the incident record is frozen from any deletion and flagged for records retention
- The incident timeline in ServiceNow is your legal document — every action, every decision, every communication should be logged with exact timestamps

---

## PART 2: ONETRUST — PRIVACY AND VENDOR RISK PLATFORM

### What is OneTrust?

OneTrust is a privacy, security, and data governance platform used for HIPAA/GDPR compliance, vendor due diligence, consent management, and privacy program management. MediGlobal uses OneTrust alongside ServiceNow (ServiceNow handles internal GRC; OneTrust handles privacy-specific workflows and vendor portals).

### 2.1 OneTrust — PRIVACY IMPACT ASSESSMENTS (PIAs)

**When to Use:** Any new technology, vendor, or process that involves PHI/PII requires a PIA at MediGlobal.

**PIA Workflow in OneTrust:**

1. **Request Intake:**
   - Business unit submits a "New Technology/Process Request" form in OneTrust
   - Form triggers a Privacy Officer review
   - Privacy Officer determines: Full PIA required / Abbreviated / No PIA needed

2. **Full PIA Process:**
   - OneTrust auto-generates PIA questionnaire based on data type detected
   - Sections: Data inventory, data flows, legal basis for processing, data subject rights, security controls, retention, international transfers
   - HIPAA-specific section: Minimum necessary analysis, PHI types, access controls
   - ISO 27001 section: Control mapping, security requirements

3. **PIA Risk Scoring:**
   - OneTrust auto-scores and flags high-risk data processing activities
   - High-risk triggers: Children's data, sensitive health data, international transfers, automated decision-making

4. **Approval Workflow:**
   - Privacy Officer review
   - Legal review (if international transfers or new data types)
   - CISO sign-off (if new security controls required)
   - CCO final approval

**Screenshot Description:**
*[OneTrust PIA Dashboard — Shows a list of 47 active PIAs. The "Telehealth Platform Expansion — 16 New Vendors" PIA is highlighted with a Risk Score of 78/100 (High). The workflow shows 3 of 5 approvals complete. A data flow diagram on the right shows patient data flowing from MediGlobal Epic EHR → Telehealth Platform → Cloud Storage (AWS us-east-1).]*

**GRC Analyst Tips for OneTrust PIAs:**
- Complete a PIA before the vendor contract is signed — if a PIA reveals unacceptable risks, you need leverage to negotiate security requirements or reject the vendor
- Data flow diagrams in OneTrust are your GDPR Article 30 Records of Processing Activities — keep them updated
- For HIPAA: the PIA should confirm whether a BAA is required (any vendor who "creates, receives, maintains, or transmits" PHI is a business associate)

---

### 2.2 OneTrust — VENDOR RISK ASSESSMENTS

OneTrust's vendor portal allows vendors to complete security questionnaires directly. MediGlobal uses both ServiceNow (for internal risk scoring) and OneTrust (for vendor-facing questionnaires and communication).

**Vendor Assessment Configuration:**
- Questionnaire template: CAIQ (Cloud Assessment Initiative Questionnaire) + MediGlobal custom HIPAA questions
- Vendor receives a branded portal link
- OneTrust tracks completion, sends reminders, and flags incomplete sections
- Completed assessments are synced to ServiceNow for centralized risk scoring

**OneTrust Vendor Monitoring:**
- Continuous monitoring integration with SecurityScorecard
- Daily risk score updates for all Tier-1 vendors
- Automated alert when vendor risk score drops by >10 points in 30 days
- MediGlobal uses this to catch vendor security deterioration between annual formal assessments

**Screenshot Description:**
*[OneTrust Vendor Risk Portal — Shows MedSync Solutions LLC profile with an overall risk score of 68/100 (previously 74/100 before the breach incident). The SecurityScorecard integration shows a live score of 71/100 with a downward trend arrow. The "Vulnerability Management" category is flagged in red at 52/100. A timeline shows score drops over the past 6 months.]*

---

### 2.3 OneTrust — CONSENT MANAGEMENT (HIPAA Authorization + GDPR)

**At MediGlobal:** OneTrust manages the patient consent/authorization tracking across 2.3 million patients.

**Key Functions:**
- Track HIPAA authorizations for research data uses
- Manage patient opt-outs from marketing communications
- GDPR consent records for EU patients (EMEA operations)
- Cookie consent management for all 8 country websites

**For GRC Analysts:**
- Consent records in OneTrust serve as evidence in HIPAA audits
- Run "Consent Audit Report" monthly — flag any patients whose data was used without valid authorization
- Integrate OneTrust consent data with Epic EHR — ensure Epic records reflect current consent status

---

## PART 3: ARCHER GRC — ADVANCED RISK QUANTIFICATION

### What is Archer GRC?

Archer is an enterprise risk management platform known for its advanced quantitative risk analysis capabilities. MediGlobal uses Archer for board-level risk reporting, financial risk quantification, and strategic risk modeling.

### 3.1 Archer — FAIR RISK QUANTIFICATION

**FAIR = Factor Analysis of Information Risk** — an international standard for quantifying cyber risk in financial terms.

**Using Archer to Quantify a Risk (Example: Ransomware Attack):**

1. **Enter Risk Scenario:**
   - Threat community: Criminal/organized cybercrime
   - Threat capability: Intermediate (3/5)
   - Asset at risk: Clinical EHR systems (42 hospitals)
   - Asset value: $420M revenue dependent on EHR uptime

2. **FAIR Inputs:**
   - Threat Event Frequency: 15% annual probability (1-in-7 years)
   - Vulnerability: 45% (probability that attack succeeds given attempt)
   - Primary Loss: $8.5M (direct cost: ransom + recovery + forensics)
   - Secondary Loss: $22M (regulatory fines, reputational damage, litigation)

3. **Archer Monte Carlo Output:**
   - Minimum annual loss: $1.2M
   - Maximum annual loss: $47M
   - Most likely annual loss: $9.4M
   - 90th percentile: $31M
   - **Recommended control investment:** Up to $9.4M/year to be cost-justified

**Screenshot Description:**
*[Archer FAIR Analysis Screen — Shows the risk scenario "Ransomware Attack — MediGlobal EHR Systems" with a bell curve loss distribution. The x-axis shows loss in millions ($0 to $50M). The curve peaks at $9.4M. A comparison shows current security controls reducing the peak from $23M (without MFA, EDR) to $9.4M (with current controls). The ROI calculator shows a return of 3.1x for the current security investment.]*

**Why This Matters for GRC:**
- Board members understand dollars, not "High/Medium/Low" risk ratings
- "Our ransomware risk is $9.4M expected annual loss" is actionable; "ransomware risk is High" is not
- FAIR analysis justifies the $8.5M security budget: the expected loss prevention far exceeds the prevention cost

### 3.2 Archer — STRATEGIC RISK REGISTER

Archer maintains MediGlobal's top 25 enterprise risks (distinct from the ServiceNow operational risk register). These are the risks the Board Audit Committee reviews quarterly.

**Top 5 Enterprise Risks (Q1 2026):**

| # | Risk | Likelihood | Impact | Score | Financial Exposure |
|---|------|-----------|--------|-------|-------------------|
| 1 | EHR system ransomware attack | Medium | Critical | 15 | $9.4M expected annual loss |
| 2 | Third-party vendor PHI breach | Medium | Very High | 12 | $3.7M expected annual loss |
| 3 | HIPAA OCR enforcement action | Low | Very High | 10 | $2.1M expected annual loss |
| 4 | Insider threat — PHI exfiltration | Medium | High | 9 | $2.3M expected annual loss |
| 5 | Cloud misconfiguration → data exposure | Medium | High | 9 | $1.8M expected annual loss |

---

## PART 4: SUPPORTING TOOLS — QUICK REFERENCE

### 4.1 SecurityScorecard — Continuous Vendor Monitoring

**What it does:** Continuously monitors vendors' external-facing security posture by scanning public internet for security signals (open ports, SSL certificate issues, vulnerability exposure, dark web presence, phishing domains, patching cadence).

**MediGlobal Configuration:**
- All 147 Tier-1 vendors enrolled
- Daily score updates
- Alert threshold: Score drops below 70 OR drops by 10+ points in 30 days
- Integration: SecurityScorecard API feeds into ServiceNow vendor records

**Score Interpretation:**
- 90–100: Low Risk | 80–89: Low-Medium Risk | 70–79: Medium Risk
- 60–69: Medium-High Risk | 50–59: High Risk | Below 50: Critical Risk

**For GRC Analysts:**
- Check SecurityScorecard weekly for all Tier-1 vendors
- Any vendor dropping below 70: trigger an out-of-cycle assessment in ServiceNow
- Include SecurityScorecard scores in vendor review meeting agenda
- Document score trends in ServiceNow vendor record

**Screenshot Description:**
*[SecurityScorecard Dashboard — Shows a portfolio view of MediGlobal's 147 Tier-1 vendors. Overall portfolio score: 76/100 (Grade B). 12 vendors shown in red (score below 70). A vendor named "BioMed Lab Solutions" is highlighted with a score drop from 82 to 61 in 30 days — the alert triggered an out-of-cycle ServiceNow assessment automatically.]*

---

### 4.2 Qualys — Vulnerability Management and Compliance Scanning

**What it does:** Scans MediGlobal's internal and cloud infrastructure for vulnerabilities, misconfigurations, and compliance deviations.

**MediGlobal Scan Configuration:**
- **Internal network:** Weekly scan of 9,200+ IP addresses across 42 hospitals and HQ
- **Cloud (AWS/Azure/GCP):** Daily cloud security posture scans
- **Compliance scans:** Monthly PCI-DSS, HIPAA, and CIS Benchmark scans
- **Scan authentication:** Credentialed scans for internal servers (deep scan)

**Integration with ServiceNow:**
- Qualys findings automatically create tickets in ServiceNow
- Critical vulnerabilities → P1 ServiceNow ticket → auto-assigned to IT Security
- SLAs: Critical = 72 hours | High = 30 days | Medium = 90 days

**For GRC Analysts:**
- Pull monthly Qualys compliance report for ISO 27001 A.8.8 (Vulnerability Management) evidence
- Track exception requests in ServiceNow for vulnerabilities that cannot be patched (medical devices, legacy systems)
- Include vulnerability management KPIs in GRC steering committee agenda

**Screenshot Description:**
*[Qualys VMDR Dashboard — Shows MediGlobal's vulnerability posture. Top section: 3 Critical (being remediated) | 47 High | 289 Medium | 1,247 Low. Below: A compliance heatmap showing HIPAA Technical Safeguard compliance at 94.7%. Network segment view shows the "Medical Device VLAN" with 17 vulnerabilities flagged (all in exception status due to EOL medical device OS).]*

---

### 4.3 Rapid7 InsightIDR — SIEM and Incident Detection

**What it does:** Collects, correlates, and analyzes log data from all MediGlobal systems to detect security incidents in real-time.

**MediGlobal Log Sources (ingested into Rapid7):**
- Epic EHR audit logs (all 42 hospitals — 2.3M patient record access events/day)
- Active Directory / Okta login events
- Firewall logs (Palo Alto)
- AWS CloudTrail, Azure Monitor, GCP Cloud Logging
- Qualys vulnerability feeds
- Endpoint events (CrowdStrike)
- Network flows (NetFlow from core switches)

**GRC-Relevant Rapid7 Use Cases:**
1. **Detecting anomalous EHR access** → Alerts for any user accessing >200 records/hour (insider threat detection)
2. **Failed authentication spikes** → Potential credential stuffing or brute force
3. **After-hours access from clinical systems** → Nurse accessing patient records at 2 AM from an unusual location
4. **DLP event correlation** → Rapid7 correlates USB insertions, large file copies, and email attachments

**For GRC Analysts:**
- Weekly review of Rapid7 compliance dashboard for HIPAA audit logging requirements (45 CFR 164.312(b))
- Monthly export of Rapid7 audit log report as ISO 27001 A.8.16 (Monitoring activities) control evidence
- Any unreviewed alerts that age past 72 hours are flagged as a control deficiency

---

### 4.4 Okta — Identity and Access Management

**What it does:** Manages all user authentication at MediGlobal — 15,000 employees, contractors, and vendors.

**MediGlobal Okta Configuration:**
- MFA enforcement: 100% of employees (target met Q2 2024 after MFA initiative)
- Adaptive MFA: Step-up authentication required for PHI access from non-corporate networks
- SSO: Okta provides single sign-on for 147 applications (Epic, ServiceNow, OneTrust, Workday, etc.)
- Privileged Access Management: Okta PAM for administrative accounts (separate vault)
- Lifecycle management: Okta provisioning/deprovisioning integrated with Workday HR system

**Access Review Process (Quarterly):**
1. Okta generates access report: all users, all roles, all applications
2. Each department manager reviews their team's access via Okta Access Review feature
3. Managers certify (approve/revoke) each access right
4. Uncertified access is automatically revoked after 14 days
5. GRC analyst reviews completion rate — target 100% before quarterly close

**For GRC Analysts:**
- Okta access review completion report = evidence for ISO 27001 A.8.2 (Privileged access rights) and A.8.3 (Information access restriction)
- HIPAA: Access review satisfies 45 CFR 164.308(a)(3)(ii)(B) — Workforce Clearance Procedures
- Export quarterly access review report to ServiceNow control test record

---

## PART 5: GRC TOOL INTEGRATION ARCHITECTURE

### How the Tools Work Together at MediGlobal

```
[Qualys Vulnerabilities] ──────────────────────┐
[Rapid7 SIEM Alerts] ──────────────────────────┤
[SecurityScorecard Vendor Scores] ─────────────┤──→ [ServiceNow GRC Hub]
[Okta Access Reviews] ─────────────────────────┤      (Risk Register,
[OneTrust Privacy Assessments] ────────────────┤       Audit Mgmt,
[CrowdStrike Endpoint Events] ─────────────────┘       Compliance)
                                                            │
                                                            ↓
                                                    [Archer — Board Reports
                                                     FAIR Risk Quantification]
                                                            │
                                                            ↓
                                                    [Board Audit Committee
                                                     Quarterly Reporting]
```

**Integration Benefits:**
- Single source of truth: All risks, issues, and findings in ServiceNow
- No manual copying between tools — API integrations auto-sync
- Complete audit trail: Auditors can see the entire evidence chain from vulnerability detection to remediation
- Real-time dashboards: GRC Director and CISO have live visibility into risk posture

---

## PART 6: INTERVIEW PREPARATION — GRC TOOLS QUESTIONS

**"What GRC tools have you used?"**
ServiceNow GRC for risk register, policy management, audit management, and vendor risk. OneTrust for privacy assessments, vendor portals, and GDPR consent management. Archer for financial risk quantification using FAIR methodology. Supporting tools: Qualys for vulnerability management, SecurityScorecard for continuous vendor monitoring, Okta for access management and quarterly access reviews.

**"How do you use ServiceNow for audit management?"**
Create an Audit Engagement → define scope → auto-generate control test plans → assign evidence collection to control owners → aggregate evidence → identify issues → issue management workflow → final report. The key is that everything is traceable in ServiceNow — auditors love that.

**"What is FAIR and have you used it?"**
FAIR is Factor Analysis of Information Risk — an international standard for quantifying cyber risk in financial terms. I've used it through Archer GRC to give board-level risk estimates in dollars rather than High/Medium/Low. For example, our ransomware risk was quantified as $9.4M expected annual loss, which directly justified the security budget ask.

**"How do you handle vendor risk management?"**
Tiered approach: 147 Tier-1 vendors get annual assessments + continuous SecurityScorecard monitoring. ServiceNow manages the assessment workflow, evidence, and BAA tracking. OneTrust manages the vendor portal communication. Any score drop below 70 or by 10+ points triggers an out-of-cycle review.

**"Walk me through a HIPAA audit evidence collection process."**
ServiceNow GRC Audit Engagement → create test plans for all HIPAA Technical Safeguard controls → assign to control owners (e.g., Okta team for access controls, IT Security for audit logs) → evidence uploaded to ServiceNow → GRC analyst reviews → issues created for gaps → management response → final audit report generated from ServiceNow.

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2024-03-01 | GRC Technology Lead | Initial creation |
| 1.5 | 2024-09-15 | GRC Team | Added OneTrust section |
| 2.0 | 2025-01-20 | GRC Technology Lead | Added SecurityScorecard post-breach |
| 2.1 | 2026-01-10 | GRC Analyst | Added Archer FAIR section, updated screenshots |

---
*End of GRC Tools Integration Guide — MediGlobal HealthTech Inc.*
