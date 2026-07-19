---
title: "The Missing Tool in Every Agent Stack: Asking a Human"
pubDate: 2026-07-19
description: "Agents need ground truth from people. Forms return text with no reliability signal. Tadeus returns scored, structured voice answers an agent can trust."
metaTitle: "The Missing Tool in Every Agent Stack: Asking a Human"
metaDescription: "Agents need ground truth from people. Forms return text with no reliability signal. Tadeus returns scored, structured voice answers an agent can trust."
faqs:
  - question: "What is the quality score actually measuring?"
    answer: "It's a per-session measure of how present and engaged a person was during a single voice conversation, read from behavioural signals like response compression, hesitation, and the arc of the exchange. It measures the conditions under which the answer was given, not whether the answer is factually correct, and it is reproducible from stored inputs rather than a judgement call."
  - question: "Can an agent commission these conversations without a human in the middle?"
    answer: "Split the verb. Querying results, yes: a connected agent reads structured, scored outcomes over a scoped, read-only connection and reasons over them autonomously. Initiating conversations, no: an agent can draft the questions and propose the population, but a named person approves every campaign, because the disclosure duty, the oversight requirements and the works council questions apply regardless of what triggered the ask. The human effort in the middle was never the bottleneck worth removing; the human accountability is the part that keeps the channel deployable."
  - question: "How is this different from sending a survey through an agent?"
    answer: "A form has no turns. A survey API distributes a static instrument and returns text and a completion rate with no signal about reliability. This returns typed, queryable answers plus a per-session quality score and a behavioural profile of how the conversation actually went. The agent gets both the answer and a confidence level on it, which a survey can never provide."
  - question: "Does the behavioural profile claim to know how employees feel?"
    answer: "No, and it is built to refuse the inference rather than guess at it. It reports observable conversational behaviour, hesitation on a specific question, a pace shift across a session, never emotional states, private motives, health conditions or diagnoses. In the EU workplace that refusal is not just good science, it is the legal line: emotion inference at work is prohibited, and a tool for agents inherits that boundary in full."
  - question: "Is an agent even allowed to initiate an AI conversation with employees?"
    answer: "The obligations do not care who initiated. Disclosure at first contact applies from August 2026 whether a human or a workflow triggered the campaign, the deployer duties on worker information and oversight stand, and in codetermined Europe the works council questions arrive identically. Practically, agent-initiated asks need a named human approver, a documented purpose, and a per-conversation record, which is the same evidence discipline this series has specified all along."
draft: false
---

**Every agentic system eventually hits the same wall: it needs ground truth from people, and the only options on the shelf are a static form, slow to type responses, trasncription with text response, or a human researcher. A form and other options returns text with no reliability signal. A researcher does not scale to thousands of conversations. There is now another woption: an agent commissioning structured voice conversations with real people, and getting back answers that carry a machine-readable measure of how much to trust each one.**

Picture the wall in a specific shape. An agent is rolling out a new shift policy across a distribution network. Before the policy goes live, someone needs to know whether roughly 400 warehouse staff actually understood the change, or whether they clicked through the acknowledgement to clear the notification off their phone. The agent has two moves. It can fire a survey link and read back a completion rate. Or it can hand the question to a human research team and wait a fortnight for a deck.

Neither returns something the agent can reason over with any confidence. The survey gives it a number that looks like understanding and isn't. The research team gives it a narrative it can't query, weeks after the decision had to be made. So the agent does what agents do when a tool is missing: it guesses, or it stops.

## Why has "ask a human" never been a real tool?

**The loop is simple to describe and, until recently, impossible to build: an agent asks another agent to ask humans, and gets a trustworthy, structured answer back. That loop needed three things at once, and no single tool had all three.**

There is a deeper reason the wall exists at all, and a philosopher named it sixty years ago. Polanyi's observation, that we know more than we can tell, and far more than we ever write down, describes exactly the knowledge agents cannot reach: the near-miss that never became an incident report, the workaround that became the process, the real reason new starters walk in week three. Every tool in the standard agent stack reads what machines already recorded. Tacit knowledge was never recorded, so retrieval cannot retrieve it and SQL cannot join against it. The only interface it has ever had is being asked.

