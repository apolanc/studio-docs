# Source: https://rasa.com/blog/introducing-rasa-university-a-hands-on-learning-path-for-agent-engineers

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a4e00149219cb9fbc8edebd_Rasa_University_Blog_Banner.png)

# Introducing Rasa University: A Hands-on Learning Path for Agent Engineers

Posted Jul 08, 2026

Updated

![Lauren Goerz](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffe8c84713f6207e5dc1a8_lauren-goerz.avif)

Lauren Goerz

Somewhere out there is a developer who built "Alexa, but better" on a Raspberry Pi with the Rasa Framework. Another community member picked up a Rasa project mostly as an excuse to finally get good at Python. Someone else again wanted a Rasa certification to strengthen a job application. When I joined Rasa in 2021, these were the people who surprised me most. They weren't just using the Rasa Framework to ship a product. They were also using it to learn, and they wanted to understand what they were building deeply enough to use it for both their jobs and their passion projects.

Today those learners get a proper home. Rasa University is live, and the first course, the Rasa Developer Certification (Foundations), is a hands-on, self-guided path to building conversational AI agents with Rasa. Free to access, start any time at [rasa.com/university](https://hellorasa.info/4p81A39).

## People have always been using Rasa to learn

Rasa has survived every wave of this field since 2016, in large part because we focused on becoming the standard framework for conversational AI, and education was part of that from the beginning.

The vocabulary has clearly shifted since then. What we called AI assistant developers we'd now call agent engineers, and virtual assistants became AI agents. The problems got bigger too: transactional conversational interfaces with varied levels of autonomy, connected to multiple systems, and built by multiple disparate teams. But the initial instinct that brought people to Rasa hasn't changed. It's the place to be if you want to build something real. Understand how it works. And see how far you can push it.

## What is Rasa University?

Rasa University is a free, structured, hands-on learning path for developers who want to build conversational AI agents with the Rasa Framework. The first course, Rasa Developer Certification: Foundations, is progressive and takes you from a basic FAQ agent to a fully orchestrated agent with memory, integrations, document search, and autonomous tool-calling. Complete all six chapters of the course, and you earn your Rasa Developer Certificate. So far, folks have been completing the course in around 3.5 hours.

In every chapter, you get a hands-on keyboard lab. You build something and test it directly in the course before moving on.

## Who is Rasa University for?

We built the Foundations course for agent engineers working on complex, transactional conversational interfaces. The agent you build connects to real systems, collects information across multi-turn conversations, retrieves from knowledge sources, and handles the full range of what users actually say.

If you're new to Rasa, this is the fastest path to a working mental model of how the platform behaves in production. If you've built with Rasa before, this course will help you get to know newer parts of the Framework you haven't used yet.

To start, you'll need an OpenAI API key, a free [Rasa Developer Edition license](https://hellorasa.info/4wbNC33), and some comfort with the command line and Python.

You don't need a machine learning background: if you can work in a terminal and read Python, you can complete the course. The OpenAI key covers the LLM calls your agent makes while you build and test, and the usage involved in finishing the course is small.

## What does the Foundations course cover?

The course covers the full spectrum of autonomy in the Rasa Orchestrator, from hard-coded responses to autonomous, prompt-driven dialogue with intelligent tool-calling. Each chapter builds on the last.

- **Set up and install.** Install Rasa and configure your environment.
- **Chapter 1** starts with responses, the smallest unit of conversation. Some are hard-coded, some rephrased. Hard-coded responses are your safety net when the agent needs to say the same thing 100% of the time. This chapter also gets you familiar with the Rasa project structure.
- **Chapter 2** connects your agent to external systems through Custom Actions: API calls and backend logic. This is the part of Rasa that runs when a conversation needs to do something, not just say something.
- **Chapter 3** is memory. You'll define what the agent stores across turns, so it stops doing the thing every user hates: asking for the order number they gave two messages ago. We've been developing the memory layer of the platform for close to a decade, and it's one of the parts many frameworks still require you to build yourself.
- **Chapter 4** is about collecting several pieces of information in a single conversation, in the right order, while handling the messy reality of how users respond: out of order, with corrections, with digressions in the middle of a task.
- **Chapter 5** covers Enterprise Search (RAG - Retrieval Augmented Generation). You'll set up your agent to search document sources and return grounded responses, and you'll see how the Orchestrator decides when to retrieve versus when to follow a guided path.
- **Chapter 6** is the far end of the spectrum: sub-agents and tool use with an MCP (Model Context Protocol) server. An LLM reasons through open-ended requests, picks the right tool, and generates a response from what comes back. By the end of this chapter, your agent covers the full spectrum of dialogue, from fully guided to completely autonomous.

You'll finish the course with three things: a working agent in a project you keep, a mental model of guided versus autonomous dialogue that transfers to any agent architecture discussion, and your Rasa Developer Certificate.

## How does Rasa University stay current?

Every course updates as the Framework evolves. We're actively developing Rasa, and how we think about dialogue management, memory, and orchestration keeps advancing, which means a tutorial written two years ago probably isn't a perfect reflection of the platform today. There's a lot of good-faith community content out there that can be misleading, as Rasa has changed a lot since 2016.

We'll keep updating this course for each new Rasa release so you can get access to the latest. The goal is a learning path that reflects how Rasa works today, not how it worked whenever someone last had bandwidth to write something up.

## How do I sign up?

The Rasa Developer Certification: Foundations course is self-paced and available any time at [rasa.com/university](https://hellorasa.info/4p81A39). You can always log back in and pick up where you left off.

And when you get stuck, come find us. My colleagues and I are in the #rasa-university channel on our Discord, waiting for your questions. 

‍

‍ 
**_‍_**

**_Thank you_**

_Massive shoutout to our partners at_ [_Codio_](https://www.codio.com/)_, Lola, and team, for helping us realize our "DataCamp, but for Rasa" ambitions and making self-serve learning for partners and the community possible._ 

_And a huge thank you to_ [_Dr. Dilini Sumanapala_](https://www.linkedin.com/in/dilini-k-sumanapala-phd/) _for her contributions as course architect, building out the course structure, assessment strategy, and much more. This wouldn't exist without you._

‍

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a4c08ed302a49bbbe07192f_Rasa-Blog-How-to-Build-an-AI-Chatbot_-Step-by-Step-Guide.png)](https://rasa.com/blog/how-to-build-an-ai-chatbot) [June 17, 2026\\ \\ /\\ \\ Building & Designing AI Assistants\\ \\ **How to Build an AI Chatbot: Step-by-Step Guide**](https://rasa.com/blog/how-to-build-an-ai-chatbot)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a33f503d58e68a0261e6044_lindsay.jpeg)

Lindsay MacDonald

[read article](https://rasa.com/blog/how-to-build-an-ai-chatbot)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6903b87d814be8b2985dd2e3_1608730510-header-rasa-blog-post.avif)](https://rasa.com/blog/13-rules-for-cui-design) [June 9, 2026\\ \\ /\\ \\ Building & Designing AI Assistants\\ \\ **Conversational UI Design: 13 Rules That Still Work**](https://rasa.com/blog/13-rules-for-cui-design)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/13-rules-for-cui-design)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a4d56d4bb8d3daa2b1b1192_Rasa-Blog-10-Best-Ecommerce-Chatbots-for-2026-(Buyer%27s-Guide).png)](https://rasa.com/blog/10-best-ecommerce-chatbots-for-2026-buyers-guide) [June 2, 2026\\ \\ /\\ \\ Building & Designing AI Assistants\\ \\ **10 Best Ecommerce Chatbots for 2026 (Buyer's Guide)**](https://rasa.com/blog/10-best-ecommerce-chatbots-for-2026-buyers-guide)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a33f503d58e68a0261e6044_lindsay.jpeg)

Lindsay MacDonald

[read article](https://rasa.com/blog/10-best-ecommerce-chatbots-for-2026-buyers-guide)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)