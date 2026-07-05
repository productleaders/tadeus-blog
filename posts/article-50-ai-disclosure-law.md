---
title: "AI Disclosure Becomes Law on 2 August"
pubDate: 2026-07-05
description: "From 2 August 2026, any AI that talks to a person must disclose it. For workforce voice tools, the real test is proving disclosure happened."
metaTitle: "Article 50: AI Disclosure Becomes Law on 2 August"
metaDescription: "From 2 August 2026, any AI that talks to a person must disclose it. For workforce voice tools, the real test is proving disclosure happened."
heroImage: "images/article-50-ai-disclosure-law.webp"
heroImageAlt: "Article 50: AI Disclosure Becomes Law on 2 August"
faqs:
  - question: "When does Article 50 of the EU AI Act come into force?"
    answer: "Article 50's transparency obligations apply from 2 August 2026, with the Act's fining powers live from the same date. This is separate from the high-risk rules for employment systems, which apply from 2 December 2027 following the Digital Omnibus. The delay to the high-risk regime did not move the transparency date. Workforce tools therefore face two deadlines, and the nearer one has no grace."
  - question: "Does Article 50 apply to AI tools that are not high-risk?"
    answer: "Yes. The transparency obligations in Article 50 apply to all AI systems in the four situations it covers, including any system that interacts directly with people. A tool does not have to be classified as high-risk to trigger the disclosure duty. If an AI talks to a person, the person must be told."
  - question: "Does Article 50 apply to companies outside the EU?"
    answer: "Yes, where the system or its output reaches people in the EU. A UK or US platform whose conversational AI talks to EU-based employees is in scope. The location of the vendor is irrelevant; the location of the person on the call is what counts."
  - question: "What counts as adequate disclosure under Article 50?"
    answer: "The Commission's draft guidelines require the disclosure before or at the first interaction, in a clear and distinguishable form, judged from the perspective of the people actually exposed. Buried terms and conditions, faint labels, and one-time small print do not meet the standard, and sensitive contexts may require the disclosure to be repeated. In practice, adequate disclosure means the tool states it clearly at the point of interaction and the deploying organisation can produce evidence that the statement was made."
  - question: "Can a vendor be \"EU AI Act certified\"?"
    answer: "Not today. Harmonised standards and conformity assessment for the Act are still being finalised, so certification claims should be treated with suspicion. The claims a careful vendor can make are narrower and more useful: disclosure by design under Article 50, logged and exportable evidence, and a conformity-ready posture for the high-risk obligations arriving in 2027."
  - question: "How is AI disclosure connected to data quality in listening programmes?"
    answer: "Both depend on treating a conversation as an evidenced event rather than a completion. A platform that only records that a response finished usually cannot show whether disclosure happened or whether the respondent was genuinely present. The same architecture that captures timestamped disclosure tends to capture the signal quality of the answers themselves."
draft: false
---

