---
title: "Build vs Buy: Why Every Major HCM Vendor Will Have a Voice Layer by 2028 (and Almost None Will Build It)"
pubDate: 2026-07-05
description: "Every major HCM platform will offer real-time voice soon, but almost none will build it. Why embedding voice via API beats a multi-year in-house build."
metaTitle: "Voice Layer for HCM: Build vs Buy by 2028"
metaDescription: "Every major HCM platform will offer real-time voice soon, but almost none will build it. Why embedding voice via API beats a multi-year in-house build."
heroImage: "images/hcm-voice-layer-build-vs-buy.webp"
heroImageAlt: "Voice Layer for HCM: Build vs Buy by 2028"
faqs:
  - question: "How long does it take to build a production-grade real-time voice layer?"
    answer: "For a team starting from a speech API, industry estimates run from 4 to 9 months for a basic production agent to 12 to 24 months for enterprise grade across multiple languages. The demo is quick. The hard tail is latency tuning, turn detection, silence handling, and reliable structured output, and each of those has to work together before the experience feels like a real conversation."
  - question: "Isn't voice just a speech-to-text API plus a language model?"
    answer: "No. Speech-to-text and a language model are two components in a longer chain that also includes turn detection, silence interpretation, multi-language recognition, sub-second latency management, and conversion into structured, timestamped data. Stitching those together reliably at scale is the actual product, and it is where most in-house builds stall."
  - question: "What do we keep control of if we embed voice rather than build it?"
    answer: "Everything that differentiates you. Your proprietary data, your workflow logic, your semantic model, and the structured signal you act on all stay yours. The voice layer is shared infrastructure that feeds those systems. Embedding it means you keep the intelligence and skip the plumbing that commoditises quickly."
  - question: "When is building voice in-house the right call?"
    answer: "When real-time conversation is itself the product you sell, when you can fund a permanent team to own it, and when you can carry the high-risk conformity obligations on your own timeline. For platforms where voice is an interface to their core offering rather than the offering itself, those conditions rarely all hold, so buying or embedding almost always wins."
  - question: "What should we evaluate in a voice layer before embedding it?"
    answer: "Measured latency under production load rather than demo conditions, behaviour under noise and accents, what the structured output contract looks like, and the conformity posture: logging, documentation, explanation export, and what the system provably does not infer about the people it talks to. That last item is the one most providers cannot answer, and it is the one your own regulatory file will depend on."
draft: false
---

**Nearly every serious HCM platform will offer a real-time voice interface within a few years, because employees increasingly expect to talk to the systems that run their working life rather than fill in forms. Almost none of those vendors will build the voice layer themselves. They will buy it, or embed it via API, because real-time voice is a multi-year engineering problem that sits well outside their core roadmap, returns very little defensible advantage for the years it swallows, and now arrives bundled with a regulatory conformity programme on a fixed deadline.**

That is the whole argument. The rest of this piece is the reasoning, because "buy it" is easy to say and expensive to get wrong.

The 2028 date is not a hunch, incidentally. It is arithmetic. High-risk obligations for employment AI under the EU AI Act land on 2 December 2027, and a from-scratch voice build takes one to two years to reach production quality. Any vendor deciding today faces both clocks at once, which is precisely why the decisions being made this year are embed decisions.

Voice looks deceptively simple from the outside. You speak, the system answers, the words come back as text. Product leaders sketch it in a planning session and assume it is a quarter of work sitting on top of a speech API. It is not. The gap between a demo that works on stage and a voice layer that holds up across dozens of languages, noisy warehouses, and a million employees is where two years of a roadmap quietly disappears.

## Build vs buy for a voice layer, at a glance

**For core HCM platforms, buying or embedding a voice layer wins on almost every dimension that matters: time to ship, engineering cost, ongoing maintenance, regulatory burden, and opportunity cost against your actual roadmap. Building only makes sense if real-time conversational voice is itself the product you intend to sell.**

