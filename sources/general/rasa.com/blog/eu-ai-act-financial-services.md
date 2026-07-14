# Source: https://rasa.com/blog/eu-ai-act-financial-services

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69d81d24346a2288bc2e4892_Rasa-Blog-Image-option1.png)

# The EU AI Act and Data Sovereignty

Posted Apr 08, 2026

Updated

![Maria Ortiz](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

**Table of Contents**

- What the EU AI Act requires of financial institutions
- The EU AI Act compliance timeline
- Where data sovereignty enters the picture
- What conversational AI teams need to know
- What “high-risk” actually means for your AI stack
- What good preparation looks like 

A new era of AI regulation, ushered in by the [Artificial Intelligence Act](https://artificialintelligenceact.eu/), is already underway in the European Union. For financial institutions operating in the EU, whether they’re headquartered in Frankfurt, Singapore, or New York, the compliance clock is ticking. The most consequential deadline lands on August 2, 2026, when full obligations for high-risk AI systems kick in (more on that below).

But here's what often gets missed in the compliance conversation: The EU AI Act doesn't exist in isolation.

For financial services companies, it sits on top of the [GDPR](https://gdpr-info.eu/) (General Data Protection Regulation), intersects with [DORA](https://www.eiopa.europa.eu/digital-operational-resilience-act-dora_en) (the Digital Operational Resilience Act), and connects directly to broader questions about data sovereignty like where your data lives and who controls it. Understanding how these frameworks interact is what separates organizations that are genuinely ready to meet AI regulatory standards from the ones that aren’t.

Below, we cover the practical implications for AI leaders and technology decision-makers at financial institutions. 

## Key takeaways:

- **The EU AI Act's most critical deadline for financial institutions is August 2, 2026.** The Act entered into force in August 2024 and is being phased in through 2027, but it is the 2026 date when full obligations for high-risk AI systems apply.
- **Several AI use cases common in financial services are explicitly classified as high-risk under Annex III of the Act.** This includes credit scoring, insurance pricing, and certain customer service AI, each of which triggers significant compliance obligations.
- **The EU AI Act doesn't operate in isolation.** For financial institutions, it intersects directly with GDPR and DORA, making data sovereignty, auditability, and third-party risk management inseparable from AI Act compliance.
- **Financial institutions that cannot demonstrate control over where their AI data is processed and stored will struggle to meet the Act's audit, logging, and transparency requirements.** This is true regardless of their existing GDPR posture.
- **Non-compliance is costly, and penalties can stack.** AI Act fines reach up to €35 million or 7% of global annual turnover, which is higher than GDPR, and can compound alongside GDPR, DORA, and NIS2 penalties for overlapping failures. 

## What the EU AI Act requires of financial institutions

The EU AI Act classifies AI systems into four risk tiers. For most financial institutions, the high-risk category is where the most attention needs to be paid.

- **Prohibited (unacceptable risk):** Systems that violate fundamental rights are banned outright. This includes social scoring, manipulative AI, and real-time biometric identification in public spaces, among others.
- **High-risk:** Systems that pose significant risk to health, safety, or fundamental rights are permitted but heavily regulated. Several use cases common in financial services fall here (more on this below).
- **Limited risk:** Systems subject to lighter transparency obligations. The biggest requirement is that users are informed they are interacting with AI. Chatbots and deepfake-generating tools fall into this category.
- **Minimal risk:** The majority of AI applications in use today (e.g., spam filters, recommendation engines, and similar tools) fall here and face no mandatory obligations under the Act.

Under Annex III of the Act, several use cases common in financial services are explicitly classified as high-risk, including:

- AI systems that evaluate the creditworthiness of natural persons or establish credit scores
- AI for risk assessment and pricing in life and health insurance
- Certain fraud-related and customer service AI systems that handle sensitive personal data

If your organization deploys conversational AI that touches any of these workflows, you need to take a careful look at how that system is classified. That’s true even if you deploy these tools indirectly or as a supporting layer.

The Act makes a critical distinction between _providers_ (those who develop or place an AI system on the market) and _deployers_ (those who use it in a professional context). Financial institutions are often deployers, but the line can be difficult to pin down. If your team substantially modifies a third-party AI system, retrains it on proprietary data, or repurposes it beyond its original intended use, the Act may reclassify you as a provider. For example, if you extend one of the general-purpose AI models or generative AI for customer service to assist with loan eligibility queries, you could qualify as a provider under the Act and face significantly heavier obligations.

For providers and deployers of high-risk systems, the core requirements are: 

- A robust risk management system across the AI lifecycle
- Data governance documentation for training and validation datasets
- Automatic record-keeping that logs relevant events
- Human oversight mechanisms built into the system
- Technical documentation sufficient to demonstrate compliance to regulators on request

These mandates require visibility into your AI stack that many organizations simply don't have today. 

## The EU AI Act compliance timeline

The Act's obligations are rolling out in phases, and several have already passed:

- **February 2025**: Prohibited AI practices are banned; AI literacy obligations begin
- **August 2025**: GPAI (General Purpose AI) model obligations and governance rules go into effect
- **August 2026**: Full high-risk AI system obligations apply, setting a critical deadline for financial services organizations
- **August 2027**: Extended deadline for AI embedded in regulated products

The [Digital Omnibus proposal](https://digital-strategy.ec.europa.eu/en/library/digital-omnibus-regulation-proposal) introduced by the European Commission in November 2025 may adjust some of these timelines, but institutions would be unwise to plan around delays. Regulators are already active, and DORA audits are happening now. 

## Where data sovereignty enters the picture

The EU AI Act itself does not mandate where data is stored. But, for financial institutions, data sovereignty and AI compliance are inseparable in practice, due to the regulatory framework they operate within.

### The AI Act: auditability and logging

Now, the AI Act is layered on top. As noted above, that means high-risk AI systems must have: 

- Documented data governance for training and validation datasets ([Article 10](https://artificialintelligenceact.eu/article/10/))
- Automatic event logging throughout their lifecycle ([Article 12](https://artificialintelligenceact.eu/article/12/))
- Transparency sufficient to explain inputs and decisions to regulators and affected individuals ([Article 13](https://artificialintelligenceact.eu/article/13/))

When your data platform runs on infrastructure you operate, your monitoring stack sees incidents as they happen. With a managed cloud platform, you become aware of incidents when the vendor notifies you, typically after their internal investigation. That gap can compress your regulatory reporting window in ways that create direct compliance exposure under DORA.

### DORA and third-party risk

DORA requires financial institutions to maintain operational resilience in their ICT systems and to demonstrate tight control over third-party technology providers, including those supplying AI. If your AI vendor subcontracts elements of model training or data management, DORA's third-party risk requirements apply down the chain. The stakes are particularly high: seven out of eight categories of high-risk AI systems identified by the AI Act involve the processing of personal data, according to [Grant Thornton](https://www.grantthornton.nl/en/insights-en/advisory/the-gdpr-and-the-ai-act-the-upcoming-challenge-of-financial-institutions/). That means GDPR compliance is directly embedded in AI Act compliance for the vast majority of high-risk use cases in this sector.

The practical implication: organizations that cannot demonstrate control over where their AI data is processed, stored, and accessed will be challenged not just to satisfy data sovereignty requirements, but also to meet the audit, logging, and transparency obligations the AI Act specifically demands.

‍**‍**

## **What conversational AI teams need to know**

Conversational AI sits at the center of many of the EU AI Act’s most consequential requirements for financial institutions. The obligation to inform users they are interacting with AI, the requirement to label AI-generated content, and the human oversight mandate all apply directly to the chat and voice interfaces many institutions are actively deploying today.

### **Credit scoring and loan eligibility via chat**

Consider this common scenario: a customer interacts with a bank’s conversational AI to understand their loan eligibility. If that agent is drawing on or influencing a creditworthiness assessment, it likely qualifies as a high-risk AI system under Annex III, regardless of whether the final decision is made by a human. The conversation interface doesn’t change the classification. What matters is the function the AI is performing and the data it is processing.

This means the full weight of high-risk obligations applies, including documented data governance, automatic event logging, human oversight mechanisms, and the ability to explain the system’s behavior to regulators on request. Building these requirements into a conversational interface after the fact is difficult. They need to be part of the architecture from day one.

### **Emergency response and critical infrastructure routing**

AI systems used in the management and operation of critical digital infrastructure are classified as high-risk under Annex III. In practice, this can include conversational AI deployed to triage and route [emergency response calls](https://rasa.com/customers/groupe-ima) or coordinate utility services. For organizations operating in these environments, the same high-risk compliance framework applies, with particular emphasis on human oversight and the ability to intervene in automated decisions.

### **Synthetic content labeling and the CALM advantage**

Under [Article 50](https://artificialintelligenceact.eu/article/50/) of the EU AI Act, providers of AI systems that generate synthetic text, audio, or video must ensure outputs are marked as artificially generated in a machine-readable format. For conversational AI, this creates a meaningful distinction between two types of responses: those generated dynamically by a large language model and those delivered via predetermined, deterministic flows.

Platforms that allow enterprises to define structured conversation flows, where specific responses are governed by business logic rather than generated on the fly, give compliance teams more clarity over what needs to be labeled and what doesn’t. Rasa’s [CALM architecture](https://rasa.com/calm) is designed around the principle that deterministic flows deliver predetermined responses, while generative responses are reserved for interactions where they add value. That distinction matters both for compliance and for the operational task of managing disclosure obligations at scale.

### **Emotion recognition: a forward-looking risk**

The Act currently prohibits the use of emotion recognition AI in workplaces and educational institutions, except for medical or safety reasons. This ban does not yet extend to customer-facing conversational AI. However, organizations using black-box AI agents in customer service should be aware of the risk if the regulatory perimeter expands. If your vendor’s model is routing or responding to customers based on inferred emotional state, and you don’t have visibility into how it works, you may have limited ability to demonstrate compliance if that use case comes under scrutiny. Deployers simply cannot rely on their vendors to carry that burden for them. 

## What "high-risk" actually means for your AI stack

For technology leaders building or procuring conversational AI in financial services, the high-risk classification has concrete architectural implications.

- **Human oversight is a design requirement.** The Act requires that high-risk AI systems be designed to allow for human intervention. For conversational AI, this means your system architecture must include mechanisms for human agents to monitor, override, or flag AI-driven interactions, particularly in any flow that could affect a customer's financial standing or access to financial services. This can't be retrofitted easily, so it needs to be baked in from day one.
- **Auditability requires visibility into your model.** You cannot produce the technical documentation the Act requires if your AI system is a black box. Vendors that obscure their model behavior, hide prompt logic, or make it difficult to trace how a decision was reached are operationally incompatible with the regulation. A key distinction for financial institutions is whether they develop their own AI systems or purchase them from external providers, because each role carries different regulatory obligations. Either way, the ability to explain the system's behavior to regulators is non-negotiable.
- **Purpose drift creates provider liability.** Repurposing a general-purpose AI model deployed initially for customer service into a creditworthiness evaluation tool directly engages the high-risk category under Annex III, and this purpose shift immediately converts the institution into a provider under Article 25. As organizations expand their AI capabilities, governance processes need to catch these transitions before they create unmanaged legal exposure.
- **Fines are substantial, and they can stack.** The AI Act establishes [maximum fines](https://artificialintelligenceact.eu/article/99/) of €35 million or 7% of global annual turnover, whichever is higher, exceeding even the GDPR's maximum fine of €20 million or 4% of turnover. For organizations subject to multiple frameworks, the cumulative regulatory risk is significant. A large financial institution could face AI Act fines, GDPR fines, DORA penalties, and NIS2 sanctions related to cybersecurity simultaneously for overlapping failures. 

## What good AI Act preparation looks like

The organizations best positioned for August 2026 aren't necessarily those with the largest compliance teams or even the most agile start-ups. They're the ones that have already done three things:

- **They've built an inventory of every AI system in use**, including those procured from third parties, and mapped each one against the Act's risk classification framework. This needs to be a living process, because purpose drift and model updates can change a system's risk classification.
- **They've assessed their infrastructure for auditability.** Can you produce logs of what data was used to train or inform a given AI decision? Can you demonstrate that your training datasets met the governance standards the Act requires? If the answer depends on a vendor's cooperation, that's a risk that needs to be addressed contractually and architecturally.
- **They've built a unified compliance framework** that addresses where their AI regulation intersects with their existing GDPR and DORA obligations (rather than running three parallel compliance workstreams). A single, well-documented framework that clearly sets out the risks arising from AI systems and the measures to address them can help ensure compliance with DORA and the AI Act, as well as GDPR.

## The bottom line

For financial institutions deploying AI in customer service, credit, or insurance workflows, the August 2026 deadline for the EU AI Act is nearly here, and the groundwork for compliance takes time to build.

The Act rewards organizations that have invested in [AI infrastructure they actually control](https://rasa.com/blog/conversational-ai-on-premise-vs-cloud-deployment): systems where data governance is documented, model behavior is explainable, human oversight is built-in, and audit logs are accessible on demand. That's the architecture that makes AI trustworthy at scale.

For institutions still evaluating their AI stack against these requirements, the time to start that conversation is now.

_For a deeper dive into the regulatory text, the_ [_EU AI Act website_](https://artificialintelligenceact.eu/) _provides the full regulation details along with helpful compliance tools and implementation guidance._

‍

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a33f3223b6709217e852f37_Rasa-Blog-What-the-EU-AI-Update-Means-For-European-Data-Sovereign-Organizations.png)](https://rasa.com/blog/what-the-eu-ai-act-update-means-for-european-data-sovereign-organizations) [June 18, 2026\\ \\ /\\ \\ Industry Solutions\\ \\ **What the EU AI Act Update Means for European Data Sovereign Organizations**](https://rasa.com/blog/what-the-eu-ai-act-update-means-for-european-data-sovereign-organizations)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a33f503d58e68a0261e6044_lindsay.jpeg)

Lindsay MacDonald

[read article](https://rasa.com/blog/what-the-eu-ai-act-update-means-for-european-data-sovereign-organizations)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a0d160a4638057153a17ba5_Rasa-ConversationalAI-POC-to-Production.png)](https://rasa.com/blog/conversational-ai-poc-to-production-financial-services) [May 19, 2026\\ \\ /\\ \\ Industry Solutions\\ \\ **Conversational AI: From POC to Production in Financial Services**](https://rasa.com/blog/conversational-ai-poc-to-production-financial-services)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/conversational-ai-poc-to-production-financial-services)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69b84158c9395cc2cf442a5a_Rasa_Blog_How_to_Map_Customer_Intents_for_Voice_Automation.avif)](https://rasa.com/blog/how-to-map-customer-intents-for-voice-automation) [March 16, 2026\\ \\ /\\ \\ Industry Solutions\\ \\ **How To Map Customer Intents for Voice Automation**](https://rasa.com/blog/how-to-map-customer-intents-for-voice-automation)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/how-to-map-customer-intents-for-voice-automation)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)