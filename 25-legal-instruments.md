# **Written Agent Authorizations: 25 Instruments, Dissected for AI-Agent Design**

Version 0.3.4 November 14, 2026 · @Dazza Greenwood / with Fable 5.2, Sol 6.1 and Grok 4.7.

## **How to read this document**

Each of the 25 instruments from the source list gets the same dissection, so they can be compared side by side and mined for AI-agent authorization design.

•      **A. Title** and **B. Blurb** — the instrument in a line.  
•      **C. Background** — (1) who issues the form or text, (2) the single most important lesson for technical authorization of AI agents, (3) the instrument itself, (4) its context and prevalence, (5) stability and variants.  
•      **C2. Drill-down: the operative clause** — your brief used “C” twice; the second is labeled C2 here. It isolates the words that actually delegate authority.  
•      **D. Outline** of the full instrument, part by part.  
•      **E. Insights** — observations, pitfalls and recent changes.

Conventions: U.S. government forms, statutes and regulations are public domain, so their operative language is quoted directly. Privately authored forms (brokerage, telecom, real estate, insurance, bank templates) are copyrighted, so their clauses are paraphrased with at most a short quoted phrase. Status is as of the date above; forms are revised often, so check the linked current revision before relying on any detail. Items 8 and 24 in the source list overlap (both cite USPS PS 3801): item 8 here centers on PS 1583 and the CMRA relationship, item 24 on the PS 3801 standing delivery order. This is research, not legal advice.

## **Synthesis: what 25 instruments teach about authorizing AI agents**

The 25 instruments converge on one anatomy, and almost every hard problem in AI-agent authorization — scoping, revocation, counterparty refusal, money movement, sub-delegation — already has a tested answer somewhere in this set. The paper world's best ideas are usually not in the grant clause itself but in the machinery around it: registries, carve-outs, notices, logs and acceptance duties.

### **The recurring anatomy**

1\.     **Principal identity and proof of authority** — who grants, and why they may (incumbency certificate, USPTO 3.73(c) chain of title, IRS line 7 officer certification).  
2\.     **Agent identity and credential** — a licensed, registered or attested agent (G-28 bar data, SSA-1696 Section 5, CMRA Form 1583-A).  
3\.     **Scope** — verbs × objects × constraints (IRS tax × form × period; VIN-bound DMV POA; PG\&E initialed categories).  
4\.     **Hot powers and hard carve-outs** — dangerous acts off by default (UPOAA § 201, IRS line 5a/5b, SLOA payee rule, VA § 7332 records).  
5\.     **Purpose** — stated, or chosen from a closed list (FERPA, HIPAA, DPPA, SSA-89).  
6\.     **Lifetime** — a clock (SSA-89 90 days, CMS-1696 one year), a workflow state (G-28 "conclusion of the matter," trademark registration), or one event (proxy: one meeting).  
7\.     **Revocation and supersession** — last-write-wins per scope tuple, whole-list replacement, or contest windows.  
8\.     **Counterparty validation** — a registry lookup (IRS CAF, VA POA, CMRA CRD), a record match (telecom CSR), or reliance on the agent's custody (customs POA).  
9\.     **Principal channel and notices** — courtesy copies, subject notices, per-transfer notices, port-out alerts.  
10\.  **Records** — consent retention and disclosure logs (FERPA § 99.32, DPPA § 2721(c), customs 5-year rule, CMS 10-year rule).  
11\.  **Execution assurance** — wet ink, notary, witnessed video, e-sign on the counterparty's own surface.  
12\.  **Liability allocation** — indemnities, statutory damages, reliance protection.

### **Ten design rules for AI-agent authorization**

1\.     **Split read, act, and move-money into separate grants.** IRS 8821 vs. 2848 (item 4), PG\&E information vs. action (item 18), Schwab trade vs. disburse (item 21).  
2\.     **Make validity a schema.** HIPAA's core elements and defect rules (item 2\) and FERPA's three fields (item 3\) can be checked by machine before anything moves.  
3\.     **Ban wildcards; default-deny hot powers.** No "all years" at the IRS; "all powers" in a POA still excludes gifts and beneficiary changes (item 23).  
4\.     **Never let the agent control the payee list or the principal's contact details.** SLOA condition 5 (item 21), IRS line 5b (item 4), VA address-change opt-in (item 7).  
5\.     **Keep a channel to the principal that the agent cannot capture.** G-28 courtesy copies (item 5), Reg E stop-payment at the bank (item 10), CFPB servicer-may-contact clause (item 19), port-out notices (item 17).  
6\.     **Put the registry on the counterparty's side and push revocation to it.** CAF, VA POA records, CMRA CRD, the carrier's BOR state machine (item 25). Notice-based revocation (item 14\) shifts risk to the principal.  
7\.     **Authenticate at use time, not just at grant time.** PS 3801 photo ID at each pickup (item 24); UPOAA § 302 agent certification at presentation (item 23).  
8\.     **Tier verification by risk, and don't over-verify protective acts.** CCPA lets businesses step up for delete/know but punishes it for opt-outs (item 1).  
9\.     **Define exclusivity and handoff.** One VA representative at a time (item 7); BOR contest windows (item 25); latest-dated proxy wins (item 22).  
10\.  **Give counterparties a duty to accept a standard mandate.** UPOAA § 120 and Cal. Prob. Code § 4406 (item 23), plus regulator-published templates such as the CFPB model (item 19), solve the "merchant won't honor my agent" problem.

### **Pattern map**

| \# | Instrument | Core pattern | AI-agent primitive |
| :---- | :---- | :---- | :---- |
| 1 | CCPA authorized agent | Signed slip; step-up only for some request types | Risk-tiered verification per action type |
| 2 | HIPAA authorization | Closed list of required elements; defects void it | Schema-validated mandate |
| 3 | FERPA consent | Records × purpose × recipient; holder logs disclosures | Minimal scope \+ subject-visible access log |
| 4 | IRS 2848 / 8821 | Read vs. act; tax × form × period; central CAF | Tuple-scoped tokens in a counterparty registry |
| 5 | USCIS G-28 | Agent credential inside the grant; delivery opt-ins | Credential-in-token; separate delivery scope |
| 6 | SSA-1696 / SSA-89 / CMS-1696 | One-shot purpose consent vs. standing role; fees split off | Single-use tokens; separate payee record |
| 7 | VA 21-22 / 21-22a | Sensitive-record opt-ins; one representative at a time | Data-class consents; single-holder slot |
| 8 | USPS PS 1583 | Identity-proof principal and agent; quarterly re-certify | Registered agent operators with liveness attestation |
| 9 | UCC 9-509 | Authorization implied by the deal; open registry \+ liability | Post-hoc validity with challenge path |
| 10 | Reg E / Nacha ACH | Bounded recurring mandate; revoke at own bank | Intent mandate with issuer-side kill switch |
| 11 | FCRA disclosure | Standalone consent; nothing bundled | Isolated, hashable consent object |
| 12 | USPTO POA | Delegate to a Customer Number roster; prove title | Group grantee with managed membership |
| 13 | DMV POA / odometer | VIN-bound; high-risk attestation non-delegable | Object-bound scope; step-up for attestations |
| 14 | Corporate resolutions | Authority to roles; incumbency binds role → person | Policy vs. role-to-key binding |
| 15 | PMA / listing agreement | Spend cap with emergency override; fixed term | Spend limits with step-up approval |
| 16 | Customs POA | Agent holds and produces the mandate; KYC on agent | Agent-held consent receipts, auditable on demand |
| 17 | Telecom LOA | Match incumbent's record \+ principal secret; port lock | Relying-party match \+ principal-held second factor |
| 18 | PG\&E 79-1095 | Paper checklist rebuilt as OAuth scopes | Direct paper-to-scope migration |
| 19 | CFPB third-party form | Regulator template; one-year expiry; refusal in writing | Shared schema; structured refusal reasons |
| 20 | DPPA consent | Closed purpose taxonomy; reseller lineage logs | Purpose codes \+ downstream lineage |
| 21 | Brokerage LPOA / SLOA | Trade freely; payees only via custodian-verified list | Payee allowlist the agent can't edit |
| 22 | SEC proxy card | Per-item choices; enumerated discretion; one meeting | Per-action instructions; bounded discretion |
| 23 | Statutory POA | Hot powers opt-in; third parties must accept | Default-deny scopes; acceptance duty |
| 24 | USPS PS 3801 | Standing list of agents; ID at each use | Standing grant \+ runtime authentication |
| 25 | Insurance BOR | One agent per account; contest window on change | Exclusive grant with two-phase handoff |

### **How this maps to current agent-authorization standards**

