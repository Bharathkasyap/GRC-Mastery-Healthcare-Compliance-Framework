# 08_INTERVIEW_PREP — GRC Interview Questions & Answer Frameworks
# MediGlobal HealthTech Inc. | 60+ GRC Interview Questions

> **Document Owner:** GRC Program Director  
> **Last Updated:** Q1 2026  
> **Purpose:** Comprehensive interview prep guide for GRC roles, based on real MediGlobal project experience

---

## HOW TO USE THIS GUIDE

For every question, use the **STAR framework** where applicable:
- **S**ituation — Set the context (use MediGlobal as your example company)
- **T**ask — What was your responsibility?
- **A**ction — What specific steps did YOU take?
- **R**esult — What was the measurable outcome?

**Pro Tip:** Never answer GRC interview questions generically. Always anchor your answer to a real project. Use MediGlobal HealthTech Inc. (the company in this repo) as your example organization.

---

## SECTION 1: FOUNDATIONAL GRC CONCEPTS

**Q1. What is GRC and why does it matter to an organization?**

**Model Answer:** GRC stands for Governance, Risk, and Compliance. Governance refers to the organizational structure, policies, and oversight mechanisms that ensure the company operates in alignment with its strategic objectives. Risk management is the process of identifying, assessing, and treating threats to those objectives. Compliance ensures the organization meets legal, regulatory, and contractual obligations.

In healthcare, GRC matters enormously because the stakes of failure are patient safety and regulatory consequences. At an organization like MediGlobal HealthTech (15,000 employees, 2.3M patients, 42 hospitals), a single HIPAA breach can cost $4M+ in notification and remediation costs, plus an OCR enforcement action. The GRC program's job is to prevent that.

---

**Q2. What's the difference between a risk and a threat?**

**Model Answer:** A threat is a potential cause of harm — it's external to the organization (e.g., a ransomware group, a careless vendor, a natural disaster). A risk is the possibility that a threat will exploit a vulnerability and cause harm to the organization. The difference matters because you can't eliminate threats — you can only reduce your vulnerabilities and minimize impact.

Example: The threat is "criminal actors using Log4j exploits." The risk is "our Tier-1 vendor fails to patch Log4j, allowing attackers to access PHI." The GRC program manages the risk — we can't eliminate the threat of attackers, but we can require vendors to patch vulnerabilities.

---

**Q3. What is the difference between a policy, a standard, a procedure, and a guideline?**

**Model Answer:**
- **Policy:** High-level statement of intent — "All PHI must be encrypted." Approved by leadership, mandatory.
- **Standard:** Specific technical or process requirements that support a policy — "PHI must be encrypted using AES-256." Also mandatory.
- **Procedure:** Step-by-step instructions for implementing a standard — "How to configure AES-256 encryption on Epic EHR servers." Mandatory.
- **Guideline:** Recommended best practices — "Consider using hardware security modules (HSMs) for key management." Optional, provides flexibility.

At MediGlobal, we maintain 47 policies, 89 standards, and 200+ procedures. Auditors want to see all four layers — policy without procedures is aspirational, not operational.

---

**Q4. What is a risk register and what does it contain?**

**Model Answer:** A risk register is a centralized repository of all identified organizational risks. At its core, each risk entry contains: risk title, description, risk owner, likelihood rating, impact rating, risk score (likelihood × impact), current controls in place, residual risk score after controls, risk treatment decision (accept/mitigate/transfer/avoid), and remediation owner/deadline.

At MediGlobal, we maintain the risk register in ServiceNow GRC. We have 287 risks across all categories — 23 Critical, 89 High, 118 Medium, 57 Low. The board reviews the top 25 risks quarterly. The key is that the risk register is NOT a document in someone's drive — it's a live, actively managed system.

---

**Q5. What are the four risk treatment options?**

**Model Answer:**
1. **Mitigate (Reduce):** Implement controls to reduce likelihood or impact. Example: MFA reduces likelihood of credential-based attacks.
2. **Accept:** Acknowledge the risk and consciously decide to live with it — used when mitigation cost exceeds potential impact. Requires formal risk acceptance sign-off.
3. **Transfer:** Shift financial risk to a third party — usually via cyber insurance or contractual liability clauses. MediGlobal uses AIG cyber insurance; the policy covered $1.5M of the MedSync breach costs.
4. **Avoid:** Eliminate the activity that creates the risk — stop doing the thing. Example: If a specific cloud region has unacceptable compliance risk, simply don't store data there.

