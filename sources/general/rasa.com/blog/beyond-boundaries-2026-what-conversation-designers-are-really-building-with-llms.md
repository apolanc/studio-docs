# Source: https://rasa.com/blog/beyond-boundaries-2026-what-conversation-designers-are-really-building-with-llms

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a034f0825ae6f7ce87243d6_Rasa_Blog_Beyond_Boundaries_2026_What_Conversation_Designers_Are_Really_Building_With_LLMs.png)

# Beyond Boundaries 2026: What Conversation Designers Are Really Building With LLMs"

Posted May 12, 2026

Updated

![Shauna Griffin](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68fe95baf92ceabc57ec448e_alan.png)

Shauna Griffin

# What changed for conversation designers in 2026 (and what didn't)

As LLMs get more fluent, designing great conversational experiences feels within reach for non-designers. Then you try to ship something past hello world. In Barcelona earlier this month, most of the conversation designers I spoke with weren't worried about being replaced. They've seen how far fluent output sits from useful conversation, and closing that gap is what they've always done. What's shifted is how they do it.

The Rasa team and I were at Beyond Boundaries 2026, the CDI Foundation's gathering of conversation designers, researchers, and enterprise practitioners. I gave a talk on multi-agent orchestration. This was a room where I was much happier to listen than talk, and one idea kept surfacing across sessions: it’s now table stakes to have a fluent CAI experience, but this makes the design work above it more valuable, not less.

## **The control spectrum**

Is reaching for an LLM always the right move? In a year when "agentic" is the default vendor answer and "rules-based" is a dirty word, the room was understandably skeptical. The question is which approach earns the call for which job, and most jobs don’t have a clean answer.

