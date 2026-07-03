---
title: "How do you know AI-collected data can be trusted?"
pubDate: 2026-07-02
description: "Every AI vendor claims trustworthy data. Few can name their failure modes. How research-grade evaluation shapes the way Tadeus scores every conversation."
metaTitle: "Can You Trust AI-Collected Data? Ask How It Fails | Tadeus"
metaDescription: "Every AI vendor claims trustworthy data. Few can name their failure modes. How research-grade evaluation shapes the way Tadeus scores every conversation."
heroImage: "images/why-we-started-with-academic-survey-rigour.webp"
heroImageAlt: "How do you know AI-collected data can be trusted?"
faqs:
  - question: "How is Tadeus different from other AI-moderated interview tools?"
    answer: "Most AI interview tools optimise for volume and completion: more sessions, faster, with a transcript at the end. Tadeus treats the transcript as half the output. The other half is a behavioural record of the conditions under which it was produced: response latency, answer compression, silence patterns, engagement arc, summarised in a per-session quality score. Tools that don't instrument respondent state cannot distinguish a reflective participant from one racing to finish, because on paper the two can look identical."
  - question: "Is this only for HR use cases, or can research and insights teams use it?"
    answer: "The platform is a horizontal voice layer, and research is a natural fit. The behavioural quality framework was shaped by research-grade evaluation practice in the first place, so insights teams get the version of the product closest to its origins: adaptive qualitative conversations at scale, with per-session validity signals that survive into analysis and reporting."
  - question: "What does the quality score actually measure?"
    answer: "It is a 0 to 100 score derived from observable behavioural signals across the session, including trends in response latency, word-count compression across turns, and disengagement events. It does not judge the content of answers or the respondent as a person. It characterises the cognitive conditions of the session, so analysts can weight, segment, or follow up accordingly."
  - question: "Doesn't all this rigour slow the product down or hide data?"
    answer: "No. Scoring runs alongside collection, not as an extra step, and nothing is ever suppressed. Flags are surfaced to the analyst with the data attached. The design commitment is transparency over tidiness: you see everything that was collected, plus an honest account of how much weight it can bear."
  - question: "Where can I read the academic work?"
    answer: "The AgentSLR paper is openly available on arXiv, and the pipeline itself is open source. The collaboration sits with Oxford's Reasoning with Machines AI Lab, which works on reliable reasoning and evidence synthesis with AI systems."
draft: false
---

**Every platform that uses AI to collect data will tell you the data is trustworthy. Almost none of them can tell you how their system fails.** That asymmetry is the single most useful test available to anyone evaluating conversational AI right now, whether you sit in people analytics, market research, or an insights function.

The reason is simple. A team that has genuinely measured its system against ground truth knows its failure modes, because measurement always finds them. A team that hasn't measured can only offer confidence. So when a vendor's answer to "where does this break?" is a reassurance rather than a list, you have learned something important about how the product was built.

This piece is about where Tadeus's answer to that question comes from. It is not a marketing methodology invented for a pitch deck. It comes from one of the more demanding corners of academic research: the systematic literature review, and specifically from work on what happens when you ask AI to do one.

## The most paranoid method in science

**A systematic literature review is what research looks like when the cost of being wrong is unacceptable.** It is the method used to synthesise medical and epidemiological evidence for bodies like the WHO, and it is deliberately, exhaustively careful: every relevant study retrieved, every one screened against explicit criteria, data extracted into predefined structures, every judgement documented so another team could reproduce it.

That care is expensive. A single review typically takes a specialist team weeks or months. The method persists anyway, because it was designed around a hard-won lesson: individual judgement, however expert, is biased in ways the person exercising it cannot see. The only defence is process. You do not trust the conclusion; you trust the procedure that produced it, and you make the procedure inspectable.

Keep that principle in mind, because it is the exact opposite of how most AI data-collection tools are built. Most of them ask you to trust the conclusion.

## What happens when you ask AI to do the most careful job in research

**In March 2026, a research team including collaborators from Oxford's [Reasoning with Machines AI Lab](https://www.oii.ox.ac.uk/research/research-groups/reasoning-with-machines-ai-lab/) published [AgentSLR](https://arxiv.org/abs/2603.22327), an open-source agentic AI pipeline for automating systematic literature reviews in epidemiology.** One of Tadeus's co-founders was part of that work. Applied to reviews of nine WHO-designated priority pathogens and validated against expert-curated ground truth, the pipeline compressed review timelines from roughly seven weeks to around twenty hours.

The headline number is striking. The methodology behind it is the part that matters here.

The team did not ask "can AI do a systematic review?" and declare victory on a plausible-looking output. They decomposed the workflow into stages, retrieval, screening, extraction, synthesis, and measured each stage separately against human reference annotations. They ran human-in-the-loop validation specifically to identify failure modes. And they published what they found: strong performance in some stages, persistent limitations in structured evidence extraction in others, and a clear-eyed conclusion that the right deployment model is human-supervised, not autonomous.

In other words: dramatic acceleration, honestly bounded. The work is as much a map of where AI evidence synthesis breaks as of where it excels. That is what evaluation looks like when the people doing it care more about being right than looking good.

## Why this is the reason to believe the signal-quality claim

