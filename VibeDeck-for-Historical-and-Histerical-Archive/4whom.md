# On Behalf Of Whom?

*IAB OPEN · IETF 127 · INVITED LOCAL SPEAKER*

What the Law Asks of Agent Protocols

Dazza Greenwood  
law.MIT.edu · CIVICS.com · Stanford CodeX

__________

# Agents already act for people

*WHERE WE ARE*

They book hotels, buy goods, and read health and bank records.

**378** named integrations indexed.  
244 are live.

In 119 of the live ones, the agent can place an order, move money or change an account.

AI agent integrations index, as of November 9, 2026

___
NINTH CIRCUIT · AUGUST 4, 2026  
**Amazon.com Services v. Perplexity AI**

“At the core of the dispute was Perplexity’s decision not to use a ‘user-agent string’.”

Held, on this record: “It is the user who ‘accesses’ Amazon’s computers, with the help of the Assistant”. The injunction was vacated.

Left open: whether “in other contexts, including tort claims, Perplexity can avoid liability for the Assistant’s actions.”
___

__________

# What the IETF is building

*WHERE THIS COMMUNITY IS*

DISCOVERY  
**DAWN**  
Find an agent: how to reach it and what protocol it speaks.  
Working group

DIALOG  
**agentproto**  
Keep one dialog together across hops and trust boundaries.  
Working group

IDENTITY AND AUTHORIZATION  
**OAuth and WIMSE**  
Which software is calling, and what its token lets it do.  
Working groups

AUDIT  
**AUDIT (proposed)**  
Records of what was delegated and what happened.  
BoF this week; not chartered

*The open question: who answers for what the agent does?*

*[TO ADD: outcomes of the AUDIT BoF and the OAuth and WIMSE sessions, if Dhruv or Nick share them]*

__________

# Three bodies of evidence

*THE EVIDENCE*

**25 everyday legal authorization instruments**  
Powers of attorney, IRS and immigration forms, HIPAA releases, ACH debits, board resolutions, proxies and more.

**34 agent specifications**  
Commerce mandates, agent access protocols, OAuth and IETF drafts, credentials and policy engines. Read November 6, 2026.

**378 agent integrations**  
244 live. Retail and travel lead. Health and banking are mostly read-only. As of November 9, 2026.

**Method.** For each legal instrument: the operative words, the legal function, and what changes when the actor is software. Then a crosswalk to the specifications, in both directions.

Legal anchors: Restatement (Third) of Agency (2006) · Uniform Electronic Transactions Act (1999) · DeMott, “When Agentic AI Met the Common Law of Agency” (forthcoming 2026)

__________

# “The AI agent is the agent”

*ASSUMPTION 1*

IN LAW  
An agent is a person who consents to act for a principal, under the principal’s control.  
Restatement (Third) of Agency §1.01. An AI tool “lacks the capacity to be an ‘agent’” (DeMott, 2026).

IN THE 25 INSTRUMENTS  
Authority runs to a named person or organization: a representative, a company, an attorney-in-fact.  
The words are short. “I authorize Company A to debit my account.”

FOR A PROTOCOL  
Name the principal. Name the legal person behind the agent and the seat it takes: agent, vendor or attestor.  
Record that it accepted.

*If nobody takes the agent’s seat, the tool is the user’s own instrument, and the appearance of authority still has legal effect.*

__________

# “A scope is an authorization”

*ASSUMPTION 2*

A scope permits a call. A legal authorization says who, for whom, to do what, within which limits, and for how long.

*Scope “is not sufficient to specify fine-grained authorization requirements”.*  
RFC 9396, OAuth 2.0 Rich Authorization Requests, Introduction

IN 34 SPECIFICATIONS  
Powers, limits, agent keys and expiry mostly have a field.  
Usually missing: the legally responsible party, the person’s instruction for this task, and terms on what the recipient may do with the data.  
Survey read November 6, 2026

