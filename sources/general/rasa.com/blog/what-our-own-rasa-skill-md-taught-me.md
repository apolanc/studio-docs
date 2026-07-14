# Source: https://rasa.com/blog/what-our-own-rasa-skill-md-taught-me

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a0317952c0db553b0b1013c_Rasa_Blog_1071x600_skillmd_article%402x.png)

# What our own Rasa SKILL.md taught me

Posted May 11, 2026

Updated May 12, 2026

![Rod Rivera](https://cdn.prod.website-files.com/68e92f16754061804418f615/697b91ab5c53b1e5747fc551_rrivera-profile-1000x1000.avif)

Rod Rivera

Just this morning, I wrote a short post on LinkedIn asking whether agentic skills were simply a new way to store and organize prompts. The answer, as far as I can tell, is: not when they are done well. Done well, a skill is a compressed form of expertise. A skill summarizes the output of many projects, mistakes, and small arguments about what "good" looks like, all folded into a single markdown file that a coding agent can read and apply while we are working.

That is a real shift in how we transmit engineering practice.

With this mindset, I sat down and went through our Rasa skills bundle the way a new Rasa developer would. I wanted to wear the hat of someone trying to ship a Rasa conversational AI agent on a deadline. I wanted to know: what would I actually change about my project if I treated these SKILL.md files as serious design guidance, rather than as reference material?

The list below is what I kept underlining. These are six patterns, each anchored to a specific skill in the bundle. The biggest benefit is that none of them requires new libraries or refactoring. Most of these patterns can be done in an afternoon.

### Summarized

In a Rasa conversational AI agent, text is infrastructure. The description of a flow routes the LLM. The description on a collect step tells the LLM what to extract. The slot type we pick constrains extraction. The layer we put our validation in determines whether we wrote three lines of YAML or fifty lines of Python. These are more than just documentation choices. They are engineering choices.

## 1\. Our flow description is the Command Generator's API

In a Rasa project, the Command Generator decides which flow to trigger based largely on the `description` field. That description is the primary routing signal. A vague description means the right flow does not trigger, or what is worse: The wrong one triggers in its place.

A mistake is to treat descriptions as written implementation notes. Something like:

`book_appointment:    description: Runs action_book_slot and fills the date slot.   `

This is documentation for a human reader, not a routing signal for a language model. Rewrite it so it describes the user's goal in plain, standard language:

`book_appointment:    description: Helps patients schedule a visit with their doctor.   `

The test: if I handed only the description to someone outside our team, could they write a realistic user message that should trigger this flow? If not, Rasa's Command Generator cannot either.

Which SKILL.md can help here? Check out `rasa-building-flows`, specifically, the section _Writing descriptions_.

## 2\. The collect step description is the extraction specification

The `description` on a `collect` step tells the LLM what value to extract from the user's message. This is the shape of the thing being captured, and not the question being asked.

Here is one straightforward example of this:

`- collect: insurance_id    description: Ask the user for their insurance ID.   `

That describes the action. It does not describe the value. Compare:

`- collect: insurance_id    description: >      Insurance member ID printed on the patient's card.      Alphanumeric, 9–12 characters, for example XYZ-123456789.   `

The second version gives the LLM format, constraints, and an example. It is an extraction logic written in English. When an ambiguous user message arrives, such as "it's XYZ-123456789-A, should I include the A?" The second description is what lets the model make the right call.

A reliable rule: describe the value, not the question. If our description starts with the word _Ask_, rewrite it.

Which SKILL.md can help here? Check out `rasa-building-flows`, and look for the section _Collect step descriptions_.

## 3\. The slot type we pick is extraction logic

Rasa offers six slot types. They are `text`, `bool`, `categorical`, `float`, `any`, and `list`. In a surprising number of projects, almost every slot is `text`. This is an extraction problem masquerading as a type problem.

`text` allows anything. `categorical` with an explicit values list, by contrast, tells the LLM what the valid answers are and auto-coerces casing. `bool` tells it this is a binary. `float` tells it this is numeric. The more restrictive the type, the more the Command Generator has to work with, and the less invalid data we have to clean up downstream.

`# Loses information   priority:    type: text      # Constrains extraction   priority:    type: categorical    values:      - low      - medium      - high   `

The rule in practice: pick the most restrictive type that fits the data. Reach for `text` only when we really mean "any string."

Which SKILL.md can help here? Check out `rasa-managing-slots`, and look for the section _Choosing a slot type_.

## 4\. Validation has three layers. Start with the cheapest.

When a developer needs to validate a slot, the reflex is often to write a custom action. For example, `validate_phone_number`, `validate_email`, `validate_age`. In practice, three layers of validation exist, and most checks belong on the cheapest layer:

1. **Domain level** — `validation.rejections` on the slot. Regex, length, range. Runs globally whenever the slot is set.
2. **Flow level** — `rejections` on the `collect` step. Business rules that apply only within a specific flow.
3. **Custom action** — `validate_{slot_name}`. External API calls or logic that cannot be expressed declaratively.

A phone-number format check is layer one. Three lines of YAML. A "is this user over 18 for this specific flow" check is layer two. A "is this phone number deliverable according to our SMS provider's API" check is layer three.

If we find ourselves writing Python to check a regex, we are probably skipping two layers.

Which SKILL.md can help here? Check out `rasa-managing-slots`, section _Validation strategies_; and `rasa-writing-custom-actions`, section _Slot validation actions_.

## 5\. For simple API calls, an MCP tool call beats a custom action

This one is newer and therefore less known. As of Rasa 3.14.0, a flow can call an MCP tool directly from a `call` step, with explicit input and output mappings. For a category of integrations such as "take these two slot values, call an API, store the result in a slot," this step replaces the entire custom action.

The custom-action version of a simple order placement might be thirty lines of Python, an action class, a domain registration, and an action server running alongside our Rasa server. The MCP version is a YAML block:

`- call: place_buy_order    mcp_server: trade_server    mapping:      input:        - param: ticker_symbol          slot: stock_name        - param: quantity          slot: order_quantity      output:        - slot: order_status          value: result.structuredContent.order_status.success   `

Use a custom action when we need real logic. Examples of this include multiple calls, conditionals, access to the full tracker, and dispatcher messages. Use an MCP call when we are only moving data between a slot and an API. The rule the skill suggests is sharp and worth internalizing: if the transformation can be expressed in a Jinja2 output mapping, it probably should be.

Which SKILL.md can help here? Check out `rasa-calling-mcp-tools-from-flows`, section _When to use MCP vs a custom action_.

## 6\. e2e tests should assert on events

A common e2e test often looks like this:

`- user: "Where is my order?"   - bot: "Sure, what is your order ID?"   `

This works until someone rewrites the response, enables the rephraser, or adds a variation. Then every test that touches that response breaks, and the test suite develops the reputation of being flaky, which is how test suites die.

Rasa's e2e testing gives us assertions that are one layer deeper. Rather than matching bot text, we can assert that a specific flow started, a specific action executed, a specific slot was set, or a specific domain response was uttered by name:

`- user: "Where is my order?"    assertions:      - flow_started:          flow_ids:            - "track_order"      - bot_uttered:          utter_name: utter_ask_order_id   `

These assertions survive rephrasing, variations, and copy edits. They fail only when the behavior actually changes, which is the entire point of a test.

Which SKILL.md can help here? `rasa-writing-e2e-tests`, section _Assertions_.

## Why this matters for a Rasa developer

None of these six patterns is a secret. All of them are documented somewhere in the Rasa reference material. What the skills do is something slightly different: they encode the decision behind each pattern. They are structured to highlight when to use it, what it replaces, what the anti-pattern looks like, and what to write instead. All of this in a form a coding agent can consume and apply while we are working.

That is the thing I did not fully appreciate before I sat down to re-read our own bundle. A good skill is much more than just a prompt. It is a compressed lesson, shaped so that the tool we are working with can help us apply it without having to remember every detail ourselves.

For Rasa specifically, this matters for one reason. Conversational AI agents are not like traditional intent-and-response bots. The Command Generator is doing real work. It is routing, extracting, and slot filling. And most of its work is guided by the English-language text we write in our YAML files. Treating that text as engineering rather than documentation is probably the single highest-leverage shift a developer building Rasa conversational AI agents can make in a given afternoon.

The skill bundle makes that shift smaller. It meets us where our code is.

In the end, the practices in these SKILL.md files are not new. What is new is that we no longer have to discover them one project at a time.

_The Rasa Agent Skill bundle is available on GitHub. The fastest way to benefit from these skills freely available is to point our coding agent at the folder and start asking questions about our own project._

‍

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a4e00149219cb9fbc8edebd_Rasa_University_Blog_Banner.png)](https://rasa.com/blog/introducing-rasa-university-a-hands-on-learning-path-for-agent-engineers) [July 8, 2026\\ \\ /\\ \\ Building & Designing AI Assistants\\ \\ **Introducing Rasa University: A Hands-on Learning Path for Agent Engineers**](https://rasa.com/blog/introducing-rasa-university-a-hands-on-learning-path-for-agent-engineers)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

[read article](https://rasa.com/blog/introducing-rasa-university-a-hands-on-learning-path-for-agent-engineers)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a4c08ed302a49bbbe07192f_Rasa-Blog-How-to-Build-an-AI-Chatbot_-Step-by-Step-Guide.png)](https://rasa.com/blog/how-to-build-an-ai-chatbot) [June 17, 2026\\ \\ /\\ \\ Building & Designing AI Assistants\\ \\ **How to Build an AI Chatbot: Step-by-Step Guide**](https://rasa.com/blog/how-to-build-an-ai-chatbot)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a33f503d58e68a0261e6044_lindsay.jpeg)

Lindsay MacDonald

[read article](https://rasa.com/blog/how-to-build-an-ai-chatbot)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6903b87d814be8b2985dd2e3_1608730510-header-rasa-blog-post.avif)](https://rasa.com/blog/13-rules-for-cui-design) [June 9, 2026\\ \\ /\\ \\ Building & Designing AI Assistants\\ \\ **Conversational UI Design: 13 Rules That Still Work**](https://rasa.com/blog/13-rules-for-cui-design)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/13-rules-for-cui-design)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)