The pieces the asking-tool needed are worth naming, because their absence explains twenty years of bad workforce data.

**Real-time voice people will actually talk to.** The science here is unforgiving. Human turn-taking runs on a roughly 200 millisecond rhythm, consistent across languages from Danish to Japanese, and when a system drifts from that rhythm the brain quietly reclassifies the exchange: not a conversation, a form with a voice bolted on. People disengage, and disengaged people produce the same noise a survey does. Text forms get autopilot answers. A conversation that holds human rhythm, adapts, and follows up gets closer to what people mean.

**Structured output.** A recording is not a tool result. An agent needs typed, timestamped, queryable fields, not a transcript it has to re-parse on every call.

**A quality layer.** Without a measure of how much to trust each answer, structured output is just tidier guessing.

Research teams have the first. Survey platforms have the second. Nothing had all three, which is why the wall has stood for as long as agents have existed.

The idea is in the air now. Noam Schwartz has described how [AI agents just got a new tool: humans](https://www.linkedin.com/posts/noamsp_ai-agents-just-got-a-new-tool-humans-activity-7425538835125768192-q7mp), pointing at projects that let an agent book a real person to run an errand in the physical world. On Hacker News, a thread asking [when we expose "humans as tools" so agents can call us on demand](https://news.ycombinator.com/item?id=46456400) drew the obvious comparison to Mechanical Turk, and the equally obvious objection: the hard part is asking the question in a way the human can meaningfully answer, and knowing what their answer is worth.

That second half is where every existing source falls down. Production agents run a perceive, reason, act, observe loop and write each result to memory. The loop is only as good as what it observes. Feed it a survey completion rate and it observes a fiction.

We wrote in the previous post that your next buyer might be an agent, reading your documentation and evaluating you before a human ever visits your site. That was agents evaluating this infrastructure. This is agents putting it to work. Reading is evaluation. Commissioning is procurement.

## What does an agent get back that a form never gave it?

**Every input an agent consumes today arrives naked. A database row, an API response, a scraped page, a form submission: all content, no metadata about how reliable that content is. Our platform returns the answer plus a per-session quality score and a behavioural profile of the conversation. For a human researcher, that scoring is a weighting aid. For an agent, it's a confidence level on a human input.**

This is the part that matters, so let's be precise about what the score is and isn't.

The quality score reads the conditions under which an answer was given. Did the person engage with the question or compress their way to the exit? Did the conversation have an arc, or did it flatline into completion mode? Two respondents can produce identical transcripts, one thinking carefully and one clicking to make the screen go away, and every text-based tool is blind to the difference. The score is built to catch exactly that difference.

The behavioural profile measures conversational behaviour signals. Hesitation before a specific answer. Pace shifts across a session. Where someone slowed down and where they raced. These are observable properties of how a person spoke, not claims about what they secretly feel, and the line matters legally as much as scientifically: inferring emotional states in the workplace is prohibited territory under the AI Act, and the science never supported it anyway. The layer does not read minds and it refuses to pretend it can. It won't infer a private motive, an emotional state, a health condition, or a diagnosis from the way someone paused. It reports that they paused, on which question, and how that compares across the campaign. It also returns abstention as a first-class result: an agent must be able to distinguish "the humans declined to say" from "the humans were not asked," because those imply opposite next actions.

Here's the line that separates this from every other source an agent can call:

> The only human-input source that tells the machine how much to trust the human.

For the HR director reading this, that's the difference between defending an engagement number to a sceptical board and handing them a dataset that says, per response, how present the person was when they gave it. You stop arguing that a 92% completion rate means understanding. You start showing which responses carried signal and which were noise, and you can see quality degrading on a question before it becomes a business problem.

| What an agent asks for | Static form returns | Human researcher returns | This layer returns |
|---|---|---|---|
| Did staff understand the policy? | Completion rate, free text | A narrative, weeks later | Structured answers per person, quality-scored |
| How reliable is each answer? | Nothing | Researcher's judgement, not queryable | Machine-readable quality score per session |
| Where did people hesitate? | Invisible | Sometimes noted, inconsistently | Flagged per question, per session |
| Can I query it in real time? | No | No | Yes |

That single property changes what an agent can responsibly do with human data. It can weight evidence instead of averaging it. It can flag low-confidence cohorts for follow-up instead of reporting them as fact. It can tell its operator: the answer is yes, with high confidence from 340 sessions and low confidence from 60, and here is which 60.

One design note that inverts this series' usual obsession, deliberately. Inside a conversation, 200 milliseconds decides everything, because a human brain judges the rhythm. Outside it, the caller is an agent, and agents wait well. A tool that returns rich, verified answers from 400 people in hours is a superb tool by agent standards; the survey era's real failure was never that answers took time, it was that they came back months later, unstructured and unverifiable. Fast inside the conversation, patient around it.

## How an agent actually commissions this

**You connect an agent, ask in plain language, and reason over the results. There's no schema to memorise and no export step. Access is scoped, read-only, and header-based, so the connected agent reads campaign results and nothing else.**

If you've wired up any connector before, this will feel familiar. The point is not the mechanics, it's what becomes askable once the connection exists. Three prompts that are real questions, not demos:

**1. "Show me the presence distribution across this campaign."** Instead of one blended score, you get the shape of the whole population. Where did engagement cluster high, where did it thin out, and does that map to a location, a shift, or a manager.

**2. "List every session where someone hesitated on the question about the new overtime rule."** Not the average sentiment on that question. The specific sessions where the behaviour signal fired, so you can look at what those people actually said rather than reading a mean and moving on.

**3. "Correlate quality score with completion."** This is the one that tends to land hardest, because it often shows the two are not the same thing at all. High completion with low quality is the pattern that has been hiding in workforce data for two decades. An agent can now surface it in one query.

None of this asks you to retire your reporting. Your analysis layer is wherever your agent lives, and as the models improve, your analysis improves with them, without waiting on anyone's dashboard roadmap. Your agent becomes another dashboard.

Two guardrails belong inside the tool rather than in a policy document, and they are where the asking side differs from the reading side. First, initiating conversations keeps a named human on the loop: an agent can draft the question set and propose the population, and a person approves the campaign, because occupying a workforce's attention is a management act, not a tool call, and the disclosure, oversight and works council duties this series has mapped apply identically whether a human or a workflow pressed go. Second, a fatigue budget, because this is the rate-limit problem nobody building agent tools has faced before: databases do not get tired of being queried, and humans do. A machine that can ask ten thousand people at near-zero marginal cost will over-ask by default, so the caps, the spacing between campaigns, and the action-gap obligation to route answers somewhere visible have to live in the primitive. An agent that asks and never answers back is a futility engine with an API.

## What this changes about the "human in the loop"

**Most of the industry means one thing by human-in-the-loop: a person approving or correcting an agent's output. The human sits at the end, checking the machine's work. This inverts it. Here the humans are the source, and the loop that reaches them, structures what they say, and scores it is the infrastructure.**

The prevailing model puts people on either side of the agent as a check on quality, the arrangement one team has described as a [human sandwich with humans as the bread](https://www.youtube.com/watch?v=GWPpLdpTo90). Useful, but it treats human input as the thing to be verified. The workforce case runs the other way. The humans hold the ground truth. The agent's job is to reach thousands of them, in every language, in the time a decision allows, and to come back with answers it knows how much to trust. The agent does not slow down to include people. It gets smarter because it can finally reach them.

There is one strange advantage worth naming, because the oldest finding in this series does its best work here. People disclose more to a disclosed machine than to a person, because the machine sits outside the org chart and cannot judge. An agent-initiated conversation inherits that in full: the picker explaining week-three attrition to an AI interviewer that announced itself is measurably more candid than the same picker explaining it to her manager. The tool gets more truth than a human asking would have, precisely because it never pretended to be one.

That's the frame worth holding onto. Workforce software spent two decades optimising for administrative efficiency and, in the process, destroyed the thing it existed to collect: trustworthy human signal. It measured whether people finished, not whether they meant it. An agent that can commission scored, structured voice conversations closes that gap, because for the first time the tool that asks the human can also tell you whether a human was really there.

The platforms that run working life were the first place this mattered. They will not be the last. Anywhere an agent needs to know what people understood, believed, or felt, the missing tool is the same: a way to ask, at scale, with a trust signal attached. The requirements were never really technical. They were the same requirements honest listening always had.

The agents are ready to ask. The question is whether your stack can answer.

## Frequently asked questions

### What is the quality score actually measuring?

It's a per-session measure of how present and engaged a person was during a single voice conversation, read from behavioural signals like response compression, hesitation, and the arc of the exchange. It measures the conditions under which the answer was given, not whether the answer is factually correct, and it is reproducible from stored inputs rather than a judgement call.

### Can an agent commission these conversations without a human in the middle?

Split the verb. Querying results, yes: a connected agent reads structured, scored outcomes over a scoped, read-only connection and reasons over them autonomously. Initiating conversations, no: an agent can draft the questions and propose the population, but a named person approves every campaign, because the disclosure duty, the oversight requirements and the works council questions apply regardless of what triggered the ask. The human effort in the middle was never the bottleneck worth removing; the human accountability is the part that keeps the channel deployable.

### How is this different from sending a survey through an agent?

A form has no turns. A survey API distributes a static instrument and returns text and a completion rate with no signal about reliability. This returns typed, queryable answers plus a per-session quality score and a behavioural profile of how the conversation actually went. The agent gets both the answer and a confidence level on it, which a survey can never provide.

### Does the behavioural profile claim to know how employees feel?

No, and it is built to refuse the inference rather than guess at it. It reports observable conversational behaviour, hesitation on a specific question, a pace shift across a session, never emotional states, private motives, health conditions or diagnoses. In the EU workplace that refusal is not just good science, it is the legal line: emotion inference at work is prohibited, and a tool for agents inherits that boundary in full.

### Is an agent even allowed to initiate an AI conversation with employees?

The obligations do not care who initiated. Disclosure at first contact applies from August 2026 whether a human or a workflow triggered the campaign, the deployer duties on worker information and oversight stand, and in codetermined Europe the works council questions arrive identically. Practically, agent-initiated asks need a named human approver, a documented purpose, and a per-conversation record, which is the same evidence discipline this series has specified all along.

## Sources

- [Universals and cultural variation in turn-taking in conversation](https://www.pnas.org/doi/10.1073/pnas.0903616106), PNAS, Stivers et al. The cross-language study establishing the roughly 200 millisecond turn-taking rhythm that real-time voice systems are judged against.
- [Response strategies for coping with the cognitive demands of attitude measures in surveys](https://onlinelibrary.wiley.com/doi/10.1002/acp.2350050305), Applied Cognitive Psychology, Krosnick. The foundational account of satisficing: why survey respondents produce answers that look structured but carry no reliability signal.
- Polanyi, The Tacit Dimension, 1966, on tacit knowledge: we know more than we can tell, the knowledge no retrieval system can reach.
- Lucas, Gratch, King and Morency, It's Only a Computer: Virtual Humans Increase Willingness to Disclose, Computers in Human Behavior, 2014, on greater candour with disclosed machine interviewers.
- [Introducing the Model Context Protocol](https://www.anthropic.com/news/model-context-protocol), Anthropic. The open standard that lets AI agents discover and use external tools, the mechanism through which agents connect to conversation platforms.
- [AI agents just got a new tool: Humans](https://www.linkedin.com/posts/noamsp_ai-agents-just-got-a-new-tool-humans-activity-7425538835125768192-q7mp), Noam Schwartz, LinkedIn. Frames the shift from automating people to agents commissioning human work.
- [Ask HN: When do we expose "Humans as Tools" so LLM agents can call us on demand?](https://news.ycombinator.com/item?id=46456400), Hacker News. Community discussion of exposing humans as callable tools and the reliability problem it raises.

## Researched with AI. Argued, verified, and signed off by humans. That's also how we think AI should work everywhere.
