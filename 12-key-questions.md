# Key Questions for Human and Machine Readable Delegations of Authority to AI Agent Systems

The below questions are primarily derived from Version [0.4](https://github.com/dazzaji/agent4whom/commit/24f01911dbba87d225d4dc4c648d9fe01319a57a) of the [25 Instruments](https://github.com/dazzaji/agent4whom/blob/main/25-legal-instruments.md) review. 

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
   

___________________________________

Annotated concordance with the [25 delegation of authority legal instruments](https://github.com/dazzaji/agent4whom/blob/main/25-legal-instruments.md)

### Who

**1. Who is granting, and by what right?**
A signature shows who signed. It does not show that the signer controls the account, asset or entity. (Anatomy 1.)
- **Proof of ownership before delegating:** item 12 (chain of title, 37 CFR 3.73(c); trademark POA signed by the owner or someone with authority to bind); item 9 (authority reaches only the collateral the signed agreement describes).
- **Signing for an entity:** item 14 (board resolution plus incumbency certificate); item 4 (authorized officer, line 7); item 16 (officers known to CBP, § 141.38); item 18 (signer declares under penalty of perjury that they can bind the customer); item 15 (entity sellers prove signing authority within three days); item 25 (officer with authority); item 24 (individual or firm officer).
- **Signing for another person:** item 2 (personal representative must state the authority); item 3 (parent or eligible student); item 6 (SSA-89: number holder, parent or guardian).
- **The true principal, dealt with directly:** item 17 (listed account owner, not a reseller); item 16 (§ 111.36(c)(3)); item 15 (impostor-seller advisory); item 22 (record-date holdings).
- **More than one principal:** item 12 (all joint owners sign); item 24 (joint addressees).
- **When the principal changes:** item 12 (assignment does not revoke); item 16 (partnership POAs last two years).

**2. Who is the agent, and who answers for it?**
An AI agent is not a legal person. The instruments name the actor and place accountability on a licensed or registered party. (Anatomy 2.)
- **Credential inside the grant:** item 5 (bar number and no-discipline attestation); item 4 (Part II declaration, CAF number); item 6 (Section 5 attestations); item 19 (license, HUD number, tax ID, signed certification); item 12 (registration numbers, bar attestations).
- **Registered or licensed operator:** item 8 (Form 1583-A, quarterly certification); item 16 (licensed broker, 19 U.S.C. § 1641); item 1 (business agents registered with the Secretary of State); item 7 (accreditation database; unregistered "claim sharks"); item 15 (licensed broker); item 18 (eleven or more customers makes a "covered entity"); item 21 (custodian may background-check the agent).
- **A person, an organization or a roster:** item 5 (one attorney per form); item 6 (individuals only; the firm is payee, not representative); item 7 (organization on the 21-22, individual on the 21-22a); item 12 (Customer Number roster, ten-name cap, sponsored accounts); item 14 (authority to roles); item 13 (entity acting through a named employee); item 24 (named list with specimen signatures); item 25 (per agent, not per agency); item 23 (co-agents and successors).
- **Accountability stays put:** item 15 (Reg. 2834); item 6 (pay the firm, hold the individual); item 16 (brokers act through licensed officers).
- **The agent's own duties:** item 1 (§ 7063(c)–(d)); item 3 (no redisclosure); item 5 (duty to continue at EOIR); item 20 (certification; reasonable care, *Gordon v. Softech*); item 23 (acceptance by conduct, § 113).
- **Pay kept apart from authority:** item 6 (fee sections); item 7 (fee limits); item 15 (compensation triggers); item 25 (commission follows the record).

**3. How was the grant made, and with what assurance?**
The form of consent is itself regulated, and assurance level decides whether counterparties accept. (Anatomy 11; rule 2.)
- **Validity as required elements:** item 2 (core elements; defects void); item 3 (signed, dated, three fields); item 10 (Nacha minimum data elements); item 19 (model form); item 25 (CMS consent elements).
- **Standalone and unbundled:** item 11 ("solely"; *Syed*, *Gilberg*); item 17 (§ 64.1130(b)–(c)); item 22 (Rule 14a-4(a)(3)); item 18 (each category initialed); item 10 (anti-tying).
- **Ceremony scaled to risk:** item 1 (signed slip versus notarized POA); item 8 (two IDs; in person, live video or notary); item 13 (ink and perjury in California, notary in Arizona, secure state form for odometer); item 21 (Medallion guarantee for full authority); item 23 (acknowledged signature presumed genuine, § 105); item 20 (North Carolina notarization versus federal e-signature).
- **Electronic signing, and where:** item 4 (online channel only; taxpayer approves in their own IRS account); item 5 (ink, or the USCIS account); item 3 (§ 99.30(d)); item 9 ("sign" is media-neutral); item 10 ("similarly authenticated"); item 22 (electronic transmission); item 25 (signature, email or recorded audio).
- **Grant without a separate document:** item 9 (implied by the security agreement); item 1 (opt-out preference signal); item 12 (trademark recognition by conduct, which is the attack surface).
- **Both sides sign:** items 4, 5, 6 (CMS-1696), 19; item 14 (certifier cannot be a signer).
- **Warning before signing:** item 13 (§ 580.5(d)).

### What

**4. What may it do, and within what limits?**
Scope is action × object × bounds, and the study's first rule is to separate reading, acting and moving money. (Anatomy 3; rules 1 and 3.)
- **Read, act and move money split:** item 4 (8821 versus 2848); item 18 (information versus action); item 21 (view, trade, fees, own-name transfers, third-party payments); item 19 (information-only forms versus POA); item 2 ("may share" versus "must deliver").
- **Scope as a tuple:** item 4 (tax × form × period); item 3 (records × purpose × recipient); item 5 (agency, form and receipt number); item 6 (claim types); item 12 (identified application); item 17 (listed numbers); item 25 (named coverage).
- **Bound to one object:** item 13 (VIN); item 9 (described collateral).
- **Procedural only:** item 1 (submit a request); item 6 (SSA-89 match or no match); item 17 (request the port).
- **Checklists and per-item choices:** item 18 (initialed categories); item 14 (power × agent × signature count); item 22 (for, against, abstain; enumerated discretion); item 15 (authorities with opt-out boxes); item 23 (subject areas A–M); item 24 (mail classes).
- **Numeric bounds:** item 15 (per-item ceiling with emergency override); item 10 (amount or range, timing); item 14 (dollar limits, dual signature); item 21 (one order, one day).
- **No wildcards:** item 4 (no "all years"; three future years); item 9 ("all assets" needs an express clause); item 12 (ten-name cap); item 22 (over-voting voids the instruction).
- **Standing grant plus instruction per transaction:** item 18; item 10 (standing authorization).

**5. What is off by default, and what can never be granted?**
A broad grant does not imply dangerous powers, and some powers no grant can reach. (Anatomy 4; rules 3 and 4.)
- **Off unless separately opted in:** item 23 (UPOAA § 201(a); Cal. § 4264); item 4 (line 5a); item 7 (7332 records, address change, affiliated staff); item 24 (Restricted Delivery per agent); item 21 (fees and disbursement optional; third-party payments only by standing letter); item 2 (psychotherapy notes need their own authorization); item 20 ("highly restricted" data); item 5 (secure identity documents to the representative); item 18 (rate changes).
- **Never, whatever the grant says:** item 4 (line 5b refund routing); item 22 (Rule 14a-4(d)); item 13 (California: odometer disclosure, Statement of Facts); item 10 (the payee cannot sign for the consumer, comment 10(b)-5); item 21 (adviser cannot name or change the payee); item 23 (health-care decisions excluded); item 15 (broker may not advance its own funds); item 1 (no reuse of returned data).
- **Passing authority on:** item 4 (line 5a opt-in); item 6 (42 CFR 405.910(l)); item 13 (Texas allows substitution, California forbids it); item 16 (no subagents except for one filing); item 5 (paralegal delegation removed); item 23 (delegation is a hot power); item 8 (sub-delegate identity-proofed); item 12 (sponsored accounts); item 17 (end customer must sign, not the reseller); item 20 (resale only for listed purposes); item 15 (accountable party unchanged).
- **Money path and contact details protected:** item 4 (line 5b); item 7 (address change); item 21 (same-name transfers; payee list); item 6 (payee record kept separate).

**6. For what purpose?**
Purpose is its own element in the study, and closed purpose lists are a named gap in current agent specs. (Anatomy 5.)
- **Purpose as a required field:** item 3 (§ 99.30); item 2 (each purpose described); item 11 (employment purposes); item 25 (CMS consent elements); item 1 (private form: "sole purpose").
- **Closed list:** item 20 (14 permissible uses, with consent as one of them); item 6 (SSA-89 listed purposes).
- **Certified under penalty:** item 20 (perjury declaration; a checkbox alone is not enough, *Gordon v. Softech*); item 11 (user certification); item 2 (§ 164.509 attestation, since vacated).
- **Purpose travels downstream:** item 3 (§ 99.33(a)); item 20 (resale logged with purpose); item 1 (§ 7063(d)); item 2 (redisclosure warning marks where control ends).
- **Purpose-specific terms:** item 7 (five-year limit for income matching); item 18 (secondary purposes consented separately); item 16 (data use must be set out in the POA).

### When

**7. When does it start and end?**
Lifetimes take three shapes (a clock, a workflow state, a single use), and missing expiry is the most common defect. (Anatomy 6.)
- **Clock:** item 6 (90 days; one year); item 19 (one year; must reach the servicer within 90 days); item 18 (one-time, one year, up to three; blank means one-time); item 2 (expiry mandatory); item 15 (§ 10176(f)); item 16 (partnership two years); item 9 (five-year lapse); item 22 (three-year cap); item 17 (90-day and 60-day windows); item 4 (three future years).
- **Workflow state:** item 5 (conclusion of the matter); item 6 (life of the appeal); item 12 (registration, ownership change, abandonment); item 13 (spent on completion; vehicle age); item 21 (ends at death or incapacity); item 23 (durable by default).
- **Single use:** item 22 (one meeting); item 6 (SSA-89); item 21 (day order); item 1 (single-request forms).
- **Liveness in place of expiry:** item 8 (quarterly re-certification); item 21 (three-year dormancy); item 18 (annual reminder).
- **Start conditions:** item 23 (springing); item 25 (effective after the window); item 10 (start date).
- **No expiry stated:** items 1, 3, 4, 7, 11, 13, 14, 20, 24.

**8. How is it changed, revoked or replaced, and who must be told?**
Revocation works only where the relying party learns of it. (Anatomy 7; rules 6 and 9.)
- **New grant replaces old:** item 4 (per tuple, with a "retain" box); item 7 (one representative); item 12; item 19 (last-in replaces); item 22 (latest-dated wins, with a cut-off); item 24 (whole-list replacement); item 25 (after the contest window).
- **Old survives unless named:** item 14 ("Effect on Previous Resolutions"); item 6 (a new principal representative does not revoke the old one).
- **Revocation recorded where the relying party looks:** item 4 (CAF); item 7; item 8 (dated termination in the CRD); item 25 (carrier's state machine).
- **Effective only on receipt or knowledge:** item 14; item 6 (42 CFR 405.910(m)); item 16 (§ 141.35; the broker may not know); item 23 (actual knowledge); item 2 (except where already relied on).
- **Principal can revoke without the agent:** item 10 (stop at own bank); item 9 (debtor files termination); item 18 (cancel in writing).
- **The agent's exit:** item 5 (withdrawal; leave at EOIR); item 12 (Director's approval); item 7 (38 CFR 20.6); item 21 (advisor notice).
- **One agent or several:** item 7 (single slot); item 25 (exclusive); item 15 (exclusive, then nonexclusive); item 6 (several, one lead); item 4 (up to four per form); item 23 (co-agents).
- **Handoff safeguards:** item 25 (incumbent notified; 5–10 days; three-way call); item 7 (silent displacement risk; status view); item 19 (displaced agent should be told).
- **Partial change:** item 6 (update by section); item 18 (cancel and re-authorize, which encourages over-requesting).
- **Events that should trigger review:** item 12 (assignment); item 16 (antecedent firm); item 4 (staff who leave); item 7 (incompetency finding).
- **No procedure stated:** items 1, 3, 11, 13, 20.

### In use

**9. What may the other side rely on, and must they honor it?**
Three things: how the counterparty checks, what protects it, and whether it may refuse. (Anatomy 8; rules 7, 8 and 10.)
- **Checks its own registry:** item 4 (CAF); item 7; item 8 (CRD); item 12 (roster, Customer Number, assignment records); item 18 (Share My Data); item 25.
- **Matches its own records:** item 17 (service record plus PIN; weak alone); item 22 (control number, holdings); item 14 (specimen signatures).
- **Authenticates at each use:** item 24 (photo ID at each pickup; door versus counter); item 23 (§ 302 certification at presentation); item 18 (instruction per transaction).
- **Relies on the agent's custody or certification:** item 16 (broker holds the POA; CBP audits); item 11 (employer's certification); item 20; item 15 (license plus agreement).
- **No check at the door:** item 9 (§§ 9-516, 9-520; authorization is a question for the court).
- **Checks tiered by risk:** item 1 (§ 7063(a) versus § 7026(j); *Honda*); item 13 (copies accepted for one form, not the other); item 21 (custodian confirms the standing letter directly).
- **Protected when it relies:** item 23 (§ 119); item 2 (reliance before revocation); item 14 (until notice); item 21 (indemnity).
- **Must honor:** item 23 (§ 120, seven business days; Cal. § 4406); item 1 (shall comply; may not require a POA); item 2 (access directive); item 17 (one business day); item 18 (tariff binds the utility); item 19 (once satisfied, treat the agent's communications as the borrower's); item 9 (ministerial refusal only).
- **May refuse, and how:** item 19 (written rejection); item 23 (statutory refusal grounds); item 21 (may refuse or remove the agent); item 3 (permissive); item 17 (common rejection reasons); item 22 (fail closed).

**10. What comes back to the principal, by a channel the agent cannot capture?**
The common thread is that the channel is independent of the agent. (Anatomy 9; rule 5.)
- **Told afterwards:** item 5 (courtesy copy); item 21 (per-transfer and annual notices); item 20 (copy of each request mailed to the subject); item 3 (copy on request); item 10 (copy of the authorization).
- **Told before:** item 10 (ten days' notice of a varying debit); item 17 (notice before the port); item 11 (copy of the report before adverse action); item 18 (annual reminder; notification to both parties).
- **Asked first:** item 15 (approval above the cap); item 1 (direct confirmation, barred for opt-outs); item 21 (custodian confirms with the client); item 25 (three-way call); item 10 (standing authorization: each debit needs a consumer action); item 4 (taxpayer approves in own account).
- **Principal can stop it:** item 10 (stop-payment); item 17 (port-out lock); item 25 (reverse within the window); item 9 (termination).
- **Counterparty keeps a direct line:** item 19 (servicer may contact the borrower; Reg O); item 15 (certified mail to the address of record); item 7 (status view).
- **Agent must not control the channel:** item 7 (address change is an opt-in); item 21 (address of record; trusted contact); item 5 (delivery elections).

**11. What record exists, who holds it, and who can see it?**
Two records are needed: one of the grant and one of each use. (Anatomy 10.)
- **Record of the grant:** item 2 (six years); item 10 (two years after termination); item 16 (until revoked, plus five years); item 25 (ten years); item 6 (relying party keeps the SSA-89); item 13 (three years with the title); item 8 (ID images in the CRD).
- **Record of each use:** item 3 (§ 99.32, though consented disclosures are exempt); item 20 (§ 2721(c), five years); item 13 (§ 580.4(b)); item 24 ("ID Verified," initialed and dated); item 21 (per-transfer notices); item 10 (identity plus assent; a screenshot alone is not enough).
- **Who holds it:** the relying party (items 4, 7, 8, 14, 24, 25); the agent or requester (items 10, 11, 16, 20); with the subject's own record (item 3); public index (item 9).
- **Who can see it:** item 3 (the subject); item 7 (the principal); item 20 (the DMV on request); item 16 (CBP on audit); item 8 (agent status confirmed without exposing the principal).
- **Integrity:** item 9 (annotate, do not delete; log a later approval beside the earlier act); item 22 (trustworthy timestamps); item 13 (tamper attempts logged).

**12. When it goes wrong, who bears the loss and how is it put right?**
The instruments allocate loss among all three parties, and penalties are what make the other rules hold. (Anatomy 12.)
- **Loss on the principal:** item 24 (after delivery to the agent); item 21 (indemnifies the custodian); item 18 (customer and agent indemnify the utility); item 15 (indemnity except for gross negligence); item 14 (bank disclaims misuse of signing codes); item 10 (liable for an agent who exceeds authority until the bank is told, comment 2(m)-2).
- **Loss on the agent:** item 9 (§ 9-625; higher state penalties); item 16 (penalties, license revocation); item 23 (treble damages for embezzlement); item 3 (five-year debarment); item 15 (broker stays responsible); item 6 (perjury; misdemeanor); item 8 (false statements); item 20 (liquidated damages, fines); item 19 (prosecution; redress orders).
- **Loss on the party that obtained or relied on consent:** item 11 (statutory damages; employer liable for a vendor's form); item 10 (bank must recredit; originating bank warrants authorization); item 20 (penalties on DMVs; reseller duty of care).
- **Loss on a counterparty that wrongly refuses or over-checks:** item 23 (§ 120 fees); item 1 (*Honda*, $632,500); item 2 (access penalties).
- **Putting it right:** item 10 (recredit and return); item 9 (unauthorized filing ineffective; information statement; termination; ratification); item 25 (rescission window); item 23 (court order to accept).
- **Sanctions make the rest hold:** item 7 (registry rules without penalties leak); item 9 (small fixed penalties do not deter); item 11 (damages make the format self-enforcing).
- **Incentives:** items 15 and 25 (whoever is paid per transaction or holds the record has a motive to transact or to take over).