---

## SECTION 2: HIPAA AND HEALTHCARE COMPLIANCE

**Q6. Explain the HIPAA Security Rule in your own words.**

**Model Answer:** The HIPAA Security Rule (45 CFR Part 164 Subpart C) requires covered entities and business associates to implement administrative, physical, and technical safeguards to protect electronic PHI (ePHI).

The three categories of safeguards:
- **Administrative (164.308):** Security management process, workforce training, access management, contingency planning. These are the most important — they're the foundation.
- **Physical (164.310):** Facility access controls, workstation use policies, device and media controls.
- **Technical (164.312):** Access control, audit controls, integrity controls, transmission security.

Key point for interviews: HIPAA uses the word "addressable" for many requirements, which people mistakenly think means "optional." Addressable means you must implement it OR document why it's not reasonable/appropriate AND implement an equivalent alternative. Skipping it entirely is not an option.

---

**Q7. What is the HIPAA Breach Notification Rule and when is notification required?**

**Model Answer:** The HIPAA Breach Notification Rule (45 CFR 164.400–414) requires covered entities to notify affected individuals, HHS OCR, and in some cases the media when a breach of unsecured PHI occurs.

Notification is required when a breach occurs, unless the covered entity can demonstrate a "low probability that PHI has been compromised" based on a 4-factor risk assessment:
1. Nature and extent of the PHI (data type sensitivity)
2. Who accessed it or used it (unauthorized person vs. trusted workforce member)
3. Whether the PHI was actually acquired or viewed
4. Extent to which the risk has been mitigated

**Timelines:** Individual notification within 60 days of discovery. OCR notification within 60 days (same). Media notification if >500 patients in a single state. Business associates must notify covered entities "without unreasonable delay" (our BAA requires 1 hour for P1 incidents).

**Real example:** In the MedSync vendor breach, 287,000 patients' PHI was potentially exposed. We applied the 4-factor test — we could not demonstrate low probability because forensics couldn't rule out exfiltration. Notification was required and executed within the 60-day deadline.

---

**Q8. What is a Business Associate Agreement (BAA)?**

**Model Answer:** A BAA is a legally required contract between a HIPAA covered entity (like MediGlobal) and any vendor (business associate) that creates, receives, maintains, or transmits PHI on behalf of the covered entity. It's required under 45 CFR 164.308(b)(1) and 164.314.

Key BAA provisions: permitted uses of PHI, requirement to implement HIPAA safeguards, breach notification obligations, right to audit the business associate, return/destruction of PHI on termination, and sub-processor disclosure requirements.

**Common interview follow-up:** "What happens if a vendor refuses to sign a BAA?" You can't engage them for services involving PHI. Full stop. At MediGlobal, we had 847 vendors and 86.3% had current BAAs. The 13.7% without BAAs were actively tracked by Legal as a high-priority compliance gap.

---

**Q9. What is the HIPAA minimum necessary standard?**

**Model Answer:** 45 CFR 164.502(b) requires covered entities to make reasonable efforts to limit the use, disclosure, or request of PHI to the minimum necessary to accomplish the intended purpose. You can only access the patient data you actually need to do your job.

In practice: A billing clerk needs insurance information and procedure codes — not the full clinical notes. A nurse needs a patient's medication history — not other patients' records. A Quality Improvement analyst needs specific readmission risk patients — not all 340,000 patients.

**Real example:** In our insider threat incident, the employee (Clinical Data Analyst) accessed 14,287 patient records when her authorized scope was ~400 patients for quality review purposes. That 35x overage violated the minimum necessary standard and triggered the HIPAA breach investigation.

---

**Q10. What is the HIPAA Safe Harbor de-identification method?**

**Model Answer:** Under 45 CFR 164.514(b), PHI is de-identified (and therefore no longer subject to HIPAA) if 18 specific identifiers are removed: names, geographic data (below state level), dates (except year), ages over 89, phone numbers, fax numbers, email addresses, SSNs, medical record numbers, health plan numbers, account numbers, certificate/license numbers, vehicle identifiers, device identifiers, URLs, IP addresses, biometric identifiers, full-face photos, and any other unique identifier.

