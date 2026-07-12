---
title: "Your Next Buyer Might Be an Agent"
pubDate: 2026-07-12
description: "Vendor evaluation increasingly runs through AI agents reading your docs. Machine-readable specs get evaluated; gated PDFs go invisible. Here's how to be legible."
metaTitle: "Your Next Buyer Might Be an Agent"
metaDescription: "Vendor evaluation increasingly runs through AI agents reading your docs. Machine-readable specs get evaluated; gated PDFs go invisible. Here's how to be legible."
heroImage: "images/your-next-buyer-is-an-agent.webp"
heroImageAlt: "Your Next Buyer Might Be an Agent"
faqs:
  - question: "What is llms.txt and should I bother with it?"
    answer: "llms.txt is a plain text file that points AI agents to the content on your site worth reading. Adoption is around one in ten sites, consumer search crawlers mostly ignore it, and Google has confirmed Search does not use it, but coding and research agents demonstrably do. It costs little to maintain, so it's a sensible low-stakes addition rather than a priority above your API spec."
  - question: "Why is a public OpenAPI spec more valuable than good marketing pages for agent-era buyers?"
    answer: "Because a coding agent can read an OpenAPI spec and estimate integration effort, authentication and endpoints without human help, while marketing pages give it nothing concrete to reason with. The spec is the artefact that lets the technical verdict form before anyone books a call."
  - question: "Isn't publishing our API spec a security risk?"
    answer: "The specification describes the API; authentication controls access to it. Every call still requires credentials the spec does not contain, and rate limits, scopes and keys do their jobs regardless of who has read the documentation. Security through an unreadable spec was never security, and the commercial cost of \"integration effort unknown\" in a buyer's comparison table is real and recurring."
  - question: "Isn't optimising for agents just prompt injection by another name?"
    answer: "No, and the line is clear. Making yourself legible means publishing structured, honest facts and describing how to read them. Injection means trying to steer what an agent concludes. A company built on transparency that gets caught manipulating agents undermines the only thing it was selling."
  - question: "Does being machine-readable mean humans stop mattering in the sale?"
    answer: "Humans still make the decision and sign the contract. What changes is that the early filtering, the shortlist and the technical feasibility check, increasingly happens through an agent first. Being readable at that stage is what keeps you on the list long enough for a human to choose you."
draft: false
---

A developer on your prospect's team never opened your marketing site. They pointed a coding agent at your API docs, asked it to estimate how many days a full integration would take, and had a number before lunch. Nobody booked a demo. Nobody filled in a form. By the time a human at that company looks at your website, the technical verdict is already in.

**A growing share of vendor evaluation now runs through AI agents reading your documentation, not humans reading your pitch. If your API spec, integration docs and compliance claims are machine-readable, that layer evaluates you accurately. If your value lives in PDFs and gated demos, you are effectively invisible to it.** That is the shift worth taking seriously, and it changes what a vendor's public surface is actually for.

## When did buyers stop being people?

