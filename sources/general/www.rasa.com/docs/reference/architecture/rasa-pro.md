# Source: https://www.rasa.com/docs/reference/architecture/rasa-pro

On this page

The diagram below provides an overview of the Rasa Architecture.

![image](https://www.rasa.com/docs/assets/images/rasa-pro-deployment-architecture-d889579fe4aa09a66b23f85738531038.png)

## Action Server (custom actions)[​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#action-server-custom-actions 'Direct link to Action Server (custom actions)')

Custom actions are used to implement business logic that cannot be handled by the Rasa bot. They include things like fetching customer information from a database, querying an API, or calling an external service.

Custom actions can be invoked via HTTP or gRPC. Rasa provides the Rasa SDK - a Python SDK to build custom actions. More details can be found at the [rasa action server documentation](https://www.rasa.com/docs/action-server/).

## Cloud Services[​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#cloud-services 'Direct link to Cloud Services')

Your deployed assistant depends on a number of prerequisite cloud services that you need to provision.

Some of these prerequisite cloud services are required (green color), while others are optional (yellow color).

You are highly advised to use **managed cloud services** for their stability, performance and backup. There are many options available at each cloud provider, and the table below lists just a few of the available choices.

| What | AWS | Azure | Google |
| --- | --- | --- | --- |
| Model Storage | Amazon S3 | Azure Blob Storage | Google Cloud Storage |
| Lock Store | Amazon ElastiCache for Redis | Azure Cache for Redis | Memorystore for Redis |
| Tracker Store | Amazon RDS for PostgreSQL | Azure Database for PostgreSQL | Google Cloud SQL for PostgreSQL |
| Event Queue (Kafka) | Amazon Managed Streaming for Apache Kafka (MSK) | Azure Kafka Service | Confluent Cloud on Google Cloud Platform |
| Secrets Manager | HashiCorp Vault on AWS | HashiCorp Vault on Azure | HashiCorp Vault with Google Cloud |

Note that the NLG Server is an optional cloud service that you have to create and deploy yourself.

Next you will find a short description of the function of each cloud service.

### [Model Storage](https://www.rasa.com/docs/reference/integrations/model-storage/) [​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#model-storage 'Direct link to model-storage')

The Model storage is a cloud service where the trained model is stored. Upon initialization or restart, Rasa will download that trained model and read it into memory.

### [Lock Store](https://www.rasa.com/docs/reference/integrations/lock-stores/) [​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#lock-store 'Direct link to lock-store')

The Lock Store is needed when you have a high-load scenario that requires the Rasa server to be replicated across multiple instances. It ensures that even with multiple servers, the messages for each conversation are handled in the correct sequence without any loss or overlap.

### [Tracker Store](https://www.rasa.com/docs/reference/integrations/tracker-stores/) [​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#tracker-store 'Direct link to tracker-store')

Your assistant's conversations are stored within a tracker store.

### [Secrets Manager](https://www.rasa.com/docs/reference/integrations/secrets-managers/) [​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#secrets-manager 'Direct link to secrets-manager')

The HashiCorp Vault Secrets Manager is integrated with Rasa to securely store and manage sensitive credentials.

### [NLG Server](https://www.rasa.com/docs/reference/integrations/nlg/) [​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#nlg-server 'Direct link to nlg-server')

The NLG Server in Rasa is used to outsource the response generation and separate it from the dialogue learning process. The benefit of using an NLG Server is that it allows for the dynamic generation of responses without the need to retrain the bot, optimizing workflows by decoupling response text from training data.

### [Event Queue (Kafka)](https://www.rasa.com/docs/reference/integrations/event-brokers/) [​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#event-queue-kafka 'Direct link to event-queue-kafka')

The Kafka Event Broker in Rasa is used to stream all events from the Rasa server to a Kafka topic for robust, scalable message handling and further processing.

## Rasa as A2A Agent Mode[​](https://www.rasa.com/docs/reference/architecture/rasa-pro/#rasa-as-a2a-agent-mode 'Direct link to Rasa as A2A Agent Mode')

When an external orchestrator invokes your Rasa assistant over the [Agent-to-Agent (A2A) protocol](https://a2a-protocol.org/latest/), Rasa acts as a governed sub-agent: it advertises flow skills via `AgentCard`, maps `contextId` to conversation state, and returns structured task lifecycle updates.

See [Rasa as A2A Agent Architecture](https://www.rasa.com/docs/reference/architecture/rasa-as-a2a-agent/) for the deployment topology, governed contract, context mapping, and task state lifecycle.

- [Action Server (custom actions)](https://www.rasa.com/docs/reference/architecture/rasa-pro/#action-server-custom-actions)
- [Cloud Services](https://www.rasa.com/docs/reference/architecture/rasa-pro/#cloud-services)
 - [Model Storage](https://www.rasa.com/docs/reference/architecture/rasa-pro/#model-storage)
 - [Lock Store](https://www.rasa.com/docs/reference/architecture/rasa-pro/#lock-store)
 - [Tracker Store](https://www.rasa.com/docs/reference/architecture/rasa-pro/#tracker-store)
 - [Secrets Manager](https://www.rasa.com/docs/reference/architecture/rasa-pro/#secrets-manager)
 - [NLG Server](https://www.rasa.com/docs/reference/architecture/rasa-pro/#nlg-server)
 - [Event Queue (Kafka)](https://www.rasa.com/docs/reference/architecture/rasa-pro/#event-queue-kafka)
- [Rasa as A2A Agent Mode](https://www.rasa.com/docs/reference/architecture/rasa-pro/#rasa-as-a2a-agent-mode)