# Source: https://www.rasa.com/docs/reference/config/studio-environment-variables

On this page

## Server[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#server 'Direct link to Server')

The Studio server handles the API, user authentication, assistant configuration, and conversation storage.

### Core[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#core 'Direct link to Core')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `RASA_PRO_LICENSE` | The Rasa Pro license key. | |
| `OPENAI_API_KEY` | The OpenAI API key for LLM-powered features. | |
| `HTTP_REQUEST_TIMEOUT` | The HTTP request timeout in milliseconds. Set this higher than your load balancer timeout to avoid premature connection drops. | `61000` |

### Database[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#database 'Direct link to Database')

The database stores conversations, assistant configurations, and analytics data. Both the Studio server and the event ingestion service use this same database connection.

| Environment Variable | Description | Default |
| --- | --- | --- |
| `DB_HOST` | The hostname of the PostgreSQL database. | |
| `DB_PORT` | The port of the PostgreSQL database. | `5432` |
| `DB_NAME` | The name of the PostgreSQL database. | `studio` |
| `DB_USER` | The username for the PostgreSQL database. | |
| `DB_PASS` | The password for the PostgreSQL database. | |
| `DB_QUERY` | Additional connection query parameters. | |
| `DB_TRANSACTION_TIMEOUT` | The database transaction timeout in milliseconds. | `10000` |
| `USE_AWS_IAM_AUTH` | Set to `true` to use AWS IAM authentication for the database instead of username/password. | `false` |
| `AWS_REGION` | The AWS region for IAM authentication. Required if `USE_AWS_IAM_AUTH` is `true`. | |
| `IAM_DB_USER` | The IAM database username. Required if `USE_AWS_IAM_AUTH` is `true`. | |

### Authentication[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#authentication 'Direct link to Authentication')

