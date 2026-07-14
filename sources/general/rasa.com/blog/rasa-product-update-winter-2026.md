# Source: https://rasa.com/blog/rasa-product-update-winter-2026

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/694a63c6f1fcadb67227f875_202512_Release_Blog_Cover.avif)

# Behind the Release Notes: Rasa Product Update Winter 2026

Posted Jan 07, 2026

Updated

![Lauren Goerz](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

Rasa Pro 3.15 addresses three critical challenges teams face when deploying LLM-powered agents: visibility into model behavior, voice channel capabilities, and shipping with confidence.

## **LLM Observability with Langfuse**

Without runtime observability of LLM inputs and outputs, teams struggle to understand how their conversational agents perform. You can't assess runtime metrics like latency and cost, and evaluating LLM outputs for specific tasks (such as command generation) becomes guesswork.

Rasa’s direct [integration with Langfuse](https://rasa.com/docs/reference/integrations/langfuse) solves this. Every LLM call is automatically traced, recording inputs, outputs, and critical performance indicators. These traces enable you to run evaluations on production data, giving you the visibility needed to measure and improve LLM performance in real-world conditions. You can now assess how well your models handle actual user interactions, identify optimization opportunities, and make data-driven decisions about your LLM infrastructure.

## **Voice Channels Get First-Class Treatment**

- [DTMF support](https://rasa.com/docs/reference/primitives/flow-steps#requesting-dtmf-input) means your agent can now handle phone keypad input natively. You can use it to help navigate (press 1 for sales) or to type in details such as account numbers or date of birth. Especially when voice recognition fails, or users are in noisy environments. They can fall back to pressing buttons without leaving the conversation flow. This provides flexibility to support users who prefer buttons over voice input while maintaining a consistent experience.
- [Streaming generated responses](https://rasa.com/docs/reference/changelogs/rasa-pro-changelog#improvements) from enterprise search or the rephraser in voice channels eliminates the awkward silence between user input and TTS output. The audio pipeline starts preparing as tokens arrive, not after the complete response is generated. Your customers experience lower perceived latency, directly translating to better satisfaction scores on voice calls.

## **Prevent Regressions in Generative Components with E2E Testing**

E2E testing now evaluates responses from custom actions using [grounding and relevance assertions](https://rasa.com/docs/pro/testing/evaluating-assistant#3-using-assertions-instead-of-steps). Custom actions that dispatch generative responses can be tested against ground truth with configurable thresholds, which means you can ship generative features without fear of regressions. You're no longer manually reviewing generated content before releases, and you catch issues before your users do.

## **Faster Testing Iteration**

When a test suite breaks, you previously had to re-run everything to verify your fix. The new failed test export solves this by allowing you to isolate and re-run [only the tests that failed](https://rasa.com/docs/reference/api/command-line-interface#rasa-test-e2e).

**Export failed tests during your initial run:**

`rasa test e2e -f failed_tests.yml`

After fixing the issue, re-run only the failures:

`rasa test e2e failed_tests.yml`

Your QA cycles shrink because you're iterating on only the failures without waiting through hundreds of passing tests.

## **Rasa Studio updates: CMS and Review Upgrades**

Rasa Studio, Rasa’s user interface, gets two workflow improvements that reduce friction for non-technical team members managing production agents.

### Centralized Slot Management

Slots now have their own [slots CMS](https://rasa.com/docs/studio/build/content-management/slots) section accessible from the navigation menu. Content managers can create, edit, and delete slots. The "See nodes" button shows exactly where each slot is referenced across your flows, which eliminates the guesswork when you need to understand slot usage or safely deprecate old slots. There is also a corresponding [button and link CMS](https://rasa.com/docs/studio/build/content-management/buttons-and-links) for content managers.

‍

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69524bcb6c7364845be0764d_66d3b8e6.avif)

Manage slots from a centralized panel

### ** 
Smarter Conversation Review**

Conversation Review now [filters by channel and agent response](https://rasa.com/docs/studio/analyze/conversation-review#filters). When you're debugging issues specific to voice channels or tracking down a problematic part of a conversation, you can narrow your search further instead of scrolling through thousands of unrelated conversations. This turns conversation analysis from a research project into a quick lookup. 
‍

‍

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69524bed9e4fc1a3e9fbda68_225ab443.png)

Filter by channel or response

## 
**User Experience Tweaks That Make a Difference**

- Default **DateTime awareness** means LLMs understand concepts like "tomorrow" or even something like "quarter past 9, two days after yesterday" without requiring custom prompt engineering. Check out the [new system prompt template](https://rasa.com/docs/reference/config/components/llm-command-generators#prompt-template) defaults to see how it’s implemented. 
- The **clarification pattern** now gives teams the option to [limit the number of options](https://rasa.com/docs/reference/primitives/patterns#triggering-clarification-when-multiple-startflow-commands-are-predicted) presented, thereby avoiding giving users too many choices.

With these editions, your team stops writing workaround code, and your agents feel more polished out of the box. 

## **What This Means for Your Roadmap**

- If you're evaluating production readiness, observability was probably on your checklist. With Langfuse, you can start checking that box.
- If voice customers often communicate with buttons or need to type in lots of numbers, native DTMF opens up new interaction modes.
- If generative testing felt too manual or brittle, you now have automation.
- If slots were hard to find and update, the slot management section of Rasa Studio should make them much easier to find, access, and edit. 

Read the full changelog [here](https://rasa.com/docs/reference/changelogs/rasa-pro-changelog#3150---2025-11-26). 

Want to try Rasa today? Check out the [Rasa Playground.](https://hellorasa.info/3XGRucE)

Questions? Comments? Get in [touch with our team](https://hellorasa.info/4poD5Of) or join the community at [forum.rasa.com](http://forum.rasa.com)

## Read more

[![Behind the Release Notes Spring 2026 Release](https://cdn.prod.website-files.com/68e92f16754061804418f615/69cbab21c01c7abaca2e1c28_202602_Product_Release_Blog_Banner_Spring.avif)](https://rasa.com/blog/behind-the-release-notes-product-updates-spring-2026) [April 9, 2026\\ \\ /\\ \\ Product News & Updates\\ \\ **Behind the Release Notes: Rasa Product Update Spring 2026**](https://rasa.com/blog/behind-the-release-notes-product-updates-spring-2026)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

[read article](https://rasa.com/blog/behind-the-release-notes-product-updates-spring-2026)

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