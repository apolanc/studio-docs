# Source: https://rasa.com/blog/reliable-agentic-bots-with-llama-8b

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6903b8d763ac21c4ca0cd378_1727797312-copy-of-recipe-for-comparing-chatbot-implementations-a-guide-to-objective-and-ecologically-valid-evaluation.avif)

# Reliable Agentic Bots with Llama 8B

Posted Oct 01, 2024

Updated

![Alan Nichol](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebc1e0dfc08aad156f45_alan.avif)

Alan Nichol

Building AI assistants that handle complex interactions at scale while maintaining low latency, high performance, and cost efficiency is a significant challenge. While models like GPT-4 deliver strong performance, they come with trade-offs: high costs, rate limitations, and latency issues. These challenges are problematic in real-time scenarios, such as voice-based assistants, where every millisecond counts. _But what if you could fine-tune smaller models that balance speed, performance, and cost?_

**Did you know**: [Amazon found that every 100ms of latency cost them 1% in sales](https://www.gigaspaces.com/blog/amazon-found-every-100ms-of-latency-cost-them-1-in-sales)? Response time directly impacts user experience quality in real-time interactions, especially in voice-based systems.

## Cut Latency and Costs by Scaling with Smaller Models

Our previous work demonstrated how CALM's structured approach to building conversational AI excels in latency, scalability, and cost-efficiency (compared to more unstructured, ReAct-style agentic systems). However, scaling assistants for real-time use cases-such as voice interactions-introduces new challenges, especially when near-instantaneous responses are required.

For these real-time use cases, maintaining performance without relying on large, expensive LLMs like GPT-4 is essential. That’s why we’ve introduced a new feature that enables users to fine-tune smaller language models (~8B parameters, such as Llama 3.1 8B!). This shift offers substantial benefits in terms of latency, cost, and control.

### Why Smaller Models?

Our customers consistently find that smaller models allow for faster response times and reduced reliance on external APIs, giving them more control over their conversational AI systems. By deploying these models through platforms like Hugging Face or within their own infrastructure, they’ve been able to mitigate rate limitations, reduce API costs, and take charge of their models’ deployment and performance. This enables them to streamline operations, improve latency, and ensure their assistants perform efficiently, even at scale.

## The Business Case for Fine-Tuning

### Faster Models with No Loss in Accuracy

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ff83be3aafa2a889d657c5_1727788638-screenshot-2024-10-01-at-9-16-32-am.avif)

**Caption**: The figure shows a trade-off between model accuracy and cost efficiency. The Y-axis represents accuracy, with higher values indicating better performance, while the X-axis shows throughput and cost efficiency. GPT-4 is highly accurate but less efficient for high-demand applications. In contrast, the fine-tuned Llama-3-8B strikes a balance, offering strong accuracy with better cost efficiency. The figure highlights that smaller models like Llama-3-8B can provide sufficient accuracy while being more economical.

Fine-tuning smaller models makes them respond faster, which is exactly what you need for voice assistants and busy environments where every second counts. To test this, we compared the following systems' latency performance.

The table below shows the mean and median latencies for various models, listed in ascending order for easier comparison (see the calculations in [this notebook](https://github.com/RasaHQ/calm-langgraph-customer-service-comparison/blob/main/metrics.ipynb)):

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ff83be3aafa2a889d657be_1727789284-screenshot-2024-10-01-at-9-27-24-am.avif)

While powerful, models like GPT-4 often struggle to meet the low-latency demands of real-time applications, such as phone-based voice assistants. Even when integrated with CALM, these larger models can be too slow to provide a seamless user experience. In contrast, CALM’s self-hosted models consistently outperform larger counterparts, especially when integrated with fine-tuned NLU components, making them the ideal choice for fast, reliable, and scalable solutions.

Also, there is no known way to make the Langchain/LangGraph approach work with an 8B model.

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ff83be3aafa2a889d657bb_1727788705-screenshot-2024-10-01-at-9-17-57-am.avif)

