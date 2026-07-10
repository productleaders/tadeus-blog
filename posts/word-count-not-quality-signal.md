---
title: "A Word Count Is Not a Quality Signal"
pubDate: 2026-07-09
description: "Word count, duration and sentiment measure output, not presence. The behavioural factors that make a response quality score reproducible and explainable."
metaTitle: "A Word Count Is Not a Quality Signal"
metaDescription: "Word count, duration and sentiment measure output, not presence. The behavioural factors that make a response quality score reproducible and explainable."
heroImage: "images/word-count-not-quality-signal.webp"
heroImageAlt: "A Word Count Is Not a Quality Signal"
faqs:
  - question: "Is a longer employee response better than a shorter one?"
    answer: "No. Length measures verbosity, not thought. A concise answer from a present respondent often carries more signal than a padded one from someone performing effort. What matters is the behaviour around the answer, timing, compression and coherence, not the word count of the answer itself."
  - question: "Can a survey platform measure presence, or do you need a conversation?"
    answer: "A traditional survey can capture some timing data, but it can't produce inter-turn signal, because a form has no turns. Coherence between consecutive answers and the shape of an engagement arc only exist in a conversation. That structural difference is why conversational intelligence surfaces quality signals a static questionnaire cannot."
  - question: "What makes a quality score reproducible?"
    answer: "Reproducibility means the same session, scored twice, returns the same result, and stored inputs are what make the claim testable rather than taken on trust. If a score varies run to run, you can't build a reliable trend on it or defend it to leadership. The test is simple: fix the inputs, check the output is identical, and only then trust the number."
  - question: "Should skipped questions count against data quality?"
    answer: "Not automatically. A genuine abstention, someone declining because they have no real view, is higher-quality input than a fabricated answer given to clear the screen. Programmes that drive skips to zero often train people to fill boxes rather than tell the truth, which degrades the dataset while making the metrics look healthier."
  - question: "How do I explain a drop in the quality score to leadership?"
    answer: "Point at the factors, not the number. A defensible score resolves into named components, so you can say latency flattened, compression events rose, or coherence weakened in a specific team. That gives leadership something to act on and gives you something to re-measure once you've responded."
  - question: "Is measuring response timing surveillance of employees?"
    answer: "It is telemetry about the conversation, and the distinction is enforceable, not rhetorical. The signals are disclosed, scoped to the session, attached to data quality rather than to the person, and exportable as part of the conversation record. What they must never become is inference about emotional states, stress, or characteristics, which is prohibited in EU workplaces and unsupported by the science. Measure the conversation. Refuse to profile the person."
draft: false
---

**A long answer and a short answer tell you the same thing: how many words a person typed. Neither tells you whether they were present when they typed them.** Presence shows up in behaviour, not volume. It lives in how latency moves against question difficulty, in where a respondent compresses, in whether their answers cohere from one turn to the next, and in whether they abstain when they have nothing real to say. A defensible quality score is built from those factors, named and reproducible, not from a word count dressed up as depth.

Here's the scene most people analytics leads know too well. You're in front of the leadership team with a slide that says completion is up, sentiment is up, and the free-text responses are longer than last quarter. Someone asks the only question that matters: "So do people actually feel this way, or did they just click through?" And you don't have an answer, because your platform never measured the one thing being asked about. It measured output. It never measured whether a human was on the other side of the output.

The instinct, when you can't see presence, is to reach for a proxy you can see. Word count is the most seductive one. If someone wrote three paragraphs, surely they cared. Anyone who has read an employee's 400-word answer that says nothing, next to a 12-word answer that reframes the whole problem, already knows the instinct fails. But you don't have to take it on intuition, because the strongest evidence comes from the reader's own field. Survey methodology spent thirty years building a subfield around exactly this problem. It is worth opening that box before opening ours.

## How big is the problem, really?

**Big enough that survey science gave it a name, a literature, and a detection toolkit.** The canonical study, Meade and Craig in Psychological Methods, identified roughly 10 to 12% of respondents in a typical sample as careless, and the broader literature puts the modal rate at 8 to 12%, with a median around 10%. The mechanism was named by Krosnick three decades ago: satisficing. When motivation drops or the task drags, respondents stop optimising for accurate answers and start optimising for finishing, and at the extreme, satisficing becomes careless responding: answers with little or no validity that still fill every cell.

