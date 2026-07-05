---
title: "The Compliance Conversation Record: A Proposed Specification"
pubDate: 2026-07-05
description: "A v0.1 specification for audit-grade conversation evidence: fields, timestamps, abstention rules, quality scores, retention, and the provider-versus-deployer duty split."
metaTitle: "The Compliance Conversation Record: A Proposed Spec"
metaDescription: "A v0.1 specification for audit-grade conversation evidence: fields, timestamps, abstention rules, quality scores, retention, and the provider-versus-deployer duty split."
heroImage: "images/compliance-conversation-record-specification.webp"
heroImageAlt: "The Compliance Conversation Record: A Proposed Spec"
faqs:
  - question: "How is a Compliance Conversation Record different from standard call recording?"
    answer: "Standard recording keeps the conversation for reference or training. A CCR keeps it to withstand audit, which means it captures the conditions under which answers were given, not just the words: the disclosure the person received, how present they were, what they declined, and what the system was forbidden from inferring. A completed transcript is one field in the record, not the record."
  - question: "Can a quality score be gamed or faked by the platform?"
    answer: "Only if the method isn't reproducible. The spec requires the score to be derived from stored inputs like response timing and abstention pattern, and to return the same result given the same inputs. Because the explanation export names the factors behind each score, a fabricated or inflated score is detectable by anyone reviewing the record. That's the safeguard against a vendor reporting presence where there is none."
  - question: "Does storing engagement timing and quality scores create a data protection problem?"
    answer: "It can, which is why retention and minimisation are explicit fields. The record ties a retention period to the consent basis and supports keeping the score and metadata after the transcript itself is deleted or de-identified. The inference abstention field works in the same direction: the record attests to what was never collected or inferred, which is data minimisation expressed as evidence rather than policy."
  - question: "Is this an official standard?"
    answer: "No. It is an open specification proposed by practitioners, published so a common evidence class can exist before harmonised standards under the AI Act arrive. If those standards supersede it, organisations that adopted the record will already hold most of what they require. Version 0.1 will be improved or replaced, and either outcome beats the current alternative, which is nothing."
  - question: "Who signs off on whether a listening programme meets this spec?"
    answer: "Responsibility splits between provider and deployer. The provider certifies the record structure, the scoring method, and honest field population. The deployer certifies consent, retention, and how the data informs decisions. An HR Director evaluates the provider column during procurement and stands behind the deployer column at audit, which keeps accountability from falling into the gap between the two."
draft: false
---

An auditor sits across from an HR Director and asks a question the engagement platform can't answer. Not "what was your completion rate", that one's easy, it's 91%. The question is: "How do you know the people who answered were actually thinking about the question?" There is no field for that. There is no log, no flag, no score. The transcript looks identical whether the respondent weighed the question or clicked through to make the screen go away.