| Dimension | Build in-house | Embed via API |
|---|---|---|
| Time to first production release | 12 to 24 months ([industry estimates](https://www.lumay.ai/blogs/best-build-vs-buy-ai-voice-agent-guide)) | Weeks |
| Year-one cost | [$800K to $2.3M for enterprise-grade](https://www.lumay.ai/blogs/best-build-vs-buy-ai-voice-agent-guide); [$250K to $2M by broader estimates](https://techsy.io/en/blog/build-vs-buy-ai-voice-agent) | Integration engineering plus usage |
| Core engineering needed | Latency, turn detection, silence handling, ASR tuning, output schemas | Integration and schema mapping only |
| Multi-language coverage | Built and maintained language by language | Included, maintained by the provider |
| Ongoing maintenance | Permanent team, plus model drift as providers update | Provider's responsibility |
| Regulatory conformity (EU AI Act, Annex III) | Yours to build and evidence by Dec 2027 | Arrives largely packaged with the layer |
| Roadmap opportunity cost | High, competes with core features | Low, roadmap stays on core |
| Defensibility gained | Low, unless voice is your product | Comes from your data and workflows, not the voice plumbing |

The pattern here is not new. Software teams don't buy because they can't build; they buy because the maths works out, and the maths is about change over time. For a workforce platform, the maths on voice rarely works out in favour of building.

## What does it actually take to build real-time voice?

**Real-time voice is a latency problem, a turn-taking problem, a silence problem, a language problem, and a data-structure problem, all at once, and all of them have to be solved together before the experience feels like a conversation rather than a walkie-talkie. Getting any one of them wrong makes the whole thing feel broken, which is why partial builds tend to stall.**

Break it down and the scope becomes clear.

**1. Sub-second latency.** Human conversation runs on a turn-taking gap of roughly [200 milliseconds, and anything above about 800 milliseconds end-to-end starts to feel like a machine](https://www.famulor.io/blog/ai-voice-agent-latency-how-fast-your-phone-bot-must-reply). You are chaining speech recognition, a language model, and speech synthesis, and the whole round trip has to land inside a budget you barely have. The sobering benchmark: [in-house builds routinely land at 1.2 to 2 seconds](https://techsy.io/en/blog/build-vs-buy-ai-voice-agent), because teams don't budget for network jitter, cold-start model calls, and streaming synthesis. At that latency the conversation is already dead; the caller just hasn't hung up yet.

**2. Turn detection.** Knowing when the person has actually finished speaking, rather than pausing mid-thought, is genuinely hard. The most-cited number in voice AI is that [callers start talking over the agent at around 0.4 seconds](https://techsy.io/en/blog/build-vs-buy-ai-voice-agent) of dead air: that is the line where natural turn-taking breaks. Cut people off and they stop trusting the system. Wait too long and it feels sluggish. This is a signal-processing and modelling problem that most teams underestimate by an order of magnitude.

**3. Silence handling.** A pause is not always hesitation. Sometimes it is someone thinking carefully before they answer, and treating that pause as a dropped call or an empty response throws away the most valuable moment in the exchange. The system has to hold space without breaking the flow, and it has to distinguish thinking from disengagement from a genuinely dead line.

**4. Multi-language.** A workforce platform serves people across dozens of markets. Voice has to work in each of them, including accents, code-switching, and the languages your speech models were not primarily trained on. This is not a translation layer bolted on afterwards. It has to be present in recognition, turn detection, and output.

**5. Structured output schemas.** A transcript is not the deliverable. The platform needs timestamped, structured input it can route back into workflows, which means every conversation has to resolve into clean fields against a schema, reliably, at volume. This is the part that turns a voice toy into workforce intelligence, and it is the part demos skip.

And none of it is ship-once. Underlying speech and language models update on their providers' schedules, and every update can silently change your agent's behaviour. The industry calls this the [maintenance tax](https://www.haptik.ai/blog/voice-ai-build-vs-buy): a permanent engineering commitment to keep yesterday's quality under tomorrow's models. Telecom went through a version of this and it is instructive. The industry spent years making "buy" viable for messaging and basic telephony, yet as SignalWire's team note, [voice lagged behind](https://signalwire.com/blogs/ceo/build-vs-buy-in-telecom) even as building on top of platforms became mainstream elsewhere. Real-time voice is simply a harder tier of the problem.

## What changed the maths: the conformity clock

**Building voice in-house no longer just means owning the engineering. Voice in employment workflows is high-risk AI under the EU AI Act, and the [Annex III obligations now land on 2 December 2027](https://www.consilium.europa.eu/en/press/press-releases/2026/05/07/artificial-intelligence-council-and-parliament-agree-to-simplify-and-streamline-rules/): risk management, data governance, technical documentation, logging, accuracy and robustness evidence, human oversight. Build the layer and you build all of that too, for a capability outside your core competence, on a regulator's timetable.**

There is a sharper edge inside that. Article 5 has prohibited emotion inference in the workplace since February 2025, and voice is exactly the modality where models infer things nobody asked them to: mood, stress, demographic traits. A vendor building in-house owns the problem of proving its system does not do what the law prohibits. That is a research-grade evaluation problem, not a feature ticket, and it lands on the same team already fighting the latency budget.

Run the two clocks together and the build case collapses on timing alone. A build started this quarter reaches production quality somewhere between mid 2027 and mid 2028, straddling the compliance deadline with an unproven system and an unwritten conformity file. A specialist layer amortises the latency engineering, the evaluation infrastructure, and the conformity work across every platform it serves. The buy case is no longer "faster to market." It is that the conformity burden is now part of the build cost, and it is the part with a fine attached.

## Why building it is a distraction from your core roadmap

**Building voice pulls your best engineers onto a problem that does not differentiate your product, for the one to two years it takes to get right, while your competitors ship features your customers actually asked for. The cost is not just the build. It is everything you didn't build instead.**

Here is the trap. A voice layer, once it works, feels essential. But the work to get there is almost entirely undifferentiated plumbing. Latency tuning and turn detection do not make your talent module better than the next vendor's. They just make voice function. You will have spent two years and a senior team reaching parity on infrastructure that a specialist provider already runs for everyone.

Josh Bersin's take on the wider build-versus-buy question in HR applies directly. He warns that [it is not as easy as it looks](https://joshbersin.com/podcast/build-vs-buy-its-so-easy-to-build-hr-software-now-or-is-it), even as AI tooling makes the first 80% feel trivial. And that last 20% is exactly where voice lives. The martech world found the same thing. Off-the-shelf gets you most of the way, but the [remaining fraction](https://newsletter.chiefmartec.com/p/build-vs-buy-is-the-wrong-question-for-martech-ai), the calibration and the guardrails, is where the real effort concentrates. For voice, the whole product is that last fraction.

There is a version of building that makes sense. Bersin describes organisations that are engineering-led to the point of perfectionism, where the integrated experience genuinely is the competitive edge and buying an off-the-shelf part feels like a compromise on the thing they sell. But for a workforce platform, voice is not the thing you sell. Your data, your workflows, and your relationship with the customer are. Voice is how people reach them.

## Where does the real defensibility come from, then?

**Your advantage was never going to come from owning the voice plumbing. It comes from what the voice layer feeds: your proprietary data, your workflow logic, and the structured signal you can act on that nobody else has. Embedding voice lets you keep all of that and skip the part that commoditises fast.**

The horizontal-versus-vertical framing from the AI world is the cleanest way to see this. As Gloat's team argue, [horizontal platforms give you the engine](https://gloat.com/academy/build-vs-buy-horizontal-ai-hr), but the real intelligence comes from the fuel, the map, and the driver who understands the domain. Voice is the engine. It is powerful, it is hard to build, and it is fundamentally shared infrastructure. The parts that are yours sit on top of it.

This also reframes the decision most CIOs are actually making. The sharper question, as one analysis puts it, [is not build versus buy but how to combine the two](https://www.cio.com/article/4097339/your-next-big-ai-decision-isnt-build-vs-buy-its-how-to-combine-the-two.html), embedding shared capability layers while keeping your semantic model and governance in-house. A voice layer accessed via API is precisely that combination. You buy the conversation. You keep the intelligence.

There is a timing argument too. HR tech stacks are being rebuilt around AI right now, and the capability arriving in platforms over the next year was, in many cases, [purchased quarters earlier](https://hrexecutive.com/your-hr-tech-stack-is-being-rebuilt-around-you-do-you-have-a-voice-in-it). Vendors who move on voice as an embed or acquisition decision reach the market a year or more ahead of anyone still scoping a build. By 2028 the ones who built from scratch will mostly have arrived late, spent more, and landed in the same place, with a conformity file still to write.

## When does building voice in-house make sense?

**Build voice yourself only if real-time conversation is the product you are selling, if you have a permanent team to own the latency and language problems forever, and if you can accept a year or more before it reaches production, with the December 2027 conformity work landing on the same team. For a platform where voice is an interface rather than the offering, those conditions almost never hold.**

Be honest about the checklist. Does your roadmap have a spare senior team for the duration? Can you maintain turn detection and multi-language recognition indefinitely, not just ship it once? Can you evidence accuracy, robustness, and the absence of prohibited inference to a market surveillance authority? Is the voice experience itself something customers will choose you for, over and above your core modules? If the answers reveal gaps, the buy or embed path is faster, cheaper, and better, and you should save your build energy for the workflows where no vendor has an answer.

The failure mode to avoid is treating voice as a feature you owe your roadmap. It is closer to an acquisition-strategy decision, the kind CHROs are already tracking. Framed that way, the choice is not whether to build a voice team. It is which voice layer to embed, on what terms, and how fast you can be in market with it.

## What "embed via API" actually means in practice

**Embedding a voice layer means your platform calls a voice service that handles the conversation end to end (latency, turn detection, silence, language) and returns structured, timestamped output against your schema, alongside the logs and documentation the regulatory file needs. You write integration code and schema mapping, not voice code. The hard parts stay the provider's problem, permanently.**

Concretely, that means giving your platform a voice without writing a line of voice code. Your engineers map conversations to the fields your workflows expect and decide where the structured output lands. The provider owns the sub-second budget, the turn model, the silence handling, the language coverage, and the evidence trail, and keeps owning them as models improve. You get the conversational interface your users increasingly expect, and your roadmap stays pointed at the product only you can build.

That is why the prediction at the top is not really a contradiction. Voice becoming standard and almost no vendor building it are the same outcome. The capability spreads precisely because it can be embedded, and it can be embedded precisely because building it does not make sense for platforms whose product is something else.

## Frequently asked questions

### How long does it take to build a production-grade real-time voice layer?

For a team starting from a speech API, industry estimates run from [4 to 9 months for a basic production agent to 12 to 24 months for enterprise grade](https://www.lumay.ai/blogs/best-build-vs-buy-ai-voice-agent-guide) across multiple languages. The demo is quick. The hard tail is latency tuning, turn detection, silence handling, and reliable structured output, and each of those has to work together before the experience feels like a real conversation.

### Isn't voice just a speech-to-text API plus a language model?

No. Speech-to-text and a language model are two components in a longer chain that also includes turn detection, silence interpretation, multi-language recognition, sub-second latency management, and conversion into structured, timestamped data. Stitching those together reliably at scale is the actual product, and it is where most in-house builds stall.

### What do we keep control of if we embed voice rather than build it?

Everything that differentiates you. Your proprietary data, your workflow logic, your semantic model, and the structured signal you act on all stay yours. The voice layer is shared infrastructure that feeds those systems. Embedding it means you keep the intelligence and skip the plumbing that commoditises quickly.

### When is building voice in-house the right call?

When real-time conversation is itself the product you sell, when you can fund a permanent team to own it, and when you can carry the high-risk conformity obligations on your own timeline. For platforms where voice is an interface to their core offering rather than the offering itself, those conditions rarely all hold, so buying or embedding almost always wins.

### What should we evaluate in a voice layer before embedding it?

Measured latency under production load rather than demo conditions, behaviour under noise and accents, what the structured output contract looks like, and the conformity posture: logging, documentation, explanation export, and what the system provably does not infer about the people it talks to. That last item is the one most providers cannot answer, and it is the one your own regulatory file will depend on.

## Sources

- [LuMay, Build vs Buy AI Voice Agent Guide](https://www.lumay.ai/blogs/best-build-vs-buy-ai-voice-agent-guide): enterprise builds at $800K to $2.3M in year one, 12 to 24 months, six simultaneous engineering domains.
- [TECHSY, Build vs Buy AI Voice Agent Decision Framework](https://techsy.io/en/blog/build-vs-buy-ai-voice-agent): from-scratch builds at $250K to $2M, why in-house latency lands at 1.2 to 2 seconds, and the 0.4 second talk-over threshold.
- [Famulor, AI Voice Agent Latency Benchmarks](https://www.famulor.io/blog/ai-voice-agent-latency-how-fast-your-phone-bot-must-reply): the 200ms conversational gap and the sub-800ms quality bar.
- [Haptik, The Build vs Buy Voice AI Checklist](https://www.haptik.ai/blog/voice-ai-build-vs-buy): the maintenance tax and model drift as the hidden cost of building.
- [Council of the EU, agreement on the AI Act simplification package](https://www.consilium.europa.eu/en/press/press-releases/2026/05/07/artificial-intelligence-council-and-parliament-agree-to-simplify-and-streamline-rules/): the revised high-risk timeline for employment AI, now 2 December 2027.
- [Josh Bersin, Build vs Buy: It's So Easy to Build HR Software Now, Or Is It?](https://joshbersin.com/podcast/build-vs-buy-its-so-easy-to-build-hr-software-now-or-is-it): why building HR software is harder than it looks.
- [chiefmartec, Build vs Buy Is the Wrong Question for Martech AI](https://newsletter.chiefmartec.com/p/build-vs-buy-is-the-wrong-question-for-martech-ai): off-the-shelf reaching 80% and the hard remaining fraction.
- [HR Executive, Your HR Tech Stack Is Being Rebuilt Around You](https://hrexecutive.com/your-hr-tech-stack-is-being-rebuilt-around-you-do-you-have-a-voice-in-it): AI capability as an acquisition-strategy decision.
- [CIO, Your Next Big AI Decision Isn't Build vs Buy](https://www.cio.com/article/4097339/your-next-big-ai-decision-isnt-build-vs-buy-its-how-to-combine-the-two.html): embedding shared capability layers while keeping data and governance in-house.
- [Gloat, Build vs Buy: Horizontal AI Platforms for HR](https://gloat.com/academy/build-vs-buy-horizontal-ai-hr): the engine versus the fuel, map, and driver.
</markdown>

## Researched with AI. Argued, verified, and signed off by humans. That's also how we think AI should work everywhere."
