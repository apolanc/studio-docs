# Source: https://rasa.com/blog/enterprises-want-control-over-their-conversational-ai-this-is-how-to-build-it

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a06052ac25e71b8b42ca157_Rasa_Blog_Enterprises_Want_Control_Over_Their_Conversational_AI.png)

# Enterprises Want Control Over Their Conversational AI. This Is How to Build It.

Posted May 14, 2026

Updated

![Maria Ortiz](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

Ask enterprise leaders what they want most from their conversational AI in 2026, and you might expect to hear about performance, speed, or scale. 

But, according to our [_2026 State of Conversational AI_](https://rasa.com/2026-state-of-conversational-ai-report?utm_source=blog&utm_medium=website&utm_campaign=state_of_conversational_ai_2026) report, what they really want is control:

- 60% of respondents rank "black box" issues or compliance as their top AI challenge
- 93% say transparency is "very important" or "critical"
- 43% won't deploy a solution without full explainability
- Two-thirds require on-premise or own-cloud deployment

And when given a choice of architecture, most prefer hybrid models combining LLM flexibility with deterministic logic over fully agentic systems by a margin of nearly five to one.

These findings paint a clear picture of an enterprise market that has moved past asking whether AI is capable of conversing with customers and prospects. It’s now asking: Can we control it?

The answer depends on how you build. In practice, control shows up differently at every layer of a conversational AI system: in the infrastructure decisions that determine where data lives, the architectural choices that determine how the AI behaves, and the measurement frameworks that determine whether you can see what's working and fix what isn't. Each layer matters, and each requires deliberate choices made early on. Here's what building for control actually looks like across all three.

‍

> This post draws on findings from Rasa's _2026 State of Conversational AI_ report, which surveyed 30 enterprise decision-makers across finance, healthcare, retail, government, and telecom. [Download the full report →](https://rasa.com/2026-state-of-conversational-ai-report?utm_source=blog&utm_medium=website&utm_campaign=state_of_conversational_ai_2026)

‍

## **1\. Infrastructure: Where your AI runs determines what you can govern**

When enterprise leaders talk about deployment control, they're often describing the same operational governance they'd require of any software system.

One VP of IT in the healthcare industry put it this way in our survey: "I need real operational governance: versioning, approvals, role-based admin, dev/test/prod separation, and change logs so IT can control behavior like a production system." 

That expectation is shaping infrastructure decisions. Two-thirds of the enterprise leaders we surveyed consider on-premise or own-cloud deployment "very important" or "essential." Only 17% say a shared cloud environment is acceptable. Half of those requiring deployment control are driven by regulatory or security mandates. The other half simply prefer it that way, which is the more revealing finding. It suggests deployment control has become a business preference independent of compliance obligations.

‍

> **How the EU AI Act is influencing AI governance for the financial services industry**

### While control over AI systems is clearly a business choice for many enterprises, the EU AI Act is still driving decisions about where AI runs and how it processes data for any enterprise operating in or serving European markets. [Read our explainer →](https://rasa.com/blog/eu-ai-act-financial-services) 

**‍**

### **What building for infrastructure control looks like**

In practical terms, building for infrastructure control means choosing deployment models that keep data within your environment: on-premises, private cloud, or a hybrid architecture where the data plane is customer-controlled even if the orchestration layer is not. 

Infrastructure control also includes selecting AI platforms that are LLM-agnostic, so you can choose which models run on your infrastructure and swap them without rebuilding. And it requires establishing the operational governance structures — role-based access, version control, change logs, environment separation — that your IT and compliance teams will require before signing off on a production deployment.

[Rasa](https://rasa.com/platform) supports flexible deployment across cloud, on-premise, and managed service environments, and is LLM-agnostic by design, meaning you choose the models, you control where they run, and your data doesn't leave your environment unless you decide it should.

‍

## **2\. Architecture: How your AI is designed determines how much you can trust it**

While deployment control governs where AI lives, architecture dictates how it behaves. And in regulated, customer-facing environments, behavior is everything.

Most enterprise leaders in our survey (63%) prefer hybrid architectures that combine LLM flexibility with deterministic logic. Only 13% favor fully agentic systems. This isn't a conservative instinct. It's a considered judgment about which approach is fit for which job.

LLMs are excellent at understanding the natural variation in how people communicate; they can interpret intent, handle ambiguity, and generate fluent responses. But they introduce variance in every output. For parts of customer conversations where variance is unacceptable — compliance disclosures, authentication flows, billing disputes, regulated actions — that unpredictability can be a serious liability. In contrast, deterministic logic doesn't improvise. It follows the path you've defined, every time.

‍

### **What hybrid architecture actually buys you**

Hybrid architecture lets you assign each approach to the job it's suited for. LLMs handle the conversational layer, while deterministic flows govern the decisions that have to be right. The result is an AI system whose behavior is both natural and auditable, rather than a trade-off between the two.

The fully agentic path simply moves the governance issue to a part of the stack where enterprises are still building the tooling, benchmarks, and organizational readiness to manage it. For most organizations, hybrid architecture is the better-supported path to control today, even as the ecosystem around agentic systems matures.

[Rasa's CALM framework](https://rasa.com/calm) is built on this principle, separating language understanding from business logic execution so that LLMs interpret conversations while deterministic flows govern the decisions that can't afford to drift from standards. The result is AI behavior that's predictable, auditable, and adjustable without rebuilding from scratch.

‍

## **3\. Measurement: How you track performance determines whether you can improve**

The third layer of control is the one enterprises are most consistently failing to build in from the start.

Achieving performance metrics is the most commonly cited pain point across the AI journey in our survey, outpacing deployment difficulty by nearly three to one. And 27% of respondents said it was the hardest phase. (Only 10% said the same about deployment.)

What enterprises want to measure reveals why performance tracking is so difficult. Response accuracy tops the list of critical metrics at 90%, a full ten percentage points above compliance adherence and well ahead of automation rate at 63%. In other words, enterprises care most about whether AI handles conversations correctly, not just whether a large volume of them are being handled at all. That's a harder thing to measure, and it requires infrastructure that most organizations are still building: evaluation frameworks, testing protocols, human review processes, and analytics pipelines that go beyond basic usage dashboards.

‍

### **Why measurement gets deprioritized, and what it requires**

Most organizations find themselves without this infrastructure because they treated it as a phase-two concern. By the time teams try to retrofit a metrics framework, they're already under pressure to justify investments and improve results, with limited visibility into what's actually happening inside the system. Getting performance measurement right is easier at the start of a build than after you've scaled a system you can't yet see clearly.

Building for measurement control means defining what "good" looks like for your use case before you go to production: for example, response accuracy, containment rate, compliance adherence, or escalation frequency. It means establishing the tooling to track those metrics reliably and being honest about the difference between metrics that tell you how much AI is doing versus how well it's doing. Automation rate and resolution rate are not the same.

‍

## **The case for building in control from the start**

When respondents in our survey were asked what would make implementation significantly easier, the top answers weren't about more powerful technology. They were about clearer paths to value (60%), clearer benchmarking data (53%), and clearer best practices for implementation (50%). 

In practice, the organizations with the most control over their conversational AI are the ones that designed for it from day one, not the ones that attempted to layer it on once a system was already in production.

An organization with flexible deployment but no architectural guardrails still ends up with a black box. One with a well-designed hybrid architecture but no measurement framework is still unable to identify what's failing or why. Getting one layer right doesn't compensate for gaps in the others.

Enterprise leaders in our survey aren't asking for AI that can do more. They're asking for AI they can govern, trust, and stand behind. That's a different kind of problem, and it calls for a different approach to how AI programs are scoped and built.

‍

## **Go deeper on control, confidence, and the state of enterprise AI**

Our _2026 State of Conversational AI_ report breaks down how challenges, expectations, and design preferences vary across industries, roles, and titles, including which functions are actually driving infrastructure decisions and what the most confident teams are doing differently.

‍

[Download the full report →](https://rasa.com/2026-state-of-conversational-ai-report?utm_source=blog&utm_medium=website&utm_campaign=state_of_conversational_ai_2026)

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a0f51c7f5a8d81f6ca5ebd2_scaling-without-confidence-blog-img%402x%20(1).png)](https://rasa.com/blog/most-enterprises-arent-yet-confident-in-conversational-ai-but-theyre-scaling-anyway) [May 21, 2026\\ \\ /\\ \\ AI Concepts & Technology\\ \\ **Most Enterprises Aren’t Yet Confident in Conversational AI, But They’re Scaling Anyway**](https://rasa.com/blog/most-enterprises-arent-yet-confident-in-conversational-ai-but-theyre-scaling-anyway)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/most-enterprises-arent-yet-confident-in-conversational-ai-but-theyre-scaling-anyway)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69e108c87a63286b72cc4cdc_Botpress%20alternatives.png)](https://rasa.com/blog/botpress-alternatives) [May 5, 2026\\ \\ /\\ \\ AI Concepts & Technology\\ \\ **10 Best Botpress Alternatives for Enterprise AI Agents (2026)**](https://rasa.com/blog/botpress-alternatives)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/botpress-alternatives)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69e109288ed96b7d73356385_sierra-alternatives.png)](https://rasa.com/blog/sierra-ai-alternatives) [April 30, 2026\\ \\ /\\ \\ AI Concepts & Technology\\ \\ **12 Best Sierra AI Alternatives for Enterprise Conversational AI (2026)**](https://rasa.com/blog/sierra-ai-alternatives)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/sierra-ai-alternatives)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)