After removing all 18 identifiers, the covered entity must also have no actual knowledge that the remaining information could identify an individual.

**Alternative method:** Expert determination — a statistical expert certifies that the risk of identification is very small (45 CFR 164.514(b)(1)).

---

## SECTION 3: ISO 27001 AND FRAMEWORKS

**Q11. What is ISO 27001 and why do organizations pursue certification?**

**Model Answer:** ISO 27001 is the international standard for Information Security Management Systems (ISMS). It provides a framework for establishing, implementing, maintaining, and continually improving an ISMS — essentially a comprehensive, systematic approach to managing information security risk.

Organizations pursue certification to: demonstrate security credibility to customers and partners, meet contractual requirements (many healthcare contracts now require ISO 27001), provide structure for their security program, and differentiate in competitive markets.

The standard consists of 11 clauses (Clauses 4–10) and Annex A containing 93 security controls across 4 themes: Organizational controls (A.5), People controls (A.6), Physical controls (A.7), and Technological controls (A.8).

At MediGlobal, ISO 27001 certification was required by several key health system customers and the UK NHS (for EMEA operations). The annual audit costs approximately $180K but validates the entire security program.

---

**Q12. Walk me through the ISO 27001 certification process.**

**Model Answer:**
1. **Gap Assessment:** Compare current state to ISO 27001 requirements. Identify gaps across all 93 Annex A controls and Clauses 4–10. At MediGlobal, we found 47 gaps in the initial assessment.
2. **ISMS Design:** Define ISMS scope (which assets, processes, locations), risk assessment methodology, Statement of Applicability (SoA — documenting which controls are implemented and why).
3. **Risk Assessment:** Identify assets → identify threats/vulnerabilities → assess likelihood and impact → determine risk scores → select controls to address risks.
4. **Control Implementation:** Implement or improve controls per the SoA. Document everything.
5. **Internal Audit:** Independent review of the ISMS before the external audit.
6. **Management Review:** Senior leadership reviews ISMS effectiveness.
7. **Stage 1 Audit (Documentation Review):** External auditor reviews documentation — policies, procedures, SoA, risk assessment records.
8. **Stage 2 Audit (Certification Audit):** Auditor conducts interviews, tests controls, reviews evidence. If satisfied, issues certificate.
9. **Annual Surveillance Audits:** Years 1 and 2 after certification. Full re-certification audit in Year 3.

**Timeline:** Typically 12–18 months from gap assessment to certification for an organization MediGlobal's size.

---

**Q13. What is the Statement of Applicability (SoA)?**

**Model Answer:** The SoA is a required document in ISO 27001 that lists all 93 Annex A controls, states whether each control is implemented, and provides justification for any controls excluded. It's essentially a roadmap of your control environment.

For each control, you document: Is it implemented? Yes/Partial/No. What is the justification for inclusion or exclusion? What are the associated policies, procedures, and evidence?

**Common interview trap:** Examiners will ask "Can you exclude controls from your SoA?" Yes — but you must document the business justification AND ensure that the excluded control doesn't cover a risk identified in your risk assessment. If you've identified a risk that the excluded control would address, you can't exclude it without accepting the residual risk.

---

**Q14. What is the NIST Cybersecurity Framework?**

**Model Answer:** The NIST CSF is a voluntary framework created by the National Institute of Standards and Technology that provides a common language and systematic approach for managing cybersecurity risk. It's organized into 5 core functions: Identify, Protect, Detect, Respond, and Recover.

Unlike ISO 27001, NIST CSF is not a certification standard — it's a framework for thinking about cybersecurity. Many organizations use it alongside ISO 27001 or as a standalone program structure.

At MediGlobal, we map our ISO 27001 controls to the NIST CSF to provide the board with a simplified view of our security posture. The five functions map nicely to board-level questions: "What do we have? How are we protected? How will we know if something goes wrong? What do we do? How do we recover?"

---

**Q15. What is the difference between ISO 27001 and SOC 2?**

**Model Answer:** Both are security assurance frameworks, but they differ in purpose and audience:

**ISO 27001:** An international standard for building and certifying an ISMS. It's process-oriented (you're certifying your processes, not just your controls). Results in a 3-year certificate. Recognized globally.