[Rebecca Evanhoe](https://www.linkedin.com/in/rebecca-evanhoe/) from [Slang.ai](http://slang.ai) gave a great case study on how they are “LLMifying” their agent. Slang handles restaurant reservations. Her team rolled LLMs out as a series of narrow experiments rather than a platform-wide swap, keeping each one small enough to roll back if it broke:

- **Reservation names:** ask the caller to spell it, then use an LLM to normalize it.
- **Hours and menu FAQs:** small rephrasing tasks where the LLM adds polish without taking over the flow.
- **Multi-language:** translate everything to English via LLM, run the logic, translate back.

The burden of proof sits on the LLM, not the rule.

## **Defining what good looks like**

> _"the designer's role has changed - from hours performing manual conversation review to defining the metrics and evals for what good conversation looks like."_

[Lorraine Burrell](https://www.linkedin.com/in/lorraineburrell/) and [Helene Benz](https://www.linkedin.com/in/helenebenz/) (Lloyds Banking Group) gave the talk I'd hand to any conversation design lead trying to scale a team past a few people. They've been turning the hours their designers used to spend reviewing transcripts into an internal eval and simulation platform. Manual review stops being the quality system and becomes one input into it. [Alice Kerly](https://www.linkedin.com/in/alicekerly/) (The CAI Company) framed why that shift is overdue: we design for the idealized conversation, but real users are messier than the flows assume. That gap is where observability earns its keep, and where most teams are still underinvested.

The hard problem isn’t whether to use "LLM-as-judge" or not." The real challenges are on either side of your workflow. Pre production: are you measuring what users actually experience, or what's convenient to score? In production: how well do your evals hold up against your production data, or are you tuning against an idealized version of the conversation? There is still a big gap here for many teams. 

## **What LLMs still can't do**

> _"doing less is what makes conversations feel human."_

Professor [Elizabeth Stokoe](https://www.linkedin.com/in/elizabeth-stokoe-5150a419/) (LSE) studies how human conversation works, and her talk was a breath of fresh air.  Two points stuck with me: timing is signal, not noise (silence carries meaning; most teams treat it as a metric to reduce); and doing less (single-line turns, small acknowledgements, minimal sounds) is what makes conversations feel human. LLMs tend to overly helpful, verbose conversation in contrast to humans mhmms that convey so much meaning in a sound. 

[Taylor Merriam](https://www.linkedin.com/in/taylormerriam/) (Capital One) made a great point about persona. An assistant should have one persona, but that persona needs emotional range. It flexes with user sentiment instead of holding a single tone whatever the user brings. A bonus from Merriam: be wary of an LLM pretending it has experienced the user's pain. Affective empathy from a bot gives most people the ick.

[Daniel Padgett](https://www.linkedin.com/in/danpadgett/) (DeepMind) shared a stealable hot take: "context engineering" is mostly a rebrand of what conversation designers have been doing for years. He was joking, and also right. Designing context that's not overloaded, adapts to feedback, and holds across interactions takes as much design thinking as engineering.

## **Multi-agent, briefly**

Most enterprises are already past the single-agent question. [MuleSoft's 2026 Connectivity Benchmark Report](https://www.salesforce.com/news/stories/connectivity-report-announcement-2026/) puts the average organization at 12 AI agents. My talk was on what you do when you get there, but the full argument needs a bit more room than a recap can hold. TL;DR: [Conway's Law](https://www.melconway.com/Home/Conways_Law.html) dictates. Your org chart becomes your architecture.

‍

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a034fb596ec2f40cd632f71_5c898cd6.png)

## **Going beyond average**

If I compress what I heard across the two days down to one idea: four parts of the conversation designer's job aren't going anywhere, regardless of what the underlying model does. Defining “what good is” for your conversational experience before your team automates against it. Designing memory and context across interactions (Padgett's joke, made earnest). Using judgement on the right tool for the job (determinism is not dead). Modelling personas with the emotional range to flex to real users. Owning content mechanics, including catching gaps before they ship.

LLMs will keep improving. That makes design more valuable, not less, because the cost of bad conversation at scale rises with the volume of cheap conversation being shipped. Your user’s trust is hard won and you don’t want to erode it at scale with mediocre conversation. Specifying what good looks like, and shaping the flow against the model's defaults, is what produces an experience that stays in your brand's control rather than the model's.

Thanks to the CDI Foundation for organizing. If you were in Barcelona, or you're hitting these problems in your own work, I'd love to compare notes.

**Sources**

1. MuleSoft (Salesforce), _2026 Connectivity Benchmark Report_. [salesforce.com/news/stories/connectivity-report-announcement-2026](http://salesforce.com/news/stories/connectivity-report-announcement-2026)

‍

‍

‍

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a4bd016defadab68727e4ed_Rasa-CMP-Prism-Social-1.png)](https://rasa.com/blog/rasa-recognized-in-the-cmp-prism-for-chatbot-virtual-agent-and-voicebot-conversational-ivr) [July 6, 2026\\ \\ /\\ \\ Company & Community\\ \\ **Rasa Recognized in the CMP Prism for Chatbot/Virtual Agent and Voicebot/Conversational IVR**](https://rasa.com/blog/rasa-recognized-in-the-cmp-prism-for-chatbot-virtual-agent-and-voicebot-conversational-ivr)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/rasa-recognized-in-the-cmp-prism-for-chatbot-virtual-agent-and-voicebot-conversational-ivr)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a0f54e9ef89379d936174d1_Where%20Rasa%20Stands%20Out-blog-img%402x%20(1).png)](https://rasa.com/blog/forrester-wave-2026-where-rasa-stands-out) [May 20, 2026\\ \\ /\\ \\ Company & Community\\ \\ **Where Rasa Stands Out in the Forrester Wave Q2 2026**](https://rasa.com/blog/forrester-wave-2026-where-rasa-stands-out)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/forrester-wave-2026-where-rasa-stands-out)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69e2e211243e0a7fc6df1c79_Rasa_Forrester_Blog-2.png)](https://rasa.com/blog/rasa-named-a-strong-performer-in-the-forrester-wave-tm-for-conversational-ai-platforms-for-customer-service) [April 21, 2026\\ \\ /\\ \\ Company & Community\\ \\ **Rasa Named a Strong Performer in The Forrester Wave™ for Conversational AI Platforms for Customer Service**](https://rasa.com/blog/rasa-named-a-strong-performer-in-the-forrester-wave-tm-for-conversational-ai-platforms-for-customer-service)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68fe95baf92ceabc57ec448e_alan.png)

Jane Lyu

[read article](https://rasa.com/blog/rasa-named-a-strong-performer-in-the-forrester-wave-tm-for-conversational-ai-platforms-for-customer-service)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)