**Caption:** Box plots comparing CALM’s performance across four configurations: CALM LLM, CALM NLU, CALM NLU self-hosted, and CALM self-hosted. The plots illustrate key metrics such as the number of output tokens, number of input tokens, and latencies (seconds). The boxes display the median, interquartile ranges, and whiskers showing variability, while individual data points are plotted to show the distribution. Shorter latencies and optimized token usage highlight the superior performance of CALM’s self-hosted models. For a deeper dive into these metrics and comparisons, check out the methodology in the rest of the post.

### Cost Efficiency

Using off the shelf smaller models reduces per token cost. Also, deploying them yourself (for example on [Hugging Face inference endpoints](https://huggingface.co/inference-endpoints/dedicated) or your own infrastructure) allows you to shift from a token based pricing to a per hour pricing for hosting. We have found the latter to be much cheaper when processing conversations at scale. Here’s a quick back-of-the-envelope calculation to illustrate this:

- Assuming your conversational assistant processes 40,000 conversations monthly with 10 concurrent sessions at peak and 3 user turns per conversation on average.
- Running a CALM assistant with GPT-4 as the LLM can result in a total cost of $7,700 for the LLM usage alone in that month.
- Whereas running the same assistant with a self-hosted fine-tuned Llama 3.1 8b model on an A100 GPU can cost somewhere between 2400 - 4800 USD for that month.

The gap widens further as your assistant processes more conversations monthly. Hence, fine-tuning and self-hosting your own model can reduce operational expenses and have more predictable costs compared to per-API call fees.

While there are no per-API call fees for self-hosted models, you do need to factor in the cost of overhead for the infrastructure to maintain your models.

### Security, Privacy, and Reliability

Enterprises with strict privacy requirements can deploy these models on their infrastructure-whether on a private cloud or an on-premise setup. This ensures sensitive data stays within the organization's control, a critical concern for industries like healthcare and finance. Self-hosting offers full control over the model’s environment and security protocols, but the models can also be run via **Hugging Face** or other cloud services for more flexible deployment.

You also need your production models to be reliable and consistently available. Unfortunately, vendor APIs often deprecate models, leading to unexpected downtime and costly migrations. See these pages from [Azure](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/model-retirements) and [OpenAI](https://platform.openai.com/docs/deprecations) for examples of their deprecated models. By opting for self-hosted models, you gain full control over versioning and updates, ensuring your models remain stable and available on your terms.

## Unlocking Performance: Fine-Tuning and Command Generation

What fine-tuning offers:

- **Custom Performance**: Fine-tuning allows smaller models to perform similarly to larger LLMs for specific tasks, making them both cost-effective and high-performing.
- **Scalability**: The need to efficiently scale increases as your assistant grows. Fine-tuned smaller models are easier to scale and manage, especially in complex environments with multiple flows.

### The Command Generator: A Key Component for Efficiency

CALM’s success with smaller models comes from the Command Generator. Rather than relying on the LLM for every conversational task, the Command Generator translates what users are saying into instructions to progress the conversation.

Without this, fine-tuning an LLM would require retraining the model on every piece of business logic, making it operationally prohibitive. CALM’s architecture, combined with the Command Generator, solves this problem by allowing businesses to fine-tune smaller models for specific tasks without overburdening them.

## Practical Steps: Fine-Tuning and Deployment Options

Fine-tuning doesn’t have to be complicated. Here’s an outline of the process:

1. **Prepare Your Dataset**: Start by writing sample conversations that can be augmented by synthetic data using the features available.
2. **Fine-Tuning**: With our fine-tuning recipe, the process is semi-automated. After preparing your data, you can fine-tune a smaller LLM on your chosen platform (e.g., AWS, GCP, Hugging Face, or locally).
3. **Deploy the Model**: Once fine-tuned, you can choose how to deploy the model-whether through Hugging Face endpoints, self-hosting on a private cloud, or using on-prem infrastructure. Each option offers different advantages in terms of control, cost, and security.

## Open-Source Resources: Instruction Tuning Dataset and Baseline Models

To support the community, we’ve open-sourced our [instruction tuning dataset](https://huggingface.co/datasets/rasa/command-generation-calm-demo-v1) on Hugging Face. There are two baseline models: fine-tuned [**CodeLlama 13B**](https://huggingface.co/rasa/cmd_gen_codellama_13b_calm_demo) and fine-tuned [**Llama 3.1 8B**](https://huggingface.co/rasa/cmd_gen_llama_3.1_8b_calm_demo). These resources provide a great starting point for developers interested in instruction tuning and building robust, efficient models.

### Why These Models?

- **CodeLlama 13B**: Known for its superior generalization, making it ideal for a range of tasks and fine-tuning applications.
- **Llama 3.1 8B**: A lighter, faster option that still delivers strong performance, particularly in real-time use cases.

Both these fine-tuned models can be deployed on HuggingFace Inference Endpoints with a single click:

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/690922824a3f7e30845fd022_68ff83be3aafa2a889d657c2_1727788784-screenshot-2024-10-01-at-9-18-56-am.avif)

## Ready to Fine-Tune Your Own Assistant?

To get started, dive into our [open-source instruction tuning dataset](https://huggingface.co/datasets/rasa/command-generation-calm-demo-v1) our [baseline](https://huggingface.co/rasa/cmd_gen_llama_3.1_8b_calm_demo) [models](https://huggingface.co/rasa/cmd_gen_codellama_13b_calm_demo) on Hugging Face and fine-tuning recipe’s documentation.

## Read more

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a0f51c7f5a8d81f6ca5ebd2_scaling-without-confidence-blog-img%402x%20(1).png)](https://rasa.com/blog/most-enterprises-arent-yet-confident-in-conversational-ai-but-theyre-scaling-anyway) [May 21, 2026\\ \\ /\\ \\ AI Concepts & Technology\\ \\ **Most Enterprises Aren’t Yet Confident in Conversational AI, But They’re Scaling Anyway**](https://rasa.com/blog/most-enterprises-arent-yet-confident-in-conversational-ai-but-theyre-scaling-anyway)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/most-enterprises-arent-yet-confident-in-conversational-ai-but-theyre-scaling-anyway)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/6a06052ac25e71b8b42ca157_Rasa_Blog_Enterprises_Want_Control_Over_Their_Conversational_AI.png)](https://rasa.com/blog/enterprises-want-control-over-their-conversational-ai-this-is-how-to-build-it) [May 14, 2026\\ \\ /\\ \\ AI Concepts & Technology\\ \\ **Enterprises Want Control Over Their Conversational AI. This Is How to Build It.**](https://rasa.com/blog/enterprises-want-control-over-their-conversational-ai-this-is-how-to-build-it)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/enterprises-want-control-over-their-conversational-ai-this-is-how-to-build-it)

[![](https://cdn.prod.website-files.com/68e92f16754061804418f615/69e108c87a63286b72cc4cdc_Botpress%20alternatives.png)](https://rasa.com/blog/botpress-alternatives) [May 5, 2026\\ \\ /\\ \\ AI Concepts & Technology\\ \\ **10 Best Botpress Alternatives for Enterprise AI Agents (2026)**](https://rasa.com/blog/botpress-alternatives)

![](https://cdn.prod.website-files.com/68e92f16754061804418f615/68ffebccbd4c5d970e09392e_maria.avif)

Maria Ortiz

[read article](https://rasa.com/blog/botpress-alternatives)

## AI that adapts to your business, not the other way around

## Build your next AI

## agent with Rasa

Power every conversation with enterprise-grade tools that keep your teams in control.

[get a demo](https://rasa.com/connect-with-rasa)

![](https://cdn.prod.website-files.com/68e69c204ba0666edacc94b1/68ee4d8c393fe398b80e895c_cta%20card.webp)