**SOC 2:** An American attestation standard (AICPA) for service organizations. Type I = assessment at a point in time. Type II = assessment over a period (typically 12 months). Results in an audit report, not a certificate. Evaluates controls against the Trust Service Criteria (Security, Availability, Processing Integrity, Confidentiality, Privacy).

**When to use which:** ISO 27001 is often required by European customers and provides a more comprehensive ISMS certification. SOC 2 Type II is often required by US SaaS customers. At MediGlobal, we require Tier-1 vendors to provide SOC 2 Type II reports AND accept that ISO 27001 certification satisfies this requirement.

---

## SECTION 4: RISK MANAGEMENT

**Q16. Walk me through how you conduct a risk assessment.**

**Model Answer:** I follow a 5-step process:

1. **Define scope and methodology:** What systems/processes are in scope? What risk rating scale will we use (we use a 5x5 likelihood × impact matrix at MediGlobal)?

2. **Asset identification:** Catalog all in-scope assets — hardware, software, data, people, processes. At MediGlobal, this includes 9,200+ endpoints, 42 EHR environments, 847 vendors, and 2.3M patient records.

3. **Threat and vulnerability identification:** For each asset, what threats exist? What vulnerabilities does the asset have? We use MITRE ATT&CK for threat identification in the healthcare context.

4. **Risk analysis and scoring:** For each threat-vulnerability pair, assign likelihood (1–5) and impact (1–5). Multiply for the risk score. Risk scores 15–25 = Critical; 8–14 = High; 4–7 = Medium; 1–3 = Low.

5. **Risk treatment:** For each risk, decide: Mitigate, Accept, Transfer, or Avoid. Document the treatment, owner, and deadline. Accepted risks require sign-off per the risk acceptance policy.

All risks go into ServiceNow GRC risk register. Critical risks are reviewed monthly; High quarterly; Medium and Low as needed.

---

**Q17. What is residual risk and why does it matter?**

**Model Answer:** Residual risk is the risk that remains AFTER controls are implemented. Inherent risk is the raw risk before any controls. The relationship is: Inherent Risk → Apply Controls → Residual Risk.

It matters because no control eliminates risk completely. Even with MFA, endpoint detection, and network segmentation, the residual risk of a ransomware attack at MediGlobal is still rated High (score: 9). The question becomes: is the residual risk within our risk appetite? If yes, we accept it. If not, we add more controls.

**Interview pro tip:** When an auditor asks about your risk management program, always talk about residual risk. It shows you understand that controls are never 100% effective and that risk management is about managing to an acceptable level, not eliminating risk entirely.

---

**Q18. How do you prioritize which risks to remediate first?**

**Model Answer:** Prioritization uses a combination of risk score, business impact, and control cost:

1. **Risk Score First:** Critical risks (15–25) get addressed first regardless of cost.
2. **Then Risk-Adjusted ROI:** For High risks, calculate the cost of remediation vs. the expected annual loss reduction. If a $50K control reduces expected annual loss by $500K, it's a clear priority.
3. **Regulatory Mandate:** If a risk maps to an ISO 27001 control or HIPAA requirement, it has regulatory pull — non-compliance is a non-option.
4. **Ease of Implementation:** Sometimes the "quick wins" — low-cost, high-impact controls — should be done first to reduce the overall risk surface quickly.

At MediGlobal, after the MedSync breach, the vendor monitoring gap was prioritized even though its inherent score was Medium — because the MedSync incident proved the potential impact was Very High, and deploying SecurityScorecard cost only $95K/year.

---

## SECTION 5: THIRD-PARTY RISK MANAGEMENT

**Q19. How do you manage vendor/third-party risk?**

**Model Answer:** Our TPRM program at MediGlobal uses a tiered approach:

**Tier Classification (before engagement):**
- Tier 1: Access to PHI or critical systems → full assessment, BAA, annual review, continuous monitoring
- Tier 2: Limited data access → abbreviated assessment, BAA if PHI adjacent, bi-annual review
- Tier 3: No sensitive data → registration only, 3-year review cycle

**Onboarding:** Security questionnaire (127 questions for Tier 1), SOC 2 Type II review, contractual security requirements, BAA execution.

**Ongoing Monitoring:** SecurityScorecard for all 147 Tier 1 vendors (daily score updates), annual reassessment, quarterly vendor risk meeting review.