**Five kinds of authorization, not one:** delegated authority · information access · transaction-specific consent · organizational authority · recognition of authority.

“Permission to obtain information is not permission to make decisions.”

__________

# “Liability is out of scope”

*ASSUMPTION 3*

Accountability is not liability.  
**Accountability:** someone has to answer for the act.  
**Liability:** what the law concludes once the facts are in.  
A protocol does not decide liability. It decides which facts exist when someone has to answer.

**A header**  
The Ninth Circuit dispute began with a user-agent string that was not sent.

**A record**  
An audit record becomes evidence of who authorized what, and when.

**A silence**  
MCP, UCP and ACP are the protocols most often named in the index. None identifies the legal person that answers for the agent.

__________

# The duty of loyalty

*BEYOND PERMISSION*

*“An agent has a fiduciary duty to act loyally for the principal’s benefit in all matters connected with the agency relationship.”*  
Restatement (Third) of Agency §8.01

No material benefit from a third party in the principal’s transactions (§8.02), unless the principal consents after disclosure of all material facts (§8.06).

WHY IT MATTERS NOW  
The browser had no stake in which shop you chose. The new agents recommend, and the shop can pay them.  
You cannot sign loyalty into a token. A protocol can carry the role that creates the duty, and a disclosure of who is paying.  
Loyalty can also be measured: loyalagents.org (Stanford)

*[TO ADD: one or two results from the Stanford loyalty evaluations]*

__________

# Legal facts a protocol should carry

*WHAT TO CARRY*

1. **Who is granting?**  
   The principal. For an organization, who signed and under what authority.

2. **Who stands behind the agent?**  
   A named legal person, the seat it takes, and its acceptance.

3. **What may it do?**  
   Acts, on what, with whom. To view is not to act; to negotiate is not to conclude.

4. **Within what limits?**  
   Amounts, counterparties and purpose, as the other side is told them.

5. **What comes back to the human?**  
   The decisions reserved for the person.

6. **When does it start and end?**  
   The term, and revocation by notice: who was told, and when.

7. **What may the other side rely on?**  
   The principal’s own statement, not the agent’s claim about itself.

8. **What record exists?**  
   Grant, instruction, action and receipt, each tied to the one before.

Each one stated in the person’s own words, and in a form a machine can check.

__________

# What this means for protocol designers

*WHAT TO CARRY*

**Discovery**  
**DAWN**  
Let a client learn who stands behind an agent, or where to ask. A pointer, not an identity system.

**Dialog**  
**agentproto**  
Carry a reference to the grant across hops, and keep one chain of authority for each side of a deal.

**Identity and authorization**  
**OAuth, WIMSE**  
Bind the token to the principal’s own statement of authority: the grant, the appointee’s seat and its acceptance.

**Audit**  
**AUDIT (proposed)**  
Record permission, approval and execution as separate facts, with the time each relying party had notice.

*The goal: predictable legal results.*

Offered for discussion. None of this asks a working group to decide liability.

__________

# Ideas for a technical specification of a human grant of authority to an AI agent

*DEEP DIVE*

Goals, issues and options for cross-domain (legal and technical) expressions of intent and authorization

Mission · Intent · Mandate: where the person’s own words sit in today’s drafts

__________

# What the expression has to do

*DEEP DIVE · GOALS*

**Be the person’s own statement**  
In law, authority is created by what the principal communicates, as the agent reasonably understands it. The words are the authority.

**Mean one thing to a person and a machine**  
One grant, readable by the human who gave it and checkable at the moment of action.

**Name the legal persons**  
Who grants, who stands behind the agent and in which seat, and that the appointee accepted.

**Tell the other side what it may rely on**  
The limits it is shown, and a status it can check.

**Leave a record that can answer later**  
Grant, instruction, action and receipt, with who knew what, and when.

__________

# A grant fits in a sentence

*DEEP DIVE · THE FACTS TO EXPRESS*

