# 04_REAL_WORLD_SCENARIOS — Scenario 02: Insider Threat Investigation
# MediGlobal HealthTech Inc. | GRC Incident Case Study

> **Incident ID:** INC-2025-0089  
> **Incident Type:** Malicious Insider — Unauthorized PHI Access and Exfiltration  
> **Severity:** P1 — Critical  
> **Subject Employee:** Rachel Kim, RN — Clinical Data Analyst, Chicago Regional Hospital  
> **Date of Initial Detection:** June 3, 2025  
> **Date of Containment:** June 5, 2025  
> **GRC Author:** GRC Analyst II — Marcus Torres  
> **Document Classification:** CONFIDENTIAL — ATTORNEY-CLIENT PRIVILEGED — HR RESTRICTED

---

## EXECUTIVE SUMMARY

On June 3, 2025, MediGlobal HealthTech Inc.'s DLP (Data Loss Prevention) system flagged unusual bulk download activity from a Clinical Data Analyst in the Chicago Regional Hospital. Investigation revealed that Rachel Kim, RN, had over a 3-week period (May 12 – June 2, 2025) accessed and exfiltrated 14,287 patient records — far beyond her role-based access requirements. Evidence indicates the data was transferred to a personal Google Drive account. Rachel Kim was employed at MediGlobal and had simultaneously been interviewing with a competing healthcare analytics startup (DataHealth Ventures LLC), which was confirmed during investigation.

**Confirmed PHI Exfiltrated:** 14,287 patient records (names, DOBs, diagnoses, insurance IDs, contact information).  
**HIPAA Breach:** Yes — required. OCR notification filed.  
**Outcome:** Employee terminated. Criminal referral made to FBI Cyber Division. Civil litigation initiated. OCR investigation opened.

---

## COMPANY PROFILE & INSIDER CONTEXT

### MediGlobal HealthTech Inc. — Chicago Regional Hospital
- **Location:** Chicago, Illinois
- **Employees at site:** 2,200 (part of 15,000 total)
- **Patient population:** 340,000 active patients (regional)
- **EHR system:** Epic (Hyperspace)
- **DLP system:** Microsoft Purview Information Protection + Symantec DLP

### Employee Profile — Rachel Kim, RN
- **Title:** Clinical Data Analyst II
- **Department:** Quality Improvement & Clinical Analytics
- **Tenure:** 2.5 years (hired March 2023)
- **Access Level:** Standard (authorized to access patient records for quality review purposes — defined scope: patients with readmission risk flags, not all 340,000 patients)
- **Prior disciplinary issues:** None
- **Performance reviews:** Rated "Meets Expectations" (no red flags)
- **Investigation finding:** Accessed 14,287 patient records (her authorized scope: approximately 400 patients in active QI review panels)

---

## INCIDENT TIMELINE

### Background: May 12–June 2, 2025 (Exfiltration Period — Unknown at the Time)

**[May 12, 14:32]** Rachel Kim begins accessing patient records beyond her normal QI review panel. Uses Epic "Reporting Workbench" to run ad-hoc patient lists — a feature available to her role but rarely used for bulk exports. These queries are logged but not immediately reviewed.

**[May 12–June 2]** Over 22 working days, Kim exports 14,287 patient records in batches of 500–1,000 records per session. Exports include: name, DOB, address, phone, insurance ID, primary diagnosis, recent visit dates.

**[Multiple dates]** Kim uploads exported CSV files to personal Google Drive account (personal.rkim.data@gmail.com) from her MediGlobal laptop using a personal browser session (Google Chrome, not managed browser). MediGlobal's DLP was configured to monitor managed browsers but had a gap for personal browser sessions on managed devices.

**[June 1]** MediGlobal HR receives an anonymous tip (via EthicsPoint hotline) that "a nurse in Clinical Analytics has been downloading a lot of patient data and seems to be taking it somewhere." Tip is logged and routed to HR and Legal — not yet to Security.

**[June 2]** HR reviews the EthicsPoint tip and escalates to Legal. Legal escalates to CISO at 5:47 PM.

---

### Day 1 — June 3, 2025 (Detection & Containment)

**[06:15]** SOC receives automated DLP alert (triggered retrospectively by pattern analysis run overnight): "Unusual bulk export activity detected — user r.kim@mediglob.com — 47 export events in 22 days — volume 10x above role baseline."

**[07:30]** SOC Manager reviews alert in context of previous day's HR escalation. Immediately escalates to CISO.

**[08:00]** CISO activates insider threat response protocol (ITP-03). Incident Response team convened.