And there is a second question coming right behind it, from the same chair: "Show me that this employee was told they were talking to an AI." From 2 August 2026 that one has legal force under [Article 50 of the EU AI Act](https://artificialintelligenceact.eu/article/50/), and most platforms cannot answer it per person, per conversation, either.

This post proposes a specification to close both gaps. It's for HR leaders who own listening programmes, and for the auditors, CISOs, and procurement teams who increasingly want evidence that workforce data means something before a decision is built on it. Treat it as v0.1: a draft to argue with, extend, and cite. If the industry is going to produce audit-grade conversation evidence, someone has to write down what "audit-grade" means. Here's a first attempt.

## What is a Compliance Conversation Record?

**A Compliance Conversation Record (CCR) is a structured, timestamped, exportable record of a workforce conversation that captures not only what was said, but the conditions under which it was said: what the person was told, how present they were, what they declined, what the system was instructed to do, and what it provably did not infer.** It's the difference between "the form was submitted" and "a person, properly informed, engaged with the question."

The distinction that matters is between telemetry and evidence. The state of the art in conversational AI observability is genuinely impressive: per-turn traces, composite quality scores, failure attribution, latency percentiles. All of it answers the operator's question, which is "did our system perform well?" The auditor's question is different: "what happened to this person?" Telemetry is organised around system events and legible to engineers. Evidence is organised around the person, retained on a defined schedule, and legible to a works council member with no technical background. A platform can have world-class telemetry and produce no evidence at all. The CCR is the evidence class.

## Why isn't a completed transcript enough?

**A completed transcript proves the screen advanced. It proves nothing about whether the respondent was present when they answered.** A person answering on autopilot and a person reasoning carefully produce transcripts that read the same, and every field in a conventional survey record is blind to the difference.

This is the failure mode HR Directors keep having to defend in front of leadership. The dashboard shows a healthy score and a high completion rate, and someone senior asks whether the numbers reflect what people actually think or just what they clicked. There's no clean answer, because the underlying record was never built to hold one. Completion rate, the metric the whole category optimises for, is the exact place its worst data hides. A CCR fixes this by treating the transcript as one field among several, not the whole record.

The contact-centre world already accepts the principle that conversations get scored before anyone acts on them: Google Cloud's Quality AI, for instance, calculates [an overall conversation score plus separate scores tagged to compliance](https://docs.cloud.google.com/contact-center/insights/docs/qai-best-practices). If a sales call is worth quality-checking before anyone acts on it, an employee's account of whether they can do their job safely deserves at least the same treatment.

## The specification, field by field

Here's the proposed record. Each numbered item is a field or field group a CCR should contain. Where a platform can't populate a field honestly, it should mark it absent rather than fake it.

### 1. Identity, purpose and consent block

Every record opens with who was asked, in what capacity, under what programme, and on what consent basis. **The consent basis is a field, not a footnote.** It states the purpose of the conversation, whether the respondent agreed to it being recorded and scored, and links to the version of the notice they saw. This is where lawful basis gets pinned to each individual record rather than assumed across the programme, and it's the first thing an auditor checks.

### 2. AI disclosure record

**The exact disclosure the respondent received, its language, its timestamp, its delivery mode, confirmed as preceding the first substantive turn.** From 2 August 2026, an AI that talks to a person must tell them so, and the deploying organisation must be able to show the telling happened. A configured setting is a behaviour; this field is the proof. A record without it fails the first regulatory question it will ever face.

### 3. Timestamps and the engagement arc

Record start time, end time, and the timing between prompt and response for each turn. **Response timing is the raw material for judging presence.** A three-second answer to a question that takes ten seconds to read is a signal. So is a long pause before a considered reply.

Together these turn-level timings form the engagement arc: how attention rose and fell across the conversation. A record that stores only the final transcript throws this away. A CCR keeps it, because response compression, answers arriving faster than the question could reasonably be processed, is one of the clearest markers that a respondent slipped into completion mode.

### 4. The response content, and what the machine was told

Store the transcript verbatim by default, with per-turn speaker attribution, and a data-minimisation option to store an AI-generated summary instead where a framework discourages retaining full conversation records. Whichever mode is used gets recorded as a field, so a later reviewer knows whether they're reading the person's words or a paraphrase.

The record also carries **a version reference for the instructions the AI was operating under.** An audit of a conversation is incomplete without the brief the interviewer was working to. What the system said matters; what it was configured to do matters just as much, and no conventional logging stack exports it.

### 5. Abstention and reflective silence

**A respondent must be able to decline a question, and the record must distinguish a deliberate abstention from a non-answer.** "I'd rather not say" and silence-then-timeout are different events, and collapsing them into the same blank cell destroys signal.

The spec proposes three states: answered, abstained (respondent actively chose not to answer), and reflective silence (a genuine pause that resolved into an answer or an explicit abstention). Reflective silence should never be scored as disengagement. It's often the opposite. Someone taking time over a hard question is exactly the presence the record is trying to protect. Forcing an answer to fill the cell is what produces the autopilot data in the first place.

### 6. Inference abstention record

**A declared list of the inferences the system does not perform, and a per-conversation attestation that none were performed.** This is negative evidence, and it is the field no logging architecture produces by accident. Proving what happened is an engineering habit. Proving what did not happen requires deciding, at design time, that certain inferences are out of bounds, then attesting in every record that they stayed there.

The regulatory pressure is not hypothetical. The AI Act's [Article 5](https://artificialintelligenceact.eu/article/5/) prohibits emotion inference in the workplace, and Article 50(3) forces disclosure wherever emotion recognition or biometric categorisation runs at all. Much of the conversational AI market currently sells inference as the product: emotional arcs, sentiment trajectories, demographic predictions. In EU employment contexts those range from disclosure-triggering to prohibited. A stated policy of restraint is a claim. An abstention field in every exported record is evidence. Any escalation to a human is logged here too, because routing a moment to a person is itself a decision the record should hold.

### 7. Quality score

Every session produces a quality score alongside the transcript, so decisions rest on input that has been quality-checked, not just collected. **The score estimates how present the respondent was, derived from the engagement arc, response timing, abstention pattern, and coherence across turns.** It is stored as a field with its inputs, not delivered as a single opaque number.

The score has to be reproducible: given the same inputs, it returns the same result, using a documented method that runs identically across every session rather than bespoke logic per conversation. That is the safeguard against a platform inventing presence where there is none, and it is what makes the next two fields possible.

### 8. Retention, integrity and minimisation

State a retention period per record, tied to the lawful basis in field 1, and default to deleting or de-identifying once that period lapses. Retention should also record what is kept: full transcript, summary only, or score-plus-metadata after transcript deletion. This lets an organisation hold the quality evidence long after the raw words are gone, which is often the right balance between audit needs and minimisation under [GDPR's storage limitation principle](https://gdpr-info.eu/art-5-gdpr/).

Integrity is the other half. **Each record carries a cryptographic hash, an access log, and, when the retention period expires, deletion evidence.** A record that cannot prove it is intact, or who has looked at it, is a document, not evidence. When the record dies, its death is itself recorded.

### 9. Explanation export

**The record must export a plain-language explanation of its quality score on demand, in a format a non-technical reviewer can read.** An auditor should not need access to the platform to understand why a session scored the way it did.

The export names the factors that moved the score: response compression on questions 4 through 6, an abstention on the pay question, a coherent and well-timed engagement arc overall. It's not just findable, it's legible without the vendor in the room.

## How does the record map to the obligations?

**Each field exists because a live or arriving obligation demands it, and the sequencing is the argument for adopting early.** The disclosure record answers Article 50(1), in force from 2 August 2026. The inference abstention record answers Article 5 and Article 50(3). The content, instruction versioning, and integrity fields anticipate the record-keeping duties that attach to high-risk employment systems from December 2027, and the explanation export anticipates the explanation rights that arrive with them. The consent, retention, and deletion fields are GDPR natives, in force now regardless of what the AI Act's timeline does next. An organisation that adopts the record this year meets the August deadline with field 2 and quietly builds most of its 2027 evidence base as a side effect.

## Who is responsible? The provider-versus-deployer split

**The platform provider is responsible for producing the record honestly. The deploying organisation is responsible for acting on it lawfully.** Confusing the two is where accountability leaks, so the spec draws the line explicitly.

The provider builds the fields, computes the score with a reproducible method, and refuses to fabricate presence where there's none. The deployer sets retention, defines consent, decides which questions get asked, and owns the downstream decision. An HR Director can hold a vendor to the provider column during procurement, and stand behind the deployer column in front of an auditor.

| Duty | Provider (platform) | Deployer (your organisation) |
|---|---|---|
| Record structure and fields | Build and populate honestly | Configure to the use case |
| AI disclosure | Deliver by design, log per conversation | Verify and produce at audit |
| Quality score method | Reproducible, explainable, documented | Set thresholds for action |
| Abstention handling | Distinguish the three states | Decide how abstentions inform decisions |
| Inference abstention | Attest per record what is not inferred | Confirm the list matches policy and law |
| Consent basis | Capture and version it | Define lawful basis and notice |
| Retention and integrity | Enforce the period, hash the record | Set the period per policy |
| Explanation export | Produce on demand | Store and disclose to auditors |

The one rule that binds both columns: neither party invents signal. A provider that scores a rushed session as engaged, or a deployer that reports completion as if it were meaning, has broken the record's purpose. Everything else is configuration.

## An honest note on implementation

No platform we are aware of fully implements this specification today, including ours. Timestamped transcripts, structured outputs, disclosure capture, and exportability exist in production systems now. Per-record inference attestation, instruction versioning in the export, and cryptographic integrity are design commitments at various stages of real. We are publishing the specification ahead of complete implementation deliberately, because a standard that only describes what its author already ships is not a standard, it is a brochure. The specification is the exam. We intend to pass it in public, and we would welcome company.

## Next steps

If you own a listening programme and want to move toward audit-grade records, three things are worth doing this quarter.

1. **Ask your current vendor for the quality field.** Not the completion rate, the presence signal. If they can't produce one per session, you're collecting volume without knowing its quality.
2. **Ask for the disclosure record.** For a named employee on a named date: were they told they were talking to an AI, in what language, and can you export the proof? After 2 August that question has legal force, and the vendors who go quiet are telling you something.
3. **Separate abstention from non-response in your own reporting.** Even before a full CCR, distinguishing "chose not to answer" from "didn't answer" recovers signal you already hold.

This is v0.1. It's deliberately more specification than sales pitch, because the point is to give auditors, engineers, and HR leaders a shared definition to evaluate any platform against, including the one you already use. Feedback, criticism, and proposed fields for v0.2 are welcome. The only rule is the one the record itself enforces: claims need evidence.

## Frequently asked questions

### How is a Compliance Conversation Record different from standard call recording?

Standard recording keeps the conversation for reference or training. A CCR keeps it to withstand audit, which means it captures the conditions under which answers were given, not just the words: the disclosure the person received, how present they were, what they declined, and what the system was forbidden from inferring. A completed transcript is one field in the record, not the record.

### Can a quality score be gamed or faked by the platform?

Only if the method isn't reproducible. The spec requires the score to be derived from stored inputs like response timing and abstention pattern, and to return the same result given the same inputs. Because the explanation export names the factors behind each score, a fabricated or inflated score is detectable by anyone reviewing the record. That's the safeguard against a vendor reporting presence where there is none.

### Does storing engagement timing and quality scores create a data protection problem?

It can, which is why retention and minimisation are explicit fields. The record ties a retention period to the consent basis and supports keeping the score and metadata after the transcript itself is deleted or de-identified. The inference abstention field works in the same direction: the record attests to what was never collected or inferred, which is data minimisation expressed as evidence rather than policy.

### Is this an official standard?

No. It is an open specification proposed by practitioners, published so a common evidence class can exist before harmonised standards under the AI Act arrive. If those standards supersede it, organisations that adopted the record will already hold most of what they require. Version 0.1 will be improved or replaced, and either outcome beats the current alternative, which is nothing.

### Who signs off on whether a listening programme meets this spec?

Responsibility splits between provider and deployer. The provider certifies the record structure, the scoring method, and honest field population. The deployer certifies consent, retention, and how the data informs decisions. An HR Director evaluates the provider column during procurement and stands behind the deployer column at audit, which keeps accountability from falling into the gap between the two.

## Sources

- [Regulation (EU) 2024/1689, the EU AI Act: Article 5 on prohibited practices](https://artificialintelligenceact.eu/article/5/) and [Article 50 on transparency obligations](https://artificialintelligenceact.eu/article/50/), Official Journal of the European Union.
- [European Commission, Guidelines and Code of Practice on transparent AI systems](https://digital-strategy.ec.europa.eu/en/faqs/guidelines-and-code-practice-transparent-ai-systems), on the disclosure standard under Article 50.
- [Regulation (EU) 2016/679, the GDPR, Article 5](https://gdpr-info.eu/art-5-gdpr/), on purpose limitation, data minimisation, and storage limitation.
- [Quality AI Best Practices](https://docs.cloud.google.com/contact-center/insights/docs/qai-best-practices), Google Cloud, on per-conversation scoring with compliance-tagged criteria.

## Researched with AI. Argued, verified, and signed off by humans. That's also how we think AI should work everywhere.