“Harbor Workshop, Inc., acting by its COO, appoints Northstar Purchasing LLC to place one order with Alder Supply for one Model R filter, at a total of no more than USD 400, before November 13. Northstar accepts.”

WHO GRANTS  
A company, by an officer with authority

TO WHOM  
A named legal person, which accepts

WHAT  
One order, one item, one merchant

LIMIT  
USD 400 in total

UNTIL  
A date, or earlier revocation

The 25 instruments say it just as briefly: “I authorize Company A to debit my account.” You can write seventy pages or five words. What you cannot write is nothing.

__________

# Where the person’s words sit: IETF drafts

*DEEP DIVE · CROSSWALK 1*

* **Draft:** Mission-Bound Authorization for OAuth 2.0 (McGuinness, -02)
  * **Unit:** Mission
  * **The person’s words:** `goal` and `task_bounds`: human-readable, shown to the Approver
  * **Who is accountable:** Approver: “the single accountable principal”
  * **Effect of the words:** They “carry no machine semantics”. The server “MUST NOT gate issuance” on them.

* **Draft:** OAuth 2.0 Bounded Work Authorization (Liu, McGuinness, -00)
  * **Unit:** The work
  * **The person’s words:** A description “in terms the approver can understand”
  * **Who is accountable:** Approver: “the single party accountable for the decision”
  * **Effect of the words:** It “does not itself restrict anything, and it has no portable meaning”.

* **Draft:** The Intent Token (Chen, Su, Liu, -00)
  * **Unit:** Intent
  * **The person’s words:** `intent` claim, “typically captured from the user’s natural language input”
  * **Who is accountable:** Not stated. The user is a recommended `sub` claim.
  * **Effect of the words:** The server interprets it. The token “is not the final access permission itself”.

* **Draft:** Verifiable Mandates for Agents (Hulea, -01)
  * **Unit:** Mandate
  * **The person’s words:** None yet. A human-readable rendering is an open issue.
  * **Who is accountable:** Principal: “natural or legal person”. An Operator is named.
  * **Effect of the words:** Structured limits only. The legal effect of a mandate is a non-goal.

Individual Internet-Drafts, not working group documents. Read November 14, 2026.

__________

# Where the person’s words sit: AAuth, AP2, AUDIT

*DEEP DIVE · CROSSWALK 2*

* **Work:** AAuth (Hardt, -11; moving to an OpenID Foundation working group)
  * **Unit:** Mission
  * **The person’s words:** `description`: a Markdown string, approved by the person through the Person Server
  * **Who is accountable:** Person: “the legal person” who “is accountable for the agent’s actions”
  * **Effect of the words:** “intentionally not a machine-evaluable policy language”. Bound by a digest.

* **Work:** AP2 v0.1 (September 2025)
  * **Unit:** Intent Mandate
  * **The person’s words:** `natural_language_description`, “generated by the shopping agent, and confirmed by the user”
  * **Who is accountable:** Signed by the user in “Human Not Present” scenarios
  * **Effect of the words:** “The goal is to have informed consent by the user.”

* **Work:** AP2 v0.2 (April 2026; donated to the FIDO Alliance)
  * **Unit:** Checkout and Payment Mandates, open or closed
  * **The person’s words:** None. Typed constraints only: merchants, items, amounts, budget, dates.
  * **Who is accountable:** Signed with a user key or the agent provider’s key
  * **Effect of the words:** “Any unknown Constraints MUST be treated as failing evaluation.”

* **Work:** AUDIT (proposed charter)
  * **Unit:** Audit record
  * **The person’s words:** “user intent declarations” are among the things to record
  * **Who is accountable:** Not defined here
  * **Effect of the words:** Authorization and delegation mechanisms are out of scope.

DAWN, agentproto and WIMSE carry no grant: they find the agent, correlate the dialog and identify the workload.

__________

# AP2 mandates: where the person’s words went

*DEEP DIVE · REFERENCE POINT*