**[08:15]** Key decision: **Do NOT alert the employee yet.** Preserve evidence integrity. Continue monitoring covertly per legal authorization for 24 hours.

**[08:20]** Legal invokes attorney-client privilege on all investigation activities.

**[08:30]** HR Director, Legal Counsel, CISO, Privacy Officer, GRC Director in secure briefing room. Investigation team established. Strict need-to-know access to investigation information.

**[09:00]** IT Security begins forensic imaging of Rachel Kim's MediGlobal-issued laptop (remote forensic agent deployed without alerting employee). Physical imaging of laptop deferred to preserve covert investigation.

**[09:30]** GRC Analyst Marcus Torres opens ServiceNow INC-2025-0089 (access restricted to investigation team only).

**[10:00]** DLP analysis team pulls all export activity logs for r.kim@mediglob.com for past 90 days. Confirms 47 export events, totaling 14,287 unique patient record exports.

**[11:00]** Epic audit trail pulled — confirms Kim accessed records using Reporting Workbench feature. All accesses were authenticated (her credentials, her workstation).

**[11:30]** IT confirms: Chrome browser history (from remote forensic agent) shows uploads to Google Drive on 19 separate dates.

**[12:00]** Privacy Officer begins HIPAA minimum necessary analysis: Kim's job duties required access to approximately 400 patients. 14,287 accesses are 35x her authorized scope — "minimum necessary" principle (45 CFR 164.502(b)) clearly violated.

**[14:00]** Legal confirms: This meets the HIPAA definition of a breach. Attorney-client privilege maintained. HIPAA 60-day clock starts.

**[14:30]** Decision: Terminate employment tomorrow (June 4) after completing initial forensic preservation. Do not alert employee today.

**[16:00]** IT Security sends Google LLC a preservation request (under 18 U.S.C. § 2703(f)) for all content uploaded to personal.rkim.data@gmail.com. Google complies with preservation within 24 hours.

**[17:30]** FBI Cyber Division notified (pre-notification only — formal referral pending additional evidence). FBI cyber coordinator assigned to case.

---

### Day 2 — June 4, 2025 (Termination & Physical Evidence Collection)

**[08:00]** Rachel Kim arrives at work. She is met by HR Director and Legal Counsel in a private conference room.