**Remediation:** Any finding gets tracked in ServiceNow with evidence-based verification — we don't accept remediation plans, we require proof.

**Offboarding:** Revoke all access, confirm data deletion/return per BAA, close vendor record.

---

**Q20. What is a vendor breach and how do you respond?**

**Model Answer:** Use the MedSync breach as your example. See Scenario 01 in this repository for the complete timeline. Key response points:

Immediate: Isolate the vendor connection → notify Legal → start HIPAA clock → engage forensics → preserve evidence.

Assessment: Scope (which data, how many patients) → HIPAA breach determination (4-factor test) → regulatory notification planning.

Vendor accountability: Use BAA to compel cooperation → litigation hold → breach of contract assessment.

Program improvement: Post-incident, we added technical scanning to vendor assessments, SecurityScorecard continuous monitoring, and strengthened BAA language.

---

## SECTION 6: INCIDENT RESPONSE AND HIPAA BREACH NOTIFICATION

**Q21. Tell me about an incident you managed from discovery to closure.**

**Model Answer:** (Use Scenario 01 or 02 from this repository as your template)

For Vendor Breach: "In March 2025, our SOC detected anomalous API traffic from a Tier-1 EHR integration vendor. I was the GRC analyst on call. Here's what I did:

1. Opened ServiceNow P1 incident immediately — started HIPAA 60-day clock
2. Notified Privacy Officer and Legal — attorney-client privilege invoked
3. Coordinated evidence collection — forensic imaging, chain of custody
4. Conducted HIPAA 4-factor risk assessment — breach confirmed, 287K patients
5. Managed notification process — 31 states, OCR filing, patient letters
6. Led lessons learned — updated TPRM program with technical scanning

Result: All regulatory notifications met within deadlines. OCR acknowledged our response as complete. Program improvements implemented within 30 days."

---

**Q22. What are the 4 factors in the HIPAA breach risk assessment?**

**Model Answer:** Per 45 CFR 164.402(2), low probability of PHI compromise can only be demonstrated if ALL four factors indicate low risk:

1. **Nature and extent of PHI involved** — What types of data? (names/DOB = lower risk; SSN/diagnoses/financial = higher risk)
2. **Who accessed or used the PHI** — Trusted employee (potentially lower risk) vs. criminal actor (very high risk)
3. **Whether the PHI was actually acquired or viewed** — Confirmed access logs showing viewing = high risk; encrypted data with no access = potentially lower risk
4. **Extent to which the risk has been mitigated** — Have you recovered the data? Confirmed it wasn't further disclosed?

If ANY factor points to high risk, you cannot use the low probability exception — notification is required.

---

## SECTION 7: GRC TOOLS AND TECHNOLOGY

**Q23. What GRC tools have you worked with?**

**Model Answer:** My primary experience is with ServiceNow GRC for risk register management, policy and compliance management, audit management, and vendor risk management. I use it daily for creating and managing risk records, tracking control testing evidence, and running audit engagements.

I also use OneTrust for privacy impact assessments and vendor portal management, and Archer for financial risk quantification using FAIR methodology — which I use when I need to translate risk scores into dollar amounts for board reporting.

For supporting tools: Qualys for vulnerability management (pulling compliance scan evidence for ISO 27001 A.8.8), SecurityScorecard for continuous vendor monitoring, and Okta for access review management and evidence collection.

---

**Q24. How do you use ServiceNow specifically for a compliance audit?**

**Model Answer:** Start by creating an Audit Engagement in ServiceNow — define the scope (ISO 27001, all 93 controls), timeline, and audit team. ServiceNow auto-generates test plans for all controls in scope. I assign each test to the appropriate control owner — IT team gets the technical control tests, HR gets the workforce training tests, etc.

As evidence comes in, I review it in ServiceNow against the test criteria. For any control with insufficient evidence or a gap, I create an Issue record — automatically linked to the control, with severity, root cause, recommendation, and remediation owner.

At the end of fieldwork, ServiceNow gives me a dashboard showing: X controls passed, Y have issues, Z are in progress. I generate the audit report directly from ServiceNow — it pulls all the issue details, links them to regulatory references, and creates a structured finding report.

The key advantage over Excel: everything is traceable, nothing falls through the cracks, and the audit trail is automatic.

