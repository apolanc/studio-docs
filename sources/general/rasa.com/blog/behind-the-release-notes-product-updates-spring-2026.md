# Source: https://rasa.com/blog/behind-the-release-notes-product-updates-spring-2026

![Behind the Release Notes Spring 2026 Release](https://cdn.prod.website-files.com/68e92f16754061804418f615/69cbab21c01c7abaca2e1c28_202602_Product_Release_Blog_Banner_Spring.avif)

# Behind the Release Notes: Rasa Product Update Spring 2026

Posted Apr 09, 2026

Updated

![Lauren Goerz](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

The Spring Release covers five areas: IDE tooling for developers, analytics and conversation review in Studio, a built-in CSAT pattern, voice improvements for ReAct agents, and optimized model support for GPT-5.1, GPT-5.2, and Claude Sonnet 4.5.

## **Rasa MCP Tools: IDE copilot support via local MCP server**

AI coding agents are really good at Python. But they are not always good at Rasa. They do not know best practices for building with Rasa, your memory schema, or why training failed. Rasa MCP Tools changes that.

[Rasa MCP Tools](https://rasa.com/docs/learn/quickstart/pro/) (currently in beta) is a local MCP server that connects to your IDE's copilot: Cursor, VS Code Agent Mode, Claude Code, and JetBrains. Once connected, your copilot tool can read your project structure, write and validate new sub-agents and flows against your domain, train your model, and debug runtime issues from logs and conversation context.

**Set up runs once:**

`rasa tools init`

Config saves to .rasa/tools.yaml. Most IDEs start the server automatically. 

## **Analytics in Studio**

Studio ships a built-in [analytics dashboard](https://rasa.com/docs/studio/analyze/analytics/). No external setup, no third-party integration required.

The dashboard covers the metrics teams most often ask for: total conversation sessions, containment rate, average latency, and CSAT score, each with a month-over-month comparison. Containment insights surface the user journeys with the lowest rates, so you know where to focus. Latency insights show the breakdown over time.  

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69ce21b7a00bbe7df1cec972_Screenshot%202026-03-31%20at%2014.04.57.avif)

Rasa Analytics Dashboard

### Conversation Review: filter by tag, language, and channel

[Conversation Review](https://rasa.com/docs/studio/analyze/conversation-review/) has new filters for **channel**, **language**, and **tag**. The filter model is additive: stack all three, or use one. Reset clears everything at once. The conversations that previously required manual scrolling to find are now a few clicks away.

‍

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69cbf330e371cce45e4f9dcf_Screenshot%202026-02-19%20at%2014.15.13.avif)

Conversation Review Panel with additional filters

## **Built-in CSAT collection**

Getting satisfaction scores after a conversation used to require a custom flow. It no longer does.

A new [pattern](https://rasa.com/docs/reference/primitives/patterns/), `pattern_customer_satisfaction`, triggers automatically after `pattern_completed` when the user indicates they are done. It collects a `csat_score` slot with two values (satisfied or unsatisfied), responds accordingly, and asks only once per session. The pattern, its responses, and its trigger conditions are all customizable.

If you already have a custom CSAT flow, populate the standard `csat_score` slot with the allowed values. Analytics picks it up without affecting your user experience.

## **ReAct filler messages**

A reAct agent that calls three tools before responding has a specific problem in voice: several seconds of silence before any response. Users in voice channels hear nothing while the agent works.

Rasa 3.16 adds [filler message](https://rasa.com/docs/reference/config/agents/react-sub-agents/#intermediate-messages) support. Before executing tool calls, the agent sends an acknowledgment, something like "Let me pull up those details." The message streams to the user immediately. The tool calls run. The full response follows when they complete.

Filler messages are on by default. Disable per agent if needed:

```yaml
configuration:
  enable_filler_messages: false
```

## **GPT-5.1, GPT-5.2, and Claude Sonnet 4.5**

Optimized [command generator prompt templates](https://rasa.com/docs/reference/config/components/llm-command-generators/#prompt-template-1) for GPT-5.1, GPT-5.2, and Claude Sonnet 4.5. While Rasa is language model agnostic, it is important to tune the system prompts for the language model you are using. This adds to the list of prompts we have benchmarked and tuned for you.  

Benchmark results: GPT-5.2 and the latest Claude models now outperform GPT-4o on command generation accuracy. 

Set the model in endpoints.yml, and the correct prompt template will be used automatically.

## **Notable fixes**

- **Session management got a full overhaul.** Every session now carries a UUID on all events, so tracking and analytics have a reliable identifier to work with. Sessions end explicitly — as ConversationInactive (resumable) or SessionEnded (permanently closed) — rather than just timing out ambiguously. A new start\_session\_after\_expiry config controls what happens when a session expires. And a new admin endpoint GET /users/{user\_id}/trackers gives you paginated conversation history per user
-  **Multilingual voice in a single deployment.** ASR and TTS reconfigure at runtime based on the built-in language slot. No separate deployment per language.

Want to learn more? Read the [release notes](https://rasa.com/docs/reference/changelogs/rasa-pro-changelog/) and check out the [version migration guide](https://rasa.com/docs/reference/changelogs/rasa-pro-migration-guide/). 

New to Rasa? Try out our [developer playground](https://hellorasa.info/4teuejO)

## **Frequently asked questions**

**Where can I find the release notes?** Rasa 3.16 release notes can be found [here](https://rasa.com/docs/).

**What are Rasa MCP Tools?** Rasa MCP Tools is a local MCP server that enables IDE copilots (Cursor, VS Code Agent Mode, Claude Code, JetBrains AI) to read, write, validate, and debug Rasa projects. It ships with Rasa 3.16.

**What models does Rasa 3.16 support?** GPT-5.1, GPT-5.2, and Claude Sonnet 4.5 ship with optimized prompt templates. Our benchmarks show they outperform GPT-4o for Rasa command generation.

**Does the CSAT pattern work with existing implementations?** Yes. If you already collect satisfaction scores, populate the standard csat\_score slot with the allowed values (satisfied, unsatisfied, skipped), and Analytics picks it up without any UX changes.

**What is the audio quality improvement in voice?** Rasa 3.16 upgrades from 8kHz mu-law to Linear PCM at 24kHz on Audiocodes and Jambonz, and 48kHz for Browser and Studio—no configuration required.

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/694a63c6f1fcadb67227f875_202512_Release_Blog_Cover.avif)](https://rasa.com/blog/rasa-product-update-winter-2026) [January 7, 2026\\ \\ /\\ \\ Product News & Updates\\ \\ **Behind the Release Notes: Rasa Product Update Winter 2026**](https://rasa.com/blog/rasa-product-update-winter-2026)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

[read article](https://rasa.com/blog/rasa-product-update-winter-2026)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6908cfb953b58ac39c1a7943_blog%20cover.avif)](https://rasa.com/blog/rasa-playground) [November 3, 2025\\ \\ /\\ \\ Product News & Updates\\ \\ **Skip the Setup, Start Building**](https://rasa.com/blog/rasa-playground)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

[read article](https://rasa.com/blog/rasa-playground)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6917499aab290f44ad610431_Rasa_Blog_1071x603_ProductUpdate-Fall-2.avif)](https://rasa.com/blog/rasa-product-update-fall-2025) [November 1, 2025\\ \\ /\\ \\ Product News & Updates\\ \\ **Behind the Release Notes: Rasa Product Update Fall 2025**](https://rasa.com/blog/rasa-product-update-fall-2025)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

[read article](https://rasa.com/blog/rasa-product-update-fall-2025)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)