**[08:15]** Employee notified of termination for "violation of MediGlobal Acceptable Use Policy and HIPAA workforce standards." No mention of criminal investigation yet (per Legal's guidance to not disclose investigation specifics).

**[08:20]** Employee access revoked (all systems simultaneously): Epic EHR, email, VPN, building access, ServiceNow.

**[08:25]** IT Security takes possession of laptop. Employee personal items allowed to be collected under HR escort.

**[08:30]** Kim asks about the reason. HR Director states: "unauthorized system access." Kim becomes agitated, states "I didn't do anything wrong" and asks to speak with a lawyer. HR Director states she is free to consult counsel and escorts her out.

**[09:00]** IT Security begins full forensic imaging of laptop (now safe to do physical imaging with device in custody).

**[10:00]** Chain of custody documentation started: laptop serial number, imaging hash (SHA-256), date/time, IT forensic analyst name (David Chen).

**[11:00]** Epic HR team (separate from IT) reviews Kim's job offer at DataHealth Ventures LLC — confirmed through LinkedIn activity and a DLP-flagged email attachment ("Resume_Rachel_Kim_DataHealth.docx" — sent from personal email using managed browser two weeks prior).

**[14:00]** Forensic imaging complete. Evidence preserved for law enforcement.

**[15:00]** Formal criminal referral submitted to FBI Cyber Division.

---

### Day 3 — June 5, 2025 (HIPAA Breach Assessment Finalization)

**[09:00]** GRC and Privacy team finalizes breach scope: 14,287 unique patient records confirmed exfiltrated.

**[10:00]** Privacy Officer completes HIPAA breach risk assessment under 45 CFR 164.402(2): probability of PHI compromise is HIGH. Notification required.

**[11:00]** Preliminary OCR notification strategy approved by Legal:
- Individual patient notifications (14,287 patients)
- OCR Breach Portal notification (>500 threshold met)
- Illinois AG notification (state breach law)

**[14:00]** External patient notification vendor engaged (Epiq — specializes in mass healthcare notification).

**[16:00]** Internal investigation report (preliminary) drafted. Distribution: CEO, CISO, CCO, Legal only.

---

## HIPAA BREACH NOTIFICATION PROCESS

### Breach Risk Assessment (45 CFR 164.402(2))

| Factor | Analysis |
|--------|---------|
| Nature and extent of PHI involved | Names, DOB, address, phone, insurance ID, diagnoses — HIGH sensitivity |
| Who accessed/used the PHI | Internal employee with specific malicious intent — HIGH probability of use |
| Whether PHI was actually acquired/viewed | YES — confirmed download and upload to personal storage |
| Extent to which risk has been mitigated | Partial — Google preservation request issued, but data in Kim's possession unknown |
| **Breach determination** | **BREACH CONFIRMED — Notification required** |

### Notification Actions

| Action | Deadline | Completed | Status |
|--------|---------|-----------|--------|
| HIPAA breach determination | N/A | June 5, 2025 | ✅ |
| Individual notifications (14,287 patients) | August 2, 2025 (60 days) | July 18, 2025 | ✅ |
| OCR Breach Portal submission | August 2, 2025 | July 30, 2025 | ✅ |
| Illinois AG notification | 30 days (July 3) | June 28, 2025 | ✅ |
| Media notification (Illinois state law) | 30 days (July 3) | June 28, 2025 | ✅ |

---

## GRC ANALYST DAY-TO-DAY WORK DURING INSIDER THREAT INVESTIGATION

### Day 1 (June 3): Immediate Actions
**What the GRC analyst actually does:**

1. **Open restricted ServiceNow ticket immediately** — Set access control to investigation team only (CISO, Legal, HR Director, Privacy Officer, GRC Director). No one else can view this ticket.

2. **Start the HIPAA 60-day clock** — Create a calendar reminder (in ServiceNow AND personal calendar) for August 2 — that is the hard deadline for everything.

3. **Document the investigation team members** — Every person with knowledge of the investigation must be documented. This is critical for attorney-client privilege and to prevent accidental disclosure.

4. **Pull and preserve DLP logs** — Export all DLP alert data to the evidence server. Hash each file.

5. **Pull and preserve Epic audit logs** — Epic retains 7 years of access logs. Export the specific user's access log for the investigation period. Hash the files.

6. **Brief Privacy Officer** — They need to run the HIPAA minimum necessary analysis. Provide them the job description and the Epic access logs.

7. **Do NOT send any emails about this** — All investigation communications are verbal or through the attorney-client privileged channel (Legal's email). Standard email is discoverable.

### Days 2–5: Evidence Management

**Evidence Log Maintenance (must be done for every item):**
- Item description (e.g., "Epic audit log — r.kim@mediglob.com — May 1 to June 3, 2025")
- Date/time collected
- Who collected it
- MD5 and SHA-256 hash values
- Storage location (secure evidence share with access logging)
- Who has accessed it since collection (maintain access log)

**Why This Matters:**
When the FBI opens an investigation and your evidence doesn't have a clear chain of custody, law enforcement cannot use it. When OCR investigates, your documentation becomes your defense. When litigation starts, your evidence is your case.

### Days 5–14: Notification Preparation

**Patient Notification Letter Content Requirements (45 CFR 164.404(c)):**
1. A brief description of what happened, including dates
2. Description of PHI involved
3. Steps individuals should take to protect themselves
4. What MediGlobal is doing to investigate and prevent future breaches
5. Contact information for questions (dedicated hotline: 1-800-MEDIGLOB-BREACH)

**What to Include in Notification (Specific to This Incident):**
- Credit monitoring (1 year — MediGlobal absorbs cost: $57/patient × 14,287 = $815,000)
- Identity theft protection services
- Dedicated patient hotline staffed for 90 days
- Website FAQ page at hipaa.mediglob.com/2025-incident

### Ongoing: Coordination Roles
| Team | What GRC Coordinates | How |
|------|---------------------|-----|
| HR | Employee termination documentation, prior disciplinary record | Weekly touchpoint with HR Director |
| Legal | Attorney-client privilege management, FBI referral, litigation hold, OCR response | Daily briefing for first 2 weeks |
| IT Security | Evidence preservation, forensic imaging, access revocation | Daily for first week |
| Privacy Officer | HIPAA breach analysis, minimum necessary review, notification content | Daily for first week |
| PR/Communications | External messaging, media notifications | When notifications go out |
| Clinical Operations | Patient care impact assessment, CMIO briefing | One-time briefing on patient scope |

---

## INSIDER THREAT DETECTION: WHAT WORKED AND WHAT DIDN'T

### What Worked
1. **Anonymous Hotline (EthicsPoint)** — The human tip is what actually triggered the investigation. Technology alone missed it initially. This reinforces the value of a strong ethics/whistleblower culture.
2. **DLP Retrospective Analysis** — Although the DLP alert came late (overnight batch analysis, not real-time), it confirmed the scope of activity and provided the documentation needed.
3. **Epic Audit Trail** — Epic's comprehensive access logging provided an undeniable record. Every access was timestamped, authenticated, and tied to the specific query run.
4. **Pre-staged Incident Response** — Having ITP-03 (Insider Threat Protocol) already documented meant the team didn't spend time debating what to do. They executed.

### What Didn't Work / Gaps Identified
1. **DLP Gap: Personal Browser Sessions** — DLP monitored managed browsers but not personal browser sessions on managed devices. Kim used Chrome (personal browser) to upload to Google Drive. **Fix:** Deployed endpoint DLP agent (Symantec DLP Endpoint) that monitors all browser activity regardless of managed/personal status.
2. **No Real-Time User Behavior Analytics (UBA)** — The Epic anomaly wasn't detected for 22 days because there was no UBA tool analyzing access patterns. **Fix:** Deployed Splunk UBA integrated with Epic's audit logs to detect anomalous access patterns in real-time.
3. **Reporting Workbench Permissions Overly Broad** — Kim's role allowed bulk exports via Reporting Workbench. Her actual job needs could have been served with read-only access to a specific patient panel. **Fix:** Audited all Epic role permissions — restricted Reporting Workbench export rights to supervisors and above.
4. **No Pre-Employment Data Access Agreement** — Kim never signed a specific "patient data handling agreement" beyond the standard HIPAA training acknowledgment. **Fix:** All employees with EHR access now sign a specific data access agreement outlining permitted uses, prohibited exports, and consequences.
5. **No Insider Threat Training** — Managers and coworkers had no training on warning signs of insider threats. **Fix:** Added "Insider Threat Awareness" module to annual security training (now required for all supervisors).

---

## POST-TERMINATION LEGAL ACTIONS

### Criminal Proceedings
- **FBI Case Reference:** CY-2025-CHI-0421
- **Charges filed:** 18 U.S.C. § 1030 (Computer Fraud and Abuse Act) | 42 U.S.C. § 1320d-6 (HIPAA criminal penalty)
- **Status (as of Q3 2025):** Kim entered plea negotiations
- **Google cooperation:** Confirmed data was uploaded and accessible. Law enforcement subpoena issued for content.
- **DataHealth Ventures:** Received a legal hold letter. Investigation ongoing into whether they received or used MediGlobal patient data.

### Civil Litigation
- MediGlobal v. Rachel Kim — Filed in Northern District of Illinois
- Claims: Breach of fiduciary duty, violation of Computer Fraud and Abuse Act, conversion of trade secrets (patient data as a business asset)
- Damages sought: All notification costs ($1.2M), investigation costs, punitive damages

### OCR Investigation
- OCR opened a compliance investigation following the breach notification
- MediGlobal provided evidence of: breach timeline, notification actions, remediation steps, program improvements
- Status: OCR reviewing response — resolution agreement expected Q1 2026

---

## PROGRAM IMPROVEMENTS POST-INCIDENT

### Technical Controls
| Control | Before | After |
|---------|--------|-------|
| DLP coverage | Managed browsers only | All browsers via endpoint agent |
| User behavior analytics | None | Splunk UBA integrated with Epic |
| Epic export controls | Reporting Workbench available to all analysts | Restricted to supervisors; exports require justification |
| Access recertification | Annual | Quarterly for all users with export rights |

### Administrative Controls
| Control | Before | After |
|---------|--------|-------|
| Data access agreements | HIPAA training acknowledgment only | Specific "Patient Data Handling Agreement" for all EHR users |
| Insider threat training | Not included | Annual module required for all supervisors |
| Epic access provisioning | Role-based (broad) | Role-based + data minimization review |
| Offboarding procedure | Standard | Enhanced (same-day access revocation confirmed by checklist) |

### Process Controls
| Control | Before | After |
|---------|--------|-------|
| EthicsPoint routing | HR → Legal → Security (linear) | HR + Legal + Security simultaneously |
| DLP alert review | Daily batch review | Real-time alert review during business hours |
| Insider threat protocol | Existed but untested | Tabletop exercise conducted quarterly |

---

## FINANCIAL IMPACT

| Category | Cost |
|----------|------|
| Forensic investigation | $340,000 |
| Legal fees (termination, FBI coordination, OCR response, litigation) | $780,000 |
| Patient notification (letters + credit monitoring for 14,287 patients) | $1,200,000 |
| Call center (90-day patient hotline) | $180,000 |
| DLP/UBA technology upgrades | $450,000 |
| Epic access audit and remediation | $120,000 |
| PR/Communications | $60,000 |
| **TOTAL** | **$3,130,000** |
| Cyber insurance recovery | ($800,000) |
| **NET COST** | **$2,330,000** |

---

## ISO 27001 CONTROLS TESTED

| Control | Reference | Finding |
|---------|-----------|---------|
| Access control policy | A.5.15 | Existing controls were in place; gap in scope verification |
| Privileged access rights | A.8.2 | Reporting Workbench access was overly broad |
| Information access restriction | A.8.3 | Minimum necessary principle not technically enforced |
| Management of technical vulnerabilities | A.8.8 | DLP gap in personal browser sessions |
| Monitoring activities | A.8.16 | UBA gap — anomaly detection was delayed 22 days |
| Response to information security incidents | A.5.26 | IRP executed per protocol — met all deadlines |
| Collection of evidence | A.5.28 | Chain of custody properly maintained |
| Information security in human resources | A.6.3 | Gaps in pre/post-employment controls identified |

---

## REAL-WORLD DIFFICULTIES ENCOUNTERED

### Challenge 1: Balancing Speed vs. Evidence Preservation
When HR escalated the tip to CISO at 5:47 PM on June 2, the instinct was to immediately revoke Kim's access. Legal stopped this — revoking access immediately would have alerted Kim that she was being investigated, potentially causing her to destroy evidence on her personal devices.

**Resolution:** 18-hour delay on access revocation. Covert forensic imaging of laptop completed first. Preservation request to Google sent first. Then terminated and revoked access.

**Lesson:** Insider threat response is NOT the same as external incident response. Speed is less important than evidence preservation. Always consult Legal before taking any action that could alert the subject.

### Challenge 2: Need-to-Know Conflicts With Normal GRC Communication
The investigation team was strictly compartmentalized. But GRC's normal job involves weekly status reports to the CCO, bi-weekly steering committee updates, and daily standups. How do you handle an ongoing investigation in this context?

**Resolution:** The investigation was listed in the weekly report only as "Active investigation — details restricted per attorney-client privilege." CCO was personally briefed but asked not to discuss at the steering committee level until investigation was complete.

**Lesson:** Your risk management documentation systems (ServiceNow, risk register) must have the ability to restrict access to sensitive investigations. If your ticketing system doesn't support access controls, create a separate channel for HR/Legal investigations.

### Challenge 3: Patient Notification at Scale (14,287 Letters)
State law required notifications within 30 days for Illinois. With 14,287 patients across multiple states (patients had moved, had P.O. boxes, some deceased), address management was a significant operational challenge.

**Resolution:** Engaged Epiq Global (specialized healthcare breach notification vendor). They managed address verification, returned mail processes, and multi-state compliance.

**Lesson:** Have a breach notification vendor pre-selected before an incident. Negotiating contracts during a crisis is expensive and slow. Include this in your incident response vendor retainer program.

### Challenge 4: Employee's Legal Claim
Two weeks post-termination, Rachel Kim filed a complaint with the Illinois Department of Labor alleging "wrongful termination." Her attorney argued that the evidence collected via the remote forensic agent was obtained improperly (privacy violation).

**Resolution:** MediGlobal's Legal team demonstrated that:
1. The Employee Handbook (signed by Kim) explicitly stated "company-issued devices are subject to monitoring"
2. The Acceptable Use Policy (signed at hire and annually) stated "no expectation of privacy on company systems"
3. Remote forensic collection was authorized by Legal prior to execution

**Lesson:** Your Acceptable Use Policy and Employee Handbook are legal documents. Make sure they explicitly state that company devices are subject to monitoring. Have employees sign them annually (not just at hire). Keep signed copies.

---

## INTERVIEW PREPARATION — GRC INTERVIEW QUESTIONS THIS SCENARIO ADDRESSES

**"Tell me about an insider threat investigation you've been involved in."**
Framework: Discovery → Containment (covert phase) → Evidence preservation → HIPAA breach assessment → Notification → Prosecution → Program improvements.

**"How does your organization handle HIPAA minimum necessary requirements?"**
Framework: Role-based access controls in EHR → regular access recertification → audit log monitoring → DLP for export controls → Privacy Officer oversight.

**"What controls would you put in place to prevent insider threats?"**
Technical: UBA, endpoint DLP, access recertification, least privilege access.
Administrative: Insider threat training, data access agreements, ethics hotline, manager training on warning signs.

**"Walk me through the HIPAA breach notification process for an insider threat."**
Framework: Confirm PHI accessed → Apply 4-factor risk assessment → If breach confirmed → 60-day clock starts → Individual notifications → OCR notification → State notifications.

---

*End of Scenario 02: Insider Threat Investigation — MediGlobal HealthTech Inc.*
*This case study is based on realistic but fictional data for educational purposes.*