---

## SECTION 8: SCENARIO-BASED AND BEHAVIORAL QUESTIONS

**Q25. You discover a Critical risk that the CISO wants to accept because remediation is expensive. What do you do?**

**Model Answer:** I would walk through the risk acceptance process formally:
1. Document the risk in ServiceNow — current score, controls in place, residual score
2. Quantify the financial exposure using FAIR methodology — express it as expected annual loss
3. Calculate the cost of remediation vs. the expected loss
4. Prepare a Risk Acceptance Form and present it to the CISO with the financial comparison
5. Explain that under our risk management policy, Critical risks require both CISO AND CCO sign-off — I would need both signatures
6. If the CISO still wants to accept: that's ultimately a business decision. My job is to ensure: (a) the risk is formally documented, (b) the acceptance form is signed by appropriate parties, (c) a review date is set (Critical risks can only be accepted for 3 months before requiring renewal), and (d) it's reported to the Board Audit Committee at the next quarterly meeting.

What I would NOT do: accept the risk verbally or without documentation. That protects me, the company, and the CISO.

---

**Q26. You're asked to implement a new GRC policy in 30 days. What's your process?**

**Model Answer:**
1. **Understand the requirement:** Why is this policy needed? Regulatory driver, audit finding, risk identified? Understand the "why" before writing the "what."
2. **Benchmark:** Review 2–3 reference policies (SANS, NIST, industry peers). Don't start from scratch.
3. **Draft:** Write a policy that is clear, actionable, and tied to specific regulatory requirements (ISO control numbers, HIPAA CFR references).
4. **Stakeholder review:** Share with affected departments for 5–7 business day comment period. Legal review mandatory. CISO review if technical.
5. **Executive approval:** Present to CCO (and CISO if security policy) for approval.
6. **Publish and communicate:** Post to intranet, send announcement, update ServiceNow policy record.
7. **Train:** Schedule attestation campaign in ServiceNow — all relevant employees must acknowledge.
8. **Track compliance:** Monitor attestation completion weekly until 100%.

30 days is tight — you can do it, but you need to move through each step efficiently and not get stuck in revision cycles.

---

**Q27. You find a gap in your ISO 27001 audit preparation 2 weeks before the auditor arrives. What do you do?**

**Model Answer:** First, assess the severity: Is this a major nonconformity (complete absence of a required control) or a minor nonconformity (control exists but documentation is weak)?

For a major nonconformity 2 weeks out: escalate to CISO and CCO immediately. You have two options: (1) implement a compensating control and document it properly in the SoA with evidence — 2 weeks is very tight but sometimes possible. (2) Disclose proactively to the auditor — credible, honest engagement often results in an "opportunity for improvement" rather than a nonconformity finding, especially if you have a clear remediation plan.

For a minor nonconformity: fix the documentation gap, update the ServiceNow control record with current evidence, and be prepared to explain the control operation clearly to the auditor.

What I would NOT do: hide the gap or misrepresent the control status to the auditor. That's a much worse outcome — auditors do find things, and they ask pointed questions.

---

**Q28. How do you communicate risk to a non-technical executive?**

**Model Answer:** Three rules:
1. **Translate to dollars:** "Critical vulnerability in our EHR" means nothing to a CFO. "This unpatched vulnerability in our Epic system has an expected annual loss of $9.4M based on our FAIR analysis, compared to a $240K remediation cost" is actionable.

2. **Avoid jargon:** Instead of "we have a CVE-2021-44228 Log4j RCE vulnerability in our HL7 integration middleware," say "a vendor's critical system had a well-known security flaw unpatched for 3 years that allows attackers to take control remotely — the fix costs $50K and takes 2 weeks."

3. **Give a recommendation:** Executives don't want a list of problems, they want to know what to DO. "I recommend we require all Tier-1 vendors to certify patch status monthly — budget impact: $80K/year for the monitoring program. Without this, we estimate 23% probability of another similar breach in the next 24 months."

---

## SECTION 9: EMERGING TOPICS

**Q29. What is Zero Trust and how does it relate to GRC?**

**Model Answer:** Zero Trust is a security architecture philosophy — "never trust, always verify." Instead of a perimeter-based model (trusted inside, untrusted outside), Zero Trust assumes breach and requires continuous verification of every user, device, and connection regardless of location.

