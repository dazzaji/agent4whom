# On Behalf Of Whom? What the Law Asks of Agent Protocols

*Dazza Greenwood, CIVICS.com* 
* Supporting research and remarks to the [IEFT San Francisco Meeting, November 20, 2026](https://datatracker.ietf.org/doc/agenda-127-iabopen/)

Abstract: AI agents now book hotels, buy goods and read people’s health and bank records, and the first appellate ruling about them turned on a header this community defined: User-Agent. The IETF is building the pieces that let agents be found, hold a dialog, be identified and authorized, and be audited. Yet the question remains: who answers for what the agent does? This talk brings a legal view to that gap. It draws on a study of 25 everyday legal authorization instruments, a survey of 34 agent specifications and an index of several hundred agent integrations. It tests common assumptions, among them “the AI agent is the agent,” “a scope is an authorization,” and “liability is out of scope,” and suggests which legal facts a protocol should carry to enable predictable legal results.

# Research Overview

AI Agent Authorization
Aligning the Business, Legal and Technical Dimensions

Dazza Greenwood, Civics.Com Open Research Project
To be published with Stanford Law School's Codex
Stanford Computational Law Report on AI Agents x Law

Version 0.3.2
November 6, 2026

___________________

To better understand the requirements and constraints for delegated authorization to AI agents, I assembled 25 fundamental legal instruments for delegation of authority to identify how to ensure valid, enforceable and predictable legal results.  Here's what I learned.

The most important point is that delegation of authority must be to a legal entity and may be carried out via AI agents but the AI agent itself is not the entity that acts as the legal agent. Therefore the authorization should include both technical authorization as well as a delegation of some kind to a legal entity that provides or operates the AI agent for the user.

Some further important distinction are that these 25 examples are not all legally equivalent forms of delegated agency. They fall into several functional categories:

- Delegated authority: An agent may represent the principal, make decisions, execute documents, or conduct transactions.
- Information-access authority: A designated party may receive protected information but cannot necessarily act for the principal.
- Transaction-specific consent: The individual authorizes a particular activity, such as a payment or background check, without establishing general agency.
- Organizational authority: A business empowers or identifies representatives authorized to bind it.
- Recognition of authority: A third party, agency, or institution accepts and records proof of an existing delegation.

These distinctions are central to AI authorization architecture. Permission to obtain information is not permission to make decisions; permission to execute one transaction is not general authority to represent someone. The IRS makes this distinction explicit between Form 2848 and Form 8821.

___________________