Two findings from that literature matter most here. First, contamination at even modest rates is not cosmetic. Simulation studies show that 5 to 10% careless responders in a dataset can meaningfully alter the conclusions of statistical analyses; the decisions built on the data inherit the noise. Second, the conditions that produce carelessness, low personal investment, long instruments, no human interaction, unproctored completion, describe the standard employee survey almost exactly. The 10% figure comes from students earning course credit. A tired shift worker clearing a notification at the end of a double has less reason to be careful, not more.

Survey researchers cope with attention-check items, consistency indices, and response-time screens. All retrofits, bolted onto an instrument that was never designed to know whether anyone was there. A conversation can be designed to know. So this piece opens the box: if a platform is going to claim a quality signal per response, you should be able to ask what it's made of and get a list, not a shrug.

## Why do the obvious proxies fail?

**Every naive proxy an analyst reaches for is confounded, because each one measures a downstream artefact of the answer rather than the conditions under which the answer was given.** Word count measures verbosity. Duration measures elapsed time. Sentiment positivity measures tone, and in large part acquiescence, the well-documented tendency to agree and answer favourably, which the survey literature treats as a bias to correct rather than a result to celebrate. None of them can separate a person thinking carefully from a person on autopilot, because both produce output, and output is all the proxy sees.

The failure is consistent enough to tabulate. On the left is the metric people trust. In the middle is what it actually measures once you're honest about it. On the right is the behavioural signal that gets at the thing the proxy was standing in for.

| What analysts reach for | What it actually measures | The behavioural alternative |
| --- | --- | --- |
| Word count | Verbosity, not thought | Response latency read against question difficulty |
| Response duration | Time elapsed on screen, not attention | Compression events across the session |
| Sentiment positivity | Tone and acquiescence, not honesty | Coherence between consecutive turns |
| Completion rate | That the screen advanced | The engagement arc across the whole session |
| Skipped questions, counted as failure | Avoidance treated as absence | Abstention treated as a signal in its own right |

Read the middle column on its own and the problem is obvious. A dataset can score perfectly on all five left-hand metrics and carry no information about whether anyone meant a word of it. That's not a small measurement error. It's the difference between a decision-ready dataset and a plausible-looking one.

## What actually indicates presence?

**Presence is a behavioural pattern, and it holds together across a session in ways autopilot can't fake.** No single factor proves it. What proves it is the combination: how a person's timing responds to difficulty, where they compress and where they expand, whether the session builds or decays, whether they decline rather than pad, and whether each turn is consistent with the ones around it.

Here is what goes into the box.

**Response latency against question difficulty.** Fast answers are not bad answers, and slow answers are not good ones. The signal is the relationship. When an easy question and a hard question draw the same instant response, that flat latency is the tell, because a present respondent slows down for the thing that deserves slowing down for. What you're reading is not speed but the *shape* of speed across questions of varying weight. A pause on a hard question is not delay. It's often reflective silence, the sound of someone actually working the problem.

**Compression events.** Response compression is where a respondent who was giving you texture suddenly starts giving you the shortest possible thing that lets them move on. It's not that short answers are bad. It's that a *transition* into terse, low-effort answers, part way through a session that started richer, marks the point where the person stopped participating and started clearing the screen. That transition is the audible onset of satisficing, detectable in the moment rather than in a post-hoc screen three weeks later. A word count averaged across the session hides it completely.

**The engagement arc.** Sessions have shape. Some build, as a respondent warms up and gives you more as trust grows. Some decay, as fatigue or indifference sets in. The engagement arc across the whole session tells you which one you got, and a single aggregate score, the kind most platforms report, flattens the arc into a number that could describe either.

**Abstention behaviour.** A respondent who says "I don't have a view on that" is giving you higher-quality data than one who invents a view to fill the box. Most platforms treat a skip as a failure to be minimised. That's backwards. Abstention, when it's genuine, is quality-checked input: the person declined rather than fabricated. Counting it as absence throws away one of the cleaner signals you have.

**Coherence between turns.** A present respondent contradicts themselves less, and when they do, they tend to be aware of it. Coherence between consecutive turns, whether answer three is consistent with answer one, is something you can assess in a conversation but not in a form, because a form has no turns. This is where conversational intelligence earns its place over the static questionnaire, and it is the conversational descendant of the consistency indices survey science already uses, computed on meaning rather than on grid patterns. The structure of a conversation gives you inter-turn signal that a survey grid physically cannot produce.