Studio uses [Keycloak](https://www.keycloak.org/) for identity and access management.

| Environment Variable | Description | Default |
| --- | --- | --- |
| `KEYCLOAK_REALM` | The Keycloak realm name. | `rasa-studio` |
| `KEYCLOAK_CLIENT_ID` | The Keycloak client ID for the Studio backend. | `rasa-studio-backend` |
| `KEYCLOAK_ADMIN_USERNAME` | The Keycloak admin username. | `kcadmin` |
| `KEYCLOAK_ADMIN_PASSWORD` | The Keycloak admin password. | |
| `KEYCLOAK_API_USERNAME` | The username for Keycloak realm management API calls. | `realmadmin` |
| `KEYCLOAK_API_PASSWORD` | The password for Keycloak realm management API calls. | |
| `KEYCLOAK_API_CLIENT_ID` | The client ID for Keycloak API authentication. | `admin-cli` |

### Model Server[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#model-server 'Direct link to Model Server')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `MS_API_URL` | The URL of the Rasa model server API. | `http://rasapro` |

### Conversation Management[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#conversation-management 'Direct link to Conversation Management')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `DELETE_CONVERSATIONS_OLDER_THAN_HOURS` | Delete conversations older than this many hours. When not set, conversations are retained indefinitely. | |
| `DELETE_CONVERSATIONS_CRON_EXPRESSION` | Cron expression controlling when the conversation deletion job runs. | `0 * * * *` |
| `VERSION_DAILY_STATISTICS_CRON_EXPRESSION` | Cron expression controlling when daily version statistics are computed. | `0 0 * * *` |

### Voice[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#voice 'Direct link to Voice')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `BROWSER_AUDIO_MONITOR_SILENCE` | Set to `false` to disable silence detection in audio sessions. | `true` |
| `BROWSER_AUDIO_ASR` | The speech-to-text (ASR) provider name. | `deepgram` |
| `BROWSER_AUDIO_TTS` | The text-to-speech (TTS) provider name. | `cartesia` |
| `DEEPGRAM_API_KEY` | The Deepgram API key for speech-to-text. | |
| `CARTESIA_API_KEY` | The Cartesia API key for text-to-speech. | |

**To enable voice features**, you must set both `DEEPGRAM_API_KEY` and `CARTESIA_API_KEY`, even if you are only using one of the providers for both speech-to-text and text-to-speech. In such a case, set the unused provider's environment variable to a placeholder value (e.g., `CARTESIA_API_KEY=unused`).

### Observability[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#observability 'Direct link to Observability')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `LOG_LEVEL_DEBUG` | Set to `true` to enable debug-level logging. | `false` |
| `LOG_FILE` | Path to a file where logs are written. When not set, logs go to stdout only. | |

### Advanced[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#advanced 'Direct link to Advanced')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `TRAINING_POLLING_INTERVAL_MS` | Interval in milliseconds at which Studio polls for model training status. Minimum value: `1000`. | `1000` |
| `MODEL_POLLING_INTERVAL_MS` | Interval in milliseconds at which Studio polls for model deployment status. Minimum value: `2000`. | `2000` |
| `MODEL_INACTIVE_AFTER_MS` | Time in milliseconds after which a running model version is marked as inactive. Minimum value: `60000`. | `3600000` |

## Event Ingestion[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#event-ingestion 'Direct link to Event Ingestion')

Studio consumes Rasa events from a Kafka topic to power analytics and conversation review. Ingested events are persisted to the same PostgreSQL database configured in the [Database](https://www.rasa.com/docs/reference/config/studio-environment-variables/#database) section above.

### Kafka[​](https://www.rasa.com/docs/reference/config/studio-environment-variables/#kafka 'Direct link to Kafka')

| Environment Variable | Description | Default |
| --- | --- | --- |
| `KAFKA_BROKER_ADDRESS` | The address of the Kafka broker. | |
| `KAFKA_TOPIC` | The Kafka topic that Rasa publishes events to. | `rasa-events` |
| `KAFKA_DLQ_TOPIC` | The Kafka dead letter queue topic for events that fail processing. | `rasa-events-dlq` |
| `KAFKA_CLIENT_ID` | The Kafka client identifier. | `kafka-python-rasa` |
| `KAFKA_GROUP_ID` | The Kafka consumer group ID. | `studio` |
| `KAFKA_SASL_MECHANISM` | The SASL mechanism for Kafka authentication (e.g. `PLAIN`, `SCRAM-SHA-256`). | |
| `KAFKA_SASL_USERNAME` | The username for Kafka SASL authentication. | |
| `KAFKA_SASL_PASSWORD` | The password for Kafka SASL authentication. | |
| `KAFKA_ENABLE_SSL` | Set to `true` to enable SSL/TLS for Kafka connections. | `false` |
| `KAFKA_REJECT_UNAUTHORIZED` | Set to `false` to allow untrusted SSL certificates. Not recommended for production. | `true` |
| `KAFKA_CUSTOM_SSL` | Set to `true` to supply custom SSL certificate files via the variables below. | `false` |
| `KAFKA_CA_FILE` | Path to the CA certificate file. Required when `KAFKA_CUSTOM_SSL` is `true`. | |
| `KAFKA_CERT_FILE` | Path to the client certificate file. | |
| `KAFKA_KEY_FILE` | Path to the client key file. | |
| `KAFKA_MAX_RETRIES` | The maximum number of reconnection attempts before giving up. | `3` |

- [Server](https://www.rasa.com/docs/reference/config/studio-environment-variables/#server)
 - [Core](https://www.rasa.com/docs/reference/config/studio-environment-variables/#core)
 - [Database](https://www.rasa.com/docs/reference/config/studio-environment-variables/#database)
 - [Authentication](https://www.rasa.com/docs/reference/config/studio-environment-variables/#authentication)
 - [Model Server](https://www.rasa.com/docs/reference/config/studio-environment-variables/#model-server)
 - [Conversation Management](https://www.rasa.com/docs/reference/config/studio-environment-variables/#conversation-management)
 - [Voice](https://www.rasa.com/docs/reference/config/studio-environment-variables/#voice)
 - [Observability](https://www.rasa.com/docs/reference/config/studio-environment-variables/#observability)
 - [Advanced](https://www.rasa.com/docs/reference/config/studio-environment-variables/#advanced)
- [Event Ingestion](https://www.rasa.com/docs/reference/config/studio-environment-variables/#event-ingestion)
 - [Kafka](https://www.rasa.com/docs/reference/config/studio-environment-variables/#kafka)