SEPTEMBER 2025 · AP2 v0.1  
The Intent Mandate carried the person’s words: a natural-language description “generated by the shopping agent, and confirmed by the user”.  
Three mandates: Intent, Cart, Payment.

SEPTEMBER 2025 · MY READING  
A “Digital Power of Attorney” that answers “Who told the agent to do that?”  
It “must be backed by a formal legal agreement, a Letter of Authorization”.  
dazzagreenwood.com, September 17, 2025

APRIL 2026 · AP2 v0.2  
Two mandates, Checkout and Payment, each open or closed. Typed constraints. No natural-language field.  
Consent is taken on a Trusted Surface that “MUST be non-agentic”. The specification now sits with the FIDO Alliance.

**What maps cleanly:** open mandate = the standing grant · closed mandate = the act · signed Mandate Receipt = the other side’s record.  
**What still sits outside:** the person’s own words, who the person is, and the legal person behind the agent.

__________

# AAuth missions: closest to a standing work order

*DEEP DIVE · CLOSE-UP*

WHAT A MISSION ALREADY HAS  
A Markdown description plus structured fields, proposed by the agent and “approved by the PS and person”.  
One identity: a SHA-256 digest that later tokens carry.  
An accountable Person, described as “the legal person”.  
An ending the person controls: “Only the person’s acceptance terminates the mission.”

WHAT THE LAW WOULD STILL ASK  
Who is the legal person behind the agent? The Agent Provider is defined as “A server that manages agent identity”.  
Did the appointee accept? No acceptance step is described.  
Are the words the authority? Missions are “intentionally not a machine-evaluable policy language”.  
Is the Person known? A person token is “not a verified legal identity”.

draft-hardt-oauth-aauth-protocol-11 (September 25, 2026). An OpenID Foundation AAuth Working Group holds its first meeting on November 30, 2026.

__________

# Where the two domains pull apart

*DEEP DIVE · ISSUES*

1. **Words or rules**  
   In law the words the person communicated are the authority. In most drafts they are context, with no effect. If words and rules differ, which governs?

2. **Who wrote the words**  
   Often the agent drafts and the person confirms. Unclear wording can be read against the party that supplied it.

3. **Where the person approved**  
   A surface the agent cannot operate: AP2’s Trusted Surface “MUST be non-agentic”. A spoken prompt can be an authorizing act too.

4. **Intent is not authority**  
   An intent token records what the user wanted. It “is not the final access permission itself”. Purpose guides the reading; the grant sets the limit.

5. **Who the persons are**  
   An accountable approver appears in several drafts. The legal person behind the agent mostly does not.

6. **Endings and notice**  
   Revocation stops new tokens; issued ones can run until they expire. The law asks who had notice, and when.

__________

# Four ways to carry the human grant

*DEEP DIVE · OPTIONS*

OPTION A  
**Words as disclosure**  
Keep the prose beside the structure, with no effect on issuance.  
Seen in: Mission-Bound Authorization, Bounded Work.

OPTION B  
**Words as bound evidence**  
Bind the exact text the person approved into the grant by digest.  
Seen in: the AAuth mission digest.

OPTION C  
**A paired instrument**  
A readable grant and a machine record, each holding the other’s digest, with a rule for conflicts.  
Seen in: my working draft of an Agent Authority Instrument.

OPTION D  
**Shared grant facts**  
One small object any carrier can hold: principal, legal person and seat, acceptance, pointer to the text.  
Could be an RFC 9396 `authorization_details` type.

*A possible first step: agree on the facts before the format.*

For the room: Which group owns the human-readable statement? Should the words ever gate issuance? Who may be named as the legal person behind an agent?

__________

# Questions

*THANK YOU*

Who answers for what the agent does?

Dazza Greenwood  
dazzagreenwood.com · law.MIT.edu · CIVICS.com · Stanford CodeX

*[CONTACT LINE: confirm or replace]*