GRC relevance: Zero Trust directly supports ISO 27001 A.5.15 (Access control policy) and HIPAA 164.312(a)(1) (Access control) and 164.312(e)(1) (Transmission security). Implementing Zero Trust reduces the risk of insider threats (like the MediGlobal Rachel Kim case) because even trusted employees need to re-verify for each sensitive access.

From a GRC standpoint: Zero Trust is a control architecture, not a product. When assessing vendors or internal controls, GRC analysts evaluate whether Zero Trust principles are implemented: MFA everywhere (Okta), least-privilege access (access reviews), network microsegmentation (VLAN isolation), continuous monitoring (Rapid7 + Splunk UBA).

---

**Q30. What is GDPR and how does it interact with HIPAA?**

**Model Answer:** GDPR (EU General Data Protection Regulation) is the EU law governing personal data privacy for EU residents. It applies to any organization that processes EU residents' data — including MediGlobal's EMEA operations covering UK, Germany, and France.

Key differences from HIPAA: GDPR covers ALL personal data, not just health data. GDPR has a 72-hour breach notification requirement (vs. HIPAA's 60 days). GDPR has explicit data subject rights (right to access, right to erasure, right to portability). GDPR fines can be up to 4% of global annual revenue ($368M for MediGlobal at $9.2B revenue) — far higher than HIPAA maximums.

Where they overlap: Both require technical and organizational safeguards. Both require breach notification. Both require data minimization. For MediGlobal, we apply the stricter requirement for any ambiguous situation — GDPR's 72-hour notification applies to any EU patient breach.

---

## QUICK REFERENCE: 20 MORE INTERVIEW QUESTIONS

31. What is the NIST 800-53 and how is it different from ISO 27001?
32. How do you track regulatory changes that may affect your compliance program?
33. What is a HIPAA Security Risk Analysis and how often should it be done?
34. Explain the concept of defense in depth.
35. What controls prevent PHI from being printed and taken home?
36. How do you handle a situation where a department head refuses to remediate a High risk?
37. What is the role of a Privacy Officer vs. a CISO?
38. How would you build a security awareness training program from scratch?
39. What is the HITRUST CSF and who uses it?
40. How do you prepare a company for an external ISO 27001 audit?
41. What are common findings in HIPAA audits?
42. Explain the concept of "reasonable and appropriate" safeguards under HIPAA.
43. What is data classification and why does it matter?
44. How do you conduct a BIA (Business Impact Analysis)?
45. What is the relationship between risk appetite and risk tolerance?
46. How would you design a third-party risk program from scratch?
47. What is a compensating control and when is it appropriate?
48. How do you ensure policies are actually followed, not just on paper?
49. What metrics do you track to measure GRC program effectiveness?
50. How would you explain the ROI of a GRC program to a skeptical CFO?

---

### SAMPLE METRICS TO MENTION IN INTERVIEWS

Always have specific metrics ready. Use MediGlobal numbers:
- **Risk register:** 287 risks managed | 23 Critical, 89 High
- **ISO 27001 compliance:** 93 controls | Current compliance: 91.4%
- **HIPAA training:** 98.3% completion rate across 15,000 employees
- **Vendor BAA compliance:** 731/847 (86.3%) — targeting 100%
- **Patch compliance:** 97.8% (critical patches within 72 hours)
- **Audit findings:** 12 findings in last ISO 27001 audit (2 High, 7 Medium, 3 Low) — all remediated
- **Time to remediate High risks:** Average 47 days (target: 30 days)
- **Security awareness training click-through rate:** Reduced from 4.2% to 0.3% after MFA+training campaign

---

## DOCUMENT CONTROL

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2024-06-01 | GRC Program Director | Initial creation (30 questions) |
| 1.5 | 2024-12-15 | GRC Analyst Team | Added scenario-based questions |
| 2.0 | 2025-03-01 | GRC Program Director | Added tool questions, expanded HIPAA section |
| 2.1 | 2026-01-10 | GRC Analyst | Added Zero Trust, GDPR, metrics section |

---
*End of Interview Preparation Guide — MediGlobal HealthTech Inc.*
*Study these questions, memorize the MediGlobal metrics, and practice the STAR framework.*
*Good luck — the GRC field needs people who can do this work in the real world.*