**From 2 August 2026, any AI system that talks directly to a person has to tell that person they are talking to an AI.** That is the core of [Article 50 of the EU AI Act](https://artificialintelligenceact.eu/transparency-rules-article-50), and it applies to all AI systems in scope, not just the ones classified as high-risk. For anyone running a voice tool that speaks to employees, the four-week question is no longer whether you disclose. It is whether you can prove you did.

Most conversations about the AI Act have circled the high-risk category, the governance paperwork, and lately the delay. When the Digital Omnibus pushed the high-risk rules for employment systems out to December 2027, a lot of the market heard "the AI Act slipped." It did not. Article 50 is a horizontal transparency duty that sits outside the high-risk regime, its date held, and the enforcement powers that back it, [fines of up to 15 million euros or 3% of worldwide turnover](https://artificialintelligenceact.eu/transparency-rules-article-50), switch on the same day the obligation does. A chatbot in a benefits portal. A voice assistant that runs an onboarding conversation. An AI that asks an employee how a new tool is landing. If a person is on one side and an AI is on the other, the disclosure obligation attaches. The date is fixed. The clock is running.

## What does Article 50 actually require?

**Article 50 sets transparency obligations that apply from 2 August 2026 across four situations: when AI interacts directly with people, when it generates synthetic content, when it is used for emotion recognition or biometric categorisation, and when it creates deepfakes or text on matters of public interest.** These obligations apply to all AI systems in those situations, not only to high-risk ones.

The first trigger is the one that matters for workforce software. When an AI system is built to interact directly with a natural person, that person has to be informed they are dealing with an AI, unless it is already obvious from the context. The [European Commission's draft guidelines](https://digital-strategy.ec.europa.eu/en/faqs/guidelines-and-code-practice-transparent-ai-systems), published in May 2026, set the bar for what counts: the disclosure must arrive before or at the first interaction, in a clear and distinguishable form. A line buried in terms and conditions does not qualify. A faint label does not qualify. In sensitive contexts, saying it once may not be enough. No person should finish a conversation unsure whether they were speaking to a human or a machine, and no organisation should be unable to show that the telling happened.

There is a second timeline worth holding in view. The Commission has confirmed that [AI systems used in employment count as high-risk, with those rules applying from 2 December 2027](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai). So workforce tools face two dates, not one. The transparency duty first, the high-risk obligations later. Treating them as a single problem to solve in 2027 is a mistake, because the earlier date has no such grace.

## Why does this land on workforce voice tools specifically?

**A voice layer that speaks to employees is, by definition, an AI system interacting directly with people, so Article 50's disclosure duty applies whether or not the tool ever gets classified as high-risk.** The classification debate is a separate track. Disclosure is the immediate one.

Here is the causal chain. The tool talks to a person, so Article 50's first trigger applies. The person must be told it is an AI. And the organisation deploying it has to be able to show that the telling happened. Fail any link and you have an exposure that is trivially easy for a regulator, a works council, or an employee's lawyer to test. They just ask: did you disclose, and can you prove it?

Do not count on the "obvious from context" exception either. The Commission's guidelines judge obviousness from the perspective of an average, reasonably observant person, weighted for the audience actually exposed. A code assistant used only by professional developers may pass that test. A voice on a phone that greets an employee by name, in their own language, with human pacing and natural turn-taking, is the opposite of obvious. It is engineered specifically not to feel like a machine, which produces an inversion worth sitting with: in conversational AI, quality creates the obligation. The more human your AI sounds, the more clearly it must say it is not. Any vendor whose pitch is "your employees won't even know it's AI" is describing an infringement as a feature.

One more split that matters commercially. The duty to design disclosure into the system belongs to the provider; the duty to inform people about emotion recognition, and to label AI-generated content the organisation publishes, stays with the deployer. Embedding a voice layer transfers the provider duties to the vendor. The deployer duties remain yours no matter what you buy, which is exactly why the vendor's evidence has to be exportable rather than merely claimed.

## What does native disclosure plus exportable proof look like?

**Native disclosure means the tool announces it is an AI at the start of every conversation as a designed behaviour, not a setting someone has to remember to switch on. Exportable proof means every one of those disclosures leaves a timestamped record you can pull out and hand to an auditor.** One without the other does not satisfy the obligation in practice.

Plenty of tools can be configured to say "I'm an AI assistant" somewhere. Fewer can tell you, six months later, that a specific employee heard that line at a specific time in a specific language on a specific date. That gap between the behaviour and the evidence is where the compliance risk actually lives.

The distinction is worth drawing out.

| | Disclosure as a feature | Disclosure as a record |
|---|---|---|
| **When it happens** | Configured, can be toggled or missed | Built into the start of every conversation |
| **What you can show later** | That the setting was enabled | That this person, at this time, was told |
| **Audit response** | "We think it was on" | A timestamped log you can export |
| **Failure mode** | Silent gaps nobody notices | None, because the record is the conversation |

A voice layer built the right way treats the disclosure as the opening move of the conversation and captures it in the same structured, timestamped record as everything else the employee said. If every conversation is returned to the platform as a logged artefact, the proof of disclosure is not a separate compliance file to maintain. It is simply part of the transcript, sitting where the rest of the signal sits. That is the model to hold vendors to.

## What is the question most voice vendors cannot answer?

**Ask any voice vendor a single question: for a named employee on a named date, can you produce a record showing they were told they were speaking to an AI, and in what language? Most cannot, because they log completions and outcomes, not the conditions under which the conversation was given.** That is the same blind spot that lets a platform report a healthy completion rate while telling you nothing about whether a person was actually present.

The two problems are the same problem wearing different clothes. A tool that cannot tell you whether an answer carried real signal is usually a tool that cannot tell you whether disclosure happened either, because both require the platform to treat the conversation as an evidenced event rather than a row in a table. Completion mode, where the screen advances and the record says "done", hides bad data and missing disclosures with equal ease.

For an HR director, this is not abstract. You already spend time defending engagement data that leadership half-trusts. Now imagine defending a listening programme against a regulator's question about AI disclosure, using a platform that can show you the response landed but not that the employee was told what they were talking to. The completion rate looks fine. The evidence you actually need is not there. This is the moment the difference between a dataset that reflects real sentiment and one built on autopilot stops being a data-quality argument and becomes a legal one.

## Won't disclosure put employees off?

**No. The best evidence we have says disclosure increases what people are willing to say, which makes Article 50 a rare regulation that pays for its own compliance.** In a [University of Southern California study](https://ict.usc.edu/pubs/It's%20Only%20a%20Computer%20-%20Virtual%20Humans%20Increase%20Willingness%20to%20Disclose.pdf) on automated interviewing, participants who were told their interviewer was fully automated disclosed more, feared judgment less, and managed their impressions less than those who believed a human was listening. Knowing it is a machine is what unlocks candour, because the machine sits outside the org chart.

So the honest framing of the first turn is not a legal disclaimer to be mumbled at speed. It is the value proposition: this is an AI conversation, here is what it is for, here is what happens to what you say. Employees told that clearly say more, and what they say is worth more. The vendors shrinking the disclosure to a whisper are optimising against their own data quality as well as against the law.

## The counter-argument, and why it does not hold

The reasonable objection is that this is small. A one-line disclosure at the top of a conversation is not a heavy lift, and most vendors will bolt on a banner or a spoken preamble well before August. True enough for the behaviour. It misses the proof.

The obligation is not satisfied by the tool saying the words once in a demo. It is satisfied by the organisation being able to demonstrate, per interaction, that the words were said. When a data protection authority or a works council asks for that demonstration across ten thousand conversations in eleven languages, "we configured it to disclose" is not an answer. The record is the answer, or there is no answer. A bolted-on banner produces a behaviour without an evidence trail, which is exactly the position that fails an audit. And with the fining powers live from the same August date, and supplying misleading information to authorities separately finable, the paper trail is not administrative hygiene. It is the defence.

## What to do before 2 August

If you own a listening or communication programme that uses any AI to talk to employees, three moves are worth making now.

**1. Inventory every AI that speaks to a person.** If you run listening or workforce comms, list every tool where an AI interacts directly with an employee: chatbots, voice assistants, survey agents. Article 50 attaches to the interaction, not the label, so anything conversational is in scope, and do not assume the obviousness exception without writing down why.

**2. Send the proof question to each vendor in writing.** If you own vendor relationships, ask each one to produce a timestamped, exportable record of disclosure for a sample employee and date. Give them a deadline before 2 August. The ones who go quiet are telling you something.

**3. Make disclosure part of the record, not a setting.** If you own the platform decision, treat a tool's ability to log disclosure alongside the conversation as a baseline requirement, the same way you would treat consent capture. A disclosure you cannot export is a disclosure you cannot defend.

The date does not move. The tools that come through this well will be the ones that already treat every conversation as an evidenced event, where disclosure, timing, language and content all live in the same exportable record. That is the standard worth buying to, and it happens to be the same standard that tells you whether the answers underneath were worth acting on in the first place.

## Frequently asked questions

### When does Article 50 of the EU AI Act come into force?

Article 50's transparency obligations apply from 2 August 2026, with the Act's fining powers live from the same date. This is separate from the high-risk rules for employment systems, which apply from 2 December 2027 following the Digital Omnibus. The delay to the high-risk regime did not move the transparency date. Workforce tools therefore face two deadlines, and the nearer one has no grace.

### Does Article 50 apply to AI tools that are not high-risk?

Yes. The transparency obligations in Article 50 apply to all AI systems in the four situations it covers, including any system that interacts directly with people. A tool does not have to be classified as high-risk to trigger the disclosure duty. If an AI talks to a person, the person must be told.

### Does Article 50 apply to companies outside the EU?

Yes, where the system or its output reaches people in the EU. A UK or US platform whose conversational AI talks to EU-based employees is in scope. The location of the vendor is irrelevant; the location of the person on the call is what counts.

### What counts as adequate disclosure under Article 50?

The Commission's draft guidelines require the disclosure before or at the first interaction, in a clear and distinguishable form, judged from the perspective of the people actually exposed. Buried terms and conditions, faint labels, and one-time small print do not meet the standard, and sensitive contexts may require the disclosure to be repeated. In practice, adequate disclosure means the tool states it clearly at the point of interaction and the deploying organisation can produce evidence that the statement was made.

### Can a vendor be "EU AI Act certified"?

Not today. Harmonised standards and conformity assessment for the Act are still being finalised, so certification claims should be treated with suspicion. The claims a careful vendor can make are narrower and more useful: disclosure by design under Article 50, logged and exportable evidence, and a conformity-ready posture for the high-risk obligations arriving in 2027.

### How is AI disclosure connected to data quality in listening programmes?

Both depend on treating a conversation as an evidenced event rather than a completion. A platform that only records that a response finished usually cannot show whether disclosure happened or whether the respondent was genuinely present. The same architecture that captures timestamped disclosure tends to capture the signal quality of the answers themselves.

## Sources

- [Regulation (EU) 2024/1689, Article 50](https://ai-act-service-desk.ec.europa.eu/en/ai-act/article-50), Official Journal of the European Union, the text of the transparency obligations.
- [The EU AI Act's Transparency Rules: A Practical Guide to Article 50](https://artificialintelligenceact.eu/transparency-rules-article-50), artificialintelligenceact.eu, on the four triggers, the 2 August 2026 application date, and penalties.
- [Guidelines and Code of Practice on transparent AI systems](https://digital-strategy.ec.europa.eu/en/faqs/guidelines-and-code-practice-transparent-ai-systems), European Commission, on the disclosure standard and the drafting of the Code of Practice.
- [AI Act | Shaping Europe's digital future](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai), European Commission, on the high-risk timeline for employment systems applying from 2 December 2027.
- [Lucas, Gratch, King and Morency, It's Only a Computer: Virtual Humans Increase Willingness to Disclose](https://ict.usc.edu/pubs/It's%20Only%20a%20Computer%20-%20Virtual%20Humans%20Increase%20Willingness%20to%20Disclose.pdf), Computers in Human Behavior, 2014, USC Institute for Creative Technologies.

## Researched with AI. Argued, verified, and signed off by humans. That's also how we think AI should work everywhere.
