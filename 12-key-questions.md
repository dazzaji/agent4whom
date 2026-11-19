# Key Questions for Human and Machine Readable Delegations of Authority to AI Agent Systems

The below questions are primarily derived from Version [0.3.4](https://github.com/dazzaji/agent4whom/commit/24f01911dbba87d225d4dc4c648d9fe01319a57a) of the [25 Instruments](https://github.com/dazzaji/agent4whom/blob/main/25-legal-instruments.md) review. 

**Who**

1. **Who is granting, and by what right?**
   - In the standard instrument: grantor identity, capacity, and the basis of authority over the account, asset or entity.
   - In the protocol: verifiable proof of control over the resource, beyond authentication.

2. **Who is the agent, and who answers for it?**
   - In the standard instrument: the named agent, its credential, and the accountable person or organization.
   - In the protocol: credential status check, operator registration, and a link from the acting instance to the named agent.

3. **How was the grant made, and with what assurance?**
   - In the standard instrument: required elements, signatures, a standalone consent, and an assurance level.
   - In the protocol: schema validation, and a consent object that can be hashed and verified on its own.

**What**

4. **What may it do, and within what limits?**
   - In the standard instrument: typed scope (action, object, bounds), with reading, acting and moving money kept separate.
   - In the protocol: structured scopes, no wildcards.

5. **What is off by default, and what can never be granted?**
   - In the standard instrument: explicit opt-ins, starting with passing authority on, and a list of powers no grant can reach.
   - In the protocol: default-deny, step-up for named powers, and a delegation chain the next party can read.

6. **For what purpose?**
   - In the standard instrument: purpose stated or chosen from a closed list.
   - In the protocol: a purpose code that travels with the request and the data.

**When**

7. **When does it start and end?**
   - In the standard instrument: effective date, plus an expiry date, an ending event, or single use.
   - In the protocol: expiry and freshness enforcement.

8. **How is it changed, revoked or replaced, and who must be told?**
   - In the standard instrument: revocation method, replacement rule, and whether there is one agent or several.
   - In the protocol: revocation pushed to relying parties, a status query for which grant governs now, and handoff rules.

**In use**

9. **What may the other side rely on, and must they honor it?**
   - In the standard instrument: what a relying party may check, and what protects it when it relies.
   - In the protocol: validation, authentication at each use, checks tiered by action, and structured refusal reasons.

10. **What comes back to the principal, by a channel the agent cannot capture?**
    - In the standard instrument: what the principal is told after, told before, or asked first.
    - In the protocol: a principal channel the agent cannot edit, and a stop the principal can use without the agent.

11. **What record exists, who holds it, and who can see it?**
    - In the standard instrument: retention of the grant and of each use, and who may inspect.
    - In the protocol: an append-only log, visible to the principal, linking each action to its grant.

12. **When it goes wrong, who bears the loss and how is it put right?**
    - In the standard instrument: liability terms and the way to challenge an action.
    - In the protocol: carry the challenge and its outcome, and supply the evidence.