Put those together and you're no longer asking "how much did they write". You're asking "did the way they moved through this session look like someone who was there". That's a different question, and it's the right one.

## What makes a quality score trustworthy?

**A quality score is only worth acting on if it clears three bars: it's derived from stored inputs, so the latencies, compression counts, abstention states and coherence measures it came from are kept with it rather than discarded after computation; it's reproducible, meaning the same inputs produce the same result; and it's explainable, meaning it resolves to a named list of factors rather than an opaque number.** Miss any of them and you've replaced one thing you can't defend with another.

Stored inputs are what make the other two checkable. A score whose ingredients were thrown away can claim to be reproducible; a score whose ingredients travel with it can prove it, which is why the conversation-record specification published earlier in this series requires exactly that.

Reproducibility is the one analysts underrate. If the same session, run twice, can yield two different scores, then the score is a mood, not a measurement, and you cannot build a trend on it. The standard here is boring on purpose: fixed inputs, fixed output, every time. That's the floor before anyone talks about what the score means.

Explainability is the one leadership will eventually demand. When a score drops in one team, "the model says so" is not an answer you can take into a room. "Latency flattened, compression events rose in the back half, and abstention fell while coherence held" is. A named factor list means you can point at *why* a score moved, and point at the same factors next quarter to see if the fix worked. An opaque number gives you a chart with no handle on it.

And this standard has to apply to us first. It would be easy to write this and then ship a black box, so the honest version is narrower than the marketing version. The behavioural principles above, latency against difficulty, compression, the arc, abstention, coherence, are the factors a presence score should be built from and the ones a buyer is right to ask to see broken out. The reproducibility bar, same inputs same result, is a commitment we hold ourselves to, not a claim about a magic number. If a vendor, us included, can't hand you the factor list and show you the score is stable, treat the score as decoration.

## What should a low score change?

**Two things, and neither of them is "delete the session."** Deleting low-presence sessions is the analyst's instinct and it is quietly destructive: it silently re-biases the dataset toward the people with the time, language and conditions to answer carefully, which, as the previous post in this series argued, is its own systematic error wearing a hygiene label. The right verb is flag. Low-confidence sessions are weighted, contextualised, and carried visibly, so the board deck can say "412 of 4,000 sessions carried low behavioural confidence and are reported separately" instead of pretending the dataset is uniform. Flagged honesty survives scrutiny. Silent cleaning does not.

The second thing a low score should change is your questions. Presence scores critique the instrument at least as often as the respondent. If question six produces compression events across every cohort, question six is bad: too long, too abstract, or asked after fatigue has set in. If abstentions cluster on one topic at one site, that is a finding about trust at that site, not missing data. The score's most valuable use is not filtering a dataset after the fact but improving the conversation design before the next campaign, which is how a listening programme compounds instead of repeating itself.

## But don't people just write more when they care?

**Sometimes, and that's exactly why word count fails, because it's right often enough to feel trustworthy and wrong often enough to mislead a real decision.** The correlation between caring and writing more is real but weak, and it collapses under the two cases you most need to catch.

Case one: the disengaged over-writer. Some people pad. They produce volume precisely because they're performing effort rather than thinking. Word count rewards this respondent. Behavioural signal doesn't, because the padding shows up as flat latency and thin coherence.

Case two: the engaged compressor. Some of your most present respondents are concise. They say the true thing in one line and move on. A word-count proxy scores them as low quality and buries the sharpest input you received.

So the counter-argument isn't wrong that effort sometimes correlates with length. It's wrong that the correlation is strong enough to run a listening programme on. You don't want a metric that's right on average and wrong on the exact respondents whose data would change your decision.

## What a presence score cannot tell you

Three honest limits, each of which will otherwise arrive as a hostile comment. Presence is not truthfulness: a fully engaged respondent can lie beautifully, no timing pattern detects it, and a presence score should never be built, bought, or marketed as a lie detector. Pacing is personal: baseline rhythm varies by individual, language, and neurotype, so every signal must be read against the person's own within-session baseline, never a population norm, and a first conversation deserves wider error bars for exactly that reason. And the line this series drew earlier holds absolutely: these are interaction signals, disclosed, scoped to the session, in service of data quality. The moment they shade into inferring emotional states or characteristics, they cross from measuring the conversation into profiling the person, which is where the science stops supporting and EU workplace law stops permitting.

