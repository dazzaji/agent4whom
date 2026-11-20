# Recent updates

## Agent identity, delegated authority, and consumer choice

Dazza Greenwood

Relevant to IAB Open, IETF 127 Talk · November 20, 2026

Recent relevat developments, connecting agents to principals, mandates, human approvals, and evidence.

---

# Singapore proposes “Know Your Agent” for finance

**November 19, 2026 · MAS announcement of protocol development under SAFR**

Singapore’s central bank will facilitate a protocol for trusted information exchange between customer agents and financial institutions.

- Establish which agent is acting and which customer or organization it represents.
- Convey its delegated authority, operating mandate, and assurances about its provenance and reliability.
- Define permitted actions, limits, and conditions; scale safeguards with the agent’s discretion and potential impact.
- Give financial institutions a basis for setting access terms and establishing dedicated, secure channels for agents.

**The delegation question** — How can a bank check that this instruction falls within the customer’s current mandate?

[MAS keynote, paragraphs 46–58](https://www.mas.gov.sg/news/speeches/2026/keynote-address-by-md-at-the-singapore-fintech-festival-2026)

---

# California proposes signed agent traffic for incident attribution

**Report dated November 16; released November 18, 2026 · Recommendations for further legislation**

GovOps’ *AI Safety in 2026 and Beyond* considers how responders could identify the agents behind a harmful incident.

- Developers could sign agents’ web requests using Web Bot Auth or similar methods.
- The report acknowledges that escaped or self-hosted agents may leave their traffic unsigned.
- For unsigned traffic, the state or licensed verifiers could correlate network addresses and timestamps with provider logs.
- State detection could use decoy servers and canary credentials to discover uncontrolled agents.
- Web Bot Auth authenticates a request through a signing key. Establishing the represented principal and delegated authority requires additional evidence.

**The delegation question** — How do we connect a signed request to the grant, its limits, and the party answerable for its use?

[GovOps report, “Incident Monitoring”](https://www.govops.ca.gov/wp-content/uploads/sites/11/2026/11/FINAL_-AI-Safety-in-2026-and-Beyond-v2.pdf#page=68) · [Release announcement](https://www.gov.ca.gov/2026/11/18/governor-newsoms-nation-leading-ai-safety-framework-is-getting-even-stronger-as-california-releases-next-steps-on-mandatory-safety-standards-and-oversight/) · [Web Bot Auth draft, §4.6](https://datatracker.ietf.org/doc/html/draft-ietf-webbotauth-httpsig-protocol-01#section-4.6)

---

# IETF 127 hears an OAuth-compatible approval flow

**November 18, 2026 · Rosenberg/White presentation; individual Internet-Draft**

Jonathan Rosenberg and Pat White presented a proposed OAuth-compatible flow for agents whose required permissions emerge as work proceeds.

- The resource server decides which operations trigger an approval flow.
- It supplies the scope challenge and the human-readable permission descriptions used for approval.
- Cryptographic validation protects the requested scopes; the approval interface uses trusted descriptions rather than agent-authored wording.
- Approval can cover one action, a short session, or continuing access, through a human or an automated decision.

**The delegation question** — Can the approved wording, permission set, and resulting action remain bound together as evidence?

[IETF 127 presentation](https://datatracker.ietf.org/meeting/127/materials/slides-127-oauth-sessa-oauth-compatible-ai-agent-authentication-01) · [draft-rosenberg-oauth-aauth-02](https://datatracker.ietf.org/doc/html/draft-rosenberg-oauth-aauth-02)

---

# Five fresh drafts on authority and evidence

**Posted or revised during IETF 127 · Individual proposals under discussion**

These drafts address different parts of the chain from a principal’s authorization to a verifiable account of what happened.

- **Accountable principal references** — Six testable properties for connecting a request to an accountable principal while controlling identification and correlation. [draft-molas-agent-principal-refs-00](https://datatracker.ietf.org/doc/draft-molas-agent-principal-refs/)
- **Open Action Record** — Evidence of authorization validity at commitment, approval of the exact action, and the resulting change to the system of record. [draft-malhotra-scitt-oar-00](https://datatracker.ietf.org/doc/draft-malhotra-scitt-oar/)
- **Delegation traceability** — Hash-chained registries and per-action attestations across user, agent, subagent, and tool relationships. [draft-cosme-audit-agent-traceability-00](https://datatracker.ietf.org/doc/draft-cosme-audit-agent-traceability/)
- **Transactional Access Tokens** — Short-lived, single-audience tokens carrying a transaction identifier and authorization context. [draft-tulshi-oauth-transactional-access-tokens-01](https://datatracker.ietf.org/doc/draft-tulshi-oauth-transactional-access-tokens/)
- **MyTerms** — Human- and machine-readable privacy agreements that individuals propose and both parties can sign and retain. [draft-curtis-myterms-02](https://datatracker.ietf.org/doc/draft-curtis-myterms/)

---

# OpenID Foundation examines agents on developers’ laptops

**November 18, 2026 · Analysis by Atul Tulshibagwale**

His OpenID Foundation post identifies the developer workstation as an especially difficult place to govern an agent’s authority.

- Coding agents inherit access to shells, repositories, cloud sessions, credentials, and local files.
- That ambient authority can greatly exceed the authority needed for the task the person assigned.
- Local MCP calls over standard input/output can bypass network-only monitoring; provider-hosted connectors execute outside endpoint visibility.
- Effective controls need to account for both the local execution path and remote services acting for the user.

**The delegation question** — What authority did the person grant for this task, and what limits actually constrain its execution?

[OpenID Foundation, “Securing the AI powered developer — Part 1”](https://openid.net/securing-the-ai-powered-developer-part-1/)

---

# Vendors connect human supervision, mandates, and runtime controls

**November 17–19, 2026 · Vendor announcements**

The companies describe products that connect agents to human supervisors, customer mandates, and controls over execution.

- **HYPR AgentPass** — Named human supervisors, gateway-controlled credentials, and passkey approval for high-risk actions. [HYPR launch, November 18](https://www.hypr.com/press-releases/hypr-launches-agentpass-to-assign-every-ai-agent-to-an-accountable-human)
- **Incode Know Your Agent** — Human identity verification, a mandate specifying tasks, spending and duration, and records of actions checked against that mandate. [Incode launch, November 17](https://www.incode.com/newsroom/incode-launches-incode-know-your-agent-to-anchor-ai-agent-trust-in-verified-human-identity/)
- **Metano** — Discovery of agents and their components, session-level analysis of identity, tools and actions, and enforcement of runtime guardrails. [Metano launch, November 19](https://metano.ai/resources/metano-emerges-from-stealth)

**The delegation question** — Which legal person accepts which duties, and what evidence shows that the particular action was authorized?

---

# EU Digital Fairness Act would let consumers set agent autonomy

**European Commission proposal, November 11, 2026 · Articles 26–27**

The proposal would let consumers choose and adjust how automated systems conclude and perform contracts on their behalf. Article 26 excludes financial services.

- At first use, expressly choose confirmation for every contract, selected contracts under consumer-set criteria, or no advance confirmation. Choices and parameters remain adjustable.
- Payment to the system’s provider for proposing a contract, or its conflict of interest with the trader, would trigger disclosure and confirmation of that contract regardless of the general setting.
- Choices and completed contracts would receive durable confirmations; contract confirmations must use plain, intelligible language.
- European Business Wallets could identify an automated system and the party it represents.
- Article 27 permits machine-readable pre-contract information for fully automated contracting, while preserving the human-readable confirmation afterward.

**The delegation question** — How do agreed limits, changes, and conflict-triggered approvals become enforceable and provable across systems?

[Official proposal, Articles 26–27](https://publications.europa.eu/resource/cellar/ce41d25c-de86-11f1-ba80-01aa75ed71a1.0001.03/DOC_1) · [Commission overview](https://commission.europa.eu/law/law-topic/consumer-protection-law/digital-fairness-act_en)