•      **OAuth 2.0 Rich Authorization Requests** ([RFC 9396](https://rfc-editor.org/rfc/rfc9396), May 2023\) carries typed authorization\_details objects with actions, locations, datatypes and identifier fields, and its worked example is a payment initiation with amount and creditor. That is the natural container for IRS-style tuples (item 4\) and PG\&E-style checklists (item 18).  
•      **Google's Agent Payments Protocol (AP2)** ([announcement, Sept. 2025](https://cloud.google.com/blog/ja/products/ai-machine-learning/announcing-agents-to-payments-ap2-protocol)) uses a signed "Intent Mandate" (price limits, timing, conditions) for human-not-present purchases and a "Cart Mandate" for exact items and prices. These map closely to Nacha standing authorizations and Reg E range notices (item 10), and the [UCP AP2 extension](https://ucp.dev/draft/specification/payment/extensions/ap2-mandates/) adds merchant-signed terms and mandate-scope-mismatch errors.  
•      **The IETF On-Behalf-Of draft for AI agents** ([draft-oauth-ai-agents-on-behalf-of-user-02](https://www.ietf.org/archive/id/draft-oauth-ai-agents-on-behalf-of-user-02.html), Aug. 2025\) names the agent in the consent screen and stamps it into the token's act claim — the G-28 idea (item 5\) that the agent's identity is part of the grant.  
•      **Gaps the paper world already solved that these specs mostly leave open:** a counterparty duty to accept (item 23), closed purpose taxonomies (item 20), exclusivity and contest windows (item 25), sensitive-class opt-ins (item 7), subject-visible disclosure logs (item 3), and payee allowlists the agent cannot edit (item 21).

### **Corrections to the source list**

•      **Item 2:** the HHS reproductive-health model attestation is obsolete; the rule behind it was vacated in *Purl v. HHS* (June 2025).  
•      **Item 12:** PTO/AIA/81 is the POA to joint inventors, not a Customer Number POA; Customer Number appointment is on AIA/80 and AIA/82B.  
•      **Item 15:** no "Orange Property Manager" sample PMA could be found online; the C.A.R. PMA sample is used instead.  
•      **Item 16:** the 2019 customs-broker client-verification rule was never finalized (19 CFR 111.43 is still reserved).  
•      **Item 21:** the Schwab link in the source list points to a retirement-plan (PCRA) application, not the adviser LPOA.  
•      **Item 25:** the AmWINS sample BOR letter could not be fetched; CDPHP, PMC and Complete Markets templates are used.  
•      **Items 8 and 24:** the source list cites PS 3801 under both; item 8 is rebuilt around PS 1583\.

## **1\. CCPA/CPRA authorized-agent signed permission**

**A. Title:** "Authorized Agents," Cal. Code Regs. tit. 11, § 7063 (CCPA Regulations, current consolidated text labeled "Effective January 1, 2026" by the CPPA), with § 7026(j) (opt-out of sale/sharing via agent), § 7027(i) (limit use of sensitive PI via agent), § 7001(d) (definition) and § 7011(e)(3)(H) (privacy-policy instructions for agents). Statutory basis: Cal. Civ. Code §§ 1798.135(e), 1798.140(ak), 1798.185. Typical private instrument: a business's "CCPA Authorized Agent Form" (e.g., Patelco Credit Union form, effective Jan. 1, 2023\) or an agent service's signed agreement (Consumer Reports' Permission Slip).

**B. Blurb:** A signed permission slip, plus the right to ask the principal directly.

### **C. Background**

**1\. Who it comes from:** The rule comes from the California Privacy Protection Agency (CPPA), which inherited the Attorney General's 2020 CCPA regulations (originally § 999.326, renumbered § 7063 in 2022). There is no official state form. Each business, or each agent service, drafts its own permission document, which the consumer signs.

**2\. Key lesson for AI-agent authorization:** **The agent's credential is never self-sufficient: the counterparty may demand proof of signed permission and also step up by confirming directly with the principal — except for low-risk "opt-out" actions, where demanding that confirmation is itself a violation.** This is a risk-tiered verification model. Read-and-delete style actions (know, delete, correct) justify out-of-band principal confirmation; protective actions (opt-out, limit) must flow on the agent's signed permission alone. The agent also carries its own statutory duties (security, purpose limitation), so an agent design needs both a delegation token and an agent-side compliance profile.

**3\. The instrument:**

•      **Scenario.** A consumer uses a person or registered business to exercise CCPA rights: know, delete, correct, opt out of sale/sharing, or limit sensitive-PI use. Agent services such as Permission Slip send these requests at scale.  
•      **Parties.** Principal: the "consumer" (a California resident). Agent: "a natural person or a business entity that a consumer has authorized to act on their behalf" (§ 7001(d)); the statute narrows business agents to persons registered with the Secretary of State (§ 1798.140(ak)). Counterparty: the "business."  
•      **Powers delegated.** Submission of the request only. The agent does not receive the consumer's account or a general power over the relationship.  
•      **Validation.** For requests to delete, correct, or know, the business may require proof of signed permission. It may also require the consumer to verify identity directly or to confirm the grant directly (§ 7063(a)). For opt-out and limit requests, the business may deny only if the agent fails to produce the signed permission (§ 7026(j)); it may not require direct consumer confirmation (CPPA *Honda* order, below).  
•      **Power-of-attorney bypass.** If the agent holds a power of attorney valid under Probate Code §§ 4121–4130, the § 7063(a) checks do not apply. A business may not require a POA (§ 7063(b)). Section 4121 sufficiency means the POA is dated, signed, and notarized or signed by two qualified witnesses.  
•      **Agent duties.** The agent must keep reasonable security and may use the information only to fulfill the request, for verification, or for fraud prevention (§ 7063(c)–(d)).  
•      **Duration and revocation.** The regulation sets no term and no revocation procedure. Private forms are usually single-request (Patelco) or ongoing until cancelled (Permission Slip agreement).  
•      **Machine-signal exception.** No written permission is needed when the opt-out arrives as an opt-out preference signal such as Global Privacy Control (§ 7026(j); § 1798.135(e)).

**4\. Context:** The authorized-agent concept dates to the original CCPA (2018) and the AG's 2020 regulations. Consumer Reports' 2022 Permission Slip beta sent 1,666 requests for 157 consumers to 32 companies; only 15 companies (about 47%) processed them without extra steps, and 6 never responded. Consumer Reports now reports about three million emails sent on users' behalf.

Enforcement: in March 2025 the CPPA Board approved a \$632,500 stipulated order against American Honda. The order found Honda required at least 14 consumers to confirm their agents' permission directly, including for opt-outs, which violated §§ 7026(j), 7027(i) and 7063(a).

**5\. Stability and variants:** The core text has been stable since the March 29, 2023 amendment. The CPPA's 2025 rulemaking (approved by OAL Sept. 22, 2025; effective Jan. 1, 2026\) lists § 7063 among sections affected. A law-firm summary says it added § 7063(a)(2): a business may not require a consumer to resubmit an agent's request in their individual capacity. The final § 7063 text could not be opened (the CPPA PDF fetch truncated), so treat that sub-clause as reported, not verified.

A sister channel is the Delete Act's DROP platform: data brokers must process DROP deletions from Aug. 1, 2026, every 45 days, and agents may assist only after the CPPA verifies residency. Other state privacy laws (Colorado, Connecticut and others) have their own agent rules.

### **C2. Drill-down: the operative clause**

"When a consumer uses an authorized agent to submit a request to delete, request to correct, or a request to know, a business may require the authorized agent to provide proof that the consumer gave the agent signed permission to submit the request. The business may also require the consumer to do either of the following: (1) Verify their own identity directly with the business. (2) Directly confirm with the business that they provided the authorized agent permission to submit the request."

— Cal. Code Regs. tit. 11, § 7063(a) (text as amended 3-29-2023; see 2026 note above)

"A consumer may use an authorized agent to submit a request to opt-out of sale/sharing on the consumer's behalf if the consumer provides the authorized agent written permission signed by the consumer."

— Cal. Code Regs. tit. 11, § 7026(j)

Paraphrase (private form): the consumer authorizes the named agent, for one purpose only, to submit a verifiable CCPA request covering the checked request types, signed before a notary. Short quote: "for the sole purpose of submitting a verifiable consumer request."

— Patelco Credit Union, CCPA Authorized Agent Form, § 4 (eff. Jan. 1, 2023\)

The grantor is the consumer and the grantee is the agent. The delegating verb is "submit": the agent gets a procedural right, not a substantive one. The object is a typed request (delete, correct, know, opt-out, limit). The scope limiter is the request type; private forms add checkboxes per type.

The counterparty has two optional checks for the higher-risk types: a document check (signed permission) and a principal check (identity or direct confirmation). It may deny an opt-out only for a missing signed permission. Not delegated: the agent cannot reuse the data for other purposes, and nothing lets a business insist on a POA. The business is bound because § 1798.140(ak) makes a request by a person authorized by the consumer a verifiable consumer request, and § 1798.135(e) says a business shall comply with opt-outs from authorized persons.

### **D. Outline of the full instrument**

1\.     Regulatory frame  
a.     § 7001(d) definition of authorized agent, cross-referencing § 7063\.  
b.     § 7011(e)(3)(H) privacy policy must explain how agents submit requests.  
c.      § 7063(a) signed permission plus optional consumer step-up, for know/delete/correct.  
d.     § 7063(b) POA carve-out and no-POA-requirement rule.  
e.     § 7063(c)–(d) agent security and purpose-limitation duties.  
f.      §§ 7026(j), 7027(i) signed permission for opt-out and limit, with opt-out-signal exception.  
2\.     Typical private permission form (Patelco model)  
a.     Request-type checkboxes (opt-in, opt-out, delete, know specific pieces, know categories, correct, limit).  
b.     Consumer identity block (name, DOB, address, phone, email).  
c.      Agent identity block, including the agent's government ID number.  
d.     Authorization statement, consumer signature and date.  
e.     Notary acknowledgment, seal dated within 30 days of receipt.  
f.      Submission channels (upload, branch, mail).  
3\.     Agent-service model (Permission Slip)  
a.     Consumer verifies email and phone, signs an agency agreement.  
b.     Agent emails each company the request plus proof of designation.  
c.      Company may route a confirmation link to the consumer; status returns to the agent.

The regulation sets the ceiling of evidence a business may demand. Private forms then compete on friction: notarized single-use forms sit at one end, app-signed standing agreements at the other.

### **E. Insights and observations**

•      **Risk tiering is explicit and enforced.** *Honda* shows that over-verifying a protective action (opt-out) is itself a violation. Agent platforms should expect counterparties to apply different proofs by action type, and should label requests accordingly.  
•      **Notarization is a business choice, not a legal requirement.** Patelco requires a notary seal dated within 30 days. Friction like this is a known reason agent requests stall.  
•      **Counterparties want agent identity too.** The *Honda* order requires agents to supply their own contact details alongside the consumer's — a precursor to registered agent identifiers.  
•      **Opt-out preference signals bypass written permission entirely.** A browser-level signal is treated as the consumer's own act — the closest existing analogue to a standing machine-readable mandate that needs no per-request paperwork.  
•      **Purpose limitation binds the agent by regulation, not by contract.** An AI agent that harvests data returned by a "request to know" for other uses would breach § 7063(d) directly.  
•      **Two-tier credential system.** A heavyweight, formally executed instrument (dated, notarized or witnessed POA) defeats the step-up checks that a lightweight signed slip invites.  
•      **Failure mode: no shared format.** Consumer Reports found company webforms "aren't uniform and often contain CAPTCHAs," blocking automated agents. A standard permission schema and agent endpoint would remove most friction.

**Sources:** [11 CCR § 7063 (LII)](https://www.law.cornell.edu/regulations/california/11-CCR-7063) · [11 CCR § 7063 (Justia, with history)](https://regulations.justia.com/states/california/title-11/division-6/chapter-1/article-5/section-7063/) · [11 CCR § 7026 (LII)](https://www.law.cornell.edu/regulations/california/11-CCR-7026) · [CPPA Regulations page](https://cppa.ca.gov/regulations/) · [CCPA Regulations eff. Jan. 1, 2026 (CPPA PDF)](https://cppa.ca.gov/regulations/pdf/ccpa_statute_eff_20260101.pdf) · [CPPA CCPA Updates rulemaking page](https://cppa.ca.gov/regulations/ccpa_updates.html) · [Approved regulations text (Sept. 2025\)](https://cppa.ca.gov/regulations/pdf/ccpa_updates_cyber_risk_admt_appr_text.pdf) · [Cal. Civ. Code § 1798.135 (Justia)](https://law.justia.com/codes/california/code-civ/division-3/part-4/title-1-81-5/section-1798-135/) · [Cal. Civ. Code § 1798.140 (Justia)](https://law.justia.com/codes/california/code-civ/division-3/part-4/title-1-81-5/section-1798-140/) · [Cal. Prob. Code § 4121 (Justia)](https://law.justia.com/codes/california/code-prob/division-4-5/part-2/chapter-2/section-4121/) · [CPPA Honda stipulated order (Mar. 2025\)](https://www.cppa.ca.gov/regulations/pdf/20250307_hmc_order.pdf) · [ZwillGen on Honda settlement](https://www.zwillgen.com/privacy/cppa-settles-with-honda-over-alleged-privacy-violations/) · [Patelco CCPA Authorized Agent Form](https://www.patelco.org/wp-content/uploads/2023/05/CCPA-Authorized-Agent-Form.pdf) · [How does Permission Slip work?](https://innovation.consumerreports.org/how-does-permission-slip-work/) · [CR: early look at agent requests (2022)](https://innovation.consumerreports.org/an-early-look-at-how-companies-handle-ccpa-requests-submitted-by-authorized-agents/) · [CPPA DROP page](https://www.cppa.ca.gov/data_brokers/) · [Greenberg Traurig on Jan. 1, 2026 regs](https://www.gtlaw.com/en/insights/2025/9/revised-and-new-ccpa-regulations-set-to-take-effect-on-jan-1-2026-summary-of-near-term-action-items)

## **2\. HIPAA authorization and right-of-access directive**

**A. Title:** HIPAA "Uses and disclosures for which an authorization is required," 45 CFR § 164.508 (core elements § 164.508(c); text last amended 78 FR 5699, Jan. 25, 2013), and the individual's third-party access directive, 45 CFR § 164.524(c)(3)(ii). Related: 45 CFR § 164.509 reproductive-health attestation (89 FR 33063, Apr. 26, 2024), vacated June 18, 2025\. Example forms: UCLA Health "Authorization for Release of Protected Health Information," Form \#30910 Rev. 02/14; New York OCA Official Form No. 960 "Authorization for Release of Health Information Pursuant to HIPAA"; HIPAA Journal sample release form.

**B. Blurb:** A disclosure grant whose validity is a checklist the holder can test.

### **C. Background**

**1\. Who it comes from:** HHS sets the required content in the Privacy Rule; the HHS Office for Civil Rights (OCR) enforces it. There is no single federal form. Covered entities (hospitals, plans), courts (NY OCA), and template publishers draft forms; the patient or a personal representative signs each instance.

**2\. Key lesson for AI-agent authorization:** **Validity is defined as a closed list of required fields and statements, and an instrument missing any one of them "is not valid," so the grant can be machine-validated against a schema before any data moves.** HIPAA lists six core elements and three required notices, plus defect rules (expired, incomplete, known revoked, known false). An agent-mandate format can copy this: required fields for data description, recipient, purpose, expiry, signature, and representative authority, with a validator that rejects the token outright. The defect list also defines when a holder may no longer rely on a grant, which maps to revocation lists and expiry checks.

**3\. The instrument:**

•      **Scenarios.** Disclosures outside treatment, payment and operations: to lawyers, insurers, employers, researchers, family, marketing, sale of PHI, psychotherapy notes.  
•      **Parties.** Grantor: the individual or a personal representative (who must state their authority). Discloser: the covered entity named or described. Recipient: named persons or a class of persons.  
•      **Power delegated.** Permission for the holder to use or disclose specified PHI to a specified recipient for stated purposes. It does not compel disclosure.  
•      **Limits.** Each purpose must be described; "at the request of the individual" suffices when the patient initiates. Psychotherapy notes need their own authorization. Treatment or payment generally cannot be conditioned on signing (§ 164.508(b)(4)).  
•      **Duration.** An expiration date or event is mandatory. Research may use "end of the research study" or "none." UCLA's form defaults to 12 months if left blank.  
•      **Revocation.** Any time, in writing, except where the entity already relied on it (§ 164.508(b)(5)).  
•      **Validation.** The holder checks the elements, signature, expiry, and known revocation, and must retain the signed form for six years (§ 164.530(j)).  
•      **The access-directive alternative.** Under § 164.524(c)(3)(ii), the patient can direct the entity to send a copy of their PHI to a designated person. The request must be in writing, signed, and clearly identify the recipient and where to send it. It is a right, not a permission: the entity must provide the copy.

**4\. Context:** The authorization rule dates to the Privacy Rule (final Dec. 2000, amended Aug. 14, 2002; compliance April 2003). The 2013 Omnibus Rule added sale-of-PHI and marketing provisions. Release-of-information is a large business handled by vendors such as Ciox (now Datavant). Enforcement has focused on access: OCR announced its 53rd Right of Access Initiative action in March 2025, a \$200,000 penalty for delayed delivery to a personal representative. In 2023 there were 13 access actions totaling \$4.18 million.

**5\. Stability and variants:** Section 164.508 has been unchanged since 2013\. Two legal shifts matter:

•      *Ciox Health, LLC v. Azar*, No. 18-cv-0040 (D.D.C. Jan. 23, 2020\) vacated the third-party directive except for electronic copies of PHI in an EHR, and confined the patient-rate fee cap to the patient's own requests. Paper or non-EHR transfers to third parties now need a § 164.508 authorization.  
•      The 2024 Reproductive Health Care Privacy Rule added § 164.509, requiring a signed attestation that requested PHI would not be used against lawful reproductive care. In *Purl v. HHS* (N.D. Tex., June 18, 2025\) nearly all of the rule was vacated nationally. HHS did not appeal, and the intervenors' appeal was dismissed by the Fifth Circuit on Sept. 10, 2025\. Notice-of-privacy-practices updates tied to 42 CFR Part 2 survived (deadline Feb. 16, 2026). As of Oct. 2026 the eCFR still prints § 164.509 with no vacatur note, so text-scraping validators can be misled. (The HHS model attestation linked in the source list is therefore obsolete.)  
•      State overlays add fields. New York's OCA-960 adds separate initials for HIV, alcohol/drug and mental-health information, and a separate grant to "discuss" PHI with a named attorney.

### **C2. Drill-down: the operative clause**

"A valid authorization under this section must contain at least the following elements: (i) A description of the information to be used or disclosed that identifies the information in a specific and meaningful fashion. (ii) The name or other specific identification of the person(s), or class of persons, authorized to make the requested use or disclosure. (iii) The name or other specific identification of the person(s), or class of persons, to whom the covered entity may make the requested use or disclosure. (iv) A description of each purpose of the requested use or disclosure. ... (v) An expiration date or an expiration event that relates to the individual or the purpose of the use or disclosure. ... (vi) Signature of the individual and date. If the authorization is signed by a personal representative of the individual, a description of such representative's authority to act for the individual must also be provided."

— 45 CFR § 164.508(c)(1) (ellipses omit the research and "at the request of the individual" sentences)

"An authorization is not valid, if the document submitted has any of the following defects: (i) The expiration date has passed or the expiration event is known by the covered entity to have occurred; (ii) The authorization has not been filled out completely, with respect to an element described by paragraph (c) of this section, if applicable; (iii) The authorization is known by the covered entity to have been revoked; (iv) The authorization violates paragraph (b)(3) or (4) of this section, if applicable; (v) Any material information in the authorization is known by the covered entity to be false."

— 45 CFR § 164.508(b)(2)

The grantor is the individual. Two grantees appear: the discloser (element ii) and the recipient (element iii). The verb is "authorized to make the requested use or disclosure" — permission, not command.

The object is PHI described "in a specific and meaningful fashion." Scope limiters are recipient, purpose, and expiry. Required statements (§ 164.508(c)(2)) add notice of revocation rights, the no-conditioning rule, and the risk of redisclosure outside HIPAA. The form must be in plain language, and the patient gets a copy (§ 164.508(c)(3)–(4)).

Not delegated: the recipient gets no HIPAA duty and no onward control, which is why the redisclosure warning is mandatory. The holder is not bound to disclose under an authorization; it is bound only when the patient uses the § 164.524 access directive.

### **D. Outline of the full instrument**

1\.     Identification — patient name, DOB, record number (UCLA adds last four SSN digits).  
2\.     Discloser — named facility or provider (UCLA checkboxes per hospital; OCA-960 item 7).  
3\.     Recipient — name and address of person or class (OCA-960 item 8).  
4\.     Information to release  
a.     Record types and date range (discharge summary, labs, imaging, billing).  
b.     Sensitive categories with separate initials (HIV, substance use, mental health; psychotherapy notes excluded).  
c.      Optional grant to discuss PHI with a named attorney or agency (OCA-960 item 9(b)).  
5\.     Purpose — "at request of individual" or other (OCA-960 item 10).  
6\.     Expiration date or event (OCA-960 item 11; UCLA default 12 months).  
7\.     Required statements — revocation right and method, no-conditioning, redisclosure warning.  
8\.     Signature block — signer, date, representative name and authority (OCA-960 items 12–13), witness if needed.  
9\.     Copy to patient and retention by the holder.

The fields map one-to-one onto § 164.508(c). State-law fields stack on top for sensitive categories that federal law alone does not single out.

### **E. Insights and observations**

•      **A schema plus a revocation check equals validity.** Only two of the five defect rules need outside knowledge ("known" revoked, "known" false). The rest are pure document checks, ideal for automated pre-flight validation.  
•      **Two instruments, opposite force.** An authorization is permissive and holder-discretionary. An access directive is mandatory and narrow (EHR, electronic, after *Ciox*). Agent designers should distinguish "may share" grants from "must deliver" directives.  
•      **Price follows the instrument.** After *Ciox*, a third party using a patient-signed authorization pays commercial rates, while the same records via the patient's own access request carry the cost-based cap. Records vendors and law firms route requests accordingly.  
•      **The redisclosure warning is an honest statement of a missing control.** Once data leaves, HIPAA stops. Agent systems that pass data to downstream tools should carry a similar label and, better, a usage constraint that travels with the data.  
•      **Purpose-attestation is fragile law.** The § 164.509 attestation (a requester-signed statement of non-prohibited purpose) lasted about 14 months before vacatur. It remains a useful pattern, akin to DPPA certifications (item 20), but depends on agency authority.  
•      **Stale regulatory text is a live hazard.** The eCFR still shows vacated § 164.509. Compliance engines should key on legal-status metadata, not just published text.  
•      **Representative authority must be described, not merely asserted.** Element (vi) requires the representative to state the source of authority — a direct parallel to an agent presenting a chain of delegation.

**Sources:** [45 CFR 164.508 (eCFR)](https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-E/section-164.508) · [45 CFR 164.524 (eCFR)](https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-E/section-164.524) · [45 CFR 164.509 (eCFR)](https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-C/part-164/subpart-E/section-164.509) · [HHS: Court order on right of access (Ciox)](https://www.hhs.gov/hipaa/court-order-right-of-access/index.html) · [UNC SOG: status of 2024 HIPAA rule (Aug. 2025\)](https://canons.sog.unc.edu/blog/2025/08/22/update-2024-hipaa-final-rule/) · [NatLawReview: appeals dropped in Purl](https://natlawreview.com/article/appeals-dropped-decision-vacating-hipaa-reproductive-health-privacy-rule-confirming) · [UCLA Form 30910](https://www.uclahealth.org/sites/default/files/documents/release-of-health-info-english_1.pdf) · [OCA Official Form 960](https://www.nyep.uscourts.gov/forms/presentence/HIPAA%20OCA-Form-960.pdf) · [HIPAA Journal: HIPAA release form](https://www.hipaajournal.com/hipaa-release-form/) · [Healthcare Law Insights: right of access enforcement](https://healthcarelawinsights.com/2026/02/enforcement-ramps-up-on-patient-right-of-access-what-providers-need-to-know)

## **3\. FERPA prior written consent**

**A. Title:** FERPA "prior consent to disclose" rule, 34 CFR § 99.30 (last amended 69 FR 21671, Apr. 21, 2004), with § 99.31 (consent exceptions; last amended Dec. 2, 2011), § 99.32 record of disclosures (Dec. 9, 2008), § 99.33 redisclosure limits (Dec. 2, 2011\) and § 99.67 five-year debarment. Statute: 20 U.S.C. § 1232g(b). Example forms: Peabody Institute of the Johns Hopkins University "Student Authorization to Release Education Record Form" (marked SAO-11/13); University of Oklahoma Open Records Office "FERPA Consent Form – Permission to Release Educational Record Information" (no revision date shown).

**B. Blurb:** Name the records, the purpose, the recipient — and the school logs it.

### **C. Background**

**1\. Who it comes from:** The U.S. Department of Education sets the rule; its Student Privacy Policy Office (SPPO) enforces it. There is no federal form. Each school or district drafts its own consent form, and the parent or "eligible student" (18 or in postsecondary school) signs it.

**2\. Key lesson for AI-agent authorization:** **A valid grant needs exactly three scope fields — which records, what purpose, which recipient — and the data holder, not the agent, must keep a per-subject log of every request and disclosure that the subject can inspect.** This is a minimal mandate schema plus a holder-side audit trail. Agent systems should pair narrow, purpose-bound tokens with a disclosure ledger stored alongside the subject's record. FERPA also shows the recipient inheriting a no-redisclosure duty enforced by debarment — a model for revoking an agent's or vendor's access after misuse.

**3\. The instrument:**

•      **Scenarios.** A student lets a school release transcripts, conduct records, financial-aid or bursar data to an employer, scholarship body, parent of a non-dependent student, attorney, or agency.  
•      **Parties.** Grantor: parent or eligible student. Holder: the "educational agency or institution" receiving Department funds. Recipient: a party or class of parties.  
•      **Power delegated.** Permission for the school to disclose personally identifiable information (PII) from education records. It is permissive; except for disclosures to the parent or student, nothing obliges the school to release (§ 99.31(d)).  
•      **Required content.** Signed and dated, specifying records, purpose, and recipient (§ 99.30(a)–(b)).  
•      **Electronic consent.** Allowed if the record identifies and authenticates the person and shows their approval (§ 99.30(d)).  
•      **Copies.** On request, the grantor gets a copy of what was disclosed (§ 99.30(c)).  
•      **Duration and revocation.** The regulation is silent. Peabody's form lasts until revoked in writing, without prejudice to earlier releases; Oklahoma's form has no duration or revocation clause.  
•      **Recipient duties.** The recipient may not redisclose without consent and may use the data only for the stated purpose (§ 99.33(a)). The school must tell the recipient about this limit (§ 99.33(d)).  
•      **Logging.** The school must log each request and disclosure with the requester's identity and legitimate interest, kept as long as the record (§ 99.32(a)).

**4\. Context:** FERPA (the Buckley Amendment) was enacted in 1974\. Every K–12 district and college taking Department funds is covered, so the consent form is ubiquitous. Enforcement is administrative only: SPPO investigates, and the remedy is withholding funds, cease-and-desist, or DOJ suit. There is no private right of action (*Gonzaga University v. Doe*, 2002); a bill in the 119th Congress would add one. Recent enforcement has focused on parental access: ED found the California Department of Education out of compliance (Jan. 28, 2026\) and four Kansas districts in violation (Apr. 17, 2026\) over gender-identity records withheld from parents.

**5\. Stability and variants:** The consent elements have been stable for decades, with electronic-signature language added in 2004\. The 2008 and 2011 amendments reworked redisclosure and recordkeeping for state authorities. Forms vary widely: some schools use free-text fields (Peabody), others record-type examples (Oklahoma), and many now use portal-based proxy or "FERPA release" toggles. State student-privacy laws (e.g., California SOPIPA) layer vendor rules on top.

### **C2. Drill-down: the operative clause**

"The parent or eligible student shall provide a signed and dated written consent before an educational agency or institution discloses personally identifiable information from the student's education records, except as provided in § 99.31. ... The written consent must: (1) Specify the records that may be disclosed; (2) State the purpose of the disclosure; and (3) Identify the party or class of parties to whom the disclosure may be made."

— 34 CFR § 99.30(a)–(b)

Paraphrase (Peabody form): by signing, the student permits the Institute to release the listed records to the named recipient for the stated purpose. The consent continues until revoked in writing, and the student releases the Institute from liability for complying. A note to the recipient bars redisclosure without the student's further written consent or legal authority.

— Peabody Institute, Student Authorization to Release Education Record Form, SAO-11/13

The grantor is the parent or eligible student; the holder is the institution. The trigger verb is "discloses," conditioned on prior consent. Scope limiters are the three required fields.

Not delegated: the recipient's freedom to pass data on, since § 99.33 attaches a redisclosure bar; and any obligation on the school to release, since § 99.31(d) makes disclosures discretionary. The holder is bound in the negative sense: it may not disclose without valid consent or an exception, on pain of loss of federal funds.

### **D. Outline of the full instrument**

1\.     Student identification — name, date of birth, student ID (Oklahoma adds optional SSN).  
2\.     Recipient — name, address, phone; "Release To" if different from requester (Oklahoma).  
3\.     Records to release — free text or examples (transcripts, conduct, police, housing, employment, financial aid, bursar).  
4\.     Purpose — free-text reason.  
5\.     Delivery method — email, fax, mail, in person (Oklahoma).  
6\.     Authorization statement and signature — signature, effective date, contact details.  
7\.     Duration and revocation — until revoked in writing (Peabody); absent on Oklahoma's form.  
8\.     Release and hold-harmless clause (Peabody).  
9\.     Notice to recipient — redisclosure prohibition (Peabody; mirrors § 99.33(d)).  
10\.  Office use — date received and staff signature.  
11\.  Holder-side, outside the form: the § 99.32 disclosure log entry, and the § 99.33(d) notice to the recipient of the redisclosure bar.

The form carries the three scope fields; the holder's log and recipient notice complete the control loop.

### **E. Insights and observations**

•      **The log is the subject's audit right.** Section 99.32 logs live with the education records, so a student reviewing their file also sees who accessed it — a subject-facing access log, rarer and stronger than an internal audit trail.  
•      **Logging has a blind spot exactly at consent.** Section 99.32(d)(3) exempts disclosures to a party with written consent from the log, so consent-based releases are tracked only through retained forms. Agent systems should log consented actions too.  
•      **Debarment is the recipient-side kill switch.** Under § 99.67(e), a third party that improperly rediscloses may be denied access to PII "for at least five years" — a revocation of the recipient, not of the grant, and a useful pattern for misbehaving agents or vendors.  
•      **Purpose binds downstream use.** Section 99.33(a)(2) lets the recipient's officers and agents use the data only for the purposes of the disclosure. Purpose is a field that travels with the data.  
•      **Missing duration is a common form defect.** FERPA does not require an expiry, and Oklahoma's form has none. Open-ended consents are hard to audit; agent tokens should always carry expiry.  
•      **The school-official exception swallows vendor consent.** Cloud and AI ed-tech vendors usually receive data as "school officials" under § 99.31(a)(1), without student consent. Agent builders serving schools should expect contract controls, not student consent, to govern them.  
•      **Electronic consent rules are technology-neutral:** authenticate the person and capture approval of the content. That standard maps cleanly to signed, verifiable credentials.

**Sources:** [34 CFR 99.30 (eCFR)](https://www.ecfr.gov/current/title-34/subtitle-A/part-99/subpart-D/section-99.30) · [34 CFR 99.31 (eCFR)](https://www.ecfr.gov/current/title-34/subtitle-A/part-99/subpart-D/section-99.31) · [34 CFR 99.32 (eCFR)](https://www.ecfr.gov/current/title-34/subtitle-A/part-99/subpart-D/section-99.32) · [34 CFR 99.33 (eCFR)](https://www.ecfr.gov/current/title-34/subtitle-A/part-99/subpart-D/section-99.33) · [34 CFR 99.67 (eCFR)](https://www.ecfr.gov/current/title-34/subtitle-A/part-99/subpart-E/section-99.67) · [Peabody FERPA form SAO-11/13](https://peabody.jhu.edu/wp-content/uploads/2019/05/FERPA-FORM-11.13.pdf) · [University of Oklahoma FERPA Consent Form](https://www.ou.edu/content/dam/openrecords/docs/ferpa-consent-form.pdf) · [JHU Registrar: What is FERPA](https://registrar.jhu.edu/ferpa-compliance/what-is-ferpa) · [CRS R46799, FERPA: Legal Issues (June 2026\)](https://www.everycrsreport.com/files/2026-06-05_R46799_ab046875ffe38de60406c87fb0aa78a0fbb1ba84.html)

## **4\. IRS Form 2848 and Form 8821**

**A. Title:** IRS Form 2848, *Power of Attorney and Declaration of Representative* (Rev. January 2021; Instructions Rev. September 2021). IRS Form 8821, *Tax Information Authorization* (Rev. January 2021; Instructions Rev. September 2021). Digital equivalents: "Submit Forms 2848 and 8821 Online" (IRS.gov/Submit2848) and the all-digital POA/TIA requests in Tax Pro Account.

**B. Blurb:** Read-only versus act-for-me, scoped by tax, form and year, in one registry.

### **C. Background**

**1\. Who it comes from:** The Internal Revenue Service (Treasury). The governing rules are the Conference and Practice Requirements at 26 CFR 601.501–601.509 and Treasury Circular 230 (31 CFR Part 10). The taxpayer, or more often the practitioner, fills in the form; the taxpayer signs Part I and the representative signs Part II.

**2\. Key lesson for AI-agent authorization:** **Split "see my data" from "act for me" into two separate grants, and scope each by a tuple of (tax type × form number × period), with dangerous powers listed as explicit opt-ins and opt-outs.** Form 8821 is a read scope only; Form 2848 adds a write scope, and even then, signing a return or adding a sub-agent needs a separate checkbox (line 5a). Every grant is written to one central registry (the CAF), which IRS staff check in real time. A new grant for the same tuple automatically revokes the old one unless the principal opts to keep it, so the registry stays consistent.

**3\. The instrument:**

•      **Scenarios.** Form 2848 covers audits, collection, appeals, penalty abatement and any matter where someone must speak or sign for the taxpayer. Form 8821 covers read-only access: transcripts for a lender, a bookkeeper monitoring notices, payroll providers, or a non-credentialed helper.  
•      **Parties.** The taxpayer (individual, spouses separately, or entity via an authorized officer) is the principal. Under 2848 the agent must be a "recognized representative" in one of Part II designations (a)–(r): attorney, CPA, enrolled agent, officer, full-time employee, family member, enrolled actuary, unenrolled preparer (limited), student, and others. Under 8821 the "designee" can be anyone, including a company.  
•      **Limits on the number of agents.** Form 2848 names up to four representatives per form, with more on extra forms. Only two may receive copies of IRS notices.  
•      **Powers.** Line 3 grants receipt and inspection of confidential information plus any act the taxpayer can perform for the listed matters, including signing agreements, consents and waivers. Line 5a adds opt-in powers: Intermediate Service Provider access, authorizing disclosure to third parties, substituting or adding representatives, and signing a return (only in narrow cases such as illness, extended absence, or IRS permission).  
•      **Hard limit.** Line 5b bars the representative from endorsing or negotiating a refund check, or steering refund payments into an account they control. The taxpayer can write in further deletions.  
•      **Scope rules.** Each line-3 row must name the tax, the form, and specific years. The instructions reject "All years," "All periods," or "All taxes." The CAF records future periods only up to 3 years after December 31 of the year the IRS receives the form.  
•      **Duration and revocation.** There is no fixed expiry. A later form for the same matters revokes earlier ones (line 6 for 2848, line 5 for 8821\) unless the "retain" box is checked and copies are attached. The taxpayer revokes by writing "REVOKE" across a copy, with a fresh signature and date; the representative withdraws by writing "WITHDRAW." In Tax Pro Account, a withdrawal is removed from the CAF immediately.  
•      **Counterparty validation.** IRS employees check the CAF before disclosing information. Each representative has a nine-digit CAF number. Line 4 "specific use" forms are not recorded on the CAF; they go straight to the IRS office handling the matter.

**4\. Context:**

•      **Volume.** Nearly 7 million Forms 2848 and 8821 were filed in 2025, per a former IRS executive writing in Accounting Today (April 2026). In FY 2021 the IRS processed 4.19 million, up 38% from FY 2020 (National Taxpayer Advocate blog, Jan. 2022).  
•      **Processing.** The historic target was 5 days. Average processing ran 22 to 70+ days in 2020–2021 and about 10 business days in 2026\. CAF work consumed over 972,000 staff hours in one year.  
•      **Origin.** Representation rules date to the Enrolled Agent program (1884). The CAF and the current 601.503 content rules were in place well before the 2021 revisions.  
•      **Content rule.** 26 CFR 601.503(a) requires taxpayer identity, representative identity, a description of the matter (tax type, form number, periods), and "a clear expression of the taxpayer's intention concerning the scope of authority granted." A non-IRS durable power of attorney can work, but it must have a Form 2848 attached for CAF entry.  
•      **Failure modes.** Rejections come from vague periods, missing signatures, or the wet-ink requirement for fax/mail. Stale authorizations linger when staff leave firms. Fraudsters have used 8821s to harvest transcripts, which drove the identity-proofing and remote e-signature attestation rules.

**5\. Stability and variants:** Both forms have been stable since the January 2021 revision, which added a line for an Intermediate Service Provider and allowed e-signatures for online submission. The IRS added an "Items to consider while completing Form 2848" note on July 8, 2026; no new form revision was found. Channels are paper or fax (wet ink only), the online upload (e-signatures accepted), and Tax Pro Account. Tax Pro Account is limited to individual taxpayers and, for POAs, to attorneys, CPAs, EAs, enrolled actuaries and enrolled retirement plan agents. Sister forms include Form 56 (fiduciary) and state POA forms. Circular 230 amendments were proposed on December 20, 2024 (adding "technological competency"); finalization could not be verified.

### **C2. Drill-down: the operative clause**

Form 2848, line 2: "...hereby appoints the following representative(s) as attorney(s)-in-fact: ... to represent the taxpayer before the Internal Revenue Service and perform the following acts:"

Line 3: "Acts authorized (you are required to complete line 3). Except for the acts described in line 5b, I authorize my representative(s) to receive and inspect my confidential tax information and to perform acts I can perform with respect to the tax matters described below. For example, my representative(s) shall have the authority to sign any agreements, consents, or similar documents (see instructions for line 5a for authorizing a representative to sign a return)."

Form 8821, line 3: "Each designee is authorized to inspect and/or receive confidential tax information for the type of tax, forms, periods, and specific matters you list below."

— IRS Form 2848 (Rev. 1-2021), Part I lines 2–3; IRS Form 8821 (Rev. 1-2021), line 3

The grantor is the taxpayer named on line 1\. The grantee is each representative on line 2, identified by name, address and CAF number. Form 2848 has two delegating verbs: "represent" (advocacy) and "perform acts I can perform" (execution). Both are bounded by "the tax matters described below," a table of type of tax × form number × year(s) or period(s).

The 8821 clause is narrower: "inspect and/or receive" only. The 8821 instructions say the designee may not speak for the taxpayer, advocate a position, sign waivers or closing agreements, re-authorize disclosure, or substitute another party.

On the 2848, "Except for the acts described in line 5b" puts a fixed carve-out ahead of the grant: a refund check can never be endorsed or redirected to the representative's account. Line 5a lists the powers that are not implied and need a checkbox: sub-delegation, third-party disclosure, ISP access, and return signing. The IRS is bound to honor the grant through the CAF record; for non-CAF "specific use" forms, the receiving office is bound directly.

### **D. Outline of the full instrument**

1\.     Form 2848 Part I — Power of Attorney  
a.     Line 1: taxpayer name, address, TIN, plan number.  
b.     Line 2: up to four representatives, with CAF number, PTIN, phone, and a checkbox to send copies of notices (maximum two).  
c.      Line 3: acts authorized, with a matter table (description, form number, years/periods).  
d.     Line 4: specific use not recorded on CAF.  
e.     Line 5a: additional acts (ISP access, disclosure to third parties, substitute/add representatives, sign a return, other).  
f.      Line 5b: acts not authorized (the check-negotiation bar plus taxpayer-listed deletions).  
g.     Line 6: retention/revocation of prior POAs.  
h.     Line 7: taxpayer signature, with a certification of authority for entity signers.  
2\.     Form 2848 Part II — Declaration of Representative: under penalties of perjury, the representative attests to Circular 230 status and a designation code (a)–(r), with jurisdiction, license number and signature.  
3\.     Form 8821  
a.     Line 1: taxpayer.  
b.     Line 2: designee(s), with CAF number and notice copies.  
c.      Line 3: tax information table (type, form, period, specific matter) plus an ISP checkbox.  
d.     Line 4: specific use.  
e.     Line 5: retention/revocation.  
f.      Line 6: taxpayer signature. Designees do not sign.

The taxpayer's half defines scope. The representative's sworn half proves the agent is eligible. The CAF ties the two together into a lookup record that front-line staff can query.

### **E. Insights and observations**

•      **Two-sided credential.** Form 2848 is only valid with the agent's own perjury-backed attestation of licensure. Form 8821 has no agent signature because it grants no power to act. For AI agents: "act" scopes should require an attested agent identity, while "read" scopes can be issued to less-verified designees.  
•      **No wildcards.** The ban on "All years/All taxes" and the 3-future-year cap are anti-wildcard rules a token issuer could copy directly: no \* scopes, and bounded forward validity.  
•      **Last write wins, per scope tuple.** Automatic revocation is keyed to the same matter and period, with an explicit "retain" opt-out. This avoids both orphaned grants and accidental mass revocation.  
•      **Payment-rail carve-out.** The line 5b ban on routing refunds to the representative's account is fixed and non-waivable. It targets the most common abuse, diverting money. Agent payment mandates should similarly forbid payee-account changes without a separate, step-up grant.  
•      **Identity-proofed e-signatures.** Electronic signatures are allowed only through the online channel. For remote signing with no prior relationship, the submitter must attest to identity verification with government photo ID and secondary documents. Fax and mail still require wet ink.  
•      **Push versus pull consent.** In Tax Pro Account the practitioner proposes a grant and the taxpayer approves it inside their own IRS Online Account, and it records to the CAF immediately. This mirrors an OAuth consent screen hosted by the resource owner and replaces the 10–70-day manual queue.  
•      **Ex-employee drift.** Authorizations name individuals, so grants stay live after staff leave a firm. Commentators push for "Business CAF" numbers tied to an EIN. Compare the USPTO's Customer Number approach in item 12\.

**Sources:** [About Form 2848](https://www.irs.gov/forms-pubs/about-form-2848) · [Form 2848 PDF (Rev. 1-2021)](https://www.irs.gov/pub/irs-pdf/f2848.pdf) · [Instructions for Form 2848](https://www.irs.gov/instructions/i2848) · [About Form 8821](https://www.irs.gov/forms-pubs/about-form-8821) · [Form 8821 PDF (Rev. 1-2021)](https://www.irs.gov/pub/irs-pdf/f8821.pdf) · [Instructions for Form 8821](https://www.irs.gov/instructions/i8821) · [Submit Forms 2848 and 8821 Online](https://www.irs.gov/tax-professionals/submit-forms-2848-and-8821-online) · [Tax Pro Account](https://www.irs.gov/tax-professionals/tax-pro-account) · [26 CFR 601.503 (LII)](https://www.law.cornell.edu/cfr/text/26/601.503) · [NTA Blog: The IRS hasn't processed my POA (Jan. 2022\)](https://www.taxpayeradvocate.irs.gov/news/nta-blog/nta-blog-the-irs-hasnt-processed-my-power-of-attorney-form-should-i-submit-another/2022/01) · [Accounting Today: The IRS CAF processing crisis (2026)](https://www.accountingtoday.com/opinion/the-irs-caf-processing-crisis) · [IR-2024-315: proposed Circular 230 regulations](https://irs.gov/newsroom/treasury-and-irs-propose-regulations-to-update-rules-for-tax-professionals-who-can-practice-before-the-irs)

## **5\. USCIS Form G-28 (and EOIR-28/27)**

**A. Title:** DHS/USCIS Form G-28, *Notice of Entry of Appearance as Attorney or Accredited Representative* (edition 09/17/18, OMB No. 1615-0105). Sister forms: G-28I (attorneys abroad). DOJ EOIR forms: EOIR-28, *Notice of Entry of Appearance as Attorney or Representative Before the Immigration Court*, and EOIR-27 (Board of Immigration Appeals). Limited-scope versions: EOIR-61 (court) and EOIR-60 (BIA).

**B. Blurb:** The agent's credentials are part of the mandate; mail routing is opted in separately.

### **C. Background**

**1\. Who it comes from:** The Department of Homeland Security, through USCIS, under 8 CFR 103.2 and 8 CFR Part 292\. It is also used before ICE and CBP. The attorney or accredited representative fills it in and signs Part 5\. The client (applicant, petitioner, requestor, respondent, or an entity's signatory) signs Part 4\.

**2\. Key lesson for AI-agent authorization:** **Make the agent's verifiable credentials and the principal's consent two signed halves of one per-matter instrument, and make "where do results get delivered" a separate, item-by-item election.** In Parts 1–2, the representative attests under penalty of perjury to bar admission, bar number, and freedom from disciplinary orders, or to DOJ accreditation and a recognized organization — a self-asserted credential the agency can check against a registry. Part 4 covers consent to representation, a Privacy Act disclosure consent, and three separate checkboxes for where originals and secure identity cards go. Agent designs should likewise separate "may act," "may see," and "receives the deliverable," especially for high-value artifacts like ID cards.

**3\. The instrument:**

•      **Scenarios.** Any USCIS benefit filing (I-130, I-485, I-129, N-400, etc.), ICE matters (detention, bond with ICE), and CBP matters. The form is filed with the application or petition it relates to.  
•      **Parties.** The client is the principal. The grantee is one attorney (a member in good standing of a U.S. bar, Part 2 item 1\) or one DOJ-accredited representative of a recognized nonprofit (item 2). Item 3 covers a practitioner "associated with" the attorney of record, appearing for a limited purpose at that attorney's request. Item 4 covers supervised law students or graduates under 8 CFR 292.1(a)(2).  
•      **Scope.** Part 3 selects one agency (USCIS, ICE or CBP) and lists "the form numbers or specific matter in which appearance is entered," plus a receipt number. Under 8 CFR 292.4(a), the appearance is recognized "until the conclusion of the matter for which it was entered," and "a new form must be filed with an appeal."  
•      **Powers.** Under 8 CFR 292.5(a), any notice, service, filing, motion, or waiver is given to or made by "the attorney or representative of record." Representatives may also examine the record (292.4(b)) and take part in interviews (292.5(b)).  
•      **Delivery elections.** USCIS mails notices to both client and representative by default. The client may check boxes to send original notices to the representative's business address (1.a), send secure identity documents such as Green Cards, EADs, and travel documents there (1.b), or send I-94 notices to the client (1.c). If notices go to the representative, the client still gets a courtesy copy.  
•      **Revocation.** The representative withdraws by letter with the receipt number. Substitution happens through written withdrawal or a new G-28 filed by a new representative (292.4(a)). There is no expiry date; the appearance ends when the matter ends.  
•      **Counterparty validation.** USCIS checks completeness, matching names, signatures, and the current edition. Signatures must be handwritten in ink; photocopies, faxes, and scans of the original are accepted, but a stamped or typewritten name is not. Electronic filing through the USCIS online account links the representative's account to the client's case.

**4\. Context:**

•      **Volume.** The 2023 Federal Register notice estimates about 4.18 million paper G-28s, 464,581 online G-28s, and 31,362 G-28Is per year — about 4.68 million responses and 4.3 million burden hours.  
•      **Origin.** The G-28 is decades old. Its current regulatory base is 8 CFR Part 292 and 8 CFR 292.4–292.5; eCFR shows no 2024–2026 amendments to 292.5.  
•      **Failure modes.** USCIS lists common rejections: unsigned forms, missing Part 1 data, name mismatches, correction fluid, old editions, and G-28s sent alone to a lockbox. The "notario" fraud problem is why the form demands bar or accreditation attestations and a disciplinary-order statement. In immigration court, EOIR requires practitioners to register in eRegistry and file through ECAS.

**5\. Stability and variants:**

•      **Current edition.** The edition is 09/17/18. AILA reported its publication on September 17, 2018, with a grace period for older editions to November 19, 2018\. The uscis.gov/g-28 landing page still references the 05/23/18 edition, which is stale text.  
•      **Pending revision.** A 2023 notice (88 FR 48489\) and a September 2024 30-day notice proposed a "designated paralegal" for limited customer-service contact. A July 25, 2025 notice (90 FR 35309; comments reopened to January 12, 2026\) instead deletes the paralegal option. It also adds a parent or guardian signature for clients under 14, bans auto-pen and typed signatures, and rejects e-signatures made outside the USCIS online account. Publication of a new edition could not be confirmed as of October 2026\.  
•      **EOIR forms.** EOIR-28 (immigration judge) and EOIR-27 (BIA) are case-specific. EOIR-28 has a scope checkbox: all proceedings, custody and bond only, or all except custody and bond. Once filed, the practitioner must continue until a motion to withdraw or substitute is granted. Since November 14, 2022, EOIR-61 and EOIR-60 allow limited document-assistance appearances without an ongoing duty.

### **C2. Drill-down: the operative clause**

"I have requested the representation of and consented to being represented by the attorney or accredited representative named in Part 1\. of this form. According to the Privacy Act of 1974 and U.S. Department of Homeland Security (DHS) policy, I also consent to the disclosure to the named attorney or accredited representative of any records pertaining to me that appear in any system of records of USCIS, ICE, or CBP."

"1.a. I request that USCIS send original notices on an application or petition to the business address of my attorney or accredited representative as listed in this form. 1.b. I request that USCIS send any secure identity document (Permanent Resident Card, Employment Authorization Document, or Travel Document) that I receive to the U.S. business address of my attorney or accredited representative ..."

— Form G-28 (Edition 09/17/18), Part 4, Client's Consent to Representation and Signature, Item 1 and Options 1.a–1.b

The grantor is the client, including an "Authorized Signatory for an Entity." The grantee is the single attorney or accredited representative named in Part 1, not a firm. The delegating verbs are "requested ... and consented to being represented" (agency) and "consent to the disclosure" (a Privacy Act data-access waiver).

Scope comes from Part 3: one agency and the listed form numbers or matter. The disclosure consent is broader: any records in any system of records of USCIS, ICE, or CBP.

Not delegated by default: receipt of originals and of secure identity documents. These are separate opt-in requests, because a card sent to a dishonest agent is a known fraud vector. The client cannot authorize a non-qualified person; eligibility comes from Part 2\. The agency is bound by 8 CFR 292.5(a): once the appearance is recognized, notice and service must go through the representative of record.

### **D. Outline of the full instrument**

1\.     Part 1 — Information about the attorney or accredited representative: USCIS online account number, name, address, contact details, and email.  
2\.     Part 2 — Eligibility information  
a.     Item 1: attorney, with licensing jurisdiction(s), bar number, a disciplinary-order statement ("am not / am subject to"), and law firm.  
b.     Item 2: accredited representative, with recognized organization and accreditation date.  
c.      Item 3: associated practitioner appearing for a limited purpose at the request of the attorney of record.  
d.     Item 4: law student or graduate under supervision.  
3\.     Part 3 — Notice of appearance: agency (USCIS, ICE or CBP), form numbers or specific matter, receipt number, the client's role, and client identity data (A-number, USCIS account number).  
4\.     Part 4 — Client's consent: consent to representation and records disclosure, notice and document delivery options 1.a–1.c, and client signature.  
5\.     Part 5 — Signature of attorney or accredited representative, attesting knowledge of 8 CFR 103.2 and Part 292, under penalty of perjury; a signature line for supervised law students or graduates follows.  
6\.     Part 6 — Additional information.

Part 2 makes the agent's credential part of the grant. Part 3 scopes it to one matter. Part 4 is the principal's consent plus routing preferences. Part 5 binds the agent to the regulations.

### **E. Insights and observations**

•      **Credential-in-token.** The agent's license data and a "no current suspension" attestation are inside the mandate. A verifier can reject the grant if the credential is revoked, without contacting the principal. For agents, embed an issuer-verifiable agent credential and its status endpoint in the delegation.  
•      **Single named grantee.** USCIS answered AILA's 2024 request for multiple designated paralegals by saying only one attorney is allowed per G-28. The 2025 draft then removed paralegal delegation altogether. The agency chose one accountable human of record over flexible sub-delegation — the opposite of the USPTO's Customer Number model in item 12\.  
•      **Delivery is a separate scope.** Routing notices and secure documents is opt-in item by item, and a courtesy copy always goes to the principal. Even when the agent is the main channel, the principal keeps an independent notification channel — a strong pattern against silent agent capture.  
•      **Matter-bounded duration.** Authority lasts until "the conclusion of the matter" and must be renewed for appeals. Lifetime is bound to a workflow instance, not a clock.  
•      **Signature integrity is tightening.** The 2025 draft bans auto-pen and typewriter signatures and rejects e-signatures made outside the USCIS online account. Electronic consent is accepted only on the counterparty's own authenticated surface, much like Tax Pro Account in item 4\.  
•      **Graded engagement at EOIR.** EOIR offers full (EOIR-28), partial (custody/bond only), and document-only (EOIR-61) appearances, each with different continuing duties and exit rules (withdrawal needs a judge's leave). Agent mandates can likewise state duty-to-continue and exit conditions, not just permissions.

**Sources:** [USCIS G-28 page](https://www.uscis.gov/g-28) · [Form G-28 (09/17/18) copy](https://torres.house.gov/imo/media/doc/g-28_form.pdf) · [USCIS: Filing Your Form G-28](https://uscis.gov/forms/all-forms/filing-your-form-g-28) · [AILA: USCIS publishes revised G-28 (9/17/18)](https://www.aila.org/library/uscis-publishes-revised-form-g-28-and-extends) · [8 CFR 292.4 (eCFR)](https://www.ecfr.gov/current/title-8/chapter-I/subchapter-B/part-292/section-292.4) · [8 CFR 292.5 (eCFR)](https://www.ecfr.gov/current/title-8/chapter-I/subchapter-B/part-292/section-292.5) · [Draft G-28 Edition xx/xx/25 (regulations.gov)](https://downloads.regulations.gov/USCIS-2008-0037-0309/content.pdf) · [G-28 Table of Changes, July 2025](https://iptp-production.s3.amazonaws.com/media/documents/2025.07.25_USCIS_-_Form_G-28_-_Table_of_Changes.pdf) · [Immigration Policy Tracking: paralegal designation removal](https://immpolicytracking.org/policies/uscis-revises-form-g-28-notice-of-entry-of-appearance-as-attorney-or-accredited-representative-to-disallow-paralegal-designation/) · [AILA: DHS notice of revision of G-28/G-28I](https://www.aila.org/library/dhs-notice-of-revision-of-forms-g-28-and-g-28i) · [Federal Register G-28 notice, July 2023](https://docs.regulations.justia.com/entries/2023-07-27/2023-15938.pdf) · [EOIR: Enter an Appearance](https://www.justice.gov/eoir/Enter-an-Appearance) · [EOIR Policy Manual Ch. 5.3](https://www.justice.gov/eoir/policy-manual-eoir/part-I/chapter-5-3) · [CLINIC: EOIR limited-appearance final rule](https://cliniclegal.org/resources/removal-proceedings/doj-issues-final-rule-allowing-eoir-practitioners-enter-limited-scope)

## **6\. SSA-1696, SSA-89 and CMS-1696**

**A. Title:** Form SSA-1696, *Claimant's Appointment of a Representative* (SSA-1696 (12-2024), mandatory since December 9, 2024; online version "e1696"). Form SSA-89, *Authorization for the Social Security Administration (SSA) To Release Social Security Number (SSN) Verification* (SSA-89 (05-2025), OMB No. 0960-0760). Form CMS-1696, *Appointment of Representative* (Medicare; OMB No. 0938-0950, expires 12/31/2028; CMS lists a revision of 2026-10-01 with minor non-substantive changes).

**B. Blurb:** One-shot, purpose-bound, 90-day consent versus standing representation with fees split off.

### **C. Background**

**1\. Who it comes from:** The Social Security Administration issues SSA-1696 (20 CFR 404.1703–404.1740 and 416.1503–416.1540, plus HALLEX and POMS GN 03910\) and SSA-89 (used with the Consent Based SSN Verification service, CBSV/eCBSV). The Centers for Medicare & Medicaid Services issues CMS-1696 (42 CFR 405.910). For SSA-1696 and CMS-1696, the representative usually fills in the form and both parties sign. The requesting company prepares the SSA-89, the number holder signs it, and the company keeps it.

**2\. Key lesson for AI-agent authorization:** **Use two different grant shapes — a single-use, purpose-coded, short-lived consent for a narrow data check (SSA-89), and a matter-scoped standing mandate with a designated primary agent (SSA-1696) — and keep the agent's compensation and payee in a separate, independently revocable record.** The SSA-89 is a one-time token with a 90-day expiry, one of eight purpose codes, and a named relying party. The SSA-1696 is a long-lived role grant for selected claim types; its fee arrangement (Section 6\) and assignment of fee payment to a firm (Section 5 Part C) can each be updated without changing the authority to act. Agent systems should likewise separate "may act," "gets paid," and "pays whom."

**3\. The instrument:**

•      **SSA-1696 scenarios.** Disability and retirement claims and appeals under Titles II, XVI, VIII and XVIII, continuing disability reviews, and post-entitlement issues. The claimant checks the claim types in Section 4\.  
•      **SSA-1696 parties.** The claimant is the principal. The grantee is one individual per form: an attorney in good standing, or a non-attorney (eligible or not for direct fee payment). SSA does not recognize entities such as law firms as representatives. A firm can be listed as the representative's affiliation (Part B) and as the assignee of fees (Part C).  
•      **Principal representative.** If there are several representatives, there is one form each, and the claimant must name a principal in Section 3\. SSA will "make contact and send notices" only to the principal. If none is named, SSA asks the claimant; failing that, the most recently appointed representative becomes temporary principal (POMS GN 03910, Dec. 2024).  
•      **Agent attestations (Section 5).** Status, past disbarment or suspension, federal program disqualification, licensing actions, and a pledge not to disclose information without the claimant's specific written consent — all signed under penalty of perjury.  
•      **Fees (Section 6).** Options are: request a fee with direct payment, request a fee without direct payment, waive the fee from the claimant (third-party payer), or waive the fee entirely. Any fee generally needs SSA approval through a fee agreement or fee petition. Fee assignment to an entity can be made or rescinded only until the first favorable decision notice.  
•      **Duration and revocation.** No expiry. Naming a new principal does not revoke the old representative; revocation needs "a separate writing that you sign, date, and file with us."  
•      **SSA-89.** The number holder (or parent or guardian) authorizes SSA to match name, SSN and date of birth and report match or no-match to a named company (and its agent). It is for one stated purpose (mortgage, bank account, credit card, loan, retirement account, job, licensing, other). It is "valid only for one-time use" and for 90 days unless the signer writes in another period.  
•      **CMS-1696.** It authorizes a representative to "make requests, present evidence, get information, and receive all communication" for Medicare claims, appeals, grievances and requests. It is valid for one year from signature by both parties; once an appeal is filed, it lasts for that appeal's life. It can be reused for other actions during the year.

**4\. Context:**

•      **Volumes.** SSA's August 2024 final rule (89 FR 67542\) estimated about 1.1 million claimants and 1.1 million representatives signing SSA-1696s per year, about 500,000 fee assignments to entities, about 7,000 entity registrations (SSA-1694), and about 15,382 representative registrations (SSA-1699). About 31,000 registered representatives are affiliated with more than one entity.  
•      **Why the 2024 rule.** It responded to *Marasco & Nesselbush, LLP v. Collins* (1st Cir.). SSA now pays authorized fees directly to entities by EFT, while still appointing only individuals. Phase 1 (registration) began September 30, 2024\. Phase 2 (new SSA-1696, mandatory current form, both signatures, entity payment) began December 9, 2024; obsolete versions and free-form letters are no longer accepted. Appointments made before December 9, 2024 remain valid.  
•      **CBSV.** It costs \$2.25 per verification (since October 1, 2023\) plus a \$5,000 enrollment fee. Paper SSA-89s need a wet signature. Electronic consent runs through the separate eCBSV channel for "Permitted Entities" under section 215 of the Economic Growth, Regulatory Relief, and Consumer Protection Act (2018). CBSV returns only yes/no plus a death indicator; it does not prove identity or I-9 eligibility.  
•      **Origins.** Representative rules date to section 206 of the Social Security Act. CMS-1696's one-year validity comes from 42 CFR 405.910(e).

**5\. Stability and variants:** SSA-1696 changed sharply in December 2024 (the 12-2024 edition). An e1696 online version exists and can be started by the representative; attachments such as fee agreements require another channel. SSA-1696-SUP1 handles additional claimants. SSA-89 was revised in 04-2023 and again as 05-2025 (the CBSV page still cites 04-2023, so check the PDF footer). CMS-1696 is stable, with a non-substantive October 2026 revision. Many Medicare Advantage and Part D plans accept their own branded versions or an equivalent written notice meeting 405.910(c).

### **C2. Drill-down: the operative clause**

SSA-89: "I authorize the Social Security Administration to verify my SSN (to match my name, SSN, and date of birth with information in SSA records and provide the results of the match) to the Company or Company's Agent, if applicable, for the purpose I identified. ... This consent is valid only for one-time use. ... valid only for 90 days from the date signed, unless indicated otherwise by the individual named above."

SSA-1696: "I appoint the individual named in Section 2 to act as my representative in connection with my claim(s) or asserted right(s) under Title II (RSDI), Title XVI (SSI), Title XVIII (Medicare Coverage), and Title VIII (SVB) of the Social Security Act, as presently amended specifically for the issues identified below: (Check all that apply)."

— Form SSA-89 (05-2025); Form SSA-1696 (12-2024), Section 4

**SSA-89.** The grantor is the SSN holder or a legal guardian. The grantee is not a representative. It is the record custodian (SSA), authorized to release a single bit (match or no-match) to a named relying party. The delegating verb is "authorize ... to verify." Scope is limited by data elements (name, SSN, DOB), recipient (Company and its Agent), purpose code, one-time use, and a 90-day term. Disclosure of the reason for a no-match is a second, conditional authorization, limited to "Permitted Entities." The company gets no SSA record and no standing to act, and is bound by its CBSV/eCBSV agreement with SSA, which restricts reuse.

**SSA-1696.** The grantor is the claimant, and the grantee is one named individual. "Act as my representative" is a broad agency verb, scoped by Title and by checked issue types. Not delegated: the representative's fee, which needs SSA approval and a separate election in Section 6, and the claimant's own signature on certain filings. SSA is bound to route notices to the principal representative.

**CMS-1696.** Similar, but it adds a clock: valid for one year from the date the form is signed by both parties.

### **D. Outline of the full instrument**

1\.     SSA-1696 (12-2024)  
a.     Section 1: reason for submission (new appointment, or an update to a specific section) and claimant information.  
b.     Section 2: representative identity, including Rep ID.  
c.      Section 3: principal representative designation.  
d.     Section 4: claim types and issues.  
e.     Section 5: representative information. Part A covers status and disqualifications; Part B entity affiliation; Part C assignment or rescission of direct fee payment to the entity; Part D the acceptance and perjury declaration.  
f.      Section 6: fee arrangement (four options).  
g.     Section 7: auxiliary claimants covered.  
h.     Section 8: signatures of claimant and representative.  
2\.     SSA-89 (05-2025)  
a.     Number holder data (name, DOB, SSN).  
b.     Reason (one of eight purposes).  
c.      Company and agent name and address.  
d.     Authorization and perjury affirmation, with the one-time and 90-day terms.  
e.     Signature and relationship.  
f.      Tear-off "Notice to Number Holder."  
3\.     CMS-1696  
a.     Section 1: person appointing.  
b.     Section 2: representative acceptance and no-disqualification certification.  
c.      Section 3: fee waiver.  
d.     Section 4: statement for the Medicare provider or supplier (waiver of payment from the beneficiary).

On the SSA-1696, scope (Section 4), identity and credential (Section 5 A/D), and money (Sections 5C and 6\) are separately updatable blocks. The SSA-89 is a self-contained consent receipt. CMS-1696 adds a fixed lifetime to the SSA-1696 model.

### **E. Insights and observations**

•      **Update by section.** Section 1 of the SSA-1696 lets a filer update only the principal designation, claim type, affiliation, fee assignment, or fee arrangement — a PATCH on parts of a grant, not a full reissue. Agent mandates benefit from addressable sub-records with their own audit history.  
•      **Primary-agent routing.** Many agents can hold authority, but SSA talks only to the principal representative. This avoids conflicting instructions while keeping co-agents' authority. A temporary-principal fallback (most recent appointee) handles the missing-designation case.  
•      **Entity as payee, not agent.** After *Marasco*, SSA chose to pay firms while keeping accountability with individuals. Agent platforms can do the same: the platform or vendor receives value, while authority and liability attach to a named, credentialed agent identity.  
•      **Consent receipts have teeth.** The SSA-89 carries a perjury affirmation and a misdemeanor warning (fine up to \$5,000). Relying parties must keep the signed consent under an SSA agreement — a model for auditable consent artifacts that a third-party verifier can demand.  
•      **Clocks differ by risk.** A 90-day single-use consent (SSA-89), a one-year reusable appointment that extends for the life of an appeal (CMS-1696), and an open-ended appointment (SSA-1696) show that expiry should follow risk and workflow, not a single default.  
•      **Revocation asymmetry.** Under CMS rules, revocation is effective only when the adjudicator receives the signed writing (42 CFR 405.910(m)). SSA likewise needs a separate signed filing. Until the counterparty's registry updates, the old grant stays live, so agent systems need push revocation to relying parties.  
•      **Sub-delegation needs consent.** Under 42 CFR 405.910(l), a Medicare representative may not delegate without written notice and the party's signed acceptance, except to attorneys in the same firm.

**Sources:** [SSA-1696 form page](https://www.ssa.gov/forms/ssa-1696.html) · [Form SSA-1696 (12-2024) PDF](https://www.ssa.gov/forms/ssa-1696.pdf) · [HALLEX HA 01110.010 Appointing a Representative](https://secure.ssa.gov/POMS.nsf/lnx/2501110010) · [POMS GN 03910 Transmittal 38 (Dec. 2024\)](https://secure.ssa.gov/apps10/reference.nsf/links/12072024080351PM) · [SSA: 2024 New Rule](https://ssa.gov/representation/2024NewRule.htm) · [89 FR 67542 final rule](https://govinfo.gov/content/pkg/FR-2024-08-21/pdf/2024-18497.pdf) · [Form SSA-89 (05-2025) PDF](https://www.ssa.gov/forms/ssa-89.pdf) · [SSA CBSV page](https://ssa.gov/cbsv) · [Form CMS-1696 PDF](https://www.cms.gov/medicare/cms-forms/cms-forms/downloads/cms1696.pdf) · [CMS-1696 forms item page](https://www.cms.gov/Medicare/CMS-Forms/CMS-Forms/CMS-Forms-Items/CMS012207) · [42 CFR 405.910 (eCFR)](https://www.ecfr.gov/current/title-42/chapter-IV/subchapter-B/part-405/subpart-I/subject-group-ECFR6a4d2b3b2b54ad2/section-405.910)

## **7\. VA Forms 21-22 and 21-22a**

**A. Title:** VA Form 21-22, *Appointment of Veterans Service Organization as Claimant's Representative* (JUL 2023). VA Form 21-22a, *Appointment of Individual as Claimant's Representative* (JUL 2023). Both fall under OMB Control No. 2900-0321, whose printed expiry is 07/31/2026; a revision notice was published May 27, 2026 (FR Doc. 2026-10482). Online channels: VA.gov online form tool, QuickSubmit via AccessVA, and the Accredited Representative Portal (VSOs only).

**B. Blurb:** One representative at a time, with sensitive-record access as separate opt-in boxes.

### **C. Background**

**1\. Who it comes from:** The Department of Veterans Affairs: the Veterans Benefits Administration for the forms, and the Office of General Counsel for accreditation. The governing rules are 38 U.S.C. 5902–5905 and 7332, and 38 CFR 14.626–14.637 (notably 14.631). The veteran or claimant completes and signs the form; the VSO's accredited representative (21-22) or the accredited attorney or agent (21-22a) countersigns.

**2\. Key lesson for AI-agent authorization:** **Bundle a broad default grant with explicit, separately revocable opt-ins for the most sensitive data classes and for account-recovery-type actions, and enforce one active agent per principal, so that a new appointment automatically revokes the old one.** Items 19–20 of the 21-22 make access to records on drug or alcohol treatment, HIV, and sickle cell anemia an opt-in, with a category-level exclusion list. Item 21 makes "change my address" a separate opt-in — the classic account-takeover lever. Under 38 CFR 14.631(e)–(f), VA recognizes only one representative at a time, and a newer POA revokes the earlier one by default. Agent systems can copy this directly: sensitive scopes off by default, contact and recovery changes behind their own grant, and a single-holder slot with last-wins revocation.

**3\. The instrument:**

•      **Scenarios.** Disability compensation, pension, survivor benefits, education and other VA benefit claims, plus decision reviews and appeals. The 21-22 appoints a recognized organization (e.g., The American Legion, DAV, or a state veterans' agency). The 21-22a appoints an individual: an accredited attorney, an accredited claims agent, a VSO representative, or a one-time unaccredited individual under 38 CFR 14.630.  
•      **Powers.** The appointee may "prepare, present and prosecute my claim(s) for any and all benefits" based on the veteran's service. VA is authorized to release "any and all" records, including federal tax information, except the 7332 categories.  
•      **Opt-ins.**  
a.     On the 21-22: Item 19 (7332 records), Item 20 (exclude specific 7332 categories), and Item 21 (address change by any official representative of the organization).  
b.     On the 21-22a: Item 19 (disclosure to the representative's affiliated firm and named staff), Item 20 (7332), Item 21 (limitation), and Item 22 (address change).  
•      **Scope limits.** Under 21-22a Item 24, an attorney or agent may limit the scope of the representation (e.g., to one claim). Unless limited, the form revokes all previously existing powers of attorney.  
•      **Fees.** VSOs may not charge. Attorneys and agents may charge only under 38 U.S.C. 5904, generally after an initial decision. A 14.630 individual attests that no compensation will be charged.  
•      **Duration and revocation.** No expiry, except that for IRS income-match purposes a VSO appointment is valid for only five years. The claimant may revoke at any time; the VSO may withdraw subject to 38 CFR 20.6. The 7332 and address-change opt-ins end on written revocation, on appointment of another representative, or (for address change) on a finding that the veteran cannot manage their financial affairs.  
•      **Counterparty validation.** VA records the POA in its corporate systems and checks the representative against the OGC accreditation database. The VA.gov "Find a Rep" tool shows a veteran's current representation status.

**4\. Context:**

•      **Volume.** VA estimates 1,046,113 respondents a year for 21-22 and 21-22a combined, at about 5 minutes each (FR Doc. 2026-10482, May 27, 2026).  
•      **Origins.** Recognition of service organizations dates to the World War I era. Today's 38 CFR 14.631 was last amended in January 2019 (84 FR 174).  
•      **Enforcement gap.** "Claim sharks" are unaccredited consultants who charge veterans contingency fees without filing a POA. In 2006 federal law removed the criminal penalty for unaccredited representation, and VA told the House in July 2024 that it lacks effective tools beyond cease-and-desist letters. The GUARD VA Benefits Act (H.R. 1732\) would restore penalties; MOAA reported in April 2026 that it was still pending. States are filling the gap: California, Maine, New Jersey and New York have laws; a federal court struck down a Louisiana law favoring unaccredited agents in February 2026; and the Kansas governor vetoed a similar provision on April 8, 2026\.  
•      **Digital shift.** VA.gov now offers an online tool: both parties sign, and the form goes in via QuickSubmit. Participating VSOs can accept electronic 21-22 requests in the Accredited Representative Portal; a secondary source (ClaimRaven, Sept. 2026\) reports this is "not currently available to attorneys or claims agents" (unconfirmed on VA's own pages).

**5\. Stability and variants:** Both forms have been stable since the July 2023 editions. A PRA revision was in progress in 2026, but no newer edition was found. Related instruments include the Board of Veterans' Appeals rules (38 CFR 20.6), VA Form 21a (application for accreditation), VA Form 21-0845 (authorization to disclose to a third party, which conveys no power to act), and fiduciary appointments for incompetent beneficiaries (38 CFR Part 13).

### **C2. Drill-down: the operative clause**

"I, the claimant named in Items 1 or 10, hereby appoint the service organization named in Item 15 as my representative to prepare, present and prosecute my claim(s) for any and all benefits from the Department of Veterans Affairs (VA) based on the service of the veteran named in Item 1\. I authorize VA to release any and all of my records, to include disclosure of my Federal tax information (other than as provided in Items 19 and 20), to my appointed service organization."

Item 19: "By checking the box below I authorize VA to disclose to the service organization named on this appointment form any records that may be in my file relating to treatment for drug abuse, alcoholism or alcohol abuse, infection with the human immunodeficiency virus (HIV), or sickle cell anemia. ... Redisclosure of these records by my service organization representative, other than to VA or the Court of Appeals for Veterans Claims, is not authorized without my further written consent. This authorization will remain in effect until the earlier of the following events: (1) I revoke this authorization by filing a written revocation with VA; or (2) I revoke the appointment of the service organization named in Item 15, either by explicit revocation or the appointment of another representative."

— VA Form 21-22 (JUL 2023), Authorization paragraph and Item 19

The grantor is the veteran or claimant. On the 21-22 the grantee is an organization, not a person: any accredited representative of that organization can work the file, and Item 21 extends address-change power to any official representative of the organization. On the 21-22a the grantee is a named individual, and staff access comes only through Item 19's list of firm and named employees.

The delegating verbs are "prepare, present and prosecute" (act) and "authorize VA to release" (disclose). Scope is "any and all benefits" tied to one veteran's service — broad by design, though attorneys and agents may narrow it.

Carved out unless opted in: records protected by 38 U.S.C. 7332, which may be disclosed only with prior written consent. Further carved out: redisclosure beyond VA and the Court of Appeals for Veterans Claims. The 7332 grant has two termination triggers and is tied to the life of the appointment. VA is bound by 38 CFR 14.631: under 14.631(e)(1), all transactions go through the representative of record until VA receives notice of a change.

### **D. Outline of the full instrument**

1\.     Section I — Veteran information (Items 1–9): name, SSN, file number, DOB, service number, branch, address, phone, email.  
2\.     Section II — Claimant information if not the veteran (Items 10–14 on the 21-22).  
3\.     Section III — Representative  
a.     21-22: Item 15 organization name; Item 16A individual representative of the organization and job title.  
b.     21-22a: Item 16B representative type (attorney, agent, VSO representative, 14.630 individual) with address and contact.  
4\.     Section IV — Authorizations  
a.     21-22: Item 17 contact info, Item 18 appointment date, Item 19 7332 opt-in, Item 20 category limitations, Item 21 address-change opt-in, Items 22–23 signatures.  
b.     21-22a: Items 17–18 14.630 attestations, Item 19 affiliated-personnel disclosure, Item 20 7332, Item 21 limitation, Item 22 address change, Item 23 claimant signature, Item 24 scope limits (attorney/agent), Item 25 representative signature.  
5\.     Conditions of appointment, fee notice (38 U.S.C. 5904), penalty notice, and VA Use Only (acknowledged/revoked).

The form is a general grant, plus a ladder of independent opt-in switches, plus two signatures. VA's POA record then becomes the single routing key for the claim.

### **E. Insights and observations**

•      **Sensitivity tiers inside one grant.** Statute (38 U.S.C. 7332\) forces a higher consent bar for four diagnosis categories. The form expresses that as a checkbox, with a negative list (Item 20\) and narrower redisclosure limits. Agent scopes can likewise carry data-class labels with their own consent, exclusions, and onward-sharing bans.  
•      **Contact-change is a privileged action.** Address change is separated out because it redirects every future notice and payment. It also expires automatically if the veteran is found incompetent and the representative is not the fiduciary. Agents should need a separate grant to change the principal's contact, payout, or recovery details.  
•      **Org-level versus person-level grantees.** The 21-22 delegates to an organization whose roster can change, much like a USPTO Customer Number (item 12). The 21-22a delegates to one person plus an enumerated staff list. The design choice determines who must be re-consented when staff turn over.  
•      **Single-slot, last-write-wins.** One representative at a time, with automatic revocation by a later appointment, prevents conflicting agents. The trade-off: a fraudulent new POA silently displaces a legitimate one. VA's "Find a Rep" status view partly mitigates this by letting the principal see who currently holds the slot.  
•      **Outside-the-registry agents.** Claim sharks act without filing a POA, so the registry cannot see or revoke them. Relying parties should refuse unregistered intermediaries — and penalties matter: VA's enforcement gap since 2006 shows registry rules without sanctions leak.  
•      **Time-boxed sub-purposes.** The five-year limit for IRS income-match use is a purpose-specific expiry inside an otherwise open-ended grant. Scopes can carry their own TTLs.

**Sources:** [About VA Form 21-22](https://www.va.gov/find-forms/about-form-21-22/) · [VA Form 21-22 online](https://www.va.gov/forms/21-22/) · [VA Form 21-22 PDF (JUL 2023\)](https://www.vba.va.gov/pubs/forms/VBA-21-22-ARE.pdf) · [VA Form 21-22a PDF (JUL 2023\)](https://www.vba.va.gov/pubs/forms/VBA-21-22a-ARE.pdf) · [VA.gov: Get help from an accredited representative](https://www.va.gov/get-help-from-accredited-representative/) · [38 CFR 14.631 (eCFR)](https://www.ecfr.gov/current/title-38/chapter-I/part-14/subject-group-ECFR4ef2a2cc0b4e5e9/section-14.631) · [38 U.S.C. 7332 (LII)](https://www.law.cornell.edu/uscode/text/38/7332) · [Federal Register PRA notice 2026-10482](https://public-inspection.federalregister.gov/2026-10482.pdf) · [VA testimony to HVAC subcommittee, July 10, 2024](https://docs.house.gov/meetings/VR/VR09/20240710/117492/HHRG-118-VR09-Wstate-PowersG-20240710.pdf) · [VA OGC Accreditation](https://www.va.gov/ogc/accreditation.asp) · [MOAA: States need support against claim sharks (2026)](https://www.moaa.org/content/publications-and-media/news-articles/2026-news-articles/benefits/advocacy-in-action-states-need-support-protecting-veterans-from-claim-sharks/) · [ClaimRaven: VA Form 21-22 example (2026)](https://claimraven.com/blog/va-form-21-22-example)

## **8\. USPS PS Form 1583 (mail delivery through a CMRA agent)**

**A. Title:** PS Form 1583, *Application for Delivery of Mail Through Agent* (current revision: June 2024); companion PS Form 1583-A, *Application to Act as a Commercial Mail Receiving Agency (CMRA)* (January 2023). Governed by Domestic Mail Manual (DMM) 508.1.8 *Commercial Mail Receiving Agencies*.

**B. Blurb:** Both principal and mail agent prove identity; the regulator keeps the registry.

### **C. Background**

**1\. Who it comes from:** Issued by the U.S. Postal Service. The principal (the "applicant" or private mailbox holder) and the CMRA (a UPS Store-type shop, a virtual-mailbox operator, an office center or a reshipper) fill in each instance together. The CMRA then keys it into USPS's CMRA Customer Registration Database (CRD).

**2\. Key lesson for AI-agent authorization:** **Identity proofing of the principal, of any named sub-delegate, and of the agent itself is built into the instrument, and the agent must be registered with and re-certify to the counterparty every quarter.** In agent terms, the CMRA is a registered "agent operator" with its own credential (Form 1583-A). Each delegation (Form 1583\) sits in a registry the counterparty (USPS) can audit, with ID images attached and expiry alerts. Revocation is a dated termination entered in the same registry, not a notice sent to the world.

**3\. The instrument:**

•      **Scenario.** A person or business wants USPS to deliver its mail to a private business that receives it on their behalf. Without a valid Form 1583, the CMRA must return the mail as undeliverable (DMM 508.1.8.4).  
•      **Parties.** Applicant (principal); CMRA owner/manager (agent); optional "Authorized Individual" (block 5\) who may collect the mail; USPS (counterparty and regulator).  
•      **Power delegated.** Receipt of all mail addressed to the applicant at the private mailbox (PMB), including restricted-delivery mail, which the 2023 rule says PMB holders receive at the CMRA address.  
•      **Identity proof.** Two IDs for the applicant and again for any authorized individual. One must be government photo ID (blocks 8, 10); the other proves home address (blocks 9, 11). A driver's license may count for only one of the two. Copies are attached.  
•      **Execution.** The applicant signs in the physical or real-time audio-video presence of the CMRA owner, manager or authorized employee, or acknowledges the signature before a U.S.-commissioned notary (in person or by audio-video). The CMRA signs block 14\.  
•      **Filing and validation.** The CMRA enters every form into the CRD and uploads legible ID images. USPS inspects them and returns errors; the CRD alerts on expiring photo IDs.  
•      **Duration.** Open-ended. Any change in the facts requires a new form with current ID.  
•      **Revocation.** Neither side files a change of address. The CMRA dates the termination (block 1b) and updates the CRD. It keeps the endorsed copy for at least six months and remails for six months at the customer's postage cost.

**4\. Context:** Form 1583 dates to USPS's 1990s CMRA crackdown on mail-drop fraud. The current regime comes from three rulemakings. A Privacy Act system of records for CMRA data (SOR 845.000) was finalized December 2022 and announced the CRD. A final rule (88 FR 32112, May 19, 2023; DMM effective July 9, 2023\) created the CRD, ID uploads, quarterly certification and a nine-month window to migrate every existing PMB customer. A clarification rule (89 FR 35716, May 2, 2024; effective May 1, 2024\) allowed virtual witnessing by the CMRA and required notaries to be U.S.-commissioned.

USPS gives no count of CMRAs or PMBs in these notices. Enforcement runs through postmaster suspension after 30 days' written notice, emergency mail-withholding orders by the Chief Postal Inspector, and criminal/civil penalties for false statements on the form.

**5\. Stability and variants:** The instrument is stable in concept but was rebuilt in 2023–2024. Revisions seen: April 2023 (CRD launch) and June 2024 (current, on about.usps.com). Several virtual-mailbox vendors still describe the April 2023 version as current. Sister forms: 1583-A for the CMRA itself; PS Form 1093 for PO Box users; PS Form 3801 standing delivery orders (item 24). PS Form 3801-A is a separate, much older agreement in which a hotel or apartment house accepts liability for registered mail handed to its designated representatives (see item 24).

### **C2. Drill-down: the operative clause**

"The mail addressee (the applicant) must sign or confirm his or her signature in the physical or virtual (in real-time audio and video) presence of the CMRA owner or manager, or authorized employee, or acknowledge his or her signature in the physical or virtual (in real-time audio and video) presence of a notary public commissioned in a United States state, territory, possession, or the District of Columbia."

— DMM 508.1.8.3 (as amended by 89 FR 35716, May 2, 2024\)

Form text: "In consideration of delivery of my mail or our firm's mail to the agent named on Page 1, the applicant and agent agree: …" and "The Applicant authorizes mail to be collected by the individual noted in item 5."

— PS Form 1583, June 2024, page 2 and note 5

The grantor is the applicant. The grantee is the CMRA named on page 1 and, as a second tier, the Authorized Individual in block 5\. The delegating act is "delivery of my mail … to the agent," framed as mutual consideration, so both principal and agent take on duties. The object is all mail to the PMB address. Scope limiters are the address format (a "PMB" or "\#" designator is mandatory) and the business-vs-residential flag in block 3\.

Not delegated: changing the address of record (no change-of-address filing is allowed at termination) and any power to alter the form, since altered forms are invalid. USPS is bound to deliver only because the form is on file in the CRD; the postmaster can suspend delivery to the whole CMRA if forms are missing or stale.

### **D. Outline of the full instrument**

1\.     Block 1 — PMB opened/closed dates (the validity window).  
2\.     Block 2 — CMRA address and PMB number (the agent and the slot).  
3\.     Block 3 — business or residential use.  
4\.     Block 4 — applicant identity, home address, protected-individual flag (4k).  
5\.     Block 5 — Authorized Individual (sub-delegate who may collect mail).  
6\.     Block 6 — forwarding address, if mail is transferred onward.  
7\.     Block 7 — business details and place of registration.  
8\.     Blocks 8–11 — photo ID and address ID for applicant and Authorized Individual.  
9\.     Block 12 — additional recipients (business use).  
10\.  Blocks 13–14 — applicant signature with certification; CMRA signature.  
11\.  Page 2 — agreement terms, ID lists, notary block, Privacy Act statement.

Blocks 1–7 define who, where and for what; 8–11 bind each named person to verified identity; 13–14 and the notary or witness step bind the signatures to those identities. The CRD entry and ID images make the paper an auditable record.

### **E. Insights and observations**

•      **Two-sided accreditation.** The agent's own Form 1583-A requires two IDs, a postmaster-witnessed signature and verification of the owner's home address. The agent is a known, sanctionable entity before it can hold anyone's authority. Agent platforms could likewise require operator registration before accepting delegations.  
•      **Quarterly attestation as liveness.** CMRAs must certify in the CRD by January 15, April 15, July 15 and October 15 that every form is current, terminations are recorded and no ID has expired — a periodic "re-attest or lose standing" control rather than per-grant expiry.  
•      **Remote proofing was adopted, then constrained.** The 2023 rule declined digital identity verification. The 2024 rule allowed real-time audio-video witnessing but did not require recording the session, and changed "acknowledge" to "confirm" so CMRA staff are not treated as notaries. Agent systems face the same choice between witnessed remote proofing and stored evidence.  
•      **"Online 1583 via USPS" could not be verified.** None of the official sources (DMM, Federal Register, USPS forms, Postal Bulletin) describe a USPS-run portal where consumers file Form 1583 or get identity-proofed at a Post Office. The "online" pieces are the CMRA-facing CRD and remote witnessing or remote online notarization (RON). Vendor pages describe RON acceptance but cite no USPS authority.  
•      **Virtual-mailbox implications.** Virtual-mailbox and reshipping firms are now expressly CMRAs (2023 definition). Each PMB needs its own 1583; IDs cannot be reused across locations. Non-U.S. customers must use a U.S.-commissioned notary. Migrating all existing customers to the new form within nine months forced mass re-papering.  
•      **Privacy partitioning.** USPS may disclose that an address belongs to a CMRA but not whose mail it holds. Protected individuals' data is withheld absent a court order. A delegation registry can likewise confirm agent status without exposing the principal.  
•      **Fraud pattern.** PMBs were used to make mail drops look like street addresses. Hence the mandatory "PMB"/"\#" designator, the ban on combining the CMRA's suite number with the PMB number, and the same unlawful-activity prohibition as PO Boxes. Labeling agent-held addresses or identities as agent-held is the analogous control.

**Sources:** [DMM 508 Recipient Services](https://pe.usps.com/text/dmm300/508.htm) · [PS Form 1583, June 2024](https://about.usps.com/forms/ps1583.pdf) · [PS Form 1583-A, January 2023](https://about.usps.com/forms/ps1583a.pdf) · [89 FR 35716, CMRA Clarification final rule (May 2, 2024\)](https://www.govinfo.gov/content/pkg/FR-2024-05-02/html/2024-06989.htm) · [CMRA Clarification proposed rule (Dec. 29, 2023\)](https://www.govinfo.gov/content/pkg/FR-2023-12-29/html/2023-28296.htm) · [88 FR 32112, CMRA final rule (May 19, 2023\)](https://www.federalregister.gov/documents/2023/05/19/2023-10536/commercial-mail-receiving-agencies) · [Postal Bulletin 22624, DMM Revision: CMRAs](https://about.usps.com/postal-bulletin/2023/pb22624/html/updt_002.htm) · [CMRA Records SOR 845.000 notice (Dec. 23, 2022\)](https://govinfo.gov/content/pkg/FR-2022-12-23/pdf/2022-28026.pdf) · [USPS Federal Register notices index](https://pe.usps.com/FederalRegisterNotice/Index) · [Anytime Mailbox Form 1583 guide (vendor)](https://www.anytimemailbox.com/usps-form-1583) · [Alliance Virtual Offices Form 1583 guide (vendor)](https://www.alliancevirtualoffices.com/virtual-office-blog/form-1583-setup/)

## **9\. UCC Article 9 authorization to file financing statements**

**A. Title:** Uniform Commercial Code §9-509 ("Persons Entitled to File a Record"), with §9-510 (effectiveness of filed record), §9-516/§9-520 (what constitutes filing; filing-office refusal), §9-518 (information statement, formerly "correction statement"), and §9-625(b), (e)(3)–(4) (damages). Official text as revised 1998 (effective 2001), amended 2010, and conformed by the 2022 UCC Amendments ("authenticate" replaced by "sign"). In practice the instrument is the authorization clause of a private security agreement — e.g., §2.3 "Authorization to File Financing Statements" in a 2025 Pledge and Security Agreement (Ballengee Group, LLC / Texas Security Bank, filed as an SEC EDGAR exhibit).

**B. Blurb:** Signing the loan deal silently authorizes the lender to file public liens.

### **C. Background**

**1\. Who it comes from:** The Uniform Law Commission and American Law Institute author the UCC; each state enacts it (e.g., Del. Code tit. 6 §9-509). The filled-in instance is the security agreement drafted by the secured lender's counsel, plus the UCC-1 financing statement the lender (or its filing service) submits to the state filing office, usually the Secretary of State.

**2\. Key lesson for AI-agent authorization:** **The authorization is not a separate artifact: it is implied by, and scoped to, the signed underlying agreement, while the registry accepts any well-formed submission and relies on after-the-fact invalidity, damages and dispute records instead of up-front verification.** For agents, this is the "open registry plus liability" design: anyone can post to a public ledger, but a posting has legal effect only if a signed grant from the principal exists. It works only if the grant is retrievable on demand, scope is machine-checkable against the grant, and false postings carry a cost. Agent systems that let agents publish claims (e.g., to a shared directory) should tie validity to a referenced, signed delegation and give subjects a cheap way to flag a bad entry.

**3\. The instrument:**

•      **Scenario:** A business borrows against collateral (often "all assets"). The lender perfects its security interest by filing a public notice, the UCC-1, in the debtor's location state.  
•      **Parties:** Debtor (grantor), secured party (grantee and filer), filing office (registry), and third parties who search the index (other lenders, buyers, bankruptcy trustees).  
•      **Power delegated:** The right to file an initial financing statement, or an amendment adding collateral or a debtor, naming the debtor. Under §9-509(a)(1) the debtor must authorize it "in a signed record" or by operation of §9-509(b) or (c).  
•      **Implied grant:** Under §9-509(b), signing a security agreement automatically authorizes filing for the collateral it describes plus identifiable proceeds. Under §9-509(c), acquiring collateral already encumbered does the same.  
•      **Scope limit:** Authorization covers only collateral described in the security agreement. Official Comment 4's example: an inventory-only agreement authorizes an inventory filing, and a filing that also lists accounts is unauthorized insofar as it covers accounts.  
•      **Super-generic description:** A financing statement may say "all assets" (§9-504(2)), but a security agreement may not. So lenders add an express clause authorizing "all assets" filings, which the implied grant alone would not cover.  
•      **Amendments and terminations:** Other amendments require the secured party of record (§9-509(d)). The debtor may file a termination itself if the secured party fails to do so after payoff (§9-509(d)(2), §9-513).  
•      **Duration:** A UCC-1 lapses after five years unless continued (§9-515). Filings marked "transmitting utility" do not lapse, a feature abused by bogus filers.  
•      **Counterparty validation:** None at filing time. The filing office may refuse only for listed ministerial defects (§9-516(b), §9-520(a)): wrong medium, fee short, missing debtor name or address. Official Comment 2 to §9-509: "The question of authorization is one for the court, not the filing office."

**4\. Context:**

•      **Who uses it:** Essentially every secured commercial lender, equipment lessor, factor and merchant-cash-advance provider in the U.S. The UCC-1 search is a standard diligence step in commercial lending.  
•      **Origin:** Notice filing dates to the 1950s UCC. Revised Article 9 (1998, effective July 1, 2001\) dropped the debtor-signature requirement on the financing statement itself, enabling electronic filing. Authorization replaced signature.  
•      **Consequences of no authorization:** Under §9-510(a), a filed record is effective only to the extent it was filed by a person entitled to file it under §9-509. An unauthorized filing does not perfect, so the lender can lose priority, often to a bankruptcy trustee.  
•      **Damages:** The filer is liable for actual loss (§9-625(b)) plus \$500 statutory damages per unauthorized filing (§9-625(e)(3)) and \$500 for failing to terminate (§9-625(e)(4)).  
•      **Ratification:** *In re The Adoni Group*, 530 B.R. 592 (Bankr. S.D.N.Y. 2015), held that a UCC-1 filed the day before any signed agreement was ratified by the later security agreement. Authorization can therefore be retroactive.  
•      **Failure mode, bogus filings:** Because offices do not check authorization, sovereign-citizen and harassment filers file liens against officials and companies. A 2019 NASS report counts at least 24 states letting offices reject fraudulent records, at least 15 with administrative removal, and at least 9 with expedited judicial review.

**5\. Stability and variants:**

•      **Uniform core, many tweaks:** The §9-509 text is uniform nationwide. Many states add nonuniform anti-fraud provisions.  
•      **Texas example:** Texas S.B. 2221 (89th Leg., eff. Sept. 1, 2025\) lets a debtor file a sworn affidavit after 5–30 days' certified-mail notice to the secured party. The Secretary of State then files a termination effective 30 days later; the secured party may sue within 90 days to reinstate. Damages for knowing fraudulent filings rose to the greater of \$10,000 or actual damages.  
•      **2022 UCC Amendments:** Section 9-102's "authenticate" definition was removed, and Article 9 now uses "sign" as defined in §1-201(b)(37), which covers electronic symbols and processes. Delaware's enacted §9-509 now reads "signed record" and "By signing or becoming bound." Per Alston & Bird (Dec. 9, 2025), New York joined 33 jurisdictions when it enacted the amendments on Dec. 5, 2025, effective in early June 2026 (sources differ on June 3 vs. June 5). The exact current national count is unverified.

### **C2. Drill-down: the operative clause**

"(a) A person may file an initial financing statement, amendment that adds collateral covered by a financing statement, or amendment that adds a debtor to a financing statement only if: (1) the debtor authorizes the filing in a signed record or pursuant to subsection (b) or (c) ... (b) By signing or becoming bound as debtor by a security agreement, a debtor or new debtor authorizes the filing of an initial financing statement, and an amendment, covering: (1) the collateral described in the security agreement; and (2) property that becomes collateral under Section 9-315(a)(2) ..."

— Del. Code tit. 6, §9-509(a)–(b) (as amended by the 2022 UCC Amendments; uniform text formerly read "authenticated record" and "By authenticating")

Paraphrase of a typical private clause: the debtor authorizes the secured party to file financing statements at any time, in any UCC jurisdiction, describing the collateral as all of the debtor's assets "or words of similar effect," and including the organizational ID and other UCC data; the secured party may also record the agreement or a short form with the USPTO and Copyright Office.

— Pledge and Security Agreement §2.3, Ballengee Group, LLC and Texas Security Bank (Nov. 2025, SEC EDGAR exhibit 10.02)

**Grantor:** the debtor (any debtor, including a "new debtor" bound by succession). **Grantee:** any "person," not only the secured party; the official commentary says Part 5 is largely indifferent to who effects a filing — what matters is whose authorization stands behind it. **Delegating verb:** "authorizes the filing." **Object:** a specific record type — initial UCC-1, or amendments adding collateral or debtors. **Scope limiter:** "the collateral described in the security agreement" plus proceeds. **Condition:** a signed record or a signed security agreement. **Not delegated:** amendments deleting collateral, assignments and terminations, which belong to the secured party of record (§9-509(d)). **Binding counterparty:** the filing office must accept a compliant record and cannot reject it for lack of authorization (§9-520(a)); effectiveness is decided later by courts under §9-510.

### **D. Outline of the full instrument**

1\.     Statutory layer (UCC Part 5\)  
a.     §9-509 — who may file; implied authorization by security agreement or acquisition; secured-party authority over other amendments.  
b.     §9-510 — unauthorized filings ineffective; multiple secured parties.  
c.      §9-516/§9-520 — filing is communication plus fee; exclusive list of refusal grounds.  
d.     §9-518 — information statement by a person who believes a record is inaccurate or wrongfully filed; no effect on the filed record.  
e.     §9-513 — duty to terminate on payoff; debtor self-help.  
f.      §9-625 — actual and \$500 statutory damages.  
2\.     Security agreement (private)  
a.     Grant of security interest and collateral description.  
b.     Authorization-to-file clause ("all assets," jurisdictions, IP-office filings, often ratification of prior filings).  
c.      Further assurances and power of attorney for perfection steps.  
3\.     UCC-1 financing statement (national form under §9-521)  
a.     Debtor name and address; secured party; collateral indication; optional transmitting-utility box.

The statute sets the authorization rule and remedies; the security agreement supplies the grant and its scope; the UCC-1 is the public post that is valid only to the extent the grant supports it.

### **E. Insights and observations**

•      **Signature moved from the post to the grant.** Pre-2001, the debtor signed the UCC-1 itself. Revised Article 9 moved signing to the private agreement so filings could be electronic — the same split as a signed delegation credential versus unsigned API calls made under it.  
•      **Implied authority has a scope trap.** The automatic §9-509(b) grant follows the security agreement's description, which cannot be "all assets," so lenders add express "all assets" authorization. Agent analog: inherited scopes should be narrower than express scopes, and the principal must expressly opt into broad wildcards.  
•      **Retroactive authorization is accepted.** *Adoni* lets later signing ratify an earlier filing. Agent systems must decide whether a principal's later approval cures an earlier unauthorized act, and log both events.  
•      **Registries without gatekeeping attract abuse.** Bogus liens against officials prompted roughly half the states to add pre-filing refusal or post-filing removal. Open agent directories or credential registries will face the same pressure and need a fast challenge path.  
•      **Dispute records do not delete.** A §9-518 information statement only annotates the index; removal requires termination, court order, or a state process like Texas's affidavit. Agent audit logs should be append-only, with annotations rather than silent edits.  
•      **The 2022 terminology change is about media neutrality.** "Sign" now includes attaching an electronic symbol or process with present intent to authenticate or adopt, which validates click-through and cryptographic signatures as the grant.  
•      **Small fixed penalties have limits.** \$500 per filing rarely deters ideological bogus filers, so states raised penalties (Texas: \$10,000 floor) and criminalized fraudulent filings (at least 17 states per NASS).

**Sources:** [UCC §9-509 (LII)](https://www.law.cornell.edu/ucc/9/9-509) · [UCC §9-625 (LII)](https://www.law.cornell.edu/ucc/9/9-625) · [UCC §9-516 (LII)](https://www.law.cornell.edu/ucc/9/9-516) · [UCC §9-518 (LII)](https://www.law.cornell.edu/ucc/9/9-518) · [UCC §9-520 (LII)](https://www.law.cornell.edu/ucc/9/9-520) · [Del. Code tit. 6, ch. 9, subch. V](https://delcode.delaware.gov/title6/c009/sc05/index.html) · [Del. Code tit. 6, §1-201](https://delcode.delaware.gov/title6/c001/sc02/index.html) · [Maine LD 2245, Official Comments to §9-509](https://legislature.maine.gov/legis/bills/bills_119th/billtexts/LD224501-323.asp) · [Pledge and Security Agreement, EDGAR Ex. 10.02](https://www.sec.gov/Archives/edgar/data/1420924/000149315225022331/ex10-02.htm) · [Duane Morris on In re Adoni Group](https://www.duanemorris.com/articles/financing_statement_filed_without_debtors_authorization_1115.html) · [NASS report on bogus filings (2019)](https://www.nass.org/sites/default/files/bogus%20filing/final-nass-report-bogus-filings-june19.pdf) · [Texas S.B. 2221 bill analysis (2025)](https://capitol.texas.gov/tlodocs/89R/analysis/html/SB02221F.htm) · [Alston & Bird: New York signs 2022 UCC Amendments](https://www.alston.com/en/insights/publications/2025/12/new-york-signs-2022-ucc-amendments) · [Equipment Finance News: New York adopts 2022 UCC amendments](https://equipmentfinancenews.com/news/lender-operations/new-york-adopts-2022-ucc-amendments/) · [Oklahoma Bar Journal: 2022 UCC Amendments report](https://www.okbar.org/barjournal/january-2023/financial-institutions-and-commercial-law-committee-report-on-the-2022-amendments-to-the-uniform-commercial-code/)

## **10\. Regulation E preauthorized EFTs and Nacha ACH debit authorization**

**A. Title:** Regulation E (Electronic Fund Transfers), 12 CFR §1005.10(b)–(e) "Preauthorized transfers," with definitions in §1005.2(k) and (m) and Official Interpretations (Supplement I) comments 10(b)-1 to 10(b)-7, 10(c)-1 to \-3, 10(d)(2)-1; Electronic Fund Transfer Act §907, 15 U.S.C. §1693e. Private layer: Nacha Operating Rules consumer debit authorization standards (PPD, WEB, TEL; "Meaningful Modernization" rules effective Sept. 17, 2021; Fraud Monitoring rules Phase 1 Mar. 20, 2026, Phase 2 June 2026). Template: Nacha "Sample Authorization for Direct Payment via ACH (ACH Debit)" (©2016).

**B. Blurb:** The original payment mandate: bounded, copied, and revocable at the bank.

### **C. Background**

**1\. Who it comes from:** The CFPB issues Regulation E (inherited from the Federal Reserve's 1979–80 rule under the EFTA of 1978). Nacha, the private ACH rule-maker, layers network rules on top. The filled-in instance is drafted by the payee (the "Originator": a gym, lender, utility, insurer), usually as a web form, paper form or recorded phone script.

**2\. Key lesson for AI-agent authorization:** **A standing payment authority is valid only if it states amount (or a range or formula), timing, account and revocation method in clear terms, the principal keeps a copy, out-of-range pulls trigger advance notice, and the principal can kill it at its own bank without the payee's cooperation.** This is essentially an AP2-style "intent mandate." The payee holds the mandate and proves it on demand; the payer's bank is an independent enforcement point that honors stop-payment and revocation. Agent designs should give the principal a revocation channel that does not run through the agent or merchant, and should treat any charge outside the signed envelope as an exception event.

**3\. The instrument:**

•      **Scenario:** Recurring debits from a consumer account: loan payments, subscriptions, insurance premiums, utilities. A "preauthorized EFT" is one "authorized in advance to recur at substantially regular intervals" (§1005.2(k)).  
•      **Parties:** Consumer (Receiver), payee/Originator, Originating Depository Financial Institution (ODFI), the consumer's bank (RDFI), and Nacha as network.  
•      **Form requirement:** Authorization must be by a writing "signed or similarly authenticated by the consumer" (§1005.10(b)). E-SIGN signatures, digital signatures and security codes count (comment 10(b)-5).  
•      **Who must sign:** Only the consumer — "not, for example, a third-party merchant on behalf of the consumer" (comment 10(b)-5). A payee may not sign for a consumer who only gave oral consent (comment 10(b)-3).  
•      **Content standard:** The authorization must be readily identifiable as such, with terms that are clear and readily understandable (comment 10(b)-6).  
•      **Copy:** The person obtaining the authorization must give the consumer a copy.  
•      **Nacha minimum data elements (since 2021):** single vs. recurring vs. standing; amount or how it is determined; timing (start date, number and/or frequency); Receiver name; account; date of authorization; revocation instructions including time and manner.  
•      **Variable amounts:** 10 days' written notice of amount and date before a varying debit, unless the consumer elects notice only when outside an agreed range (§1005.10(d)). Comment 10(d)(2)-1 says the range must be one the consumer could anticipate, e.g., the highest winter and lowest summer bill.  
•      **Revocation:** The consumer can stop a payment by telling the bank orally or in writing at least three business days before the debit (§1005.10(c)). The bank may demand written confirmation within 14 days. On notice of revocation, the bank must block all future debits and may not wait for the payee to terminate them (comment 10(c)-2).  
•      **Anti-tying:** No creditor may condition credit on repayment by preauthorized EFT (§1005.10(e)(1)).  
•      **Proof:** The Originator keeps the authorization for two years after termination and must produce it to the ODFI on request.

**4\. Context:**

•      **Scale:** ACH is the dominant U.S. channel for recurring bill pay and payroll. (A current Nacha volume figure was not verified for this entry.)  
•      **Origin:** EFTA (1978); Regulation E (1979–80); CFPB recodified at 12 CFR 1005 in 2011\.  
•      **Enforcement:** Payees that skip written authorization violate Reg E; the account bank does not (comment 10(b)-2). Network discipline is via returns: R10 (consumer says unauthorized), R05, R07 (authorization revoked). Nacha's unauthorized-return-rate threshold is 0.5% (R05, R07, R10, R29, R51), with 3.0% administrative and 15.0% overall thresholds.  
•      **Failure modes:** Merchants that make cancellation hard; "authorization" buried in terms of service; account-number fraud; and authorized-push fraud by impersonation. Comment 2(m)-2 makes the consumer liable if they gave an access device and authority to someone who exceeds it, until they notify the bank.  
•      **2026 Nacha fraud-monitoring rules:** All ODFIs, plus non-consumer Originators, TPSPs and TPSs with 2023 volume of 6 million or more, had to implement risk-based processes to identify entries that are unauthorized or authorized under "False Pretenses" by Mar. 20, 2026\. Everyone else followed in June 2026\. Processes must be reviewed at least annually; liability allocation under UCC 4A is unchanged. Companion rules require "PURCHASE" as the company entry description for e-commerce WEB debits and "PAYROLL" for payroll credits.

**5\. Stability and variants:**

•      **Reg E core:** The text of §1005.10(b)–(d) has been stable for decades. The hybrid prepaid-credit card exception in §1005.10(e)(1) was added by the 2016–2019 prepaid rule.  
•      **Nacha SEC codes:** PPD (written/paper, prearranged), WEB (internet or wireless authorization; requires commercially reasonable fraud detection and account validation), TEL (oral, by phone; recorded or confirmed in writing before settlement), plus CCD/CTX for business debits (agreement-based, not Reg E).  
•      **Meaningful Modernization (Sept. 17, 2021):** Applied the "clear and readily understandable" standard network-wide; added "standing authorizations" for consumer-initiated subsequent entries; accepted oral authorizations through any channel (including voice assistants); and set TEL-style minimum data elements for all consumer debits.  
•      **Templates:** Nacha's sample form; bank and processor templates for WEB and TEL scripts.

### **C2. Drill-down: the operative clause**

"Preauthorized electronic fund transfers from a consumer's account may be authorized only by a writing signed or similarly authenticated by the consumer. The person that obtains the authorization shall provide a copy to the consumer."

— 12 CFR §1005.10(b)

"A consumer may stop payment of a preauthorized electronic fund transfer from the consumer's account by notifying the financial institution orally or in writing at least three business days before the scheduled date of the transfer."

— 12 CFR §1005.10(c)(1)

Paraphrase: the consumer authorizes the named company to debit the stated checking or savings account electronically, for a stated amount (or method or dollar range), on stated dates or frequency, and to credit the account to correct erroneous debits. The authorization stays effective until the consumer notifies the company, in a specified manner and with a specified lead time, that it is revoked. Short quote: "remain in full force and effect until I (we) notify COMPANY".

— Nacha, Sample Authorization for Direct Payment via ACH (ACH Debit), ©2016

**Grantor:** the consumer account holder. **Grantee:** the designated payee/Originator (not the bank). **Delegating verb:** "authorize ... to electronically debit." **Object:** a stated account. **Scope limiters:** amount or range, dates or frequency, and the regular-recurrence pattern. **Conditions:** signed or similarly authenticated writing; copy delivered; notice of varying amounts. **Not delegated:** the right to change the account, raise amounts beyond the range without notice, or block revocation; Nacha notes written authorizations must state the time and manner of revocation. **Counterparty binding:** the RDFI honors entries presumptively but must honor the consumer's stop-payment and revocation and must recredit unauthorized debits. The ODFI warrants authorization to the network and can be charged back via R10.

### **D. Outline of the full instrument**

1\.     Regulation E  
a.     §1005.2(k), (m) — definitions of preauthorized and unauthorized EFT.  
b.     §1005.10(a) — notice of received preauthorized credits.  
c.      §1005.10(b) — written authorization and copy.  
d.     §1005.10(c) — stop-payment by notice to the bank.  
e.     §1005.10(d) — notice of varying amounts; range option.  
f.      §1005.10(e) — compulsory-use ban.  
g.     Supplement I comments — e-signatures, who may sign, validity test, revocation duty of bank.  
2\.     Nacha Operating Rules  
a.     General authorization rule and minimum data elements.  
b.     SEC-code specifics (PPD, WEB, TEL, standing authorizations).  
c.      Retention and production of proof; warranties; return codes and thresholds.  
d.     2026 fraud-monitoring obligations.  
3\.     Payee's authorization form  
a.     Account and routing data; amount/range; timing; revocation method; signature and date.

Reg E sets the consumer-protective floor; Nacha converts it into warranties and returns across banks; the payee's form is the concrete mandate both rely on.

### **E. Insights and observations**

•      **Two revocation paths by design.** The consumer can revoke with the payee (per the form's terms) or stop it at its own bank (Reg E), and the bank must act even if the payee disagrees. Agent mandates should likewise be revocable at the wallet or issuer, not only at the merchant or agent.  
•      **"Standing authorization" is the closest analog to agent intent mandates.** Nacha's 2021 category lets a consumer pre-approve future debits that each require a later consumer action — a scoped mandate plus per-transaction trigger, comparable to an agent's cart confirmation.  
•      **Range-based notice is a soft cap.** Reg E does not cap amounts; it requires advance notice outside the range. Agents could adopt the same: hard caps for some scopes and "notify before executing" thresholds for others.  
•      **Third-party signing is barred.** Comment 10(b)-5 says the merchant cannot authorize on the consumer's behalf. An AI agent "authorizing" a debit for its user needs either a principal-signed mandate or a framework that treats the agent's credential as the consumer's "similarly authenticated" signature. This is unsettled; no CFPB guidance on agent-initiated authorizations was found.  
•      **Proof is evidence of identity plus assent.** Nacha's 2022 WEB proof-of-authorization paper lists IP address logs, login timestamps, screenshots of the terms and the identity-linking method, and says a screenshot alone "does not constitute adequate proof of authorization." That maps directly to agent audit logs.  
•      **2026 shift to "False Pretenses."** The fraud-monitoring rules target authorized-but-induced payments (BEC, vendor and payroll impersonation). Authorization validity is no longer the only control; monitoring of authorized flows is now required too — a lesson for agent payment rails.  
•      **Unverified:** The Nacha rulebook text itself is paywalled, so subsection numbers and the ODFI's production deadline are not confirmed here.

**Sources:** [12 CFR 1005.10 and interpretations (CFPB)](https://www.consumerfinance.gov/rules-policy/regulations/1005/10/) · [12 CFR 1005.2 (CFPB)](https://www.consumerfinance.gov/rules-policy/regulations/1005/2/) · [12 CFR Part 1005 Supplement I (eCFR)](https://www.ecfr.gov/current/title-12/chapter-X/part-1005/appendix-Supplement%20I%20to%20Part%201005) · [Nacha Sample Authorization for Direct Payment via ACH](https://www.nacha.org/system/files/2021-07/DP-Authorization-Form.pdf) · [Nacha Meaningful Modernization](https://www.nacha.org/rules/meaningful-modernization) · [EPCOR: Meaningful Modernization and debit authorizations](https://epcor.org/nycu-stories/may-august2021/meaningful-modernization-and-debit-authorizations.html) · [Nacha Fraud Monitoring Phase 2](https://www.nacha.org/rules/risk-management-topics-fraud-monitoring-phase-2) · [Ramp: 2026 Nacha rule changes](https://ramp.com/blog/2026-nacha-rule-changes) · [Nacha ACH Network Risk and Enforcement Topics](https://www.nacha.org/rules/ach-network-risk-and-enforcement-topics) · [Nacha WEB Proof of Authorization Industry Practices (2022)](https://www.nacha.org/system/files/2022-11/WEB_Proof_of_Authorization_Industry_Practices.pdf) · [Nacha: Importance of Compliant ACH Authorizations (Nov. 2025\)](https://www.nacha.org/news/importance-compliant-ach-authorizations) · [Worldpay NACHA Requirements V2.1](https://docs.worldpay.com/assets/pdf/NACHA_Requirements_V2.1.pdf)

## **11\. FCRA employment background-check disclosure and authorization**

**A. Title:** Fair Credit Reporting Act §604(b)(2), 15 U.S.C. §1681b(b)(2)(A) "Disclosure to consumer" and written authorization for consumer reports for employment purposes; with §1681b(b)(1) user certification, §1681b(b)(3) pre-adverse action notice, §1681n civil liability. Companion federal form: CFPB "A Summary of Your Rights Under the Fair Credit Reporting Act" (12 CFR Part 1022, Appendix K; model forms updated March 2023, mandatory from March 20, 2024). State add-on: California Investigative Consumer Reporting Agencies Act (ICRAA), Cal. Civ. Code §1786.16. The employer's form itself has no official number; it is usually titled "Disclosure Regarding Background Investigation" plus a separate "Authorization."

**B. Blurb:** A consent screen that must contain nothing but the consent.

### **C. Background**

**1\. Who it comes from:** Congress (FCRA 1970; employment disclosure added 1996, same-document authorization allowed 1998). The CFPB writes the Summary of Rights; the FTC and EEOC publish employer guidance. Employers or their background-screening vendors (consumer reporting agencies) draft the actual forms, often inside an applicant-tracking system.

**2\. Key lesson for AI-agent authorization:** **The consent artifact must be isolated: one screen or document that discloses one thing and captures one authorization, with no waivers, releases, unrelated terms or even well-meant extra notices bundled in.** Agent platforms should render scope grants as standalone consent objects, not clauses inside terms of service. The consent record should be hashable on its own so an auditor can prove what the user saw. FCRA shows that strict formal rules plus statutory damages and class actions make the format self-enforcing.

**3\. The instrument:**

•      **Scenario:** An employer (or prospective employer) wants a consumer report — criminal records, credit, driving, employment verification — for hiring, promotion, retention or reassignment.  
•      **Parties:** The applicant or employee (consumer and grantor); the employer (user and grantee); the consumer reporting agency (CRA, the counterparty who furnishes the report).  
•      **Disclosure:** A "clear and conspicuous disclosure ... in writing" before the report is procured, in a document that "consists solely of the disclosure," saying a consumer report may be obtained for employment purposes.  
•      **Authorization:** Written authorization from the consumer, which may appear on the same disclosure document (1998 amendment).  
•      **Exception:** Positions applied for by mail, phone or computer where the employer is regulated by the Department of Transportation (e.g., truckers) can use oral, written or electronic notice and consent (§1681b(b)(2)(B)–(C)).  
•      **Counterparty validation:** The CRA may furnish the report only if the employer certifies it has complied with the disclosure and authorization rule and will comply with adverse-action rules (§1681b(b)(1)(A)). The CRA does not inspect the form; it relies on the certification.  
•      **Duration and revocation:** The statute is silent. Many forms state the authorization covers ongoing checks during employment ("evergreen"). Whether consent can be withdrawn is handled by state law and form drafting, not by FCRA.  
•      **Downstream steps:** Before adverse action, the employer must give a copy of the report and the CFPB Summary of Rights (§1681b(b)(3)); then a final adverse-action notice (§1681m).

**4\. Context:**

•      **Who uses it:** Most U.S. employers that screen applicants through third-party vendors. (No authoritative 2024–2026 count of background checks per year was found.)  
•      **Damages:** For willful noncompliance, actual damages or statutory damages of "not less than \$100 and not more than \$1,000" per consumer, plus punitive damages and attorney's fees (§1681n). "Willful" includes reckless disregard (*Safeco v. Burr*, 2007).  
•      **Litigation engine:** Per-applicant statutory damages turn a form defect into class exposure across every hire. Example: a 2021 settlement of \$174,980 for 1,000+ class members over a liability waiver on the disclosure (*Taafua v. QGT*, per Asurint).  
•      **Key cases:**  
a.     *Syed v. M-I, LLC*, 853 F.3d 492 (9th Cir. 2017): a liability waiver on the disclosure form violates the "solely" rule; the violation was willful as a matter of law because the text is unambiguous.  
b.     *Gilberg v. California Check Cashing Stores*, 913 F.3d 1169 (9th Cir. 2019): including state-law disclosures makes the form noncompliant; extraneous information confused a reasonable reader, so it also failed "clear"; ICRAA's identical standalone rule was also violated.  
c.      *Walker v. Fred Meyer*, 953 F.3d 1082 (9th Cir. 2020): a concise explanation of what a report is and how it is obtained is allowed; paragraphs about other rights were not.  
d.     *Luna v. Hansen & Adkins* (9th Cir. 2020): a standalone disclosure may be handed over at the same time as other application papers.  
e.     *Groshek v. Time Warner Cable* (7th Cir. 2017): extraneous content alone, without confusion or harm, gives no Article III standing; this limits suits outside the Ninth Circuit.

**5\. Stability and variants:**

•      **Federal text:** Unchanged since 1998 apart from CFPB substitution (Dodd-Frank, 2010).  
•      **Summary of Rights:** The CFPB updated agency contact information in March 2023 (doc. 2023-05216); use of the updated forms became mandatory March 20, 2024\.  
•      **State variants:** California ICRAA requires its own standalone disclosure with the nature and scope of the investigation, the agency's name, address, phone and website, and a check-box to request a copy (§1786.16). Practice guidance is to give state notices on separate pages. Other states (e.g., New York, Minnesota, Oklahoma, Vermont) have add-on notices; not individually verified here.  
•      **Guidance churn:** On May 12, 2025, the CFPB withdrew 67 guidance documents, including its January 2024 Background Screening advisory opinion and Circular 2024-06 on worker surveillance dossiers. The statutory disclosure rule is unaffected.

### **C2. Drill-down: the operative clause**

"(A) In general. Except as provided in subparagraph (B), a person may not procure a consumer report, or cause a consumer report to be procured, for employment purposes with respect to any consumer, unless— (i) a clear and conspicuous disclosure has been made in writing to the consumer at any time before the report is procured or caused to be procured, in a document that consists solely of the disclosure, that a consumer report may be obtained for employment purposes; and (ii) the consumer has authorized in writing (which authorization may be made on the document referred to in clause (i)) the procurement of the report by that person."

— 15 U.S.C. §1681b(b)(2)(A)

**Grantor:** the consumer (applicant or employee). **Grantee:** "that person" — the specific employer, not affiliates or the CRA. **Delegating verb:** "authorized in writing ... the procurement." **Object:** a consumer report for employment purposes. **Format conditions:** "clear and conspicuous," "in writing," "before," and "consists solely of the disclosure"; the only extra content the statute permits is the authorization itself. **Not delegated:** release of claims, consent to unrelated data uses, arbitration, or state-law acknowledgments; courts treat their presence as invalidating. **Counterparty binding:** the CRA must obtain the employer's certification under §1681b(b)(1); the employer bears liability for a defective form. The FTC's employer guidance says the notice "must be in writing and in a stand-alone format" and "can't be in an employment application."

### **D. Outline of the full instrument**

1\.     Disclosure document  
a.     Heading identifying it as a background-check disclosure.  
b.     Statement that a consumer report (and, if applicable, an investigative consumer report) may be obtained for employment purposes.  
c.      Optional concise explanation of what a report is and its sources (*Walker*).  
2\.     Authorization (same page or separate)  
a.     Consumer's written or e-signed consent naming the employer.  
b.     Identifying data for the CRA (name, DOB, SSN, prior addresses), often on a separate data sheet.  
3\.     Separate documents (must not be merged)  
a.     CFPB Summary of Rights.  
b.     State notices (California ICRAA, New York Article 23-A, etc.).  
c.      Any release, arbitration, or application terms.  
4\.     Employer certification to the CRA (§1681b(b)(1)).  
5\.     Pre-adverse and adverse action notices (§1681b(b)(3), §1681m).

The disclosure and authorization are the only items allowed on the consent page; everything else travels as separate documents in the same packet, and the employer's certification lets the CRA rely on the consent without seeing it.

### **E. Insights and observations**

•      **"Solely" means solely.** Even helpful or legally mandated content (state notices) breaks compliance (*Gilberg*). For agents, consent UIs should resist "just one more line" additions such as data-retention notes or indemnities.  
•      **Bundling a waiver is the paradigm violation.** *Syed* found willfulness because the text was unambiguous. A design rule that is mechanically checkable (one purpose per consent object) is easier to comply with and easier to prove.  
•      **Vendor templates propagate defects.** The *Syed* form came from a third-party vendor, yet the employer was liable. Agent platforms supplying consent templates to integrators carry similar systemic risk.  
•      **Counterparty relies on certification, not inspection.** The CRA's legal shield is the user's certification. Agent ecosystems often work the same way — the API provider trusts the client app's attestation that consent was obtained — so audit rights over the consent record matter.  
•      **Standing doctrine limits enforcement.** After *Spokeo* and *TransUnion v. Ramirez*, circuits differ on whether a cluttered form is a concrete injury (*Groshek* vs. *Syed*). Strict format rules depend on private plaintiffs who can still get into court.  
•      **Evergreen consent is a gap.** FCRA does not set an expiry; many forms authorize checks throughout employment. Agent mandates should set expiry explicitly rather than inherit this ambiguity.  
•      **Unverified:** No 2024–2026 appellate decisions on FCRA disclosure formatting surfaced in searches.

**Sources:** [15 U.S.C. §1681b (LII)](https://www.law.cornell.edu/uscode/text/15/1681b) · [15 U.S.C. §1681n (LII)](https://www.law.cornell.edu/uscode/text/15/1681n) · [Syed v. M-I, LLC (vLex)](https://case-law.vlex.com/vid/syed-v-m-i-894363444) · [DWT on Syed (2017)](https://www.dwt.com/blogs/employment-labor-and-benefits/2017/03/ninth-circuit-solely-means-solely-when-it-comes-to) · [Jones Day on Gilberg (2019)](https://www.jonesday.com/en/insights/2019/02/ninth-circuit-holds-state-and-fcra) · [Cooley on Gilberg (2019)](https://www.cooley.com/news/insight/2019/2019-01-31-stricter-interpretation-of-fcra-requirement-for-standalone-background-check-disclosure) · [Polsinelli on standalone disclosure (2019)](https://www.polsinelli.com/polsinelli-at-work/navigating-the-fcras-standalone-disclosure-requirement) · [Foley on Walker and Luna (2020)](https://www.foley.com/insights/publications/2020/05/twin-ninth-circuit-clarify-fcra-disclosure/) · [Ogletree on Groshek (2017)](https://ogletree.com/insights-resources/blog-posts/seventh-circuit-finds-no-standing-when-background-check-disclosures-contain-extraneous-information) · [FTC: Background Checks, What Employers Need to Know](https://www.ftc.gov/business-guidance/resources/background-checks-what-employers-need-know) · [Cal. Civ. Code §1786.16](https://leginfo.legislature.ca.gov/faces/codes_displaySection.xhtml?lawCode=CIV&sectionNum=1786.16) · [ClearStar: CFPB Summary of Rights update](https://www.clearstar.net/cfpb-updates-summary-of-your-rights-under-the-fair-credit-reporting-act-with-mandatory-compliance-date-of-march-20-2024/) · [ClearStar: CFPB withdraws FCRA guidance (2025)](https://www.clearstar.net/?p=23058) · [Asurint: class settlement over liability waiver (2021)](https://asurint.com/blog/class-action-settlement-for-violation-of-fcras-stand-alone-disclosure-requirement/)

## **12\. USPTO powers of attorney (patent and trademark)**

**A. Title:** Patents: PTO/AIA/80, *Power of Attorney to Prosecute Applications Before the USPTO* (by assignee of record, Rev. 07-17). PTO/AIA/82A/82B/82C, *Transmittal for Power of Attorney* / *Power of Attorney by Applicant* / list of practitioners (Rev. 07-13). PTO/AIA/81, *Power of Attorney to One or More of the Joint Inventors and Change of Correspondence Address* (Rev. 07-12). PTO/AIA/96, *Statement under 37 CFR 3.73(c)*. PTO/SB/124, *Request for Customer Number Data Change*. Trademarks: *Change Address or Representation (CAR) Form* (TEAS, now also in Trademark Center). Rules: 37 CFR 1.31–1.36, 3.71–3.73, 2.17–2.19.

**B. Blurb:** Delegate to a Customer Number roster, and prove chain of title before delegating.

### **C. Background**

**1\. Who it comes from:** The United States Patent and Trademark Office (Department of Commerce). For patents, the applicant or patent owner (often a corporate assignee) signs the POA, usually on a form a practitioner prepares, and the firm maintains the Customer Number roster. For trademarks, the owner or the attorney files the CAR electronically; under 37 CFR 2.17(b), a qualified attorney can be recognized simply by appearing and signing.

**2\. Key lesson for AI-agent authorization:** **Let principals delegate to a stable group handle (a Customer Number) whose membership the agent-side organization maintains in a registry, and require the principal to first prove its own title to the asset before it can delegate.** Under 37 CFR 1.32(c)(2), a POA may name "those registered patent practitioners associated with a Customer Number." Adding or removing a practitioner on that number (PTO/SB/124) updates authority across every application that appointed it, avoiding new papers in each application (MPEP 403). The assignee's own standing rests on a 3.73(c) chain-of-title statement citing recorded assignments (reel and frame). In agent terms: grant to a team or service identity with registry-managed membership, cap individually named grantees, and require the grantor to present a verifiable ownership credential.

**3\. The instrument:**

•      **Scenarios.** Prosecuting patent applications and handling issued patents (reexamination, supplemental examination, maintenance petitions). Prosecuting and maintaining trademark applications and registrations.  
•      **Who may be named (patents, 1.32(c)).** Joint inventors; "those registered patent practitioners associated with a Customer Number"; or "ten or fewer patent practitioners, stating the name and registration number of each." Firms are not recognized (MPEP 402). More than ten named practitioners forces Customer Number use.  
•      **Powers.** "To transact all business in the United States Patent and Trademark Office connected therewith" for the identified application (82B). PTO/AIA/80 covers "any and all patent applications assigned only to the undersigned" per USPTO assignment records.  
•      **Principal's proof of authority.** Original applicants are presumed owners (3.73(a)). An assignee that is not the original applicant must establish its ownership (3.73(c)(1)) with documentary chain-of-title evidence or a statement of where the chain is recorded (reel and frame). The signer must show authority through a title with apparent authority, a statement of authorization, or a practitioner's signature (3.73(d)). Each AIA/80 must be filed together with a 3.73(c) statement in each application where it is used.  
•      **Duration and revocation.** No expiry. A new POA revokes earlier ones; a POA to a Customer Number is treated as a request to revoke prior powers (1.36(a)). An assignment does not of itself revoke a POA. Practitioner withdrawal requires the Director's approval, and a request to delete all practitioners from a Customer Number may be refused if a reply is due soon (1.36(b)).  
•      **Trademarks.** Only individuals qualified under 37 CFR 11.14 may represent (2.17(a)). A POA must be signed by the owner or someone with legal authority to bind, and all joint owners must sign (2.17(c)). One POA can cover all existing applications or registrations with the identical owner name (2.17(d)). Recognition ends when the mark registers, ownership changes, or the application is abandoned (2.17(g)). Revocation must be signed by the owner; a change of correspondence address does not revoke (2.19). The Office corresponds only with the recognized attorney (2.18).  
•      **Counterparty validation.** The USPTO checks registration numbers against the roster of registered practitioners, Customer Number association, assignment records, and (trademarks) attorney bar attestations. The CAR requires bar state, year of admission, and license number, plus an attestation of good standing.

**4\. Context:**

•      **Origin.** Customer Number practice and the current 1.32 structure come from the 2004 *Revision of Power of Attorney and Assignment Practice* rule (69 FR 29877\) and the 2012 AIA implementation (77 FR 48813). The AIA rule shifted POA signing from inventors to the "applicant" (often the assignee) for applications filed on or after September 16, 2012\.  
•      **Trademark U.S. Counsel Rule.** Effective August 3, 2019 (84 FR 31498), foreign-domiciled trademark applicants must use a U.S.-licensed attorney, and domicile is a street address (2.189). The USPTO cited foreign filings rising from 19% (FY15) to 26% (FY17) and foreign pro se filings from 25.4% to 44.0%. By August 2023 it counted 258 final sanction orders, 18,789 terminated applications, and 3,297 sanctioned registrations. On August 6, 2025, it terminated over 52,000 applications and registrations tied to one foreign filing firm that had forged U.S. attorneys' e-signatures and misused USPTO.gov accounts.  
•      **Identity verification.** Required for trademark filing since August 6, 2022, through ID.me or a notarized paper form. Attorney support staff had to verify and be sponsored by a verified attorney from January 20, 2024\. Patent Center required verification for all users from September 11, 2025, ending guest access.  
•      **Patent foreign-applicant rule.** *Required Use by Foreign Applicants and Patent Owners of a Patent Practitioner* (91 FR 13519, March 20, 2026; effective July 20, 2026): juristic entities and any foreign-domiciled applicant or patent owner must act through a registered practitioner. It also revised the 1.32(a)(1) definition of "patent practitioner."

**5\. Stability and variants:** Patent forms are old but stable (AIA/80 Rev. 07-17, AIA/82 Rev. 07-13, AIA/81 Rev. 07-12), with OMB approval through November 30, 2028\. Note that PTO/AIA/81 is the power of attorney to joint inventors, not a Customer Number POA; both AIA/80 and AIA/82B offer a Customer Number option or a named list. Pre-AIA versions (PTO/SB/80, SB/81) remain for applications filed before September 16, 2012\. On the trademark side, the CAR is a TEAS form; in May 2026 IIPLA reported that Trademark Center now supports address and representation changes (the TEAS CAR retirement date was not verified).

### **C2. Drill-down: the operative clause**

"I hereby revoke all previous powers of attorney given in the application identified in either the attached transmittal letter or the boxes below. ... I hereby appoint the Patent Practitioner(s) associated with the following Customer Number as my/our attorney(s) or agent(s), and to transact all business in the United States Patent and Trademark Office connected therewith for the application referenced in the attached transmittal letter (form PTO/AIA/82A) or identified above."

— PTO/AIA/82B, Power of Attorney by Applicant (Rev. 07-13)

"I hereby appoint: Practitioners associated with Customer Number: ... As attorney(s) or agent(s) to represent the undersigned before the United States Patent and Trademark Office (USPTO) in connection with any and all patent applications assigned only to the undersigned according to the USPTO assignment records or assignment documents attached to this form in accordance with 37 CFR 3.73(c)."

— PTO/AIA/80 (Rev. 07-17)

The grantor is the applicant (inventor, assignee, obligated assignee, or a person with sufficient proprietary interest) or the assignee of record. A juristic entity signs through a person authorized to act on its behalf, whose title is stated.

The grantee is indirect: whoever is "associated with" the Customer Number at the time of action. The delegating verbs are "appoint ... as my/our attorney(s) or agent(s)" and "to transact all business ... connected therewith." Scope is limited by asset: one application (82B), or every application "assigned only to the undersigned" per assignment records (AIA/80). The revocation clause comes first, making this a "replace, not add" operation.

Not delegated: anything outside that application or patent, and practice by non-registered persons. Some acts also need the applicant's own signature or a 3.73(c) showing. The Office is bound to correspond with and accept papers from practitioners of record (1.33), and assignment alone does not cut off their authority (1.36(a)).

### **D. Outline of the full instrument**

1\.     PTO/AIA/82A — Transmittal: application number, filing date, first inventor, title, art unit, examiner, docket number. Signed by applicant or practitioner.  
2\.     PTO/AIA/82B — Power of Attorney by Applicant  
a.     Revocation of prior POAs.  
b.     Appointment: Customer Number or named list (82C, up to ten).  
c.      Correspondence address: Customer Number address or firm or individual.  
d.     Applicant identity: inventor, legal representative, assignee or obligated assignee, or proprietary-interest party.  
e.     Signature, name, title (for a juristic entity), and date.  
3\.     PTO/AIA/80 (assignee version) — revocation, Customer Number or named appointment over all applications assigned to the signer, correspondence address, and assignee signature. Paired with a PTO/AIA/96 3.73(c) statement per application.  
4\.     PTO/AIA/96 — 3.73(c) statement: assignee identity, chain of title via attached documents or reel and frame, and authority of the signer.  
5\.     PTO/SB/124 — Customer Number data change: add or delete practitioners, change correspondence or fee address.  
6\.     Trademark CAR — owner information and domicile; attorney information (bar state, year, license number); domestic representative; correspondence emails; revoke or appoint attorney; signature attestation (owner, U.S. attorney, or Canadian agent), with /name/ e-signature.

Ownership proof (3.73) authorizes the principal. The POA points to a roster handle. The roster (SB/124) is maintained separately, so personnel changes never touch the client's grant.

### **E. Insights and observations**

•      **Indirection through a registry.** A Customer Number works like an OAuth "group" or SPIFFE trust domain: the principal trusts the handle, and the firm manages membership. The risk is that the principal no longer controls who is in the group. A practitioner who leaves must be removed and needs a new POA to keep a client (MPEP 403).  
•      **Hard cap on enumerated grantees.** More than ten named individuals forces use of a group handle. This bounded-list rule keeps grants auditable and pushes large teams into a managed registry.  
•      **Delegator must prove title.** The 3.73(c) chain-of-title requirement means an assignee cannot delegate until it shows recorded ownership. For agents, the issuer of a mandate should present a verifiable credential for the asset or account, not just authenticate.  
•      **Recognition by conduct versus by document.** In trademarks, an attorney can be recognized just by signing or appearing (2.17(b)). The 52,000-filing termination shows this shortcut is the attack surface — forged attorney credentials and borrowed accounts — hence identity verification and sponsorship.  
•      **Sponsorship as delegated account access.** Since January 2024, paralegals must verify their own identity and be sponsored by a verified attorney: a two-layer credential (human identity plus delegator link) that maps neatly to agent sub-identities operating under a principal's account.  
•      **Lifecycle-bound recognition.** Trademark recognition ends automatically at registration, change of ownership, or abandonment (2.17(g)). Authority expires with workflow state rather than time — a useful default for agents.  
•      **Assignment does not revoke.** Under 1.36(a), the old POA survives a transfer until the new owner acts. This is a known gap: agent systems should flag or suspend grants when ownership of the governed resource changes.

**Sources:** [37 CFR 1.32 (eCFR)](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-1/subpart-A/subject-group-ECFRf0c3b6dc1ff4fce/section-1.32) · [37 CFR 1.36 (eCFR)](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-1/subpart-A/subject-group-ECFRf0c3b6dc1ff4fce/section-1.36) · [37 CFR 3.73 (eCFR)](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-3/section-3.73) · [37 CFR 2.17 (eCFR)](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-2/subject-group-ECFR4cdc1af6c3b4a63/section-2.17) · [37 CFR 2.19 (eCFR)](https://www.ecfr.gov/current/title-37/chapter-I/subchapter-A/part-2/subject-group-ECFR4cdc1af6c3b4a63/section-2.19) · [PTO/AIA/80](https://www.uspto.gov/sites/default/files/documents/aia0080.pdf) · [PTO/AIA/81](https://www.uspto.gov/sites/default/files/documents/aia0081.pdf) · [PTO/AIA/82A-C](https://www.uspto.gov/sites/default/files/documents/aia0082.pdf) · [MPEP 402](https://www.uspto.gov/web/offices/pac/mpep/s402.html) · [MPEP 403](https://www.uspto.gov/web/offices/pac/mpep/s403.html) · [TEAS Change Address or Representation form](https://www.uspto.gov/sites/default/files/documents/TM-TEAS-Change-Address-or-Reprensentation-Form.pdf) · [84 FR 31498: U.S. counsel rule (2019)](https://www.federalregister.gov/documents/2019/07/02/2019-14087/requirement-of-us-licensed-attorney-for-foreign-trademark-applicants-and-registrants) · [USPTO: 52,000 fraudulent filings terminated (Aug. 2025\)](https://www.uspto.gov/about-us/news-updates/uspto-has-terminated-more-52000-fraudulently-filed-trademark-applications-and) · [USPTO trademark identity verification](https://www.uspto.gov/trademarks/apply/identity-verification) · [Patent Center identity verification (Sept. 2025\)](https://www.uspto.gov/subscription-center/2025/effective-tomorrow-identity-verification-will-be-required-all-patent) · [91 FR 13519 foreign applicant patent rule (2026)](https://www.govinfo.gov/content/pkg/FR-2026-03-20/pdf/2026-05564.pdf) · [IIPLA: Trademark Center address/representation changes (2026)](https://iipla.org/news/uspto-enhances-trademark-center-with-new-filing-features-for-address-changes-and-renewals)

## **13\. DMV vehicle power of attorney and the federal odometer POA**

**A. Title:** California DMV *Power of Attorney*, REG 260 (REV. 3/2007, still the version posted); Texas DMV *Limited Power of Attorney for Eligible Motor Vehicle Transactions*, Form VTR-271 (Rev. 11/20), with its secure sister *Power of Attorney for Transfer of Ownership to a Motor Vehicle*, Form VTR-271-A; Arizona MVD *Power of Attorney*, Form 48-1001 (R07/25). Federal overlay: 49 CFR Part 580, *Odometer Disclosure Requirements*, §§ 580.4, 580.5, 580.13–580.17, as amended by 84 FR 52664 (Oct. 2, 2019; effective Dec. 31, 2019).

**B. Blurb:** One VIN, one transaction, and the odometer statement stays with the principal.

### **C. Background**

**1\. Who it comes from:** State motor-vehicle agencies (California DMV, TxDMV, Arizona ADOT MVD) publish the forms. NHTSA writes the federal odometer rules that cap what any state POA may do. The vehicle owner fills in each instance, usually at the request of a dealer, lender, buyer or relative.

**2\. Key lesson for AI-agent authorization:** **Bind ordinary delegated authority to a single object identifier (the VIN), and for the one high-risk attestation (mileage) either forbid delegation or require a regulator-issued, tamper-evident, logged instrument with a strict fallback order.** In agent terms, routine title paperwork is a scope like title:transfer bound to vin=…, while the odometer statement is a separate, non-delegable-by-default claim. Where federal law allows delegation, it demands a jurisdiction-issued secure form or an electronic record that logs creation, signing, access and tampering attempts — a step-up credential with a mandatory audit trail.

**3\. The instrument:**

•      **Scenarios.** The owner cannot appear: a dealer or lender needs to sign title papers; the title is held by a lienholder or lost at sale; the owner is out of state.  
•      **Parties.** Grantor (owner, buyer or seller); attorney-in-fact (person, dealer or business entity acting through a named employee); the DMV as counterparty.  
•      **Powers.** California: "to complete all necessary documents, as needed, to transfer ownership." Texas: every act needed to purchase, transfer and assign title, with "full power of substitution." Arizona: sign papers to secure title and endorse and transfer it.  
•      **Binding to an object.** All three forms open with VIN, year, make and body style. California's procedures manual says a restricted POA must contain the VIN/HIN; only a general POA may omit it.  
•      **Limits.** California's manual bars using a POA to disclose odometer mileage, to sign a Statement of Facts attesting the principal's knowledge, to re-delegate, or to act for executors. Texas VTR-271 cannot be used in a dealer transaction to assign title on a vehicle subject to odometer disclosure; the secure VTR-271-A must be used instead.  
•      **Execution.** California: ink signatures, certified under penalty of perjury, no notary. Texas: blue or black ink, no alterations, and photocopies of both parties' photo ID when used to apply for title or registration. Arizona: acknowledgment before a notary or an MVD agent.  
•      **Duration and revocation.** None of the three forms states an expiry or a revocation method. In practice the authority is spent when the transaction completes.

**4\. Context:** Dealers, lenders and title services use these forms daily. The federal secure-POA regime is generally traced to the Truth in Mileage Act of 1986 (the original statute and rulemaking were not opened for this entry). NHTSA estimates that more than 450,000 vehicles are sold each year with false odometer readings. The 2019 rule records at least 40 million odometer disclosures a year in the U.S. Failure modes include dealers holding blank POAs to "wash" mileage, and transferees signing for both sides; § 580.5(h) bans signing as both transferor and transferee in the same transaction except as §§ 580.13–580.14 allow.

**5\. Stability and variants:** Every state has its own form. California's REG 260 has not been revised since 2007; California has stopped producing its Secure Power of Attorney (SPOA) form but still accepts it, and uses the POA section on the secure REG 262 for convenience. Texas revised VTR-271 in 2020 alongside bulletin RTB 013-20 on the federal exemption change and broader use of VTR-271-A. Arizona's 48-1001 was revised July 2025\. The 2019 federal rule added electronic titles, electronic POAs and scanned-paper POAs, and extended the age exemption from 10 to 20 years for model year 2011 and newer.

### **C2. Drill-down: the operative clause**

Federal (49 CFR 580.13(a), (c), summarized with quoted fragments): if the law of the jurisdiction permits and the transferor's physical title is held by a lienholder or lost, or the electronic title is held by a lienholder or cannot be accessed, "the transferor may grant a power of attorney to their transferee" for mileage disclosure. The transferor "must appoint the transferee their attorney-in-fact for the purpose of mileage disclosure," and signs a disclosure giving the reading (no tenths), date, both parties' names and addresses, and make, model, year, body type and VIN.

— 49 CFR 580.13(a), (c) (84 FR 52699, Oct. 2, 2019\)

State: "\[I/we\] appoint … as my attorney in fact, to complete all necessary documents, as needed, to transfer ownership as required by law."

— California REG 260 (REV. 3/2007)

The federal grantor is the seller. The grantee is the buyer only, never a stranger. The verb is "appoint … attorney-in-fact for the purpose of mileage disclosure," and the object is one VIN at one reading. Conditions are a legally unavailable title and state permission. The seller still makes the substantive mileage certification personally, choosing actual, exceeds-mechanical-limits, or not-actual; the agent only copies it onto the title exactly (§ 580.13(g)). If the POA mileage is lower than the title mileage, the POA is void unless a discrepancy warning was given. The DMV must keep the POA with the title for three years or its own retention period. A reverse POA (§ 580.14) lets the buyer authorize the seller to review the title and acknowledge disclosure, only on the same Part B/C form.

### **D. Outline of the full instrument**

1\.     State POA (REG 260 / VTR-271 / 48-1001)  
a.     Vehicle block — VIN, year, make, model, body, plate.  
b.     Grantor and attorney-in-fact identities (DL, ID or dealer number in CA; DL and DOB in AZ).  
c.      Grant clause — transfer/title acts only.  
d.     Certification and signature — perjury (CA), felony warning (TX), notary or MVD agent (AZ).  
e.     Tear-off copy for the principal (CA).  
2\.     Federal secure odometer POA (§ 580.13–580.15)  
a.     Part A — seller-to-buyer mileage POA and disclosure.  
b.     Part B — buyer-to-seller POA to review title and acknowledge (§ 580.14).  
c.      Part C — certification under § 580.15.  
d.     Federal warning on fines and imprisonment.

The state form handles routine paperwork. The federal form is a separate, jurisdiction-issued, secure document because mileage is the attestation fraudsters target.

### **E. Insights and observations**

•      **Security is the issuer's job.** § 580.4(a) requires physical POAs under §§ 580.13–580.14 to be issued by the jurisdiction on a secure process. California rejects copies of REG 262 as a secure document but accepts photocopies or faxes of the plain REG 260\. Risk tier decides whether a copy counts.  
•      **Electronic POA logging (2019).** § 580.4(b) requires electronic POAs held in a secure environment, with systems recording creation, odometer-signing and access times plus unauthorized alteration attempts — essentially a regulator-specified audit log for a delegated attestation.  
•      **Warnings before signing.** For electronic transactions the federal warning must display before any electronic signatures are executed (§ 580.5(d)). Agent UX should likewise surface liability before the principal approves.  
•      **Substitution is a design choice.** Texas grants "full power of substitution" (re-delegation); California forbids reassigning the right. Agent frameworks need an explicit may\_redelegate flag.  
•      **Exemption by age.** Vehicles of model year 2011 and newer stay subject to disclosure for 20 years (§ 580.17); model year 2010 and older stay on the 10-year rule. Scope can expire by object attributes, not just by time.  
•      **No expiry or revocation on the face.** None of the three state forms carries an end date. A long-lived VIN-bound POA held by a dealer is a latent risk; agent grants should carry explicit expiry.  
•      **Verification gap.** The VTR-271-A form itself and the full text of RTB 013-20 could not be opened, so how Texas issues and serializes the secure form is unverified here.

**Sources:** [49 CFR Part 580 (eCFR)](https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-580) · [49 CFR 580.13 (eCFR)](https://www.ecfr.gov/current/title-49/subtitle-B/chapter-V/part-580/section-580.13) · [49 CFR 580.14 (LII)](https://www.law.cornell.edu/cfr/text/49/580.14) · [49 CFR 580.4 (LII)](https://www.law.cornell.edu/cfr/text/49/580.4) · [49 CFR 580.5 (LII)](https://www.law.cornell.edu/cfr/text/49/580.5) · [84 FR 52664, Odometer Disclosure Requirements final rule (Oct. 2, 2019\)](https://www.govinfo.gov/link/fr/84/52673) · [NHTSA Odometer Fraud](https://www.nhtsa.gov/equipment/odometer-fraud) · [CA DMV REG 260](https://www.dmv.ca.gov/portal/form/power-of-attorney-reg-260-pdf/) · [CA DMV VIRPM 1.125 Signature by POA](https://www.dmv.ca.gov/portal/handbook/vehicle-industry-registration-procedures-manual-2/general-registration-information/signature-by-power-of-attorney-poa/) · [CA DMV VIRPM Secure Power of Attorney](https://www.dmv.ca.gov/portal/handbook/vehicle-industry-registration-procedures-manual-2/odometer-mileage-reporting/secure-power-of-attorney) · [TxDMV VTR-271](https://www.txdmv.gov/sites/default/files/form_files/VTR-271.pdf) · [TxDMV forms list](https://www.txdmv.gov/forms) · [TxDMV RTB 013-20 notice](https://txdmv.blogs.govdelivery.com/rtb-013-20-federal-odometer-disclosure-exemption-change-and-additional-use-of-the-power-of-attorney-for-transfer-of-ownership-to-a-motor-vehicle-form-vtr-271-a/) · [ADOT Power of Attorney page](https://azdot.gov/content/power-attorney) · [ADOT Form 48-1001](https://apps.azdot.gov/files/mvd/mvd-forms-lib/48-1001.pdf)

## **14\. Corporate signing resolutions and incumbency certificates**

**A. Title:** Board (or manager/member) resolutions authorizing signers for bank accounts, borrowing and contracting, paired with a Secretary's Certificate / Certificate of Incumbency with specimen signatures. Examples: First Internet Bank of Indiana "Corporate Authorization Resolution" (no form number or revision date printed); Louisiana Division of Administration, LCDBG Grantee Handbook Appendix D-3 "Sample Resolution of the Board of Directors" and Form A-3 "Authorized Signature Form" (2021). Governing law: Delaware General Corporation Law (DGCL) §§ 141(f), 142, 158; Delaware LLC Act § 18-402; FinCEN Customer Due Diligence (CDD) rule, 31 CFR 1010.230.

**B. Blurb:** The board grants power to titles; the secretary certifies which humans hold them.

### **C. Background**

**1\. Who it comes from:** No single author. Banks, lenders and grant agencies publish their own resolution templates; the entity's board (or LLC managers/members) adopts the resolution, and the corporate secretary (or another officer) signs the certificate. Corporate law supplies the authority chain: the board acts under DGCL § 141, and officers derive their roles from § 142 and the bylaws.

**2\. Key lesson for AI-agent authorization:** **Separate the grant of authority (to a role) from the binding of that role to an identity (a named person plus a specimen signature), and let the counterparty rely on the last certified binding until it receives written revocation.** In agent terms, the resolution is a policy that grants scopes to roles ("any two of Agents A–F may borrow"), and the incumbency certificate is a signed role-to-key binding, like a certificate mapping a role to a public key. Rotation means replacing the binding, not re-passing the policy. Because the relying party's duty is defined by notice received, revocation must be pushed to each relying party and acknowledged.

**3\. The instrument:**

•      **Scenarios:** opening deposit accounts, signing checks and wires, borrowing and pledging collateral, signing grant or loan agreements, closing deals.  
•      **Parties:** the entity (principal); the board or managers (grantor body); officers or named agents (grantees); the secretary (certifier); the bank, lender or agency (relying party).  
•      **Powers delegated:** The First Internet Bank form lists six powers, with a column for which agents hold each and how many signatures are required: (1) all powers in the resolution, (2) open accounts, (3) endorse and withdraw, (4) borrow and sign notes, (5) pledge assets and guarantee, (6) "Other." A "Limitations of Powers" box lets the entity narrow authority.  
•      **Conditions:** signature counts (single or dual control), and specific dollar or account limits written into the limitation box.  
•      **Duration and revocation:** the resolution stays in force until the bank receives and records written notice of rescission or modification. Prior resolutions survive unless the new one names what it supersedes.  
•      **Validation:** the bank compares signatures to specimens; the secretary's certificate attests that the resolution was duly adopted and remains unrevoked. The Louisiana Form A-3 adds a separation-of-duties rule: the certifying officer may not be one of the authorized signers, and two signatures are required on each payment request.

**4\. Context:** Every corporate or LLC bank account and nearly every commercial loan closing uses this pair. Credit agreements make an incumbency certificate a closing condition; agents and lenders may rely on the most recent certificate until a newer one or written notice arrives. Banks typically want a certificate dated within about six months (market practice, not a legal rule).

The CDD rule (81 FR 29451, May 11, 2016; amended 2017\) adds a separate layer: banks must identify and verify each 25% owner and one control person of a legal entity customer. On February 13, 2026, FinCEN issued exceptive relief limiting re-verification to the first account opening, later doubt about reliability, or risk-based triggers. FinCEN has also exempted domestic U.S. companies from Corporate Transparency Act BOI reporting (interim final rule, March 2025; FinCEN's BOI page reports a final rule effective August 14, 2026), so banks cannot lean on a government registry for domestic entities.

Failure modes: stale certificates naming departed officers, forged secretary's certificates, and blank "Other" powers that grant more than intended.

**5\. Stability and variants:** The legal pattern has been stable for decades, but there is no single form. Variants include bank-specific corporate, LLC, partnership and nonprofit resolutions; unanimous written consents in lieu of a meeting (DGCL § 141(f)); LLC manager consents (where § 18-402 lets the operating agreement override the default rule that every member or manager can bind the LLC); grant-program resolutions (Louisiana D-3); and closing-set secretary's certificates with attached charter, bylaws and good-standing certificate.

### **C2. Drill-down: the operative clause**

Paraphrase (First Internet Bank Corporate Authorization Resolution, Resolution 2): the resolutions and the agents' authority stay in full force until the bank receives, and has a reasonable time to record, written notice that they were rescinded or modified; any change must come with documentation satisfactory to the bank. Short quote: "until express written notice of its rescission or modification has been received".

— First Internet Bank of Indiana, Corporate Authorization Resolution, Resolutions 2–3 (undated form)

"...any action required or permitted to be taken at any meeting of the board of directors or of any committee thereof may be taken without a meeting if all members of the board or committee, as the case may be, consent thereto in writing..." and "...a consent may be documented, signed and delivered in any manner permitted by § 116 of this title."

— 8 Del. C. § 141(f)

The grantor is the corporation acting through its board, either at a meeting or by unanimous written consent. The delegating verbs are "designate" and "authorize": the bank becomes the depository, and the listed agents get specific powers with specified signature counts. Resolution 3 makes an agent's signature conclusive evidence of authority, and Resolution 7 lets the bank honor facsimile signatures, PINs and digital signatures, with agents allowed to hold the private key. Not delegated: anything outside the checked powers or beyond the written limitations. The counterparty is bound to honor the grant until notice arrives, and it is protected for acting on it before then.

### **D. Outline of the full instrument**

1\.     Header: identifies the bank and the entity, with EIN and state of incorporation.  
2\.     Secretary's certification: confirms a duly called meeting (or written consent), that the text is a true copy, and that it has not been rescinded.  
3\.     Agents table: letters A–F, each with name, title, signature and optional facsimile signature (the specimen layer).  
4\.     Powers granted: six powers, each with an agent-letter column and a signatures-required column.  
5\.     Limitations of powers: free-text narrowing.  
6\.     Effect on previous resolutions: names any superseded resolution; if blank, prior ones stay in force.  
7\.     Certification of authority: confirms the board had power to adopt; nonprofit checkbox; seal; attesting second officer.  
8\.     Resolutions 1–7:  
a.     Bank designated as depository.  
b.     Continuing effect until written notice.  
c.      Agent signature is conclusive evidence; agents may sign ancillary agreements.  
d.     Ratification of prior transactions.  
e.     Account agreements bind the entity; the bank may charge items with the required signatures.  
f.      Bank may issue cards and access devices.  
g.     Alternative signature and verification codes (facsimile, PIN, digital).  
9\.     Bank-use block: receipt date, initials, superseding reference.

The resolution (policy) and the agents table (identity binding) sit in one document but play different roles. Banks often accept a fresh incumbency page without a new resolution when only people change.

### **E. Insights and observations**

•      **Two-key separation is built in.** The Louisiana A-3 form bars the certifying officer from being an authorized signer, and many bank forms require an attesting second officer. This mirrors separating the credential issuer from the credential holder in an agent system.  
•      **Notice-based revocation shifts risk to the principal.** Until the bank records written notice, a fired treasurer remains a valid signer to the bank. An agent registry needs push revocation with acknowledgment receipts, not passive status pages.  
•      **Default-continuation trap.** The "Effect on Previous Resolutions" box means old grants survive unless named. Agent platforms should default new mandates to replace old ones explicitly, or list every live grant the principal holds.  
•      **Statutory officer floors.** Some regimes treat titles as self-authenticating: 19 CFR 141.38 lets a known president, vice president, treasurer or secretary sign customs documents without a power of attorney (see item 16). Role-based trust works only when the relying party can verify the role.  
•      **Beneficial ownership is a different question from signing authority.** The CDD rule asks who owns or controls the entity, not who may sign. The 2026 FinCEN relief and the BOI exemption for U.S. companies leave banks relying more on customer certification, with re-verification required when facts reasonably call reliability into question (31 CFR 1010.230(b)(2)).  
•      **Digital-signature clause is a precedent for agent keys.** Resolution 7 already contemplates an agent holding a private key, and it disclaims bank liability for unauthorized use of those codes — a template for allocating loss when an AI agent's credential is misused.  
•      **LLCs flip the default.** Under Del. § 18-402, every member or manager can bind the LLC unless the operating agreement provides otherwise. Counterparties therefore ask for the operating agreement or a manager's certificate, not just a resolution.

**Sources:** [First Internet Bank – Corporate Authorization Resolution](https://www.firstib.com/wp-content/uploads/2016/02/Corporate-Resolution.pdf) · [First Internet Bank – corpdepapp.pdf](https://www.firstib.com/resource/files/corpdepapp.pdf) · [Louisiana DOA – D-3 Sample Resolution of the Board of Directors](https://www.doa.la.gov/media/jnsbmges/d-3-sample-resolution-of-the-board-of-directors.pdf) · [Louisiana DOA – 2021 Authorized Signature Form (A-3)](https://doa.la.gov/media/affhgrni/2021-authorized-signature-form.pdf) · [Delaware Code Title 8, Subchapter IV (§§ 141–142)](https://delcode.delaware.gov/title8/c001/sc04/index.html) · [Delaware Code Title 8, Subchapter V (§ 158\)](https://delcode.delaware.gov/title8/c001/sc05/index.html) · [Delaware Code Title 6, Ch. 18, Subchapter IV (§ 18-402)](https://delcode.delaware.gov/title6/c018/sc04/index.html) · [LII – 19 CFR 141.38](https://www.law.cornell.edu/cfr/text/19/141.38) · [eCFR 31 CFR 1010.230](https://www.ecfr.gov/current/title-31/subtitle-B/chapter-X/part-1010/subpart-B/section-1010.230) · [DLA Piper – FinCEN exceptive relief from CDD rule (Mar. 2026\)](https://www.dlapiper.com/insights/publications/2026/03/fincen-issues-exceptive-relief-from-cdd-rule-requirements) · [FinCEN – BOI page](https://www.fincen.gov/BOI) · [Law Insider – Incumbency Certificates clauses](https://www.lawinsider.com/clause/incumbency-certificates) · [UpCounsel – Certificate of Incumbency](https://www.upcounsel.com/incumbency-certificate)

## **15\. Property management and listing agreements**

**A. Title:** California Association of REALTORS® (C.A.R.) Property Management Agreement (Form PMA; C.A.R.'s standard-forms list, updated June 2026, shows revision 12/24; the publicly hosted sample reviewed here is PMA 8/12). C.A.R. Residential Listing Agreement – Exclusive (Form RLA; the June 2026 list shows 12/24; a December 2025 release reportedly revised it again; text reviewed here is the RLA 6/24 draft). Sister forms: RLAN (open listing), RLASR (seller-reserved), KLA (keysafe/lockbox addendum). Governing law: Cal. Bus. & Prof. Code §§ 10131, 10145, 10176(e)–(f); 10 CCR §§ 2831.2, 2832, 2832.1, 2834, 2835\.

**B. Blurb:** Exclusive, dated, fee-linked agency with a dollar cap that forces owner sign-off.

### **C. Background**

**1\. Who it comes from:** C.A.R., a private trade association, authors and copyrights both forms and distributes them to members through zipForm and other platforms. The listing or managing broker fills in each instance with the owner. The state supplies the licensing frame: only a licensed broker may, for compensation, lease, rent, collect rents or solicit listings for another (B\&P § 10131(b)). The "Orange Property Manager" sample PMA cited in the source list could not be located (see E).

**2\. Key lesson for AI-agent authorization:** **Grant broad standing authority for routine operations, but put a per-item dollar ceiling on spending and require prior principal approval above it, with a narrowly defined emergency override.** This is a spend-limit scope plus step-up approval: the agent acts alone below \$X, must get consent above \$X, and may exceed \$X without consent only for listed emergencies (protecting property, preventing injury, avoiding suspended services or legal penalties). The exclusive grant, the fixed termination date and the compensation triggers show how to bound an agent's tenure and incentives in the same instrument that grants its power.

**3\. The instrument:**

•      **PMA scenario:** an owner hands a residential rental to a licensed broker to run day to day.  
a.     Grant: the owner appoints the broker with the exclusive right to rent, lease, operate and manage the property for a stated term. An optional clause allows termination on 30 days' written notice after an initial period, after which the agreement becomes nonexclusive.  
b.     Powers: advertise and post signs; sign, renew, modify or cancel leases within stated term and rent limits; collect rents and deposits; serve notices and evict; hire contractors; make repairs.  
c.      Limits: prior owner approval for any expenditure over a per-item dollar amount (left blank to negotiate), except emergencies. The broker may not advance its own funds.  
d.     Money flow: receipts go to an insured trust account. Disbursement order is broker compensation, then operating expenses, then reserves and deposits, then the balance to the owner.  
e.     Owner duties: liability insurance of at least \$1,000,000 naming the broker as additional insured; indemnity except for the broker's gross negligence or willful acts.  
•      **RLA scenario:** a seller hires a listing broker to sell a home.  
a.     Grant: "the exclusive and irrevocable right to sell or exchange the real property" (para. 1\) for a listing period ending at 11:59 p.m. on a stated date.  
b.     Specific authorizations, each with an opt-out checkbox in para. 2: MLS and internet marketing, Coming Soon status, keysafe/lockbox, FOR SALE sign, publishing seller concessions.  
c.      Compensation (para. 4): earned when the broker produces a ready, willing and able buyer on acceptable terms, or when the seller withdraws or transfers the property without consent. A protection period covers buyers the broker registered in writing before expiry.  
d.     Post-2024 change: compensation to buyer's brokers is optional and no longer published in the MLS.  
e.     Entity sellers must deliver proof of signing authority within three days (para. 26).  
•      **Revocation:** fixed end dates; the PMA has optional early termination on notice. A seller who withdraws an exclusive listing early generally still owes the fee.  
•      **Counterparty validation:** tenants, buyers and escrow rely on the broker's license and the signed agreement. Title and escrow verify the owner separately.

**4\. Context:** The California DRE oversees about 434,000 licensees (DRE advisory, Dec. 30, 2025); the share engaged in property management was not verified. Trust fund rules are strict. Funds must be deposited within three business days (§ 10145; Reg. 2832). The broker may keep no more than \$200 of its own money in the trust account for bank fees (Reg. 2835). Any disbursement that drops the balance below what is owed to owners needs "the written consent of every principal who is an owner of the funds in the account" (Reg. 2832.1).

Accounts are reconciled monthly (Reg. 2831.2) and records kept three years (§ 10148). An unlicensed employee may withdraw trust funds only with written broker authorization and a fidelity bond at least equal to the funds accessible (Reg. 2834). B\&P § 10176(f) makes it a disciplinary offense to collect a fee under an exclusive agreement that lacks "a definite, specified date of final and complete termination." Commingling is barred by § 10176(e).

Failure modes: trust-account shortages and commingling, which recur in DRE disciplinary decisions, and seller-impersonation fraud on vacant land.

**5\. Stability and variants:** The PMA has been stable in structure for over a decade; C.A.R. revises forms in semiannual releases (June/July and December). The RLA changed sharply in July/August 2024 after the NAR commission settlement: commission-sharing fields were removed, MLS-specific terms moved to the MLS Addendum (MLSA), and the DM-LA form was created to amend existing listings. The December 2025 release (about 40 forms) added referral-fee references to the RLA. C.A.R.'s public list (updated June 2026\) still shows RLA 12/24, so the current footer code could not be confirmed without member access. Variants: RLAN (open, nonexclusive listing), RLASR (seller-reserved), and commercial and vacant-land listing forms.

### **C2. Drill-down: the operative clause**

Paraphrase (C.A.R. PMA, para. 3, Authority and Powers – Repairs): the broker may make, cancel and pay for repairs, alterations and maintenance, and hire contractors. The broker must first get the owner's approval for any single expenditure above a stated dollar amount. Emergency spending above that limit is allowed without prior approval when needed to protect the property, prevent injury, avoid suspended services or avoid penalties, and the broker must keep the property habitable. Short quote: "Broker shall obtain prior approval of Owner for all expenditures over \$".

— C.A.R. Property Management Agreement, para. 3 (PMA 8/12 public sample; same structure reported in later revisions, not verified for 12/24)

The grantor is the owner and the grantee is the broker — and, through the broker, its licensees and employees. The delegating verbs are "appoints" and "grants exclusive right," followed by enumerated "authority and powers." The object is operation of a specific property. Scope limiters are the per-item cap, lease-term and rent limits, and the duty to act within habitability law. Not delegated: sales, refinancing, legal or tax advice, and on-site management unless separately agreed. Tenants and vendors deal with the broker as the owner's disclosed agent; the cap binds the broker to the owner and does not usually limit the broker's apparent authority toward a contractor.

### **D. Outline of the full instrument**

1\.     Appointment of broker — exclusive term with optional early termination.  
2\.     Broker acceptance — standard of care, no guarantee of results.  
3\.     Authority and powers  
a.     Advertising.  
b.     Rental and leasing (term and rent limits).  
c.      Tenancy termination and evictions.  
d.     Repairs and maintenance (cap and emergency override).  
e.     Reports, notices and signs.  
f.      Contracts and services.  
4\.     Expense payments, trust funds, reserves, disbursement order, owner statements, broker funds, keysafe/lockbox.  
5\.     Owner responsibilities and representations.  
6\.     Tax withholding (FIRPTA and state).  
7\.     Disclosures (lead paint, pool and spa drain).  
8\.     Compensation (management, leasing, eviction, vacancy and overhead fees).  
9\.     Agency relationships (possible dual agency; consent to manage competing properties).  
10\.  Notices, dispute resolution, equal housing, attorney fees, entire agreement.

The grant (1), the powers and limits (3), the money rules (4) and the fees (8) form a closed loop: authority, constraint, custody and incentive.

### **E. Insights and observations**

•      **Default-on, opt-out permissions.** RLA para. 2 lists each specific authority (lockbox, sign, MLS, Coming Soon) with a checkbox to withhold — a consent screen with granular toggles inside a signed grant. Agent platforms can copy it: default scopes are visible and each one can be switched off.  
•      **The term is a hard expiry by statute.** § 10176(f) makes an exclusive agency without a definite end date unenforceable for fees — a legislated rule that standing authority must carry an expiry, the equivalent of a token exp.  
•      **Compensation drives agency conduct.** RLA fees are earned on producing a willing buyer or on the seller's unilateral withdrawal, and survive into a protection period. Paying an AI agent per transaction would create similar incentives to transact, so success fees need guardrails.  
•      **Custody rules beat contract terms.** The trust-fund regulations, not the PMA, govern how money moves: a three-day deposit, no commingling, monthly reconciliation, and written consent from every affected owner before an under-balance disbursement. An agent holding user funds needs segregated, reconciled accounts that are auditable apart from the mandate itself.  
•      **Identity fraud targets the listing grant.** DRE's December 30, 2025 advisory describes impostors who list unencumbered vacant land, avoid video calls and use their own notary. Recommended controls include a government ID check, a tax-bill match, and certified mail of the signed listing to the owner's address of record — out-of-band confirmation to the true principal before an agent acts.  
•      **Requested source not found.** No sample management agreement from "Orange Property Manager" (orangepropertymanager.com) was found online; its site lists services but posts no agreement, repair threshold or fee schedule.  
•      **Delegated withdrawal still leaves the broker liable.** Reg. 2834 lets a bonded, unlicensed employee sign trust withdrawals, but the broker stays responsible — a parallel to sub-delegation to tools or sub-agents: the accountable party does not change.

**Sources:** [zipForm – C.A.R. PMA sample (PMA 8/12)](https://www.zipform.com/forms/property_management/samples/PMA.pdf) · [Consumer Federation of America – C.A.R. RLA 6/24 draft](https://consumerfed.org/wp-content/uploads/2024/06/RLA_6-2024_draftv10-3-CAR-Seller-Listing-Agreement.pdf) · [C.A.R. – List of Standard Forms](https://www.car.org/en/transactions/standard-forms/list-of-standard-forms) · [CRMLS – Understanding the New/Revised C.A.R. Forms (Aug. 2024\)](https://go.crmls.org/wp-content/uploads/2024/08/Understanding-the-NewRevised-C.A.R.-Forms-Flyer.pdf) · [OnlineEd – C.A.R. New & Revised Forms December 2025](https://www.onlineed.com/catalog/2314/C..R.-New-Revised-Forms-December-2025) · [Orange County REALTORS® – C.A.R. New and Revised Forms Alert](https://www.ocrealtors.org/news/car-new-and-revised-forms-alert) · [Justia – Cal. B\&P Code § 10131](https://law.justia.com/codes/california/code-bpc/division-4/part-1/chapter-3/article-1/section-10131/) · [Justia – Cal. B\&P Code § 10176](https://law.justia.com/codes/california/code-bpc/division-4/part-1/chapter-3/article-3/section-10176/) · [DRE – Trust Funds guide RE 13](https://dre.ca.gov/files/pdf/re13.pdf) · [DRE – Advisory on Vacant Land Scams (Dec. 30, 2025\)](https://www.dre.ca.gov/Licensees/Advisories/Advisory_2025_12_30_Vacant_Land_Scams.html) · [Orange Property Manager – Owner FAQ](https://www.orangepropertymanager.com/owner-faq)

## **16\. Customs Power of Attorney (CBP Form 5291\)**

**A. Title:** CBP Form 5291, "Customs Power of Attorney" (footer "CBP Form 5291 (09/08)" on the copy reviewed; the cbp.gov form page did not load, so a later revision cannot be ruled out). Governing rules: 19 CFR Part 141, Subpart C, §§ 141.31–141.46 ("Powers of Attorney"); 19 CFR 111.23(b), 111.36(c)(3), 111.39; "Modernization of the Customs Broker Regulations," final rule, 87 FR 63267 (Oct. 18, 2022), effective Dec. 19, 2022; CBP Publication No. 2034-1022, "Power of Attorney Job Aid" (Oct. 2022).

**B. Blurb:** The importer's mandate lives in the broker's files, not CBP's.

### **C. Background**

**1\. Who it comes from:** U.S. Customs and Border Protection (DHS) issues the form and the regulations. The importer of record (IOR) or drawback claimant signs it in favor of a licensed customs broker. Brokers usually send their own pre-filled version of Form 5291, or a private equivalent, to new clients.

**2\. Key lesson for AI-agent authorization:** **Make the agent the custodian and verifier of its own mandate: the broker must obtain a valid POA directly from the principal before acting, keep it on file for audit, and answer for it, while the government counterparty never receives the document at all.** This is the model where a platform acting for users holds provable, auditable consent records and produces them on demand, instead of registering every grant with each counterparty. It works only because the agent is licensed, supervised, auditable and penalized for misuse, so a design that pushes verification onto the agent needs equivalent accountability for the agent operator.

**3\. The instrument:**

•      **Scenarios:** filing import entries, paying duties, posting bonds, claiming drawback, filing protests, and submitting the importer identity form (CBP Form 5106).  
•      **Parties:** the principal (IOR or drawback claimant: individual, partnership, corporation or sole proprietor); the agent (licensed broker, acting through its licensed officers and authorized employees); CBP (counterparty and regulator).  
•      **Powers delegated:** Form 5291 grants authority over entries, declarations, bills of lading and drawback documents; signing bonds; vessel and conveyance papers; and transacting customs business generally, including protests under section 514 of the Tariff Act of 1930\.  
•      **Scope:** "a specified part or all the Customs business of the principal" (§ 141.31(a)). A non-5291 document must be either an unlimited general power or a limited power that states its scope (§ 141.32).  
•      **Duration:** unlimited, except partnership POAs, which expire after two years (§ 141.34).  
•      **Revocation:** by written notice given to and received by CBP, at the port or electronically (§ 141.35). Form 5291 also lets the principal set an end date.  
•      **Sub-delegation:** a resident principal's agent cannot appoint a subagent except to file Electronic Export Information. Brokers act through licensed officers or authorized employees (§ 141.43).  
•      **Who signs for a corporation:** no POA is needed if the signer is known to CBP as the president, vice president, treasurer or secretary (§ 141.38). Otherwise a duly authorized person executes it; Form 5291 has an optional block where another officer certifies that the signer was authorized by board resolution, plus a seal. Nonresident principals must name a resident agent for service of process (§ 141.36), and nonresident corporations not qualified in the state must attach proof of the grantor's authority (§ 141.37).  
•      **Validation:** CBP relies on the broker's license and its duty to hold the POA; CBP can audit the broker's records.

**4\. Context:** Customs POAs date at least to the 1984 rewrite of Part 141 (T.D. 84-93, 49 FR 17754). Nearly all commercial imports are filed by licensed brokers, each needing a POA from each importer client (broker and entry counts were not verified here).

The 2022 modernization rule replaced district permits with a single national permit, required brokers whose clients come through freight forwarders to "execute a customs power of attorney directly with the importer of record or drawback claimant" (§ 111.36(c)(3)), and added 72-hour reporting of breaches of importer identification numbers (§ 111.21(b)). The separate client identity verification rule (NPRM 84 FR 40302, Aug. 14, 2019, proposing § 111.43) would have required brokers to collect ID, EIN, credit report, state registration and the grantor's authority, and to re-verify annually. It was **not** finalized: § 111.43 is still "\[Reserved\]" in the eCFR (current to Oct. 16, 2026). Continuing education (20 hours for the Feb. 1, 2024–Jan. 31, 2027 period) came in a separate rulemaking (89 FR 87387, Nov. 1, 2024).

On Aug. 19, 2026, under Executive Order 14411, CBP announced it would void IOR numbers with inaccurate Form 5106 data starting Sept. 18, 2026; practitioners stressed checking that brokers hold a POA executed directly with the importer. Failure modes: shell importers using brokers obtained through forwarders, impostor IORs, and stale POAs from entities that no longer exist.

**5\. Stability and variants:** The form and Part 141 rules have been stable for decades. Variants: broker-branded Form 5291 copies; private POAs that meet § 141.32; foreign-principal attachments for nonresidents; partnership POAs with two-year renewal; and "Broker A–Broker B" special appointment language letting a client authorize its broker to use another broker (CBP job aid). POAs are not filed in ACE as a rule; the broker retains them.

### **C2. Drill-down: the operative clause**

"Before transacting Customs business in the name of his principal, a customhouse broker is required to obtain a valid power of attorney to do so. He is not required to file the power of attorney with CBP. Customhouse brokers shall retain powers of attorney with their books and papers, and make them available to representatives of the Department of the Treasury as provided in subpart C of part 111 of this chapter."

— 19 CFR 141.46

"Any power of attorney shall be subject to revocation at any time by written notice given to and received by CBP..." — 19 CFR 141.35. "Powers of attorney must be retained until revoked, and revoked powers of attorney and letters of revocation must be retained for 5 years after the date of revocation or for 5 years after the date the client ceases to be an 'active client'... whichever period is later." — 19 CFR 111.23(b)

The grantor is the importer or claimant; the grantee is the broker. The Form 5291 verb is "constitutes and appoints." The object is customs business at named ports or all ports, either general or limited. Condition precedent: the POA must exist before any transaction. The burden of custody and production falls on the agent. CBP is bound by regulation to honor the broker's filings without seeing the POA, but it can audit, penalize (19 U.S.C. § 1641\) or revoke the license. Not delegated: authority to appoint subagents (except for EEI), and anything beyond a limited POA's stated scope.

### **D. Outline of the full instrument**

1\.     Principal identification — legal name, trade names, type of entity, state, address and IOR number.  
2\.     Appointment — names the broker, its officers, employees and specifically authorized agents, and the port(s) or "all ports."  
3\.     Grant of powers (five paragraphs)  
a.     Entries, documents and merchandise for import, transport and export.  
b.     Bills of lading and drawback documents.  
c.      Bonds and consignee or owner declarations.  
d.     Vessel and conveyance documents.  
e.     Customs business generally, including protests.  
4\.     Ratification — the principal ratifies acts done under the power.  
5\.     Duration and revocation — until a stated date or until written revocation is received by the CBP port director; two-year cap for partnerships.  
6\.     Signature, title and date of the grantor.  
7\.     Optional corporate certification — a second officer certifies the board resolution authorizing the signer; seal.  
8\.     Optional notary or witness block.

Parts 2–3 grant the authority. Part 5 bounds it in time. Parts 6–7 prove that the signer could bind the entity — a nested authority chain much like item 14\.

### **E. Insights and observations**

•      **"Directly with the principal" is an anti-intermediary rule.** § 111.36(c)(3) forbids brokers from taking POAs through freight forwarders. Agent platforms should likewise forbid consent captured by a reseller or upstream bot, and require the principal's own authenticated act.  
•      **Retain until revoked, then five more years.** § 111.23(b) sets a concrete audit retention period that runs from revocation or from client inactivity, whichever is later ("active client" means at least two transactions in the prior 12 months). Agent audit logs need lifecycle rules like this.  
•      **Revocation goes to the counterparty, while custody stays with the agent.** CBP must receive written revocation, but it never held the grant. That asymmetry can leave the broker unaware of a revocation filed with CBP. Agent systems should notify every party when a grant is revoked.  
•      **Title-based trust.** § 141.38 waives the POA for a corporate president, VP, treasurer or secretary known to CBP — role-based trust that depends on the counterparty already knowing the role holder, the same pattern as an incumbency certificate.  
•      **Know-your-principal was proposed, then stalled.** The 2019 identity verification NPRM (annual re-verification, \$10,000 per-client penalties) remains unadopted as of October 2026\. CBP is instead enforcing IOR data accuracy directly (Form 5106 voiding from Sept. 18, 2026). KYC duties may land either on the agent or on the registry, so design for both.  
•      **Partnership time-box.** The two-year cap for partnership POAs exists because partner turnover silently changes who the principal is; § 141.39 refuses to recognize a POA from an "antecedent firm." Mandates from entities with volatile membership need short expiry.  
•      **Data use needs consent in the POA.** The 2022 rule's preamble says any broker use or disclosure of client information "must be set forth in the power of attorney." The mandate doubles as a data-use consent — a precedent for bundling data scopes with action scopes.

**Sources:** [eCFR – 19 CFR Part 141 Subpart C](https://www.ecfr.gov/current/title-19/chapter-I/part-141/subpart-C) · [LII – 19 CFR 141.46](https://www.law.cornell.edu/cfr/text/19/141.46) · [LII – 19 CFR 141.35](https://www.law.cornell.edu/cfr/text/19/141.35) · [LII – 19 CFR 141.34](https://www.law.cornell.edu/cfr/text/19/141.34) · [LII – 19 CFR 141.32](https://www.law.cornell.edu/cfr/text/19/141.32) · [LII – 19 CFR 141.31](https://www.law.cornell.edu/cfr/text/19/141.31) · [LII – 19 CFR 141.38](https://www.law.cornell.edu/cfr/text/19/141.38) · [eCFR – 19 CFR 111.23](https://www.ecfr.gov/current/title-19/chapter-I/part-111/subpart-C/section-111.23) · [eCFR – 19 CFR 111.36](https://www.ecfr.gov/current/title-19/chapter-I/part-111/subpart-C/section-111.36) · [eCFR – 19 CFR 111.39](https://www.ecfr.gov/current/title-19/chapter-I/part-111/subpart-C/section-111.39) · [eCFR – 19 CFR Part 111](https://www.ecfr.gov/current/title-19/chapter-I/part-111) · [Federal Register – Modernization of the Customs Broker Regulations (2022)](https://www.federalregister.gov/documents/2022/10/18/2022-22445/modernization-of-the-customs-broker-regulations) · [CBP – Power of Attorney Job Aid, Pub. 2034-1022](https://cbp.gov/sites/default/files/assets/documents/2022-Oct/CBP%20Publication%20%232034-1022%20-%20Power%20of%20Attorney%20Job%20Aid.pdf) · [CBP Form 5291 (09/08) copy](https://flatworldgs.com/wp-content/uploads/2021/04/ram-form-5291-poa.pdf) · [govinfo – Customs Broker Verification of an Importer's Identity NPRM (2019)](https://www.govinfo.gov/content/pkg/FR-2019-08-14/html/2019-17179.htm) · [govinfo – Continuing Education notice (Nov. 1, 2024\)](https://www.govinfo.gov/content/pkg/FR-2024-11-01/html/2024-24464.htm) · [Akerman – CBP will void IOR numbers (Sept. 2026\)](https://www.akerman.com/en/perspectives/cbp-will-void-importer-of-record-ior-numbers-for-inaccurate-data-starting-septe.html)

## **17\. Telecom Letter of Authorization (LOA) for number porting**

**A. Title:** Carrier-drafted *Letter of Authorization* (also "Letter of Agency") for local number porting. Examples: Intermedia *LOA (General) – Letter of Authorization for Local Number Porting, Hosted PBX Services* (undated PDF); Zoom Phone US/Canada/Puerto Rico porting LOA (in-portal); Telnyx porting LOA. Federal framework: 47 CFR 64.1120 and 64.1130 (carrier-change verification and LOA content), 47 CFR 52.35–52.36 (porting intervals and standard port-request fields), and 47 CFR 52.37 (wireless port-out authentication, added by FCC 23-95, 88 FR 85794, Dec. 8, 2023).

**B. Blurb:** The new carrier speaks for you; the old carrier checks its records.

### **C. Background**

**1\. Who it comes from:** No single author. Each gaining provider (Intermedia, Zoom, Telnyx, etc.) drafts its own LOA. The FCC supplies the content rules borrowed from anti-slamming law and the standard port-request data fields. The end customer or account administrator signs; the gaining carrier submits it.

**2\. Key lesson for AI-agent authorization:** **An agent acting against an incumbent counterparty succeeds only when its mandate matches the incumbent's own record (the Customer Service Record) and carries a principal-held secret (account number plus port-out PIN), with the principal notified before execution.** In agent terms, the LOA is a signed delegation token validated at the relying party against fields it already holds, not against the agent's claims. The PIN works as a second factor the agent can only get from the principal. Notification and an account "port-out lock" give the principal a veto channel outside the agent's control.

**3\. The instrument:**

•      **Scenario.** A business or consumer moves phone numbers from a losing carrier to a gaining carrier (or a UCaaS platform) without changing numbers.  
•      **Parties.** Subscriber (principal); gaining provider (agent); losing provider (counterparty that must release the number); NPAC (the neutral number database that records the move).  
•      **Power delegated.** Authority to contact the current provider and request the port of the listed numbers.  
•      **Required data.** Billing name and service address as on the losing carrier's record, account number, each number to be ported, current carrier, and for wireless the PIN, tax ID or last four of the SSN (Intermedia). One LOA per account.  
•      **Who may sign.** Only an account owner or administrator listed with the current provider (Intermedia, Telnyx). Resellers must have the end customer sign (Telnyx).  
•      **Freshness.** Telnyx rejects LOAs signed more than 90 days earlier and invoices older than 30 days.  
•      **Conditions.** Keep the old service active until the port completes; disconnecting first kills the port (Intermedia, Zoom). Clear balances; avoid account changes; confirm no DSL or alarm circuits ride the lines.  
•      **Validation.** The losing carrier matches the request to its CSR. Mismatched name or address, missing numbers, an unauthorized signer, or a stale LOA are the common rejection reasons (Telnyx).  
•      **Execution timing.** Simple wireline and intermodal ports must complete within one business day (47 CFR 52.35). Zoom quotes about 4 business days for most wireless and 7–21 for landlines.

**4\. Context:** Number portability dates from the Telecommunications Act of 1996\. Slamming verification rules (64.1120/64.1130) apply to preferred-carrier changes; porting LOAs copy their structure. A 2010 FCC order standardized simple port requests to 14 fields with a one-business-day interval (implemented August 2, 2010; small providers February 2, 2011).

The main failure mode is port-out fraud: a criminal ports a victim's mobile number to take over SMS-based account recovery. The FCC adopted FCC 23-95 on November 15, 2023 to address SIM swaps and port-outs. A security-vendor blog citing FBI IC3 data reports 982 SIM-swap complaints and \$25.98M in losses in 2024 (not checked against the IC3 report).

**5\. Stability and variants:** The content is stable but every carrier formats its own LOA. Variants include toll-free LOAs (RespOrg change), wireless port-outs that rely on account number and PIN rather than a signed LOA, and non-U.S. letters of agency (Zoom posts a UK mobile LOA). Zoom's numbering policy states the customer has no ownership rights in phone numbers. The Intermedia LOA link in the source list now redirects to intermedia.com.

### **C2. Drill-down: the operative clause**

Federal content rule: the LOA must confirm "the subscriber's billing name and address and each telephone number to be covered," the decision to change carriers, and that the subscriber designates the carrier "to act as the subscriber's agent for the preferred carrier change." A non-conforming LOA "is invalid for purposes of this part."

— 47 CFR 64.1130(a), (e)

Carrier form (paraphrase): the customer, signing as an owner or administrator on record with its current provider, lets Intermedia contact that provider and port the listed numbers. The customer attests the data is accurate and accepts a per-number fee. Short quote: "you authorize Intermedia Communications to communicate with your current telephone provider."

— Intermedia LOA (General), page 1 (undated)

The grantor is the subscriber of record. The grantee is the gaining carrier. The verbs are "designate … as agent" (FCC) and "authorize … to communicate" (Intermedia). The object is a closed list of telephone numbers on one account. Scope limiters: the numbers listed, the account, and identity fields that must match the CSR. Not delegated: cancelling the old service, changing the account, or any power over numbers not listed.

The losing carrier is bound to honor a valid, matching request within the port interval. Under § 52.36 it may require only the standard fields; a passcode is optional "unless the passcode has been requested and assigned by the end user." The standard fields include an "agency authority status" indicator — the gaining carrier's assertion that it holds the LOA.

### **D. Outline of the full instrument**

1\.     Authorization statement — subscriber authorizes the gaining carrier to request the port.  
2\.     Account details (from the losing carrier) — account number, billing name, account type, PIN/tax ID for wireless.  
3\.     Service address — must match the losing carrier's records; no PO Box.  
4\.     Current carrier name.  
5\.     Numbers to be ported — 10-digit list or attachment.  
6\.     Attestation — accuracy; no DSL or alarm dependencies.  
7\.     Signature block — signature, printed name, title, company, date; e-signature consent.  
8\.     Instructions — keep service active, one LOA per account, attach a recent bill.

Parts 2–5 are the match key against the CSR. Part 7 must come from a person the losing carrier recognizes. Part 8 manages the handoff.

### **E. Insights and observations**

•      **The 2023 SIM-swap/port-out order is only partly in force.** Under FCC 23-95, § 52.37(b) (secure authentication before port-out, reviewed annually) and (f) (employee training) took effect January 8, 2024\. Paragraphs (c), (d), (e) and (g) — immediate customer notification, the free port-out lock, fraud reporting and records — were delayed pending OMB review. The Wireline Competition Bureau's July 5, 2024 waiver (DA 24-649) tied compliance to OMB approval plus a Federal Register notice, and CTIA asked OMB in November 2024 to withhold approval. As of October 2026 the eCFR shows those paragraphs as "Reserved," and no compliance-date notice was found. The FCC's 2023 news item still states the superseded July 8, 2024 date.  
•      **CSR matching is weak authentication.** Name, address and account number are often obtainable from a stolen bill. That is why wireless carriers added PINs and why the FCC demanded secure methods. Agent systems should not treat record-matching as proof of principal intent.  
•      **Out-of-band notice and lock beat the token.** The FCC's design (notify the customer before the port, offer a free lock) assumes LOAs and PINs will leak. A principal-controlled freeze on agent actions is the analogous control.  
•      **Freshness windows.** A 90-day LOA validity (Telnyx) and the 60-day rule for carrier-change LOAs (§ 64.1130(j)) put a time-to-live on a static signed mandate.  
•      **Separate-document rule.** § 64.1130(b)–(c) requires the LOA to be standalone, with no inducements on the same page — an early "clean consent screen" rule, like FCRA's (item 11).  
•      **Reseller trap.** The signer must be the losing carrier's account holder, not the reseller. Agents acting through intermediaries must carry the principal's own credential.

**Sources:** [47 CFR 64.1120 (LII)](https://www.law.cornell.edu/cfr/text/47/64.1120) · [47 CFR 64.1130 (LII)](https://www.law.cornell.edu/cfr/text/47/64.1130) · [47 CFR 52.35 (LII)](https://www.law.cornell.edu/cfr/text/47/52.35) · [47 CFR 52.36 (LII)](https://www.law.cornell.edu/cfr/text/47/52.36) · [47 CFR 52.37 (eCFR)](https://www.ecfr.gov/current/title-47/chapter-I/subchapter-B/part-52/subpart-C/section-52.37) · [FCC 23-95, 88 FR 85794 (govinfo)](https://www.govinfo.gov/content/pkg/FR-2023-12-08/html/2023-26338.htm) · [FCC: effective date for SIM swapping item](https://www.fcc.gov/consumer-governmental-affairs/fcc-announces-effective-date-sim-swapping-item) · [Telecom Law Partners on DA 24-649 waiver](https://www.tlp.law/2024/07/08/fcc-amends-sim-swapping-port-out-fraud-compliance-date/) · [CTIA comments to OMB (Nov. 29, 2024\)](https://www.reginfo.gov/public/do/DownloadDocument?objectID=150107702) · [Kelley Drye on 2010 porting order](https://www.kelleydrye.com/viewpoints/client-advisories/fcc-issues-order-standardizing-number-porting-process) · [Intermedia LOA (General)](https://www.intermedia.com/wp-content/themes/intermedia-website/assets/pdf/legal/loa-local.pdf) · [Zoom US/Canada/PR porting guide](https://library.zoom.com/es/zoom-workplace/zoom-phone/number-porting-and-management-field-guide/us-canada-and-puerto-rico-porting) · [Zoom Phone Numbering Policy](https://www.zoom.com/en/trust/zoom-phone-numbering-policy/) · [Telnyx porting requirements](https://support.telnyx.com/en/articles/6460777-porting-requirements) · [SafeBrowz SIM swap guide (IC3 figures)](https://safebrowz.com/blog/sim-swap-fraud-attack-guide-2026)

## **18\. Utility third-party authorization (PG\&E 79-1095 and Share My Data)**

**A. Title:** Pacific Gas and Electric Company Sample Form No. 79-1095, "Authorization to Receive Customer Information or Act Upon a Customer's Behalf," form dated April 2025: Electric version on Cal. P.U.C. Sheet No. 59555-E (Advice 7572-E) and Gas version on Sheet No. 40051-G (Advice 5058-G), both effective May 17, 2025\. Governing rules: CPUC Decision D.11-07-056 (July 2011), implemented as PG\&E Electric/Gas Rule 27 "Privacy and Security Protections for Energy Usage Data"; D.13-09-025 (Sept. 2013, third-party data access); Resolution E-4868 (Aug. 2017, click-through authorization). Machine successor: PG\&E "Share My Data," a Green Button Connect My Data implementation of NAESB REQ.21 ESPI over OAuth 2.0.

**B. Blurb:** The paper agency form that a utility rebuilt as OAuth scopes.

### **C. Background**

**1\. Who it comes from:** PG\&E drafts the form, but it is a tariff sheet filed with and approved by the California Public Utilities Commission (CPUC). The customer of record and the agent (consultant, ESP, CCA, solar or efficiency firm) fill in and sign each instance. Utility staff call it the "CISR" form (Customer Information Service Request).

**2\. Key lesson for AI-agent authorization:** **Split delegation into two tiers — "receive information" versus "act on the account" — and make every data type, action, and duration a separately initialed checkbox, because that structure converts one-for-one into OAuth scopes, token lifetimes and revocation endpoints.** PG\&E did exactly this. The paper form's checklist became Share My Data's data groups and ESPI "Function Block" scope strings, and the paper's one-time/one-year/three-year terms became refresh-token lifetimes and customer-set end dates. Even the paper form survives inside the API as Function Block 40, "offline authorization," so legacy and digital grants share one registry.

**3\. The instrument:**

•      **Scenarios.** Energy consultants auditing bills, rate analysts, solar and storage installers sizing systems, demand-response providers, ESPs and CCAs, property managers.  
•      **Parties.** Customer of record (principal); third party named "Agent"; PG\&E (counterparty and data holder).  
•      **Powers.** The customer appoints the agent for listed accounts, in initialed categories:  
a.     Billing records, billing history, meter usage for bill calculation.  
b.     Copies of correspondence (rate verification, contracts, adjustments, disputed items).  
c.      Investigation of utility bills.  
d.     Special metering and access to interval data.  
e.     Rate analysis.  
f.      Rate changes.  
g.     Verification of balances and discontinuance notices.  
•      **Information vs. action.** Items 1–5 and 7 are read-type. Item 6 (rate changes) and bill investigation are act-type, and the indemnity clause specifically names agent actions such as rate changes.  
•      **Per-transaction instruction.** The form alone does nothing. The agent must then send specific written instructions (email allowed) for each account before release or action.  
•      **Duration.** One initialed box: one-time, one year from signing, or fixed term capped at three years. A blank defaults to one-time.  
•      **Revocation.** Customer may cancel at any time in writing.  
•      **Validation.** PG\&E reserves a right to verify any authorization before acting. The customer's signer declares under penalty of perjury that they can bind the customer. Release may be limited to the last 12 months; free twice per 12 months per account.  
•      **Liability.** Customer and agent each release and indemnify PG\&E.

**4\. Context:** The CISR form dates back at least to 2000 (a "USP 23" version dated 1/11/00); the 2007 revision already had the seven-item, three-duration layout. SB 1476 (2010, Pub. Util. Code § 8380\) bars utilities from sharing consumption data with third parties without customer consent, and D.11-07-056 then adopted Fair Information Practice rules for PG\&E, SCE and SDG\&E. Scale: PG\&E's 2017 privacy report counted about 15,400 third parties authorized by customers and about 96 Share My Data vendors. It also reported 8 non-compliances affecting about 9,600 customers, seven of them emails sent to unauthorized third parties.

**5\. Stability and variants:** The paper form is stable in structure; 2025 changes were administrative. The 2007 and 2000 copies at older PG\&E URLs are superseded. Variants: separate Electric and Gas tariff sheets; an ESP/CCA submission channel; a demand-response-specific CISR-DRP form; SCE and SDG\&E equivalents. The digital track evolved through D.13-09-025 (customer-initiated third-party access) and Resolution E-4868 (click-through authorization), which capped the quick path at "four clicks and only two screens," allowed indefinite terms for demand-response providers, and required revocation via the utility portal. Green Button Connect My Data is deployed beyond California; the Green Button Alliance reported 75+ certified implementations in July 2023\.

### **C2. Drill-down: the operative clause**

Paraphrase: the customer of record appoints the named third party as its agent and consultant for the listed service accounts, limited to the categories the customer initials. Before PG\&E releases anything or takes any action on a given account, the agent must send specific written instructions, which may be by email. The grant lasts one time, one year, or a fixed term of up to three years; a blank means one-time, and the customer may cancel in writing at any time. Short quote: "act as my agent and consultant (Agent) for the listed account(s)."

— PG\&E Form 79-1095, Sections 4–5 (April 2025; PG\&E-authored, CPUC-approved tariff form)

"Covered entities shall provide to customers upon request convenient and secure access to their covered information" and convenient mechanisms for "granting and revoking authorization for secondary uses of covered information."

— CPUC D.11-07-056, Attachment D, Rule 4 (Individual Participation), carried into PG\&E Rule 27 § 4

The grantor is the customer of record, through a signer who swears to authority to bind. The grantee is the named agent. The verbs are "receive" (information) and "act" (on the customer's behalf). The object is the listed service accounts. Scope limiters are the initialed categories, the account list, the duration box, and the delivery format. Conditions: each use needs a specific written request, and PG\&E may verify.

Not delegated: anything not initialed, accounts not listed, and new accounts (adding service IDs to a digital grant requires a new authorization). The utility is bound by tariff to honor a valid form, and keeps a verification right and an indemnity.

### **D. Outline of the full instrument**

1\.     Instructions sheet — purpose, mailing and email submission, ESP/CCA channel, keep a copy.  
2\.     Customer of record — name, title, mailing address.  
3\.     Agent — name, mailing address.  
4\.     Accounts — up to three service addresses and account numbers; attach more.  
5\.     Authorized acts — seven initialed items, correspondence sub-options a–d.  
6\.     Duration — initial one: one-time, one-year, fixed term up to three years.  
7\.     Release format — mail, fax, or email.  
8\.     Customer signature — penalty-of-perjury authority declaration, title, date and place.  
9\.     Agent signature — company, telephone, date.  
10\.  Releases and notices — mutual indemnity, verification right, CPUC modification clause, privacy policy reference, legally-binding-contract banner.  
11\.  Digital successor (Share My Data)  
a.     Third-party registration — EIN, contacts, OAuth redirect URI, notification URI, TLS 1.2 X.509 certificate; testing within 90 days.  
b.     Customer click-through — authenticate at PG\&E, choose data groups (Usage, Billing, Basic, Account, Program Enrollment), service IDs, end date.  
c.      Tokens — authorization code 600 s, access token 1 hour, refresh token 1 year.  
d.     Scope string — ESPI Function Blocks plus "AdditionalScope," e.g. "FB=1\_3\_...;AdditionalScope=Usage".  
e.     Management — customer can remove service IDs, extend end date, cancel; third party can DELETE; notifications on change.

The paper form and the API encode the same three axes: what data, which accounts, how long. The API adds machine verification of the agent (mutual TLS) and real-time revocation.

### **E. Insights and observations**

•      **The utility sector already ran the migration agent designers face.** A paper mandate became a registered-client, consent-screen, scoped-token flow without changing the underlying law.  
•      **Standing-consent hygiene.** Under Rule 27, secondary-purpose consent must be "prior, express, written" and separate for each type of secondary purpose. Residential consent does not expire, but the recipient must contact the customer at least annually to describe the grant and offer revocation, and revocation must work through the same mechanism used to grant it. These are directly reusable rules for long-lived agent tokens.  
•      **Recipients become regulated entities.** A third party authorized by 11 or more customers becomes a "covered entity" under Rule 27 and inherits its duties. Agent operators should expect similar status thresholds.  
•      **Act-type powers survive only on paper.** Share My Data is read-only (usage, billing, account, enrollment). Rate changes and account actions still need Form 79-1095. The machine path went first for low-risk reads.  
•      **Friction is regulated, not left to the counterparty.** Resolution E-4868 capped click counts, barred SSNs as credentials, and required auto-notification to both parties. Regulators can mandate low-friction consent, unlike the CCPA world (item 1\) where counterparties invent hurdles.  
•      **Failure modes.** Human-error email disclosures dominated PG\&E's 2017 non-compliance count. Paper and email channels leak; tokens and mutual TLS reduce the error surface.  
•      **Scope granularity has costs.** Changing data elements requires cancelling and re-authorizing, so third parties tend to over-request at the outset. Incremental consent would help.

**Sources:** [PG\&E Gas Form 79-1095 (tariff, Apr. 2025\)](https://www.pge.com/tariffs/assets/pdf/tariffbook/GAS_FORMS_79-1095.pdf) · [PG\&E Electric Form 79-1095 (tariff, Apr. 2025\)](https://www.pge.com/tariffs/assets/pdf/tariffbook/ELEC_FORMS_79-1095.pdf) · [PG\&E Share My Data: third-party companies](https://www.pge.com/en/save-energy-and-money/energy-saving-programs/smartmeter/third-party-companies.html) · [PG\&E scope string mapping (Click Thru 2.0)](https://www.pge.com/assets/pge/docs/save-energy-and-money/energy-savings-programs/Supported-Function-Block-Scope-String-Mapping-Click-Thru-2.0.pdf) · [PG\&E Gas Rule 27](https://PGE.com/tariffs/assets/pdf/tariffbook/GAS_RULES_27.pdf) · [CPUC D.11-07-056](https://docs.cpuc.ca.gov/word_pdf/FINAL_DECISION/140369.pdf) · [CPUC D.13-09-025](https://docs.cpuc.ca.gov/PublishedDocs/Published/G000/M077/K191/77191980.PDF) · [CPUC Resolution E-4868](https://docs.cpuc.ca.gov/PublishedDocs/Published/G000/M194/K746/194746364.PDF) · [PG\&E 2017 annual privacy report](https://www.cpuc.ca.gov/-/media/cpuc-website/files/legacyfiles/s/6442459427-smartgridoir-pge-annualprivacy-report2017.pdf) · [Green Button Alliance: PG\&E](https://greenbuttonalliance.org/news/pacific-gas-and-electric-pge) · [Green Button Alliance: 75+ certified implementations](https://www.greenbuttonalliance.org/news/press-release--gba-marks-green-button-certified-milestone-with-over-75-implementations-certified)

## **19\. CFPB model Third Party Authorization for mortgage servicers**

**A. Title:** CFPB model "Third Party Authorization" form, whose operative section is headed "Borrower Authorization of Third Party" (released July 2014; no form number, edition date or OMB number printed). Companion consumer handout: "Allowing a third party to work with your mortgage company" (CFPB, July 2014). Regulatory context: Regulation X, 12 CFR §1024.35, §1024.36, §1024.38, §1024.41 (comment 41(f)(3)(ii)(C)-2 "Borrower's representative"); Regulation O (Mortgage Assistance Relief Services), 12 CFR Part 1015\.

**B. Blurb:** A regulator-blessed template so servicers stop rejecting borrowers' helpers.

### **C. Background**

**1\. Who it comes from:** The CFPB published it as part of loan-modification scam-prevention work, developed (per the CFPB) with government agencies, consumer advocates, housing counselors and the mortgage industry. The borrower and the third party (HUD-approved counselor, attorney, or other helper) complete it and send it to the servicer. Many servicers and investors publish derived versions (e.g., Freddie Mac's "Borrower Authorization to Share Information with a Third Party," Aug. 2016).

**2\. Key lesson for AI-agent authorization:** **A single, regulator-published delegation template with explicit agent identity fields, scope verbs, a fixed expiry and a signed agent attestation lowers counterparty rejection, because the receiving institution knows exactly what to check.** Agent ecosystems face the same problem: if every bank or merchant invents its own agent-consent format, agents get refused. A shared schema (agent identity and license, scope, expiry, revocation path, agent's signed compliance attestation) lets counterparties automate acceptance. The form also keeps the principal's direct channel open: the servicer may still contact the borrower.

**3\. The instrument:**

•      **Scenario:** A homeowner in hardship wants a housing counselor, attorney or other helper to talk to the servicer, collect documents, or negotiate a loan modification or other "workout."  
•      **Parties:** Borrower(s) (principals); Third Party (agent); Mortgage Servicer (counterparty) with its affiliates, agents and successors; U.S. Treasury and its agents (for Making Home Affordable programs, now ended).  
•      **Agent identity fields:** Entity name, phone, authorized individuals, office and mailing address, email, state license number, website, tax ID and issuing state. Non-profits give HUD counseling status, HUD HCS number and approval expiry. Attorneys give firm, names, states licensed, and whether they represent the borrower.  
•      **Scope (initialed items):** (1) authority to "discuss, assist with, or, if applicable, negotiate" a workout; (2) consent to share public and non-public data, including SSN, credit score, income and debts, among servicer, third party and Treasury.  
•      **Acknowledgments (initialed):** the servicer may still contact the borrower directly, except in limited cases such as attorney representation; the servicer may decline the form and must say so in writing.  
•      **Duration:** expires one year from signing unless cancelled earlier.  
•      **Transmission:** must reach the servicer within 90 days of signing.  
•      **Revocation:** written notice to the servicer, or signing an authorization for a different third party (last-in replaces).  
•      **Agent attestation:** the third party signs, certifying compliance with Regulation O where applicable and other laws, and acknowledging that misrepresentation in a government program may be prosecuted.  
•      **Counterparty validation:** Reg X lets servicers use reasonable procedures to determine whether a person claiming to be a borrower's agent has authority, including requiring documentation from the borrower. Once satisfied, the servicer must treat the agent's communications as the borrower's.

**4\. Context:**

•      **Why it exists:** After 2008, servicers often refused to talk to counselors or rejected unfamiliar authorization forms, while foreclosure-rescue scammers used authorizations to harvest data and fees. The model form tries to serve both goals: help legitimate helpers and flag scams.  
•      **Prevalence:** Many servicer and investor forms (PNC 2014, Freddie Mac 2016, and others) follow the same pattern. No usage statistic was found.  
•      **HUD counselors:** About 4,200+ HUD-certified counselors work at local nonprofits (Consumer Federation of America, Oct. 2025). In October 2025, HUD ordered layoffs of nearly all Office of Housing Counseling staff during the shutdown; a court blocked it and the November 2025 continuing resolution reversed shutdown RIFs. The FY2027 budget request proposes eliminating Housing Counseling Assistance (down from \$57.5M in FY2026). HUD's March 26, 2026 NOFO restricted reimbursement for delinquency counseling to FHA, VA and USDA borrowers (Shelterforce, Aug. 2026).  
•      **Fraud rule:** Regulation O (12 CFR 1015, originally the FTC's 2010 MARS rule) bans advance fees until the consumer has a signed written agreement with the lender (§1015.5(a)), bans telling consumers they "cannot or should not contact" their servicer (§1015.3(a)), and requires the disclosure "You may stop doing business with us at any time" (§1015.4(b)(1)). Attorneys have a conditional exemption (§1015.7).  
•      **Enforcement example:** In February 2024 the CFPB resolved a 2014 action against a foreclosure-relief operation: \$10.9M redress and a \$1.1M penalty for advance fees, missing disclosures, and telling consumers not to contact lenders.

**5\. Stability and variants:**

•      **Model form:** One 2014 version; no CFPB revision found. It still references Treasury and Making Home Affordable, which closed to new applications in 2016, so it is partly outdated.  
•      **Servicer variants differ on key terms:** PNC (Aug. 2014\) runs for the life of the loan or until revoked, covers information only, and says legal authority needs a separate power of attorney. Freddie Mac (Aug. 2016\) has no fixed expiry and requires delivery within 10 days.  
•      **Regulation X:** The CFPB's July 2024 proposal to replace the complete-application process with a "loss mitigation review cycle" was still at the final-rule stage per a September 2025 CRS report; no 2026 final rule was confirmed.

### **C2. Drill-down: the operative clause**

"I (Borrowers listed below) authorize the above named Third Party to discuss, assist with, or, if applicable, negotiate a workout arrangement on my mortgage(s) with the above named Mortgage Servicer (its affiliates, agents, employees, and successors). A workout arrangement could include a modification or other relief."

"I authorize my Mortgage Servicer, and Third Party and Treasury (and its agents) to share with each other public and non-public information about my finances and my mortgage for the purpose of assisting me in obtaining a workout arrangement, including but not limited to: (i) my mortgage payment history, terms of my mortgage; and (ii) my social security number, credit score, income, debts and other information related to obtaining and servicing my mortgage."

"This Authorization expires one year from the date signed unless Borrower cancels it earlier."

— CFPB model Third Party Authorization, "Borrower Authorization of Third Party" (July 2014\)

**Grantor:** each borrower, by initialing each item and signing. **Grantee:** the named Third Party entity and its listed individuals. **Delegating verbs:** "discuss," "assist with," "negotiate," and "share." **Object:** a workout arrangement on the identified loan(s). **Scope limiters:** "if applicable" on negotiation (in some states only licensed attorneys or exempt entities may negotiate); purpose limitation on data sharing ("for the purpose of assisting me in obtaining a workout"); one-year term. **Not delegated:** signing a modification agreement (any workout needs servicer and borrower agreement), receiving loan proceeds, or excluding the borrower from direct contact. **Counterparty binding:** the form does not compel acceptance; the servicer may decline but must notify the borrower in writing. Reg X then requires the servicer to treat a documented agent's communications as the borrower's.

The companion handout frames scope as a borrower choice: a helper may negotiate a modification, or only receive information while the borrower handles the servicer. The model form itself has no checkboxes; scope is set by initialing.

### **D. Outline of the full instrument**

1\.     Header data — servicer name and loss-mitigation phone; loan number(s); property address; borrower names.  
2\.     Third Party Information — identity, contact, license, tax ID; non-profit and HUD-approval block; attorney block.  
3\.     Third Party Acknowledgement — signed certification of Reg O and legal compliance; warning of prosecution for misrepresentation.  
4\.     Borrower Authorization of Third Party — initialed scope grant and data-sharing consent.  
5\.     Borrower Authorization — initialed acknowledgments (servicer may still contact borrower; servicer may decline); expiry and cancellation; signatures, SSN last digits, contact data, dates.  
6\.     "Be aware of scams\!" box — up-front fee warning; HOPE Hotline 888-995-HOPE.

The agent describes and binds itself first, the borrower then grants scoped authority, and the scam box tells the principal what an illegitimate agent looks like.

### **E. Insights and observations**

•      **Agent self-identification plus attestation.** The third party supplies verifiable identifiers (license number, HUD HCS number, tax ID) and signs a compliance certification — the paper version of an agent credential bound to an accountable legal entity.  
•      **Fixed expiry beats "until revoked."** The model's one-year term contrasts with PNC's life-of-loan grant. Stale authorizations are a known scam vector; agent mandates should default to expiry.  
•      **Last-in replaces.** Signing a new authorization for a different third party revokes the old one. Agent systems can use the same rule to avoid conflicting delegates, but must notify the displaced agent.  
•      **Principal channel stays open.** The acknowledgment that the servicer may contact the borrower directly, combined with Reg O's ban on telling consumers not to contact servicers, prevents an agent from isolating the principal. Agent designs should never let the agent become the sole channel.  
•      **Counterparty may decline but must explain.** A required written rejection gives the principal a feedback loop. Agent protocols should return structured refusal reasons rather than silent failures.  
•      **Separate information access from negotiation.** Several servicer forms grant information access only and require a POA for legal acts — the same "read vs. act" split as OAuth read and write scopes, and as IRS 8821 vs. 2848 (item 4).  
•      **Infrastructure risk.** HUD's 2025–2026 cuts to counseling show that a trusted-agent category depends on a funded certifying body. Agent trust registries need a durable governance owner.

**Sources:** [CFPB model Third Party Authorization form (2014)](https://files.consumerfinance.gov/f/201407_cfpb_model-third-party-authorization-form.pdf) · [CFPB handout: Allowing a third party to work with your mortgage company](https://files.consumerfinance.gov/f/documents/201407_cfpb_handout_allowing-a-third-party-to-work-with-your-mortgage-company.pdf) · [Consumer Financial Services Law Monitor on the model form](https://www.consumerfinancialserviceslawmonitor.com/?p=1678) · [12 CFR 1024.38 (eCFR)](https://www.ecfr.gov/current/title-12/chapter-X/part-1024/subpart-C/section-1024.38) · [12 CFR 1024.41 (eCFR)](https://www.ecfr.gov/current/title-12/chapter-X/part-1024/subpart-C/section-1024.41) · [Reg X comments to §1024.41 (CFPB)](https://www.consumerfinance.gov/rules-policy/regulations/1024/interp-41/) · [Reg X comments to §1024.35 (CFPB)](https://www.consumerfinance.gov/rules-policy/regulations/1024/interp-35/) · [12 CFR Part 1015 (eCFR)](https://www.ecfr.gov/current/title-12/chapter-X/part-1015) · [PNC Third Party Authorization (2014)](https://www.pnc.com/content/dam/pnc-home-hq/pdfs/Third%20Party%20Auth%20Form.FINAL-8.21.14.pdf) · [Freddie Mac Borrower Authorization (2016)](https://myhome.freddiemac.com/docs/3rd_party_auth_form_dps.pdf) · [Orrick InfoBytes: CFPB foreclosure relief resolution (2024)](https://infobytes.orrick.com/2024-02-09/cfpb-secures-12-million-after-decade-old-complaint-against-foreclosure-relief-scam-company/) · [Orrick InfoBytes: CRS report on servicing rule (2025)](https://infobytes.orrick.com/2025-09-24/congressional-report-outlines-cfpbs-final-rule-on-mortgage-servicing/) · [CFA: HUD housing counselors (Oct. 2025\)](https://consumerfed.org/news/blogs/frontline-workers-in-a-housing-crisis-the-administration-s-attacks-on-hud-housing-counselors/) · [NRMLA: HUD RIFs reversed (Nov. 2025\)](https://www.nrmlaonline.org/2025/11/14/hud-rifs-reversed) · [HUD FY2027 CJ: Housing Counseling Assistance](https://www.hud.gov/sites/dfiles/CFO/documents/2027_CJ_Program_HCA.pdf) · [Shelterforce: HUD funding notice upends counseling (Aug. 2026\)](https://shelterforce.org/2026/08/27/hud-funding-notice-upends-housing-counseling-assistance/)

## **20\. DPPA driver-record consent and permissible-use certification**

**A. Title:** Driver's Privacy Protection Act of 1994, 18 U.S.C. §§ 2721–2725 (Pub. L. 103-322, Title XXX; opt-in amendment of 1999 effective June 1, 2000), especially § 2721(b)(1)–(14) permissible uses, § 2721(b)(13) written-consent use, and § 2721(c) resale/redisclosure records. State instruments: California DMV INF 70 "Request for Record Information" (REV. 2/2023) and INF 1125 "Request for Own Driver License/Identification Card (DL/ID) Vehicle/Vessel Registration (VR) Record" (REV. 9/2020); North Carolina DMV DL-DPPA-1 "Driver Privacy Protection Act Request Form" (rev. July 3, 2024\) and DL-DPPA-2 "Authorization to Disclose Personal Information" (rev. Dec. 22, 2022).

**B. Blurb:** Pick one of fourteen lawful purposes, swear to it, keep resale records.

### **C. Background**

**1\. Who it comes from:** Congress set the rules; state DMVs implement them with their own request forms, and may add stricter state law (Cal. Veh. Code § 1808 et seq.; N.C.G.S. § 20-43.1). The requester fills in the request form. For consent-based access, the driver signs a release (NC's notarized DL-DPPA-2).

**2\. Key lesson for AI-agent authorization:** **Make purpose a field chosen from a closed, enumerated list, require the requester to certify it under penalty, and require every downstream reseller to keep a five-year log of who received the data and for which listed purpose.** This turns "why do you want this?" into a machine-checkable code, and the redisclosure rule keeps that code attached to each onward transfer. For agents, this suggests purpose-coded scopes, signed purpose attestations with legal consequences, and mandatory lineage logs available to the original data holder on demand.

**3\. The instrument:**

•      **Scenarios.** Insurers rating policies, lenders and collectors locating debtors, attorneys serving process, towing firms notifying owners, employers checking CDL drivers, researchers, private investigators, and anyone holding the driver's written consent.  
•      **Parties.** Data holder: the state DMV. Requester: any person or business. Data subject: the driver or owner. Downstream: resellers and their customers.  
•      **What is protected.** "Personal information" (name, address, photo, SSN, driver ID, phone, medical/disability data). Not covered: accidents, violations, driver status. "Highly restricted" data (photo, SSN, medical) needs express consent except for narrow uses.  
•      **Access gate.** The requester must fit one of 14 permissible uses in § 2721(b). Two are consent-based: (b)(11) when the State has obtained express consent, and (b)(13) when the requester shows the subject's written consent.  
•      **Express consent.** Written, and may be electronic with an E-SIGN signature (§ 2725(5)).  
•      **Certification.** California INF 70 requires a declaration under penalty of perjury and a no-unlawful-use statement. NC DL-DPPA-1 requires the requester to certify eligibility under a circled category and to agree not to redisclose except for listed reasons.  
•      **Subject notice.** California mails a copy of each INF 70 request to the record subject (Veh. Code § 1810(b)), but withholds the requester's confidential data.  
•      **Downstream control.** Recipients may resell only for (b) uses, and must log each recipient and purpose for five years, available to the DMV on request (§ 2721(c)).  
•      **Duration and revocation.** The statute sets none for consents. NC's DL-DPPA-2 is a one-recipient release with no stated term.

**4\. Context:** Congress passed the DPPA after the 1989 murder of actress Rebecca Schaeffer, whose address a private investigator obtained from California DMV records. The Supreme Court upheld it in *Reno v. Condon*, 528 U.S. 141 (2000). Remedies: criminal fines (§ 2723(a)); civil penalties on DMVs up to \$5,000 per day of substantial noncompliance (§ 2723(b)); private suits with liquidated damages of at least \$2,500 (§ 2724(b)(1)).

Scale: InvestigateTV found 23 states earned at least $282millionsellingdriverdatainfiscal2024,includingCalifornia($49 million) and Georgia (over \$53 million); LexisNexis was the top buyer in nearly every state analyzed. In September 2026 a federal court in *Illinois v. U.S. Department of Transportation*, No. 1:26-cv-02547 (E.D. Va.), preliminarily enjoined transfer of CDLIS driver records to federal agencies, finding the government-use exception, § 2721(b)(1), likely did not cover a bulk demand apparently meant for sharing with DHS.

**5\. Stability and variants:** The federal text has been stable since 1999–2000. Variation lives in state forms. California splits requests by type: INF 1125 for one's own record (no third-party option), INF 70 for others' records (purpose checkboxes, subject notice), INF 1161E for attorneys. California residence addresses are confidential under Veh. Code § 1808.21 regardless of DPPA purpose. North Carolina uses DL-DPPA-1 for every request, with 12 categories, and DL-DPPA-2 as the notarized subject release (NC's forms call it "DPPA-2" while its web page says "DL-DPPA-2").

### **C2. Drill-down: the operative clause**

"(13) For use by any requester, if the requester demonstrates it has obtained the written consent of the individual to whom the information pertains."

— 18 U.S.C. § 2721(b)(13)

"An authorized recipient of personal information (except a recipient under subsection (b)(11) or (12)) may resell or redisclose the information only for a use permitted under subsection (b) (but not for uses under subsection (b)(11) or (12)). ... Any authorized recipient (except a recipient under subsection (b)(11)) that resells or rediscloses personal information covered by this chapter must keep for a period of 5 years records identifying each person or entity that receives information and the permitted purpose for which the information will be used and must make such records available to the motor vehicle department upon request."

— 18 U.S.C. § 2721(c)

"I certify (or declare) under penalty of perjury under the laws of the State of California that the foregoing is true and correct."

— California DMV INF 70, Section 5 (REV. 2/2023)

"Your notarized, written consent is required for the release of this information to any person or entity not otherwise authorized to receive it under these statutes."

— NC DMV DL-DPPA-2 (rev. Dec. 22, 2022\)

In (b)(13), the grantor is the driver. The grantee is "any requester" who "demonstrates" the consent: the burden of proof sits on the requester, and the DMV may set the evidence standard. North Carolina demands notarization; federal law accepts an e-signature.

The DMV-side verb is "disclose," limited by the requester's certified purpose. Section 2722(b) separately makes it unlawful to make a false representation to obtain personal information, which turns the certification into the main enforcement hook. Not delegated: onward use outside the 14 purposes, and, for (b)(11) or (12) recipients, resale under another purpose's cover. The DMV is permitted, not compelled, to release; its duty is only to refuse non-permitted requests.

### **D. Outline of the full instrument**

1\.     California INF 70, Part I — Record request  
a.     Requester information (name or business, address, phone).  
b.     DL/ID record request (name plus DL number or DOB; \$5 automated, \$20 photocopy).  
c.      VR/vessel request (plate or VIN/HIN; history, owner-as-of-date, up to 8-vehicle asset search).  
d.     Purpose of request — permissible-use checkboxes (safety and theft, legitimate business, legal proceedings, insurance, CDL employer, other California law by code section).  
e.     Certification, signature, DL/ID number.  
f.      Return mailing label.  
2\.     California INF 70, Part II — Notice to record subject, with mailing label; instructions on fees, permissible uses, and penalties (Veh. Code § 1808.45; DPPA civil remedy).  
3\.     NC DL-DPPA-1 — 12 permissible-use categories (item 11 is written notarized consent, with DL-DPPA-2 attached); up to 10 drivers; record type and fees ($12.75–$18.00); certification of qualification and no-redisclosure.  
4\.     NC DL-DPPA-2 — recipient named, subject's name, signature, NC license number, DOB, notary block.

The request form carries the purpose code and the requester's oath. The subject release supplies consent when no other code fits, and § 2721(c) logs follow the data downstream.

### **E. Insights and observations**

•      **A closed purpose taxonomy is enforceable because it is closed.** Every request maps to one statutory code. Auditors can test whether the code fits the requester, as the *Illinois v. DOT* court did when it rejected the government-use code for a bulk transfer.  
•      **The consent path is the "everything else" bucket.** Consent (b)(13) works when no institutional purpose fits. For agents, user consent should be one enumerated purpose among several, not the default.  
•      **Checkboxes alone are weak controls.** In *Gordon v. Softech* (2d Cir. 2013), the court held that resellers must take reasonable care and found a drop-down menu and checkbox insufficient against an obviously suspicious buyer. Certified purpose needs back-end vetting.  
•      **Lineage logging is reseller-side and pull-based.** The DMV can demand § 2721(c) records but receives no push feed. Agent ecosystems can improve on this with append-only, holder-visible disclosure logs.  
•      **Subject notice is a strong, cheap control.** California sends the record subject a copy of every INF 70 request. Notifying principals of each agent access is the equivalent.  
•      **Evidence standards for consent vary by state.** NC requires notarization; federal law accepts e-signatures. Agent consent artifacts should carry assurance-level metadata so counterparties can apply their own threshold.  
•      **Monetization creates pressure.** With over \$282 million in state sales in 2024, permissible-use certifications carry heavy commercial volume, and misuse litigation (e.g., crash-report resale suits) continues.

**Sources:** [18 U.S.C. § 2721 (LII)](https://www.law.cornell.edu/uscode/text/18/2721) · [18 U.S.C. § 2722 (LII)](https://www.law.cornell.edu/uscode/text/18/2722) · [18 U.S.C. § 2723 (LII)](https://www.law.cornell.edu/uscode/text/18/2723) · [18 U.S.C. § 2724 (LII)](https://www.law.cornell.edu/uscode/text/18/2724) · [18 U.S.C. § 2725 (LII)](https://www.law.cornell.edu/uscode/text/18/2725) · [California DMV INF 70 (REV. 2/2023)](https://www.dmv.ca.gov/portal/uploads/2023/04/Revised-upload-INF-70.pdf) · [California DMV INF 1125](https://dmv.ca.gov/portal/file/request-for-your-own-driver-license-identification-card-dl-id-or-vehicle-vessel-registration-vr-information-record-inf-1125-pdf) · [California DMV: Obtaining Information From DMV Records](https://www.dmv.ca.gov/portal/driver-education-and-safety/educational-materials/fast-facts/public-information-request-ffdmv-4/) · [NC DMV DL-DPPA-1](https://www.ncdot.gov/dmv/downloads/Documents/DL-DPPA-1.pdf) · [NC DMV DL-DPPA-2](https://www.ncdot.gov/dmv/downloads/Documents/DL-DPPA-2-english.pdf) · [EPIC: DPPA overview](https://epic.org/the-drivers-privacy-protection-act-dppa-and-the-privacy-of-your-state-motor-vehicle-record/) · [InvestigateTV: states collect millions selling driver data (Oct. 2025\)](https://www.live5news.com/2025/10/27/states-collect-millions-by-selling-drivers-data-private-investigators-data-brokers/) · [Winston & Strawn on Gordon v. Softech](https://www.winston.com/en/blogs-and-podcasts/privacy-law-corner/second-circuit-holds-need-reasonable-care-for-dmv-information) · [Illinois v. DOT preliminary injunction order (Sept. 17, 2026\)](https://oag.ca.gov/system/files/attachments/press-docs/pi-order_1.pdf) · [CCJ: court hands DOT another defeat over CDLIS records](https://www.ccjdigital.com/regulations/article/15835535/court-hands-dot-another-defeat-in-battle-over-cdlis-records)

## **21\. Brokerage limited power of attorney and trading authorization**

**A. Title:** Charles Schwab "Limited Power of Attorney (LPOA) for Investment Advisor," APP10504-33 (rev. 06/26); Fidelity "Account Authority" form and Account Authority Customer Agreement, 1.926568.119 (footer 09/25). Governing rules: FINRA Rule 3260 (Discretionary Accounts), FINRA Rule 4512(a)(1)(F) and Supplementary Material .06 (trusted contact person), SEC Advisers Act Rule 206(4)-2 (custody rule), and the SEC staff no-action letter to the Investment Adviser Association on standing letters of authorization (SLOAs), Feb. 21, 2017, with Custody Rule FAQ II.4.

**B. Blurb:** Let the agent trade freely, but never let it send money elsewhere.

### **C. Background**

**1\. Who it comes from:** Custodians (Schwab, Fidelity, Pershing and others) draft their own LPOA and trading-authority forms; FINRA and the SEC set the rules the forms implement. The account owner and the registered investment adviser (RIA) or other agent complete each instance, often via the custodian's e-signature workflow.

**2\. Key lesson for AI-agent authorization:** **Split authority into separately granted tiers (view, trade, pay fees, move to the owner's own accounts, pay third parties), and allow outbound transfers to third parties only through a standing instruction the custodian verifies directly with the principal, which the agent cannot create or edit.** This maps to agent scopes: a trading or "read-write within the account" scope is low-risk because value stays in the principal's name. Money-movement out of the principal's control needs a payee allowlist set by the principal, out-of-band confirmation by the custodian, notices after each transfer, and periodic reconfirmation.

**3\. The instrument:**

•      **Scenario:** An account owner hires an RIA to manage a brokerage account, or names a family member or other agent to trade.  
•      **Parties:** Account owner (principal); advisor or agent; custodian broker-dealer (counterparty and verifier); third-party payees (for SLOAs).  
•      **Schwab LPOA tiers:**  
a.     Trading: buy and sell, including margin, short sales and options up to the account's approval level; order aggregation across accounts. Schwab may act without further approval from the owner.  
b.     Fee payment (optional): advisory fees deducted in amounts the advisor specifies.  
c.      Disbursement (optional): checks to the owner at the address of record, and journals to other Schwab accounts in the owner's name. Excludes wires, MoneyLink and third-party payments.  
d.     Information access and duplicate statements to CPAs or reporting vendors.  
•      **Fidelity tiers:** "Limited Authority" (view, trade, deposit checks; no removal of money) and "Full Authority" (adds withdrawals, rollovers, Roth conversions, transfers between Fidelity accounts; requires a Medallion signature guarantee). Neither tier allows naming beneficiaries or opening IRAs, and the agent may not be paid for managing the account under this form.  
•      **Duration and termination:** Schwab's LPOA continues until revoked by notice from the owner or advisor. It ends on notice of death or on a licensed physician's written notice of incapacity; it is expressly not durable. Fidelity's authority ends on written withdrawal, agent resignation, death or incapacity of the owner or agent, or Fidelity's removal of the agent, which it may do at any time for any reason.  
•      **Counterparty duties:** Both custodians disclaim any duty to supervise the agent. The owner indemnifies the custodian for acting on the agent's instructions. Fidelity may run identity and background checks on the agent.  
•      **SLOA path for third-party payments:** A separate standing letter signed by the client names the payee and its account or address. The custodian verifies it and sends notices. The adviser cannot change the payee.

**4\. Context:**

•      **Why it exists:** Advisers need trading discretion daily, but direct withdrawal authority would give them "custody" under Rule 206(4)-2(d)(2)(ii), which covers any arrangement, including a general power of attorney, under which the adviser may withdraw client funds or securities. Custody triggers an annual surprise examination by an independent accountant (§(a)(4)). Forms are built to stay below that line.  
•      **FINRA discretion:** Rule 3260(b) bars any discretionary power without the customer's prior written authorization naming the individual(s) and the firm's written acceptance of the account. Time-and-price discretion on a specific customer order (definite amount, specified security) lapses at the end of the business day it was granted, unless the customer signs and dates a contrary written instruction (3260(d)(1)).  
•      **SEC SLOA no-action (Feb. 21, 2017):** An adviser acting under a SLOA has custody, but staff will not recommend enforcement for skipping the surprise exam if seven conditions hold:  
a.     The client gives the custodian a signed written instruction with the third party's name and address or account number.  
b.     The client authorizes the adviser in writing to direct transfers, on a schedule or from time to time.  
c.      The custodian verifies the authorization (e.g., signature review) and sends the client a transfer notice after each transfer.  
d.     The client can terminate or change the instruction.  
e.     The adviser cannot designate or change the payee or its details.  
f.      The adviser keeps records showing the payee is not a related person and not at the adviser's address.  
g.     The custodian sends an initial notice confirming the instruction and an annual reconfirmation.  
•      **Reporting:** Advisers report SLOA assets in Form ADV Item 9 from annual amendments filed after Oct. 1, 2017\.  
•      **First-party transfers:** FAQ II.4 says moving assets between a client's own accounts is not custody if the client authorized it in writing and the custodians have a copy.  
•      **Custodian hygiene:** Schwab expires standing instructions unused for three years and sends notices (Marotta, Oct. 2025).  
•      **States:** Connecticut (Nov. 2022\) and other states adopted the same seven-condition enforcement position for state-registered advisers.

**5\. Stability and variants:**

•      **Forms:** Schwab's LPOA is on its 33rd revision (APP10504-33, June 2026). Fidelity also offers a separate Registered Investment Advisor Authorization form. Schwab has a separate PCRA LPOA for retirement plans. (The Schwab link in the source list points to the PCRA plan application, not the adviser LPOA.)  
•      **Custody rule:** The SEC's 2023 "Safeguarding Advisory Client Assets" proposal was withdrawn in June 2025\. The July 2026 regulatory agenda revived custody rulemaking, focused on crypto assets; a proposal entered White House review on Aug. 25, 2026, and its text is not public, so effects on SLOAs are unknown.  
•      **FINRA 2026 proposals:** Regulatory Notice 26-02 (Jan. 8, 2026\) and filing SR-FINRA-2026-018 would let firms call trusted contacts "emergency contacts," allow multiple contacts (Rule 4512); extend Rule 2165 exploitation holds from 55 to 145 business days; and create Rule 2166 permitting up to 10-business-day delays of disbursements for suspected fraud for any adult customer. Status: filed, not yet SEC-approved as of the filing text reviewed.  
•      **Trusted contact:** Rule 4512(a)(1)(F) calls for a trusted contact person age 18 or older for non-institutional accounts. The contact has no authority to transact; firms may contact them about suspected exploitation, health status, or the identity of a guardian, executor, trustee or POA holder.

### **C2. Drill-down: the operative clause**

Paraphrase: the account holder appoints the named advisor as agent and attorney-in-fact to buy, sell and otherwise trade securities in the account, and directs Schwab to follow the advisor's instructions without further approval; if the holder checks the boxes, the advisor may also have fees paid from the account and request disbursements, but only by check to the holder's address of record or by transfer to another Schwab account in the holder's name. Schwab takes on no duty to supervise or monitor the advisor's trading or performance.

— Schwab, Limited Power of Attorney for Investment Advisor, APP10504-33 (06/26), trading, fee and disbursement sections

Paraphrase: no member or representative may exercise discretion in a customer account unless the customer has given "prior written authorization to a stated individual or individuals" and the firm has accepted the account in writing through a designated principal under Rule 3110\.

— FINRA Rule 3260(b)

**Grantor:** the account owner(s). **Grantee:** a named advisor firm, or individual agent. **Delegating verbs:** "appoint," "buy, sell," "instruct." **Object:** the specific account(s) listed. **Scope limiters:** the account's approved options and margin level; disbursement destinations limited to the owner; checkbox opt-ins for fees and disbursements. **Not delegated:** third-party payments, wires, changing the address of record, beneficiary designations, opening new accounts. **Counterparty binding:** the custodian agrees to follow instructions within scope and is indemnified for doing so, but may refuse, restrict or remove the agent.

### **D. Outline of the full instrument**

1\.     Account and advisor identification — owner names, account numbers, advisor firm and master account number.  
2\.     Grant of trading authority — scope by product (equities, options, margin, short sales); aggregation.  
3\.     Optional authorities (checkboxes)  
a.     Fee payment from this or another owned account.  
b.     Disbursements to owner only (check to address of record; journal to own Schwab account).  
4\.     Information sharing and duplicate statements.  
5\.     Custodian disclaimers — no supervision, advisor independence, no advice.  
6\.     Indemnification of custodian.  
7\.     Duration, revocation and termination — notice, death, physician-certified incapacity; non-durable.  
8\.     Signatures — owner(s) and advisor; e-signature, or Medallion guarantee for higher tiers (Fidelity).  
9\.     Separate instruments — SLOA for third-party payees; trusted contact designation; full POA for broader acts.

The LPOA grants bounded in-account authority; any value leaving the owner's name must go through a separate, owner-signed, custodian-verified instrument.

### **E. Insights and observations**

•      **"Same name" is the key invariant.** LPOA disbursements stay inside accounts titled to the owner. Agent payment systems can use the same test: transfers to accounts bound to the principal's verified identity are low-risk; anything else needs a principal-set allowlist.  
•      **The agent must not control the payee list.** SLOA condition 5 bars the adviser from designating or changing the payee, blocking the classic insider fraud of redirecting funds. For agents, payee creation should require principal-side authentication.  
•      **Custodian as independent verifier.** Conditions 3 and 7 make the custodian confirm with the client directly and send per-transfer and annual notices — out-of-band verification plus continuous transparency, not reliance on the agent's say-so.  
•      **Dormancy expiry.** Schwab's three-year expiry of unused standing instructions is a concrete stale-grant policy agents could copy.  
•      **Non-durable by default.** Brokerage LPOAs end at incapacity, unlike durable estate POAs (item 23). This protects vulnerable clients but can strand accounts; FINRA's trusted contact is the escape valve, with notification rights but no transaction rights.  
•      **Day-scoped discretion.** FINRA's time-and-price rule shows a narrow, auto-expiring grant: one order, one day — a model for single-task agent tokens.  
•      **Liability shifts to the principal.** Both custodians disclaim monitoring and require indemnity. Agent platforms will likely push the same terms, so principals need logs and notices to detect misuse themselves.

**Sources:** [Schwab LPOA for Investment Advisor, APP10504-33 (via GeoWealth)](https://resources.geowealth.com/hubfs/Support%20Center/Schwab/Schwab_LPOA_CS_Template_APP10504.pdf) · [Fidelity Account Authority form](https://www.fidelity.com/bin-public/060_www_fidelity_com/documents/customer-service/trading-authority.pdf) · [FINRA Rule 3260](https://www.finra.org/rules-guidance/rulebooks/finra-rules/3260) · [FINRA Rule 4512](https://www.finra.org/rules-guidance/rulebooks/finra-rules/4512) · [SEC staff no-action letter, Investment Adviser Association (Feb. 21, 2017\)](https://www.sec.gov/divisions/investment/noaction/2017/investment-adviser-association-022117-206-4.htm) · [SEC Custody Rule FAQ](https://www.sec.gov/divisions/investment/custody_faq_030510.htm) · [17 CFR 275.206(4)-2 (LII)](https://www.law.cornell.edu/cfr/text/17/275.206\(4\)-2) · [Connecticut DOB: Standing Letters of Authorization (2022)](https://portal.ct.gov/dob/securities-licensing/advisers-state/standing-letters-of-authorization) · [Marotta: Schwab expiration notices for standing instructions (2025)](https://marottaonmoney.com/why-schwab-sends-expiration-notices-for-advisor-standing-instructions/) · [Bressler: custody rule back on agenda (July 2026\)](https://www.bressler.com/news-custody-rule-or-perhaps-the-safeguarding-rule-is-back) · [The Defiant: SEC custody rewrite enters White House review (Aug. 2026\)](https://thedefiant.io/converge/regulation/sec-crypto-custody-rewrite-enters-white-house-review) · [FINRA Regulatory Notice 26-02](https://www.finra.org/rules-guidance/notices/26-02) · [SR-FINRA-2026-018](https://www.finra.org/sites/default/files/2026-08/SR-FINRA-2026-018.pdf)

## **22\. SEC form of proxy (proxy card)**

**A. Title:** Form of proxy (proxy card) under Exchange Act Rule 14a-4, 17 CFR 240.14a-4 (last amended 86 FR 68378, Dec. 1, 2021), and Rule 14a-19 (universal proxy), adopted in Release No. 34-93596 (Nov. 17, 2021), effective Jan. 31, 2022, for meetings after Aug. 31, 2022\. Related: the SEC "Sample Proxy Card" (Spotlight on Proxy Matters, 2010); the broker voting instruction form (VIF); NYSE Rule 452 and Listed Company Manual § 402.08; DGCL § 212 (stockholder proxies).

**B. Blurb:** Per-item choices, bounded discretion, one meeting, latest-dated card wins.

### **C. Background**

**1\. Who it comes from:** The SEC sets the content rules. Each soliciting party (the board, or a dissident) drafts its own card and files it with the proxy statement. Brokers and their agent (mainly Broadridge) send VIFs to street-name holders. State corporate law (e.g., DGCL § 212\) supplies the underlying right to vote by proxy.

**2\. Key lesson for AI-agent authorization:** **Give the principal an explicit for/against/abstain choice on every separately identified action, and allow the agent discretion only for a short, enumerated list of disclosed residual categories, never a blank check.** Rule 14a-4 is effectively a consent schema: unbundled line items, a bolded default for unmarked items, a whitelist of discretionary categories ((c)(1)–(7)), and a blacklist of things a proxy can never authorize ((d)(1)–(4)). An agent mandate can copy this: enumerate the planned actions with per-item choices, state the default for blanks, and limit "use your judgment" to named, foreseeable classes of minor matters.

**3\. The instrument:**

•      **Scenario:** a shareholder appoints named proxy holders to vote shares at a specific annual or special meeting.  
•      **Parties:** the shareholder (principal); named proxies, usually officers (agents); the soliciting party; the company and inspector of elections (counterparty and validator); for street-name holders, the broker or bank, which votes per the VIF.  
•      **Powers delegated:** voting on each listed matter as instructed; voting unmarked items as the card states in bold; limited discretion under (c).  
•      **Hard limits (14a-4(d)):** no authority to vote for anyone who is not a bona fide nominee named in a proxy statement; no authority for any annual meeting other than the next one; no more than one meeting (including adjournments); no action other than what the proxy statement proposes, plus (c) matters.  
•      **Format (14a-4(a)–(b)):** bold statement of who is soliciting; a blank for the date; each matter identified "clearly and impartially," whether or not related to or conditioned on others; for/against/abstain boxes; director choices of for/withhold or for/against/abstain depending on state law; 1/2/3-year/abstain for say-on-pay frequency.  
•      **Universal proxy (14a-19):** in contested elections every card must list all duly nominated candidates from both sides, grouped and alphabetized, in the same font, with the maximum number of votes and the effect of over- or under-voting disclosed. Dissidents must give notice 60 days before the anniversary and solicit holders of at least 67% of the voting power.  
•      **Duration and revocation:** DGCL § 212(b) caps a proxy at 3 years unless it states longer; 14a-4(d) narrows it to one meeting. A proxy is revocable unless it says so and is "coupled with an interest" (§ 212(e)). A later-dated proxy, written revocation, or voting at the meeting revokes an earlier proxy; SEC guidance says companies record the last completed proxy before the close of the election.  
•      **Validation:** the inspector of elections checks signature, date, control number and record-date holdings. Under § 212(c) a proxy may be granted by a signed document or by electronic transmission.

**4\. Context:** Proxy voting is how almost all public-company shares are voted. Broadridge reports that in the 2025 season retail investors voted 28.0% of their shares (a 9-year low) and institutions 76.6%. The 14a rules date from the 1930s under Exchange Act § 14(a).

Broker discretion has shrunk. Under NYSE Rule 452, a broker may vote uninstructed street-name shares only on "routine" matters if it has no instructions by the 10th day before the meeting. Director elections became non-routine for meetings from Jan. 1, 2010, and executive-pay votes from Aug. 2010 under Dodd-Frank § 957\. In contested meetings brokers cannot use discretion on any item. Failure modes: over-voting on universal cards (all director votes invalid), undated cards, conflicting cards, and lost votes in the custody chain.

**5\. Stability and variants:** Rule 14a-4's core has been stable for decades; the 2021 universal-proxy release made the last major change. Variants: management and dissident cards; VIFs for beneficial owners; telephone and internet voting by control number; investment-company cards (excluded from 14a-19). Pending change: on Sept. 16, 2026 the SEC **proposed** amending 14a-4(c) to widen company discretion over proposals not in its proxy materials, with a mandatory checkbox letting holders withhold that discretion, and proposed rescinding Rule 14a-8. These are proposals only as of Oct. 20, 2026\.

### **C2. Drill-down: the operative clause**

"Means shall be provided in the form of proxy whereby the person solicited is afforded an opportunity to specify by boxes a choice between approval or disapproval of, or abstention with respect to each separate matter referred to therein as intended to be acted upon, other than elections to office and votes to determine the frequency of shareholder votes on executive compensation..."

— 17 CFR 240.14a-4(b)(1)

\[A proxy may not grant authority\] "(1) To vote for the election of any person to any office for which a bona fide nominee is not named in the proxy statement..." \[or\] "(4) To consent to or authorize any action other than the action proposed to be taken in the proxy statement, or matters referred to in paragraph (c) of this section."

— 17 CFR 240.14a-4(d) (excerpt; bracketed lead-in paraphrased)

"...where the person solicited specifies by means of a ballot provided pursuant to paragraph (b) of this section a choice with respect to any matter to be acted upon, the shares will be voted in accordance with the specifications so made."

— 17 CFR 240.14a-4(e)

The grantor is the shareholder. The grantees are the named proxies, who must be named. The verbs are "appoint" and "authorize to vote." The object is the shares, at one meeting. Scope limiters: per-matter instruction, a bolded default for blanks under (b)(1), enumerated discretion under (c), and absolute prohibitions under (d). Paragraph (e) binds the proxy holder to vote as instructed. The company is bound by state law to count a valid, unrevoked, latest-dated proxy.

### **D. Outline of the full instrument**

1\.     Header — company, meeting date, and the bold "solicited on behalf of the Board" (or dissident) line.  
2\.     Appointment — named proxies, power of substitution, the record date, and shares covered.  
3\.     Board recommendation — for each item.  
4\.     Voting items  
a.     Election of directors — for/withhold or for/against/abstain; universal list in contests with a maximum number of votes.  
b.     Company proposals (auditor ratification, say-on-pay, plans) — for/against/abstain.  
c.      Say-on-pay frequency — 1/2/3 years/abstain.  
d.     Shareholder proposals — for/against/abstain.  
5\.     Default and discretion statement — how unmarked cards are voted, and discretion on other business properly brought before the meeting.  
6\.     Voting methods — mail, phone, internet with a control number; deadline.  
7\.     Signature block — date, joint-owner signatures, and full title for attorneys, executors, trustees and corporate officers.

The appointment (2) creates the agency, the items (4) carry the instructions, and the default and discretion statement (5) says what happens without instructions. The signature block (7) carries the grantor's own authority chain, such as an officer signing for a corporate holder.

### **E. Insights and observations**

•      **Unbundling is a consent primitive.** 14a-4(a)(3) bars bundling separate matters, even if they are conditioned on the approval of other matters. Agent consent screens should not let a principal approve a risky action only by approving a safe one.  
•      **The default must be disclosed, not implied.** An unmarked item may be voted only as the card states in bold. For agents, the fallback for silence belongs in the grant itself.  
•      **Latest-dated wins is simple, but timestamps must be trustworthy.** Elliott's 2025 Phillips 66 materials stress that only the latest dated proxy counts. Revocation by supersession needs reliable timestamps and a cut-off (close of the election). Agent systems should version mandates and resolve conflicts deterministically.  
•      **Over-authorization voids the instruction.** On a universal card, marking more FOR boxes than seats invalidates all director votes. Agent policies should fail closed when instructions exceed limits, instead of guessing.  
•      **Intermediary discretion has steadily narrowed.** Rule 452 moved director elections and pay votes out of broker discretion in 2010, and contested meetings remove it entirely — a regulatory trend toward instructed authority for consequential actions, the model for AI agents acting on high-impact items.  
•      **Standing instructions are growing.** Broadridge's voting-choice programs grew from 116 to 374 funds in the year to June 30, 2025\. These are durable policy mandates that replace per-meeting instructions, close to the "standing scope plus policy" model agents use.  
•      **Watch the 2026 proposal.** If adopted, broader 14a-4(c) company discretion would come with an opt-out checkbox — a regulator's own design for widening agent discretion while preserving principal control.

**Sources:** [eCFR – 17 CFR 240.14a-4](https://www.ecfr.gov/current/title-17/chapter-II/part-240/subject-group-ECFR8c9733e3d6f0a5c/section-240.14a-4) · [LII – 17 CFR 240.14a-4](https://www.law.cornell.edu/cfr/text/17/240.14a-4) · [LII – 17 CFR 240.14a-19](https://www.law.cornell.edu/cfr/text/17/240.14a-19) · [SEC – Universal Proxy fact sheet (34-93596)](https://www.sec.gov/files/34-93596-fact-sheet.pdf) · [Morrison Foerster – SEC adopts universal proxy card rules](https://www.mofo.com/resources/insights/211214-us-sec-adopts-universal-proxy-card-rules.html) · [SEC – Sample Proxy Card](https://www.sec.gov/spotlight/proxymatters/proxy_sample.htm) · [SEC – Voting mechanics (Proxy Matters)](https://www.sec.gov/spotlight/proxymatters/voting_mechanics.shtml) · [Delaware Code Title 8, Subchapter VII (§ 212\)](https://delcode.delaware.gov/title8/c001/sc07/index.html) · [Seyfarth – SEC approves NYSE Rule 452 amendments (2009)](https://www.seyfarth.com/news-insights/sec-approves-nyse-rule-amendments-prohibiting-discretionary-broker-voting-in-uncontested-director-elections-and-certain-investment-company.html) · [Cooley – NYSE eliminates discretionary voting on executive compensation (2010)](https://www.cooley.com/news/insight/2010/sec-approves-nyse-rule-change-eliminating-discretion-voting-on-executive-compensation-matters) · [SEC EDGAR – Elliott DEFC14A for Phillips 66 (2025)](https://www.sec.gov/Archives/edgar/data/1534701/000092189525000972/defc14a10168303_04032025.htm) · [Broadridge – ProxyPulse 2025](https://www.broadridge.com/_assets/pdf/2025proxypulse-updated.pdf) · [Morgan Lewis – SEC proposes proxy amendments (Sept. 2026\)](https://www.morganlewis.com/pubs/2026/09/sec-proposes-amendments-to-modernize-proxy-solicitation-process-seeks-to-rescind-rule-14a8) · [Skadden – Major changes to federal proxy rules (Oct. 2026\)](https://www.skadden.com/insights/publications/2026/10/skadden-discusses-major-changes-to-federal-proxy-rules)

## **23\. General and statutory durable powers of attorney**

**A. Title:** California "Uniform Statutory Form Power of Attorney," Cal. Prob. Code § 4401 (form as amended by Stats. 2011, ch. 113, operative Jan. 1, 2012), with §§ 4264 (powers requiring express grant) and 4406 (compelling third parties). Uniform Power of Attorney Act (UPOAA), approved by the Uniform Law Commission in 2006; key sections 104 (durability), 113 (agent acceptance), 119 (reliance), 120 (acceptance and refusal; the bracketed Alternative A), 201 ("hot powers"), 301 (statutory form), 302 (agent's certification). Enacted versions quoted here: Virginia Code §§ 64.2-1602, \-1611, \-1618, \-1622, \-1639.

**B. Blurb:** Dangerous powers are off unless initialed; banks must honor proper POAs.

### **C. Background**

**1\. Who it comes from:** State legislatures, usually enacting the ULC's model act or the older 1988 Uniform Statutory Form Power of Attorney Act (California's form follows the older model). The principal fills in the statutory form, often with a lawyer, and signs it before a notary. Banks, brokers and title companies are the counterparties.

**2\. Key lesson for AI-agent authorization:** **Deny dangerous scopes by default so they exist only by explicit, separate opt-in, and pair this with a statutory duty on counterparties to accept a properly executed, verifiable grant within a deadline.** UPOAA § 201(a) lists "hot powers" (gifts, trust changes, beneficiary and survivorship changes, delegation, waivers of survivor annuities) that a general grant cannot imply — the same as high-risk scopes that need a separate consent. § 120 then requires a third party to accept or request a certification within seven business days, and makes wrongful refusal cost money. That solves the "merchant won't honor my agent's mandate" problem with a standard credential, a standard verification request and liability for refusal.

**3\. The instrument:**

•      **Scenarios:** managing finances during absence or incapacity: banking, real estate, investments, taxes, benefits, litigation, retirement plans. Health care decisions are excluded and go in a separate advance directive.  
•      **Parties:** principal; agent (attorney-in-fact), plus optional co-agents and successors; third parties who accept the POA.  
•      **Powers:** California § 4401 lists subject areas (A)–(M) and (N) "ALL OF THE POWERS LISTED ABOVE," granted by initialing. The UPOAA statutory form uses the same subject-area method (§§ 204–217).  
•      **Hot powers:** need an express grant even with "all powers" (UPOAA § 201(a); Cal. § 4264 lists trusts, gifts, disclaimers, survivorship, beneficiary designations and loans to the agent).  
•      **Durability:** under UPOAA § 104 a POA is durable unless the document says otherwise. The California form includes a durability sentence that the principal must strike to opt out.  
•      **Effective date:** immediately unless the document makes it "springing" on a stated event.  
•      **Agent acceptance:** by exercising authority or any other assertion or conduct indicating acceptance (UPOAA § 113; Va. § 64.2-1611). Some states add an acceptance form.  
•      **Revocation and termination:** on the principal's death or revocation; the California form says revocation does not bind a third party until it has "actual knowledge" of it.  
•      **Counterparty validation:** a notarized (acknowledged) signature is presumed genuine (§ 105). The third party may request an agent's certification under penalty of perjury (§ 302 form), an English translation, or an opinion of counsel, and may rely on them without further investigation (§ 119(d)).

**4\. Context:** POAs are the most common private delegation of a person's whole financial life, and elder financial abuse is the main failure mode. The UPOAA was approved in 2006\. A Michigan House analysis reported 30 states plus D.C. had enacted it or a substantially similar law as of June 13, 2023; Michigan's version took effect July 1, 2024, and Miller Canfield described Michigan as joining "30 other states and the District of Columbia." Recent enactments include Oklahoma (effective Nov. 1, 2021\) and Vermont (Act 60, effective July 1, 2023). A Massachusetts bill (H.1523) went to study in June 2024\.

Non-adopters include California, New Jersey, Massachusetts, Indiana, Missouri, Minnesota, Tennessee and Louisiana (per a 50-state survey). No 2025–2026 enactments were verified, and the ULC enactment map did not load. California's § 4406 already lets an agent compel a third party that refuses a properly executed statutory form, with attorney's fees if the refusal was unreasonable; refusal is deemed unreasonable when the only reason is that the POA is not on the institution's own form.

**5\. Stability and variants:** Each state's act diverges. Some omit or rewrite the § 120 acceptance mandate; the UPOAA offers Alternative A (mandatory acceptance with liability) and Alternative B (common-law rules). States vary execution formalities (notary versus two witnesses), and some add hot powers (Virginia adds control of electronic communications; Michigan adds foreign financial accounts). Electronic signing and remote notarization are increasingly accepted. Sister instruments include health care directives, springing POAs, limited POAs (e.g., real estate closings), and agency-specific forms such as IRS Form 2848 (item 4), which statutes often exclude.

### **C2. Drill-down: the operative clause**

"...an agent under a power of attorney may do the following on behalf of the principal or with the principal's property only if the power of attorney expressly grants the agent the authority and exercise of the authority is not otherwise prohibited or limited by another statute, agreement, or instrument to which the authority or property is subject: 1\. Create, amend, revoke, or terminate an inter vivos trust; 2\. Make a gift; 3\. Create or change rights of survivorship; 4\. Create or change a beneficiary designation; 5\. Delegate authority granted under the power of attorney; 6\. Waive the principal's right to be a beneficiary of a joint and survivor annuity, including a survivor benefit under a retirement plan; 7\. Exercise fiduciary powers that the principal has authority to delegate..."

— Va. Code § 64.2-1622(A) (enacting UPOAA § 201(a))

"A person shall either accept an acknowledged power of attorney or request a certification..." \[within seven business days, per the section\]; if one is requested, "the person shall accept the power of attorney no later than five business days after receipt"; and "A person may not require an additional or different form of power of attorney..."

— Va. Code § 64.2-1618(A) (enacting UPOAA § 120, Alt. A); verbatim fragments, with the bracketed deadline paraphrased

"TO GRANT ONE OR MORE, BUT FEWER THAN ALL, OF THE FOLLOWING POWERS, INITIAL THE LINE IN FRONT OF EACH POWER YOU ARE GRANTING. TO WITHHOLD A POWER, DO NOT INITIAL THE LINE IN FRONT OF IT." ... "I agree that any third party who receives a copy of this document may act under it."

— Cal. Prob. Code § 4401

The grantor is the principal and the grantee the agent, appointed by name. The object is enumerated subject areas, with general authority inside each. Scope limiters: initials per area, special instructions, and the hot-power carve-out that needs specific words. Not delegated by default: gifts, trust changes, beneficiary changes, delegation, and health care. Counterparties are bound by § 120 (or Cal. § 4406\) to accept, and protected by § 119 good-faith reliance.

### **D. Outline of the full instrument**

1\.     Notice to principal — broad powers, no health care, revocable, get advice.  
2\.     Designation of agent — plus optional co-agents (acting separately unless stated) and successors.  
3\.     Grant of general authority — initialed subject areas (Cal. A–N; UPOAA real property, tangible personal property, stocks, banking, business, insurance, estates, claims, family maintenance, benefits, retirement, taxes, gifts).  
4\.     Grant of specific authority (hot powers) — separately initialed in the UPOAA form; under California law it must be written into special instructions.  
5\.     Limitations and special instructions — free text.  
6\.     Effective date and durability — immediate or springing; durable unless struck.  
7\.     Nomination of conservator or guardian (optional).  
8\.     Third-party reliance and indemnity — California form.  
9\.     Signature and acknowledgment — notary certificate.  
10\.  Agent's acceptance or important-information page — duties of loyalty, records and avoiding conflicts.  
11\.  Agent's certification (§ 302, separate form) — signed under penalty of perjury when presented.

The initialed grants (3–4) set the scopes, the formalities (9) make the instrument self-authenticating, and the certification (11) is a fresh, signed status assertion at the moment of use.

### **E. Insights and observations**

•      **"All powers" does not mean all powers.** Even initialing (N) in California does not reach § 4264 acts. A wildcard scope in an agent system should exclude a defined list of dangerous actions unless they are named individually.  
•      **The certification is a just-in-time status attestation.** The § 302 form has the agent swear that the principal is alive, that the POA was not revoked, and that any springing event occurred — an on-presentation freshness proof that patches the lack of a revocation registry. It maps to short-lived assertions minted at transaction time.  
•      **Revocation needs actual knowledge.** The California form says revocation does not bind a third party until it has actual knowledge, and UPOAA § 119 protects good-faith reliance. Without a registry, revocation is weak, so agent systems should add a queryable status endpoint.  
•      **Refusal costs money on both sides.** The wrongful refuser can be ordered to accept and pay attorney's fees, and a requester who asks for a frivolous opinion of counsel pays for it (Michigan analysis). This balances the counterparty's duty to accept against its right to verify.  
•      **Statutory refusal grounds are a template for counterparty policy.** Refusal is allowed for actual knowledge of termination, a conflict with federal law, a refused certification request, a good-faith belief that the agent lacks authority, or a report to adult protective services about suspected abuse. Platforms can publish equivalent accept/refuse rules for agent mandates.  
•      **Abuse controls sit around the grant.** Michigan imposes treble damages for agent embezzlement and bars banks from demanding their own forms. Durability by default makes misuse after incapacity hard to detect. Agent systems acting for incapacitated or absent users need monitoring by a named second party.  
•      **The count is uncertain.** About 30–31 states plus D.C. had adopted the act by 2024; no enactments after Michigan were verified. California still relies on its 1988-model statutory form with § 4406 enforcement rather than the UPOAA.

**Sources:** [FindLaw – Cal. Prob. Code § 4401](https://codes.findlaw.com/ca/probate-code/prob-sect-4401/) · [FindLaw – Cal. Prob. Code § 4264](https://codes.findlaw.com/ca/probate-code/prob-sect-4264/) · [FindLaw – Cal. Prob. Code § 4406](https://codes.findlaw.com/ca/probate-code/prob-sect-4406/) · [UPOAA official text with comments](https://www.sos.ms.gov/content/documents/pol_res/power%20of%20attorney/5upoaa_final_may08.pdf) · [Va. Code § 64.2-1622](https://law.lis.virginia.gov/vacode/title64.2/chapter16/section64.2-1622/) · [Va. Code § 64.2-1618](https://law.lis.virginia.gov/vacode/title64.2/chapter16/section64.2-1618/) · [Va. Code § 64.2-1611](https://law.lis.virginia.gov/vacode/title64.2/chapter16/section64.2-1611/) · [Va. Code § 64.2-1639](https://law.lis.virginia.gov/vacode/title64.2/chapter16/section64.2-1639/) · [Michigan House Fiscal Agency analysis, HB 4644 (2023)](https://ombudsman.legislature.mi.gov/documents/2023-2024/billanalysis/House/pdf/2023-HLA-4644-5336C19D.pdf) · [Miller Canfield – Michigan UPOAA in effect](https://www.millercanfield.com/resources-Michigans-Uniform-Power-of-Attorney-Act-Goes-into-Effect.html) · [Hall Estill – Oklahoma UPOAA](https://hallestill.com/news-insights/what-to-expect-from-the-new-uniform-power-of-attorney-actnbsp) · [Vermont Act 60 summary](https://legislature.vermont.gov/Documents/2024/Docs/ACTS/ACT060/ACT060%20Act%20Summary.pdf) · [Massachusetts H.1523 (193rd)](https://malegislature.gov/Bills/193/H1523) · [Ezel – Power of attorney requirements by state](https://ezel.ai/surveys/power-of-attorney-requirements)

## **24\. USPS PS Form 3801 Standing Delivery Order**

**A. Title:** PS Form 3801, *Standing Delivery Order* (September 2016, PSN 7530-02-000-9048); PS Form 3801-A, *Agreement by a Hotel, Apartment House, or the Like to Assume Responsibility for Registered Mail Delivered to an Authorized Representative* (July 1998). Governed by DMM 508.1.1.5 (identification), 1.1.7 (accountable mail), 1.1.8 (Restricted Delivery) and 1.4 (delivery to agents); PS Form 3849 (*Delivery Notice/Reminder/Receipt*) is the one-off alternative.

**B. Blurb:** A standing list of named agents, with ID checked at each pickup.

### **C. Background**

**1\. Who it comes from:** Issued by the U.S. Postal Service. The addressee (an individual or firm) fills it in and files it with the local Post Office. A postal clerk verifies each agent's ID and initials the form at first pickup.

**2\. Key lesson for AI-agent authorization:** **Separate the standing authorization for a class of transactions from authentication at execution time: the principal pre-registers a list of named agents and the mail classes they may sign for, and the counterparty still checks a photo ID every time it releases an item.** In agent terms, Form 3801 is a long-lived grant (receive:accountable\_mail, optional receive:restricted) bound to named agent identities, while the release step is a per-use credential check by the relying party. Restricted Delivery is an opt-in elevated scope that must be stated explicitly. Revocation is written and prospective, and a new order revokes all earlier ones.

**3\. The instrument:**

•      **Scenario.** A business, office, executive or household regularly receives signature-required mail and wants named people to sign for it without a fresh note each time.  
•      **Parties.** Addressee (principal, signing as individual or firm officer); authorized agents (named list); the Post Office (counterparty, which holds the order on file).  
•      **Powers.** Receive "all mail" addressed to or in care of the principal, expressly including Adult Signature Required, Certified, Insured, C.O.D., Priority Mail Express, Signature Confirmation and unrestricted Registered Mail.  
•      **Elevated scope.** Per-agent checkboxes extend authority to Restricted Delivery and Adult Signature Restricted Delivery. The DMM requires the notation "this authorization is extended to include restricted delivery" when done by letter.  
•      **Per-use authentication.** Agents must present valid government- or employer-issued photo ID before release. Clerks request the agent's signature if missing, inspect the ID, tick "ID Verified," initial and date. DMM 508.1.1.5 lets employees withhold mail pending primary ID.  
•      **Duration.** Until cancelled in writing; USPS describes a standing order on file as permanent authorization unless revoked.  
•      **Supersession.** A dated footnote says USPS "will revoke all orders submitted before this date": each new form replaces the prior list.  
•      **Liability shift.** The principal assumes all responsibility for loss, rifling or damage after delivery to an agent.

**4\. Context:** Delivery to agents is old common practice codified in DMM 508.1.4.1: mail "may be delivered to an employee, to a competent member of the addressee's family, or to any person authorized to represent the addressee." DMM 508.1.1.8 adds that mail for famous personalities and executives of large organizations is normally delivered to an authorized agent. Government officials and military commanders have parallel designations, such as DD Form 285 for unit mail clerks.

Form 3801 was revised in June 2011 for Adult Signature services (Postal Bulletin 22313\) and again in September 2016\. USPS also published an "Automated PS Form 3801" bulk-upload spec in 2019, but its robots policy blocked fetching it, so details are unverified. No usage statistics were found. Failure mode: a stale list — departed employees remain authorized until the principal files a replacement.

**5\. Stability and variants:** Very stable. Variants: a letter to the postmaster with the required restricted-delivery notation; one-off authorization on the back of PS Form 3849, or plain signed paper; the online Redelivery "Customer Pickup" naming option; PO Box co-users listed on PS Form 1093, each presenting two IDs (DMM 508.4.2.1); and "Signature on File" for some accountable mail at competitive PO Box locations (DMM 508.4.5.4).

PS Form 3801-A is the institutional sister. A hotel or apartment house owner (by corporate resolution, if a corporation) designates representatives, accepts financial responsibility for registered mail, and must report changes in ownership, management or representatives at once; either side may end it on written notice. Item 8 (PS Form 1583\) covers a full agent-of-address relationship; Form 3801 delegates only receipt.

### **C2. Drill-down: the operative clause**

"As the above-named individual or firm, I authorize the agent(s) named below to receive all mail addressed to or in care of the above-named individual or firm, including these services; Adult Signature Required, Certified, Insured, C.O.D., Priority Mail Express®, Signature Confirmation™, and unrestricted Registered Mail™. … I understand that this Standing Delivery Order will remain in effect until I cancel it in writing."

— PS Form 3801, September 2016

"An addressee who regularly receives restricted delivery mail may authorize an agent on Form 3801 or by letter to the Postmaster and must include the notation 'this authorization is extended to include restricted delivery (or Adult Signature Restricted Delivery) mail'."

— DMM 508.1.1.8, item 6

The grantor is the addressee or a firm officer who signs with title. The grantees are the agents listed by printed name, each with a specimen signature. The verb is "authorize … to receive." The object is all mail, with the listed accountable services spelled out. Scope limiters: restricted classes are excluded unless ticked per agent; Restricted Delivery mail must name a natural person as addressee, and Adult Signature Restricted Delivery requires an agent aged 21 or over. Not delegated: anything beyond receipt, such as changing address, opening a box or filing claims. The Post Office is bound because the order is on file, but it still releases each piece only after photo ID and signature on the delivery record.

### **D. Outline of the full instrument**

1\.     Principal block — name and address of individual or firm, date submitted, telephone.  
2\.     Authorization statement — scope of mail classes; until-cancelled duration; liability assumption.  
3\.     Principal signature with title.  
4\.     Agent table — one row per agent:  
a.     Printed name.  
b.     Restricted Delivery and Adult Signature Restricted Delivery checkboxes.  
c.      Agent specimen signature.  
d.     USPS verification — "ID Verified," clerk initials, date.  
5\.     Note on photo ID at every release.  
6\.     Footnote — this order revokes all earlier orders.  
7\.     Customer instructions and USPS instructions.

The principal defines scope and the agent list once. The USPS columns record first-use verification. The ID note and DMM 508.1.1.5 make authentication repeat at every pickup.

### **E. Insights and observations**

•      **Grant-level plus use-level controls.** The standing order says who may act; the ID check proves the person present is that agent. Agent platforms should not let a stored grant replace runtime authentication of the actor.  
•      **Specimen signatures as enrollment.** Capturing each agent's signature on the form, verified at first pickup, is enrollment of a credential to compare later.  
•      **Whole-list replacement as revocation.** "Revoke all orders submitted before this date" is atomic list replacement. It avoids dangling grants but depends on the principal remembering to refile. No USPS rule requiring periodic renewal was found, though local offices may ask for updates.  
•      **Explicit elevation for sensitive classes.** Restricted Delivery exists so senders can demand the named person. The addressee can still delegate it, but only by a specific, written, per-agent opt-in — a pattern that suits high-risk agent scopes such as payments or legal notices.  
•      **Carrier vs. counter asymmetry.** Per USPS FAQ, carriers at the door need not verify that the person signing is truly the authorized agent, but at a Post Office the agent must show ID. Assurance levels differ by channel, and agent systems should log which channel authenticated an action.  
•      **Joint principals.** Mail addressed jointly requires all addressees or their agents to be present (DMM 508.1.1.8 item 7\) — a multi-party quorum rule.  
•      **Liability transfer.** The principal accepts all post-delivery loss. A clear liability-handoff point at the moment the agent takes custody is useful in agent-commerce terms of service.

**Sources:** [PS Form 3801, Standing Delivery Order (Sept. 2016\)](https://about.usps.com/forms/ps3801.pdf) · [PS Form 3801-A (July 1998\)](https://about.usps.com/forms/ps3801a.pdf) · [DMM 508 Recipient Services](https://pe.usps.com/text/dmm300/508.htm) · [DMM 503 Extra Services](https://pe.usps.com/text/dmm300/503.htm) · [DMM Forms Glossary](https://pe.usps.com/text/dmm300/Forms_Glossary.htm) · [USPS FAQ: Authorizing Someone to Accept Your Redelivery](https://faq.usps.com/articles/Knowledge/Authorizing-Someone-to-Accept-Your-Redelivery) · [Postal Bulletin 22313 forms update (June 2011\)](https://about.usps.com/postal-bulletin/2011/pb22313/html/updt_006.htm)

## **25\. Insurance Agent/Broker of Record (AOR/BOR) letters**

**A. Title:** *Broker of Record Letter* / *Agent of Record Letter* (generic; no official form number). Examples: CDPHP *Broker of Record (BOR) Letter Template* (undated); PMC Insurance Group BOR template waiving the rescinder period (2016); State Compensation Insurance Fund (California) BOR process, which accepts ACORD 36 as an alternative. Health-marketplace counterpart: consumer consent and application-review documentation under 45 CFR 155.220(j)(2)(ii)–(iii), with CMS's Model Consent Form.

**B. Blurb:** One broker per account; the newest dated letter wins after a short contest window.

### **C. Background**

**1\. Who it comes from:** No single author. Carriers (CDPHP, State Fund), brokers and wholesalers publish templates. The insured (the policyholder or group employer) signs the filled letter on its own letterhead. For ACA Marketplace coverage, CMS sets federal consent rules that agents and brokers must follow.

**2\. Key lesson for AI-agent authorization:** **Make some agency exclusive: one agent of record per account and line, a dated effective time, explicit supersession of the incumbent, and a short window in which the incumbent is told and the principal can confirm or reverse.** In agent terms, a BOR is a mutually exclusive grant: issuing a new one revokes the old one at a defined time. The counterparty (the carrier) notifies the displaced agent and holds a rescission window, typically 5–10 days, before switching. That two-phase handoff blocks both duelling agents and silent takeover.

**3\. The instrument:**

•      **Scenario.** A business or employer group changes broker mid-term or before renewal, or a consumer changes the agent on a Marketplace plan.  
•      **Parties.** Insured (principal); new broker (agent); incumbent broker (displaced agent); carrier (counterparty that records the agent, routes service and pays commission).  
•      **Powers.** Act as the insured's sole representative with the carrier for named coverage; receive policy, rating, loss and renewal information; negotiate and market the account; draw commission.  
•      **Form.** On the insured's letterhead; addressed to the carrier; identifies the group or policy numbers; names the new agency and, if replacing, the former one; signed and dated by an officer with authority (State Fund requires an active brokerage email and the State Fund access number).  
•      **Effective time.** Varies by carrier. CDPHP's template says the change is immediate. State Fund treats the BOR as effective on the date it receives the letter, once the incumbent's five business days pass with no rescission.  
•      **Contest window.** State Fund notifies the incumbent, then decides the BOR five business days later. Hylant describes 5–10 days in commercial lines generally. Some templates ask the carrier to waive the five-day "rescinder" period.  
•      **Duration and revocation.** Until a newer written letter. CDPHP's notes say a contrary notice applies only from future renewals.  
•      **Commission.** CDPHP's letter acknowledges the new broker is paid from the group's monthly premium. State Fund keeps mid-term commission on the in-force term with the original BOR.

**4\. Context:** BOR letters are routine in commercial P\&C, workers' comp and group benefits. Carriers will not take quote requests on the same account from two brokers, so the BOR also controls market access. In the individual ACA market, the "AOR" is the agent's National Producer Number (NPN) on the enrollment. Commissions follow the NPN, which motivates fraud.

CMS received 90,863 complaints of unauthorized plan switches and 183,553 of unauthorized enrollments from January to August 2024, and suspended 850 agents and brokers from June to October 2024\. From July 19, 2024 it blocked agents not already on an enrollment from changing it without a three-way call with the consumer and the Marketplace call center. A December 2025 GAO preliminary report found the three-way call identity checks weak, and CMS told GAO all 850 suspended agents were reinstated (Governing). In 2026 CMS cancelled about 315,000 plan-year-2026 policies (August 31\) and imposed a moratorium on new FFM agent and broker registrations from September 22, 2026 (Morgan Lewis).

**5\. Stability and variants:** The commercial BOR is a stable custom, not a regulated form, with carrier-specific variants (ACORD 36, carriers' own templates, wholesale-plus-retail BORs such as PMC's). The Marketplace variant is a regulated consent record. The 2024 Payment Notice required documented consent and documented application review. The 2026 Payment Notice (final January 2025\) added a model consent form with audio scripts and immediate-suspension powers. The 2027 Payment Notice (issued May 2026, effective July 20, 2026, per a broker-tech summary) requires an HHS-created consent form for plan years from January 1, 2028\. A September 23, 2026 interim final rule (91 FR 60317\) further amended § 155.220.

### **C2. Drill-down: the operative clause**

Federal: an agent, broker or web-broker must "obtain and document the receipt of consent of the consumer or their authorized representative … prior to assisting with or facilitating enrollment through a Federally-facilitated Exchange." The documentation "must include a description of the scope, purpose, and duration of the consent," the consumer's name, the date, the agent's name, and "a process through which the consumer or their authorized representative may rescind the consent." It must be kept "for a minimum of 10 years."

— 45 CFR 155.220(j)(2)(iii) (eCFR, current as of October 2026\)

Commercial (paraphrase): the group tells the carrier it has named a new agency as its only representative for its coverage. If replacing a broker, it says the new agency acts in place of the prior one. It lets the carrier release account information to the new broker and accepts that commission comes from premium. Short quote: the new agency is the group's "sole insurance representative."

— CDPHP Broker of Record (BOR) Letter Template

In the commercial letter the grantor is the insured, acting through an authorized officer. The grantee is one named agency. The verbs are "appoint" and "authorize … in place of," which supersede the incumbent. The object is the insured's coverage with that carrier. Scope limiters are the carrier, group or policy numbers, and sometimes the line of coverage. Not delegated: binding new coverage without the insured, or altering in-force terms. The carrier is bound by custom and contract to recognize the latest valid letter after its window.

In the federal rule, the consumer's documented consent defines scope and duration. The agent must keep it as audit evidence, and from plan year 2028 a typed signature or checkbox will not count.

### **D. Outline of the full instrument**

1\.     Letterhead and date — proves the principal's origin; dates the handoff.  
2\.     Addressee — carrier underwriting or broker services.  
3\.     Account identifiers — insured name, group ID or policy numbers, lines, policy periods.  
4\.     Appointment clause — new agency named as exclusive broker of record.  
5\.     Supersession clause — rescinds the prior broker (optional, named).  
6\.     Information release — carrier may share contracts, rates, loss data.  
7\.     Commission acknowledgment — paid from premium or per carrier rules.  
8\.     Timing — effective date, or request to waive the rescission period.  
9\.     Signature — authorized officer, printed name, title.  
10\.  Carrier-side process (not on the letter) — notify incumbent; hold 5 business days or similar; record new BOR.

Parts 3–5 define the exclusive scope and the displacement. Part 10, run by the counterparty, turns the letter into a time-stamped, contestable handoff.

### **E. Insights and observations**

•      **The counterparty runs the state machine.** The letter is a request. The carrier notifies the incumbent, waits, then flips the record. Agent ecosystems need a relying-party-side registry of "current agent" with transition rules, not just tokens held by agents.  
•      **Contest windows protect principals too.** Unauthorized ACA plan switches show what happens when the agent of record can be changed by the agent alone. CMS's 2024 fix (consumer on a three-way call before a new agent can act) is a step-up confirmation by the principal at handoff.  
•      **Waivers move risk.** Templates asking carriers to waive the rescinder period trade incumbent protection for speed; State Fund says a policyholder's waiver does not remove the period. Agent frameworks should decide who may waive a cooling-off window.  
•      **Consent must be structured and retained.** CMS lists required elements (scope, purpose, duration, rescission method, date, both names), acceptable capture methods (signature, consumer email, recorded audio), and 10-year retention. This is close to a spec for an agent-consent receipt.  
•      **Per-agent identity, not per-agency.** CMS FAQs say an NPN change needs fresh consent unless agency-wide consent covers it. Agent tokens should name the acting identity, not only the vendor.  
•      **Commission as the attack incentive.** Whoever holds the record gets paid. Where an agent is paid per transaction it controls, expect hijacking attempts and design the handoff accordingly.  
•      **Unverified.** The AmWINS sample BOR letter in the source list could not be fetched; CDPHP, PMC and Complete Markets templates were used instead. CMS's 2027 Payment Notice details come from a vendor summary, not the Federal Register.

**Sources:** [CDPHP broker forms page](https://www.cdphp.com/brokers/broker-resources/a-z-forms) · [CDPHP BOR Letter Template](https://www.cdphp.com/-/media/files/brokers/samplebor2.pdf) · [State Fund BOR process](https://www.statefundca.com/broker/broker-of-record-process/) · [Hylant: Broker of Record Letter](https://www.hylant.com/2022/10/broker-of-record-letter/) · [PMC Insurance BOR template (waive rescinder)](https://pmcinsurance.com/wp-content/uploads/2016/01/BOR-Template-waive-rescinder-period.pdf) · [Complete Markets sample BOR letter](https://completemarkets.com/article/article-post/1309/sample-broker-of-record-letter/) · [45 CFR 155.220 (eCFR)](https://www.ecfr.gov/current/title-45/subtitle-A/subchapter-B/part-155/subpart-C/section-155.220) · [CMS FAQ: Consumer Consent and Application Review](https://cms.gov/files/document/frequently-asked-questions-consumer-consent-application-review-requirements.pdf) · [CMS press release, Oct. 17, 2024](https://www.cms.gov/newsroom/press-releases/cms-update-actions-prevent-unauthorized-agent-broker-marketplace-activity) · [Morgan Lewis on 2026 cancellations and moratorium](https://www.morganlewis.com/pubs/2026/09/cms-cancels-marketplace-enrollments-and-imposes-moratorium-on-new-aca-broker-registrations) · [Governing: ACA enrollment fraud persists (Dec. 2025\)](https://www.governing.com/despite-warnings-obamacare-enrollment-fraud-persists) · [Quotit on 2027 Payment Notice](https://hub.quotit.com/blog/cms-2027-payment-notice-new-aca-marketing-rules-every-agent-needs-to-know) · [Rise Health on 2026 Payment Notice](https://www.risehealth.org/insights-articles/marketplace-final-rule-cracks-down-on-agent-broker-oversight/)

