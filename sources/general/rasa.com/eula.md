# Source: https://rasa.com/eula

# The developer platform for enterprise AI agents

The developer platform

for enterprise AI agents

Rasa extends LLMs with your business logic to create reliable AI agents across millions of conversations, giving your team full control over behavior and performance.

[book a demo](https://rasa.com/connect-with-rasa)

[try now](https://hello.rasa.com/)

[try now](https://rasa.com/rasa-pro-developer-edition-license-key-request)

Top enterprises trust Rasa

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ef7bd8f4568496c646be06_autodesk_logo.svg.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68f8eddcfa3169325ce7a315_bnp%20paribas.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68f8eddc74c7dcce83b3d8b3_groupe%20ima.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ef7bd8a0baab03c5046663_swisscom.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68f8eddc4341fa416a3fb4db_providence.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/6903b0eb0559db4af59486e6_smartrecruiters.svg)

# The developer platform for enterprise AI agents

Rasa extends LLMs with your business logic to create **compliant** AI agents across millions of conversations, giving your team full control to build, deploy, and manage performance across every channel.

##### What would you like to build?

![Customer support agent](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69aec97d4eb2263a887c0a04_customer-support.svg)

Customer support agent

![Internal helpdesk agent](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69aec97cfa3ab51b28432d5e_user-icon.svg)

Internal helpdesk agent

![Search agent](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69aec97d4624954be3785123_search-agent.svg)

Search agent

![Voice agent](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69aec97d65979e93d64eae10_agent-voice.svg)

Voice agent

![Something else](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69aec97c84c999df688c942c_round-menu.svg)

Something else

[Get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e6dfa025a5fa33f59695d5_bg%20motion.webp)

Banking Agent main

Update available

banking-agent

This project helps automate tasks related to personal banking and financial management.

Test agent

Analytics Production

Conversations

125

In the last 7 days

Sessions

222%

In the last 7 days

Recent activity Refresh

May 04

Add Stock Explorer subagentNew

ag1144 · 5m ago

May 04

Connect trade\_server MCP toolsNew

8de256 · 4h ago

May 04

Scope tool permissions for trading

9123gr · 2d ago

May 03

Tune Stock Explorer prompt template

87da34 · 3d ago

May 02

Add technical analysis flow

b21f08 · 4d ago

Show earlier activity

Details

Agent details GitHub

Modelsopenai-gpt-4o

Languagesen, de, fr

Channels WhatsApp Messenger

Integrations

Action serverscard\_details, fraud\_prevention + 3 more

Tools inventory\_server payment\_server customer\_database

Knowledge base Salesforce

Skills

card actions

6 flows

investments

12 flows

fraud\_detection

Monitor transactions to identify and prevent fraudulent activities

loan\_eligibility\_assessment

Evaluate user's financial data to determine loan qualification

investment\_research

Help user research and analyze investment options

ReAct

investment\_portfolio\_tracking

Provide real-time updates and insights on user's investment holdings

budget\_planning

Assist users in creating and managing monthly budgets

New chat

👋 What can I help you do today?

What's Acela Tech trading at right now, and any news I should know about?

Worked for 8 seconds ▸

ACLT is at $184.20, up 1.4% today. Recent headlines: a new data-center chip announced this morning, a Meridian Capital upgrade, and continued coverage of supply constraints. Want me to dig into any of these?

Run the technicals on it.

Activated Stock Explorer subagent

Worked for 11 seconds ▸

On the daily: price is above its 50- and 200-day moving averages, RSI is 68 (nearing overbought), and it's testing resistance around $186. MACD is positive but flattening. For context, not a recommendation, that mix often points to a stock that's extended after a strong run.

Message...

sub\_agents / stock\_explorer / **config.yml**

agent**:** name**:** _stock\_explorer_ protocol**:** _RASA_ description**:** _"Researches stocks, surfaces company news, and runs technical analysis on request."_ configuration**:** llm**:** model\_group**:** _openai-gpt-5-1_ timeout**:** 30 tool\_timeout**:** 30.0 max\_retries**:** 3 include\_date\_time**:** true module**:** "path.to.custom.module" connections**:** mcp\_servers**:** - name**:** _trade\_server_ include\_tools**:** _\- find\_symbol_ _\- get\_company\_news_ _\- apply\_technical\_analysis_ _\- fetch\_live\_price_ exclude\_tools**:** - place\_buy\_order - view\_positions

rasa runlocalhost:50053 agents · 1 mcp

Top enterprises trust Rasa

![Autodesk](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ef7bd8f4568496c646be06_autodesk_logo.svg.svg)![BNP Paribas Fortis](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68f8eddcfa3169325ce7a315_bnp%20paribas.svg)![Groupe IMA](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68f8eddc74c7dcce83b3d8b3_groupe%20ima.svg)![Swisscom](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ef7bd8a0baab03c5046663_swisscom.svg)![Providence](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68f8eddc4341fa416a3fb4db_providence.svg)![Smart Recruiters](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/6903b0eb0559db4af59486e6_smartrecruiters.svg)

### Features

#### Patented dialogue management

Rasa provides a patented dialogue management system designed for enterprise AI agents. It orchestrates autonomous reasoning, guided workflows, and shared conversational memory within a builder-friendly architecture.

Teams can design, test, and refine complex conversational logic while maintaining transparency and control, enabling agents to reliably support structured business processes and adapt to real-world interactions.

[GET a demo](https://rasa.com/connect-with-rasa)

![Patented dialogue management](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69ba8975f93fdcf183afbb37_45eca8564e1619f8ab7a03eed5219cd0_finance-agent-chat.webp)

#### On-prem / private cloud deployment

Deploy Rasa on your own infrastructure, private cloud, or fully offline environments—including air-gapped deployments when required. Organizations retain full control over their data, security, and model providers.

Built with regulated industries in mind, Rasa enables teams to meet strict compliance and governance requirements without sacrificing flexibility in infrastructure, integrations, or AI model choice.

[GET a demo](https://rasa.com/connect-with-rasa)

![On-prem / private cloud deployment](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69ba9fd7377c8bcfad816118_26017b77c53327f970f7747a62930775_telecom-agent-chat.avif)![On-prem / private cloud deployment](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/6a059f88e4bbe26234f3a422_b0f6d474568886ea0235e9297fe9c3fb_on-prem-private-cloud-deployment-mobile.avif)

#### Multi-agent orchestration

Rasa enables organizations to coordinate multiple AI agents across systems and workflows. Agents can share conversational state, access unified memory, and hand off tasks seamlessly between domain-specific skills.

This architecture allows teams to start with a single production agent and scale to a distributed network of enterprise agents without redesigning their underlying conversational infrastructure.

[GET a demo](https://rasa.com/connect-with-rasa)

![Multi-agent orchestration](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69ba9fd8d438330652af5be3_1f19cbaf6c1742d731df873bfaa0f737_telecom-agent-chat-latest.webp)![On-prem / private cloud deployment](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/6a05f6341540e694b56f019a_telecom-agent-chat-latest-mobile.avif)

#### Open framework

Built on open principles and inspired by its open-source roots, Rasa provides full access to prompts, policies, and the underlying codebase. Teams can choose their preferred LLMs, infrastructure, and integration layers without vendor lock-in.

This flexibility allows organizations to adapt the framework to evolving requirements while maintaining full visibility and control over their AI systems.

[GET a demo](https://rasa.com/connect-with-rasa)

![Open framework](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69ba9fd72cac7303bb722edc_77e10ca0d79bbeb47c8e3a6a7043f579_telecom-agent-chat-code.avif)

#### Voice/IVR

Rasa supports real-time voice interactions designed for natural, human conversation. Low-latency processing enables streaming speech recognition, fast turn-taking, and responsive dialogue flow across phone and voice channels.

The system supports core voice primitives such as barge-in, turn-taking, and background noise handling, allowing AI agents to manage interruptions, respond quickly, and sustain fluid back-and-forth conversations.

[GET a demo](https://rasa.com/connect-with-rasa)

![Voice/IVR](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69ba9fd8bb6f9295e08a127d_7f5458cc8cdd6149ad3a39078a1e852f_telecom-agent-chat-preview.avif)

#### Real-time observability and control

Rasa provides built-in tools to monitor, evaluate, and improve AI agent behavior in production. Teams can trace conversations, inspect decision paths, and analyze workflow performance to quickly diagnose issues.

With transparent logs, evaluation tools, and feedback loops, organizations maintain operational oversight while continuously optimizing agent reliability, safety, and business impact.

[GET a demo](https://rasa.com/connect-with-rasa)

![Real-time observability and control](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69ba9fd868d2a0ad15bfab76_ecc4986a70ab7a0ac000ab4de47e6069_telecom-agent-dashboard.avif)

#### How it works

![Copilot code feature](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69bb8bbb6e352e9db2e1e9e3_51377a9fdff347404e985bebc987c6dd_copilot-code-feature.avif)![Copilot code feature](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69bbc5b696bc4136f9e22633_fed822e51ec15682d568de38b26559d9_copilot-code-feature-mobile.avif)

**1: Build** your conversational voice or chat agent in our open developer framework using our coding copilot to accelerate development and follow best practices.

![Rasa slack feature](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69bb8bbba62439401ddaaa8f_a9d8b1a34f16c785157f4d24c724d7b7_Rasa-slack-feature.avif)![Rasa slack feature](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69bbc5b6ac983a731eb17d93_603b711a636550d2673dacf28d16ce0b_Rasa-slack-feature-mobile.avif)

**2: Deploy** your Rasa Agent on your own infrastructure while Rasa orchestrates conversations, guided flows, external agents, and knowledge retrieval.

![Rasa performance dashboard](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69bb8bbb291b0a3f41995972_7eedca4981fd1c889d4fd1e9b04ca24c_Rasa-performance-dashboard.avif)![Rasa performance dashboard](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69bbc5b6da6242586054ad36_146ebe044fcf7ad0a41b641be4874582_Rasa-performance-dashboard-mobile.avif)

**3: Refine** your agent in Rasa Studio to optimize the experience and track performance across channels and modalities.

[Get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69eb30ab7589ff9a8796b5f3_bg.jpg)

![Forrester](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69e233d3e2a33cd31d95e661_5843f1680376cee950b55d9f3728be3f_forrester.webp)

THE FORRESTER WAVE™: CONVERSATIONAL AI PLATFORMS FOR CUSTOMER SERVICE, Q2 2026

## Strong Performer

Conversational AI Platforms For Customer Service, Q2 2026 evaluated among 14 leading enterprise platforms.

5/5

Resource Orchestration

5/5

App Lifecycle Management

5/5

Pricing Transparency

[read the report](https://rasa.com/forrester-wave-2026)

![The Forrester Wave](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69e106edc6eec59b11d15bd4_6874bf41fa71742c28141bf091b13d82_forrester-wave-chart.webp)![The Forrester Wave Strong Performer Q2 2026](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69e106f3ffd0b2fb5acdb17d_3917a53e57bde1c14bd37e57b81feb1e_forrester-badge.webp)

## The powerful engine behind reliable AI agents

Rasa Platform

## The powerful engine 

## behind reliable AI agents

The Rasa Platform gives you complete control over how your AI agents reason, respond, and perform, offering a flexible development experience that fits both technical and business teams.

[See how it works](https://rasa.com/platform)

[Full control, no black boxes\\ \\ Build, version, and test agents with complete visibility, whether you build visually or with code.\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9040b0fcf62585a2fc1b0_card%20bottom%201.avif)\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e90496dc633c8e8f96c978_shape.svg)](https://rasa.com/#) [Performance at scale\\ \\ Rasa agents stay fast, flexible, and cost-efficient by using LLMs only when needed.\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9040b0fcf62585a2fc1b0_card%20bottom%201.avif)\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/690e08d2a156687b9e48b589_shape.webp)](https://rasa.com/#) [Customized to your business\\ \\ Integrate with existing systems, handle complex logic, and deploy however you want, whether on premises, in your infrastructure, or managed by our partners.\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9040b53096a83414c3f76_card%20bottom%203.avif)\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e90496a6137034a06c3a04_shape%203.svg)](https://rasa.com/#)

## See what our customers are saying

customers

## See what our

## customers are saying

Enterprise teams use Rasa to build and deploy high-trust AI agents that perform in production.

![providence logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079ac6593b8f9b948a9483_6a079aa2343867bc5795ec64_providence-white.svg)

We've built a scalable, compliant platform with Rasa that supports real patient needs and drives measurable outcomes. CALM gives us a framework to keep that momentum going, with the flexibility to grow responsibly as expectations around AI continue to evolve.

Wayne Foley

Director Software Engineering, Digital Innovation Group, at Providence

![Serbia eUprava logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a0e2d7c3f5cc942a6af20bf_6902c179134e73373f50b849_cs%2520logo%2520euprava.avif)

With Rasa, we launched quickly and gave citizens a simpler way to access government services. The system allows us to expand at our own pace while controlling how services are delivered. Studio and CALM allow us to build new use cases while maintaining stability as the platform grows.

Bogdan Stešević

Head of the Group for Quality of Services and Development of AI at eUprava

![groupe-ima logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079acb1fa98b137182d22c_6a079aa5088fa5614f9615d0_groupe-ima-white.svg)

We’re not experimenting with voice. We’re deploying it. That’s the difference.

Loic Mayet

Information Systems Director, Groupe IMA

![eddy-travels logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079aca69c67892132dbd3c_6a079aa4c5fb00cf257abc91_eddy-travels-white.svg)

Switching to Rasa accelerated development. We now process thousands of conversations each month with 96% accuracy, which resulted in better user engagement and more searches per conversation.

Edmundas Balčikonis

CEO, Eddy Travels

![orange logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079ac987600fd93013f639_6a079aa3fb59efcce62cb908_orange-white.svg)

We developed a real partnership with Rasa based on developing skills rapidly, correcting bugs quickly, and sharing a wish list with the dev team.

Richard Popa

Project Leader and Solutions Manager, Orange

![albert-heijn logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079ac7d754e68eee4e5e4f_6a079aa3c0460e36625e8b8e_albert-heijn-white.svg)

Albert Heijn adopted Rasa and began migrating to CALM through a coexistence strategy — starting with a single flow and gradually expanding coverage, achieving a 22% improvement in prevented contact rate and a 37% increase in quality score.

Albert Heijn

Largest supermarket chain in the Netherlands

![providence logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079ac6593b8f9b948a9483_6a079aa2343867bc5795ec64_providence-white.svg)

Grace acts as a multi-purpose patient-facing assistant — booking appointments, routing based on symptoms, and helping users navigate their care journey entirely through our app.

Providence Health

Digital Innovation Team

![nib-group logo](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a079ac5343867bc5795f6b3_69037213afd6918bcce68a18_nib%2520logo.svg)

With Rasa, we consolidated five bots into a single assistant experience. Fallback rates dropped from 18% to 3.5%, and we’re now expanding to voice.

nib Group

Digital Team Lead

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69dcf786162d6c11ad1052ad_n26.svg)

N26 transitioned from concept to production in just four weeks, deploying the AI assistant within their secure cloud environment to maintain full data control.

N26

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69dcf6f6446b5f8fbb5819c0_nib%20group.svg)

Rasa’s platform enabled us to customize and scale our AI assistant’s capabilities, ensuring it evolved with changing member needs and organizational goals.

nib Group

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68e930414439d143e674b947_ergo%20logo.svg)

With Rasa, we at ERGO are completely rethinking how we build customer support experiences. It’s about developing faster and cheaper, and at scale. Rasa helps us to realize these goals.

Gregor Wiest

Head of Innovation, ERGO Group AG

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68e92ff6638de532dba7c2c6_t-mobile.svg)

Since the chatbot based on Rasa CALM can process around 50% of service desk inquiries independently, we reduced the need for human agents by approximately 30%. Thanks to the excellent backend integration capabilities of the Rasa solution, we quickly implemented the chatbot’s self-service features.

Roland Csibi

Service Hub Owner – User Support Service Hub

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68e92fa938a73b8083fc4807_swisscom.svg)

Our goal was to align cutting-edge AI technology with customer needs to provide seamless and innovative experiences. Partnering with Rasa allowed us to rethink how conversational AI could transform support.

Daniel Schupmann

Head of CAI/ GenAI @B2C and Digital Care Platforms/ Experience

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68e92f3d9bfbe47c60310488_autodesk%20logo.svg)

We needed a solution that could scale with our ambitions. Rasa solves some hard problems related to conversational AI that enable us to move faster.

James Bradley

Senior Director of Data Science & Machine Learning

## The powerful engine behind reliable AI agents

features

## Built-in Voice, IVR, and

## omnichannel support

[Text & Messaging\\ \\ Deploy across web, mobile, and messaging apps with built-in support for natural, fluid conversations.\\ \\ Build better chat experiences\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e93339e754b0a3e6b323ff_pattern.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e932015cb968c049305bf9_gradient%201.webp)](https://rasa.com/chat) [Voice Gateway\\ \\ Launch seamless voice experiences with built-in turn-taking, timeouts, and latency control.\\ \\ Power your voice AI\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e933399774ec46b987bd97_pattern%202.svg)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9320149aec29bd0dcdefe_gradient%202.webp)](https://rasa.com/voice)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e93a89c1ea8454b2ed2017_gradient%20spotlight.avif)

## Building with high trust agents drives results

impact

Building with high trust

agents drives results

See how enterprise teams ship faster, automate more, and keep full control with Rasa.

50%

Cost reduction in operational expenses across 50+ enterprise deployments

59%

Goal completion rate per conversation

4.4

Star customer satisfaction consistently maintained

## AI that adapts to your business, not the other way around

use cases

## AI that adapts to your business,

## not the other way around

Use Rasa across your organization and teams to automate key interactions without changing how you work.

[Customer Experience\\ \\ Deliver faster, more efficient service across channels, at scale.\\ \\ See how teams deflect routine requests\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9040b0fcf62585a2fc1b0_card%20bottom%201.avif)\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e93e7b3d1f4d01748fcba6_square%20swirl.svg)](https://rasa.com/use-cases/customer-experience) [Sales\\ \\ Guide prospects, qualify leads, and hand off at the right moment.\\ \\ Explore sales and conversion flows\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9040b0fcf62585a2fc1b0_card%20bottom%201.avif)\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e93e7bb5625ba1efd90a04_pathway.svg)](https://rasa.com/use-cases/sales-enablement) [Employee Experience\\ \\ Automate internal tasks in IT, HR, and operations with always-available AI agents.\\ \\ Reduce manual requests across departments\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e9040b53096a83414c3f76_card%20bottom%203.avif)\\ \\ ![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68e93e7b066c6c12e39f4f96_circle%20move.svg)](https://rasa.com/use-cases/operational-efficiency)

## AI that adapts to your business, not the other way around

team

## A trusted and

## experienced team

[meet the team](https://rasa.com/about#team)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69205385ef2d9d8598be27e2_AmyJordisonPhotography-46AJc_websize%20(1)%20(1).avif)![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69205385e273338ec3838333_image%20(1).avif)![Smiling man with short gray hair and round tortoiseshell glasses wearing a red shirt against a blurred light background.](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69661f003d9865c1cc096775_AmyJordisonPhotography-145AJe_websize.avif)![Smiling woman with long wavy hair wearing a dark blouse against a neutral background.](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/69661f01f67c2ff2f8547e0f_AmyJordisonPhotography-59AJe_websize.avif)

## Learn more about Rasa and Conversational AI

resources

Learn more about Rasa

and Conversational AI

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6901309c27e645f7fc780835_File%2017.avif)\\ \\ **Conversation Design in the Age of AI Agents**\\ \\ Our new conversation design blueprint shows how to build assistants that solve real problems. Download the blueprint and see why modern conversation design is more important than ever.\\ \\ View Ebook](https://6711345.fs1.hubspotusercontent-na1.net/hubfs/6711345/2025%20eBooks/Rasa_Conversation%20Design%20AI%20Agents.pdf)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/691dd2e1db9156904a9ab39e_690135076c4aabc93d3a7fc0_calm.avif)\\ \\ **Building Conversational AI Assistants with CALM**\\ \\ Learn the fundamentals of building conversational AI assistants using CALM, powered by Rasa Pro.\\ \\ View Tutorial](https://info.rasa.com/building-conversational-ai-assistants-with-calm-video-tutorial-series)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6901365535d3ba476764d782_thumbnail15.avif)\\ \\ **Beyond Prompt-and-Pray: Building Reliable LLM-Powered Software in an Agentic World**\\ \\ Join Alan Nichol, Rasa Co-Founder and CTO, Lauren Goerz, Sr. Technical Marketing Engineer, and Bertisa Grezda, Customer Success Manager, to learn how leading companies are moving beyond the risky "prompt-and-pray" methodology to develop reliable, secure, and scalable AI systems.\\ \\ View Online Event](https://info.rasa.com/webinars/beyond-prompt-and-pray)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6903ad1edc49b20a41d4e989_guide.avif)\\ \\ **Conversational AI Platform Buyer's Guide**\\ \\ Navigate the world of generative conversational AI solutions and make the right choice to drive business success and innovation.\\ \\ View Guide](https://info.rasa.com/conversational-ai-platform-buyers-guide?utm_campaign=2024-10-Conversational-AI-Buyers-Guide&utm_source=Website&utm_medium=Resources)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)