## What this means if you own the dataset

If you're the person who defends the numbers to leadership, the shift is practical, not philosophical.

- **If you report engagement, stop leading with completion.** Report the quality score alongside it, and be ready to say what the score is made of. Completion tells you the screen advanced. It was never a claim about presence, and treating it as one is where the trust erodes.
- **If you run a listening programme, treat abstention as data, not leakage.** Stop driving skips to zero. A genuine "no view" is cleaner than a fabricated view, and a programme that punishes abstention is training people to fill boxes.
- **If you're evaluating a platform, ask for the factor list, the stored inputs, and the reproducibility test.** Ask what the quality signal is composed of and whether the same session scores the same twice. If the answer is a single number with no anatomy, you're being sold volume with better packaging.
- **If you brief your data science colleague, hand them this and the questions in it.** They will ask whether the factors are confounded, whether latency is normalised against difficulty, and whether the score is stable. Those are the right questions, and they are the same ones their own field asks of survey data. A platform that can answer them is measuring presence. One that can't is counting words.

The category has spent two decades getting very good at collecting more and telling you almost nothing about whether any of it was meant. A word count was never a quality signal. It was the most convincing thing that was easy to measure. The next era of workforce intelligence belongs to the platforms that can tell whether a human was actually present when they answered, and can show you exactly how they know.

## Frequently asked questions

### Is a longer employee response better than a shorter one?

No. Length measures verbosity, not thought. A concise answer from a present respondent often carries more signal than a padded one from someone performing effort. What matters is the behaviour around the answer, timing, compression and coherence, not the word count of the answer itself.

### Can a survey platform measure presence, or do you need a conversation?

A traditional survey can capture some timing data, but it can't produce inter-turn signal, because a form has no turns. Coherence between consecutive answers and the shape of an engagement arc only exist in a conversation. That structural difference is why conversational intelligence surfaces quality signals a static questionnaire cannot.

### What makes a quality score reproducible?

Reproducibility means the same session, scored twice, returns the same result, and stored inputs are what make the claim testable rather than taken on trust. If a score varies run to run, you can't build a reliable trend on it or defend it to leadership. The test is simple: fix the inputs, check the output is identical, and only then trust the number.

### Should skipped questions count against data quality?

Not automatically. A genuine abstention, someone declining because they have no real view, is higher-quality input than a fabricated answer given to clear the screen. Programmes that drive skips to zero often train people to fill boxes rather than tell the truth, which degrades the dataset while making the metrics look healthier.

### How do I explain a drop in the quality score to leadership?

Point at the factors, not the number. A defensible score resolves into named components, so you can say latency flattened, compression events rose, or coherence weakened in a specific team. That gives leadership something to act on and gives you something to re-measure once you've responded.

### Is measuring response timing surveillance of employees?

It is telemetry about the conversation, and the distinction is enforceable, not rhetorical. The signals are disclosed, scoped to the session, attached to data quality rather than to the person, and exportable as part of the conversation record. What they must never become is inference about emotional states, stress, or characteristics, which is prohibited in EU workplaces and unsupported by the science. Measure the conversation. Refuse to profile the person.

## Sources

- [Meade and Craig, Identifying Careless Responses in Survey Data](https://psycnet.apa.org/record/2012-10015-001), Psychological Methods, 2012, on the 10 to 12% careless responding rate and detection methods.
- Krosnick, Response Strategies for Coping with the Cognitive Demands of Attitude Measures in Surveys, Applied Cognitive Psychology, 1991, on satisficing as the mechanism behind low-effort responding.
- [Careless responding and its systematic effects on reliability, validity, and measurement invariance](https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2026.1815225/full), Frontiers in Psychology, 2026, on the 8 to 12% modal prevalence and the simulation evidence that 5 to 10% contamination alters statistical conclusions.
- The Compliance Conversation Record: A Proposed Specification (v0.1), earlier in this series, on the quality score's required properties: stored inputs, reproducibility, explanation export.

## Researched with AI. Argued, verified, and signed off by humans. That's also how we think AI should work everywhere.