**Tadeus's central claim is that a completed conversation is not the same as a trustworthy one, and that the difference can be measured.** Every voice session the platform runs produces, alongside its structured output, a behavioural quality score built from signals like response latency trends, answer compression across turns, and disengagement events. Sessions where the respondent was answering to finish rather than to communicate get flagged.

You could treat that as a feature. It is more accurate to treat it as an epistemology, and it is the same one that produced AgentSLR.

The connective tissue is a set of commitments about how the platform handles uncertainty:

Low-quality sessions are flagged, never suppressed. The researcher sees the flag and the data, exactly as a systematic review documents its excluded studies rather than silently dropping them.

Outputs carry their confidence with them. Insights derived from compressed, fatigued, or pressured respondents are contextualised as such, even when that makes the output look less polished than a competitor's.

Quality is assessed per stage, not asserted in aggregate. The platform instruments the conditions of collection turn by turn, rather than pointing at a completion rate and calling it validity.

These are uncomfortable commitments for a commercial product. A flagged session looks worse in a demo than an unflagged one. An uncertainty-labelled insight looks weaker than a confident summary. The willingness to carry that discomfort is not a branding choice. It is what a research-grade approach to data quality costs, and it is very hard to fake, because it shows up in the product's behaviour, not its copy.

## Why insights and research teams should pay particular attention

**The research industry has an acute version of the problem this solves.** AI-moderated interviews and synthetic-adjacent data collection are flooding qualitative research with volume. Fifty AI-conducted interviews can now be run in the time one human-moderated session used to take. What almost none of these tools can tell you is which of those fifty interviews contained a person who was actually thinking.

Researchers already know the failure modes by name: satisficing, straight-lining, professional respondents, panel fraud. The discipline has spent decades building detection heuristics for forms and panels. What it has not had is a collection instrument that measures respondent state natively, at the moment of collection, in the conversation itself.

That is what behavioural instrumentation of voice provides. Silence classified by type rather than treated as dead air. Engagement arcs tracked across the session. A quality score attached to every transcript before it reaches analysis. For an insights team, this changes the economics of scale: volume stops being a threat to validity, because validity travels with each record.

For HR and workforce buyers, this rigour arrives as a benefit. For research buyers, it arrives as the whole point. If your deliverable is evidence, an instrument that documents the conditions of its own data collection is not a nice-to-have. It is the difference between findings you can defend and findings you can only present.

## Trust is a track record of published honesty

**Anyone can write "data quality" on a landing page. What cannot be improvised is a history of doing evaluation the hard way, in public, with the failure modes included.**

The AgentSLR work is exactly that kind of history: open-source, benchmarked against expert ground truth, explicit about limitations, published where anyone can check it. The habits it represents, decompose the pipeline, measure each stage, surface uncertainty, keep the human in the loop where the evidence says you should, are the same habits that shaped how Tadeus scores, flags, and reports every conversation it runs.

So when the question is "why should I believe your quality scores mean anything?", the answer is not a promise. It is a paper, a methodology, and a product that behaves the same way the research does: honest about what it knows, explicit about what it doesn't, and built on the assumption that trust is earned through inspection, not assertion.

## Frequently asked questions

### How is Tadeus different from other AI-moderated interview tools?

Most AI interview tools optimise for volume and completion: more sessions, faster, with a transcript at the end. Tadeus treats the transcript as half the output. The other half is a behavioural record of the conditions under which it was produced: response latency, answer compression, silence patterns, engagement arc, summarised in a per-session quality score. Tools that don't instrument respondent state cannot distinguish a reflective participant from one racing to finish, because on paper the two can look identical.

### Is this only for HR use cases, or can research and insights teams use it?

The platform is a horizontal voice layer, and research is a natural fit. The behavioural quality framework was shaped by research-grade evaluation practice in the first place, so insights teams get the version of the product closest to its origins: adaptive qualitative conversations at scale, with per-session validity signals that survive into analysis and reporting.

### What does the quality score actually measure?

It is a 0 to 100 score derived from observable behavioural signals across the session, including trends in response latency, word-count compression across turns, and disengagement events. It does not judge the content of answers or the respondent as a person. It characterises the cognitive conditions of the session, so analysts can weight, segment, or follow up accordingly.

### Doesn't all this rigour slow the product down or hide data?

No. Scoring runs alongside collection, not as an extra step, and nothing is ever suppressed. Flags are surfaced to the analyst with the data attached. The design commitment is transparency over tidiness: you see everything that was collected, plus an honest account of how much weight it can bear.

### Where can I read the academic work?

The AgentSLR paper is openly available on [arXiv](https://arxiv.org/abs/2603.22327), and the pipeline itself is open source. The collaboration sits with Oxford's [Reasoning with Machines AI Lab](https://www.oii.ox.ac.uk/research/research-groups/reasoning-with-machines-ai-lab/), which works on reliable reasoning and evidence synthesis with AI systems.

## Sources

- [AgentSLR: Automating Systematic Literature Reviews in Epidemiology with Agentic AI](https://arxiv.org/abs/2603.22327), arXiv, March 2026, on automating the full systematic review workflow across nine WHO priority pathogens, validated against expert-curated ground truth, including identified failure modes and the case for human-supervised deployment.
- [Reasoning with Machines AI Lab](https://www.oii.ox.ac.uk/research/research-groups/reasoning-with-machines-ai-lab/), Oxford Internet Institute, the research group behind work on reliable machine reasoning and AI-assisted evidence synthesis.