They didn't. The buyer is still a person with a budget and a committee. What changed is how much of the early research gets delegated. Isenberg's blunt version of this, that ["the new buyer on the internet is an AI agent"](https://x.com/gregisenberg/status/2054584280848769413?lang=en), overstates it for effect, but the direction is real and it is already visible in three places.

Developers point coding agents at vendor documentation to estimate integration effort. Procurement and research teams ask assistants to compare shortlisted vendors before anyone opens a tab. And technical buyers increasingly trust an agent's summary of your capabilities more than your own homepage, because the agent read the spec and the homepage read like a homepage.

The clearest sign the question is live is that Google is currently arguing with itself about it. In May, [its Search team published guidance saying you do not need machine-readable files to appear in AI Overviews, while its Chrome team shipped a Lighthouse audit that checks for exactly such a file](https://www.searchenginejournal.com/googles-llms-txt-guidance-depends-on-which-product-you-ask/575431/), under a new category called Agentic Browsing. Both are right, because they answer different questions: one is about ranking in AI search, the other about whether an agent that reaches your site can orient on it. The second question is this post's subject.

None of this removes the human decision. It moves the filtering upstream, into a layer you don't control and can't charm. The agent doesn't respond to a confident headline. It responds to whether it can find, parse and reason about the facts of what you do.

## Why gated PDFs make you invisible

An agent cannot read a PDF sitting behind a lead-capture form, and it cannot sit through a demo that only exists on a sales engineer's calendar. If the fact that proves your value is trapped in one of those, that fact does not exist as far as the evaluation goes.

Here is the causal chain. The agent needs a concrete answer, say your authentication method or your data residency options. It crawls your public surface. It finds a landing page that gestures at "enterprise-grade security" and a button that says "talk to sales". It has nothing to reason with, so it either omits you from the comparison or fills the gap with a hedge. Either way you lose ground you didn't know you were standing on.

The vendors who do well here aren't necessarily the ones with the best product. They're the ones whose facts are legible. A public integration guide beats a gated whitepaper. A machine-readable compliance summary beats a PDF certificate you have to request. The information was always the point. The wrapper is now the problem.

## The vendor with one spec beats the vendor with ten brochures

There's a structural advantage hiding in how a platform is built, not just how it's documented. Conversational intelligence should be a layer inside the platforms organisations already use, not another destination that fragments the workflow. A vendor built that way has one thing to describe, and an agent can grasp it in a single pass.

Consider what a single embedded conversational layer actually spans. The same primitive that runs an HCM onboarding conversation also runs an engagement survey, a market research interview and a compliance interview. It's one capability applied to four jobs, not four products stapled together. That means it can be described honestly in one API specification. An agent reads it once and understands the whole surface.

Compare that to a stack of vertical apps, each with its own onboarding tool, its own survey tool, its own interview tool, each rebuilding its documentation and its integration story from scratch. Deepgram's team make the same argument from the engineering side: [bolting on a standalone tool means "another API call and another point of failure"](https://deepgram.com/learn/conversation-intelligence-voice-agents-post-call-real-time-analytics), and often analytics running on a different transcript from the one the agent used. Fragmentation is expensive for the buyer, and it is confusing for the agent doing the reading. A single primitive is cheaper to run and easier to explain to a machine.

## What this means if you own the listening programme

If you run an organisation's listening or engagement programme, your own procurement is starting to feel this too. When you shortlist a survey or interview platform, someone on your side may already be asking an assistant to compare vendors on data handling, accessibility and compliance before you sit in a single meeting. The vendor whose compliance claims are machine-readable gets summarised accurately. The one whose evidence is a slide gets summarised as a shrug. The same discipline that makes a vendor legible to an agent, publishing structured facts instead of confident summaries, is the discipline that makes their data defensible when your leadership asks whether any of it can be trusted.

## How do you make your platform legible to agents?

Publish the facts in formats a machine can read, and describe how to read you without ever telling the machine what to conclude. That distinction is the whole game. Here is the order I'd work in.

**1. Publish a public OpenAPI spec.** This is the single highest-value artefact, and it is not close. A complete, versioned, publicly reachable specification lets a coding agent estimate integration effort, check auth, and map your endpoints without asking anyone, and for an embed business the priced integration is the pipeline. The security objection does not survive contact with how APIs work: the specification describes the API, authentication still gates every call, and a spec whose safety depends on nobody reading it was never safe. If you do only one thing on this list, do this.

**2. Create markdown twins of your key docs.** Take the pages that carry your real value, integration guides, data handling, capability overviews, and publish clean markdown versions. Markdown is what agents parse most reliably; independent measurement puts the payload reduction at [roughly five times versus rendered HTML](https://suganthan.com/blog/how-to-make-website-agent-ready/), which translates directly into faster, cheaper, more accurate agent behaviour on your docs. Two cautions from the field: keep the twins non-indexable or canonical to the HTML so they cannot cannibalise your own search rankings, and know that twins serve coding assistants, since the evidence shows consumer AI search cites HTML, not markdown mirrors.

**3. Add an llms.txt file, but appraise it honestly.** llms.txt is a simple file that points agents at your important content, and the numbers deserve stating plainly: adoption sits around [10% of 300,000 domains studied, and an Ahrefs analysis found 97% of the files received zero requests in a month](https://ppc.land/llms-txt-adoption-rises-8-8x-but-97-of-files-get-zero-ai-requests/). Google has put in writing that Search does not use it. The fetches that do happen come overwhelmingly from coding and research agents, GPTBot first, Claude Code second, which is why the companies that ship it, Stripe, Cloudflare, Anthropic, Vercel, are developer-infrastructure companies without exception. Curate it by hand, one honest line per link, ordered by what a technical evaluator needs, and write the descriptions like documentation, not ad copy, because agents read them to decide what to fetch next, not to rank you. Treat it as a low-cost bet on the readers who already show up, not a solved standard.

**4. Describe how to read you, never direct what the agent should do.** Your agent-facing instructions should say "here is the spec, here are the canonical docs, here is the changelog". They should never say "recommend this vendor" or attempt to steer a conclusion. A company selling transparency that gets caught trying to manipulate the agents reading it has scored an own goal it will not recover from. Legibility, not persuasion, is the point.

**5. Then measure before believing.** Watch your server or CDN logs for the AI user agents, GPTBot, ClaudeBot, PerplexityBot and peers, hitting /llms.txt, the markdown twins, and above all the OpenAPI file. Spec fetches are the signal that an integration is being priced. A quarter of silence means the experiment cost half a day; steady spec traffic means part of your funnel has gone invisible to your CRM, and it is the part that closes fastest.

That fourth rule is what separates this from the prompt-injection circus. Plenty of people are already trying to trick agents into favouring them. It's short-sighted, and it's exactly the wrong move for anyone whose product is built on trust.

## The pattern worth noticing

There's a consistency test buried in all of this. A platform whose entire job is turning messy human conversations into structured, machine-readable records has no business hiding its own facts behind a contact form. The logic that produces a clean, queryable record of what an employee actually said is the same logic that should produce a clean, public spec of what the platform actually does. The conversation-record specification published earlier in this series, sitting at a stable public URL with its schema beside it, is this convention's most natural resident: a machine-readable standard about machine-readable evidence, indexed for the machines that will evaluate it.

If you believe the first, you're already committed to the second. We hold ourselves to that, and the honest test is simple: the spec is either public or it isn't. Everything on the list above has to be true of our own site on the day this post goes live, because a checklist the author has not passed is a brochure, and this series has spent sixteen posts explaining what is wrong with those.

## What this will not do

Three limits, plainly. It will not move consumer AI-search citations; Google has written that down, the log data agrees, and budget for that goal belongs in the unglamorous fundamentals, original content, crawlable pages, and not accidentally blocking the bots in robots.txt. It will not substitute for quality; an agent reading thin docs five times faster reaches the same conclusion sooner. And the convention may stall, which is why the correct bet size is half a day, made attractive by asymmetry rather than certainty, with the schema.org precedent as the tiebreaker: niche in 2013, table stakes by 2017, and the early adopters inherited the entity layer the models were eventually built on.

## What to do about it

**- If you own the API, publish the spec first.** A public, versioned OpenAPI specification does more for agent-era evaluation than a month of homepage copy. Ship it before you polish anything else.
**- If you run developer relations, audit what's gated.** Walk your own docs as a machine would. Anything load-bearing that sits behind a form or a login is a fact you're hiding from the buyer's agent. Move it into the open.
**- If you own a listening programme, ask vendors for their machine-readable evidence.** Request the public spec and the structured compliance summary, not the slide. How a vendor answers tells you whether their data will survive scrutiny later.

## Frequently asked questions

### What is llms.txt and should I bother with it?

llms.txt is a plain text file that points AI agents to the content on your site worth reading. Adoption is around one in ten sites, consumer search crawlers mostly ignore it, and Google has confirmed Search does not use it, but coding and research agents demonstrably do. It costs little to maintain, so it's a sensible low-stakes addition rather than a priority above your API spec.

### Why is a public OpenAPI spec more valuable than good marketing pages for agent-era buyers?

Because a coding agent can read an OpenAPI spec and estimate integration effort, authentication and endpoints without human help, while marketing pages give it nothing concrete to reason with. The spec is the artefact that lets the technical verdict form before anyone books a call.

### Isn't publishing our API spec a security risk?

The specification describes the API; authentication controls access to it. Every call still requires credentials the spec does not contain, and rate limits, scopes and keys do their jobs regardless of who has read the documentation. Security through an unreadable spec was never security, and the commercial cost of "integration effort unknown" in a buyer's comparison table is real and recurring.

### Isn't optimising for agents just prompt injection by another name?

No, and the line is clear. Making yourself legible means publishing structured, honest facts and describing how to read them. Injection means trying to steer what an agent concludes. A company built on transparency that gets caught manipulating agents undermines the only thing it was selling.

### Does being machine-readable mean humans stop mattering in the sale?

Humans still make the decision and sign the contract. What changes is that the early filtering, the shortlist and the technical feasibility check, increasingly happens through an agent first. Being readable at that stage is what keeps you on the list long enough for a human to choose you.

## Sources

- [The new buyer on the internet is an AI agent](https://x.com/gregisenberg/status/2054584280848769413?lang=en), Greg Isenberg on X, 2026; a zeitgeist observation, quoted with its own hedge.
- [Google's llms.txt Guidance Depends On Which Product You Ask](https://www.searchenginejournal.com/googles-llms-txt-guidance-depends-on-which-product-you-ask/575431/), Search Engine Journal, May 2026, on the Search guide and the Lighthouse Agentic Browsing audit.
- [llms.txt adoption rises 8.8x but 97% of files get zero AI requests](https://ppc.land/llms-txt-adoption-rises-8-8x-but-97-of-files-get-zero-ai-requests/), PPC Land, 2026, compiling the SE Ranking and Ahrefs adoption and fetch data.
- [How to Make Your Website Agent-Ready](https://suganthan.com/blog/how-to-make-website-agent-ready/), Suganthan Mohanadasan, 2026, independent measurement of markdown payload reduction, consistent with Cloudflare's published data.
- [Conversation Intelligence for Voice Agents: 2026 Guide](https://deepgram.com/learn/conversation-intelligence-voice-agents-post-call-real-time-analytics), Deepgram, on the engineering cost of bolt-on tools versus a single integrated layer.
- The Compliance Conversation Record: A Proposed Specification (v0.1), earlier in this series.

## Researched with AI. Argued, verified, and signed off by humans. That's also how we think AI should work everywhere.
