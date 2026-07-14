# Source: https://www.rasa.com/docs/reference/primitives/custom-actions

On this page

info

In many cases, you can call tools of an MCP (Model Context Protocol) server directly from your flow steps as an alternative to writing custom actions. Directly invoking MCP tools is often a simpler and more maintainable way to integrate with external APIs, databases, or services. Consider this approach before implementing a custom action. See [Calling an MCP Tool](https://www.rasa.com/docs/reference/primitives/flow-steps/#calling-an-mcp-tool) for more details.

For details on how to implement a custom action, see the [SDK documentation](https://www.rasa.com/docs/reference/integrations/action-server/running-action-server/). Any custom action that you want to use in your stories should be added into the actions section of your [domain](https://www.rasa.com/docs/reference/config/domain/).

When the dialogue engine predicts a custom action to be executed, it will call the action server, with the following information:

```json
{
  "next_action": "string",
  "tracker": {
    "conversation_id": "default",
    "sender_id": "string",
    "slots": {},
    "latest_message": {},
    "latest_event_time": 1537645578.314389,
    "followup_action": "string",
    "paused": false,
    "events": [],
    "latest_input_channel": "rest",
    "active_loop": {},
    "latest_action": {}
  },
  "domain": {
    "config": {},
    "session_config": {},
    "intents": [],
    "entities": [],
    "slots": {},
    "responses": {},
    "actions": [],
    "forms": {},
    "e2e_actions": []
  },
  "version": "version"
}
```

Your action server should respond with a list of events and responses:

```json
{
  "events": [{}],
  "responses": [{}]
}
```

## Running Custom Actions Directly by the Assistant[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#running-custom-actions-directly-by-the-assistant 'Direct link to Running Custom Actions Directly by the Assistant')

New in 3.10

You can now run Python custom actions directly on the Rasa Assistant without the need for a separate Action Server.

Building an assistant often involves executing custom logic like API calls or database queries. Traditionally, this requires an Action Server. However, for a more integrated and efficient approach, you can run custom actions written in Python directly on the Rasa Assistant. This simplifies deployment and enhances the overall efficiency of your assistant.

### Benefits of Direct Custom Action Execution[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#benefits-of-direct-custom-action-execution 'Direct link to Benefits of Direct Custom Action Execution')

- **Simplified Architecture**: Removes the need for a separate Action Server, reducing the complexity of your architecture and deployment process.
- **Lower Latency**: Improves response times by eliminating the network roundtrips required to communicate with an external Action Server.
- **Unified Environment**: Executes all components of your assistant within the same environment, making debugging and local development smoother.
- **Cost Efficiency**: Reduces infrastructure costs as there is no need to maintain an additional server for handling custom actions.

### Disadvantages of Direct Custom Action Execution[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#disadvantages-of-direct-custom-action-execution 'Direct link to Disadvantages of Direct Custom Action Execution')

- **Higher Effort To Secure Rasa Environment**: The Rasa assistant will need access to the same sensitive resources required by the custom actions to access remote services (i.e. tokens, credentials), which may introduce security risks. Therefore, the Rasa instance should be secured properly by running in a more protected environment.

### How to Configure the Feature[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#how-to-configure-the-feature 'Direct link to How to Configure the Feature')

To use this feature, you need to update the `action_endpoint` section of the `endpoints.yml` file. Add the `actions_module` field and specify the path to your custom actions Python package. This package will be imported and used directly by the Rasa Assistant to run the actions.

For example, consider this is your project structure:

```plaintext
my_project/
├── actions/
│   ├── __init__.py
│   ├── actions.py
├── data/
├── models/
├── tests/
├── domain.yml
├── config.yml
├── credentials.yml
├── endpoints.yml
```

You can configure the `actions_module` field in the `endpoints.yml` file as follows:

endpoints.yml

```yaml
action_endpoint:
    actions_module: "actions"
```

This configuration is mutually exclusive with the `url` field, which you would typically use for pointing to an external Action Server. If both `url` and `actions_module` are specified, `actions_module` will be prioritized.

info

Every time you update the custom actions code, you must restart the Rasa Assistant to reflect the changes via the `rasa run` or `rasa inspect` commands.

## Streaming custom actions[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#streaming-custom-actions 'Direct link to Streaming custom actions')

New in Rasa Pro 3.17 / Rasa SDK 3.17

Custom actions can stream text and rich responses incrementally instead of waiting until the action completes. This reduces perceived latency on channels that consume partial output — especially voice assistants that synthesize TTS from streaming text tokens.

### How to write a streaming action[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#how-to-write-a-streaming-action 'Direct link to How to write a streaming action')

Use the `CollectingDispatcher` streaming API in your action's `run` method:

```python
await dispatcher.stream_start()
async for token in my_token_generator():
    await dispatcher.stream_chunk(text=token)
await dispatcher.stream_end()
```

See the [SDK dispatcher reference](https://www.rasa.com/docs/reference/integrations/action-server/sdk-dispatcher/#streaming-responses) for the full API, including rich-content chunks, barge-in handling, and transport behaviour.

### Where streaming is supported[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#where-streaming-is-supported 'Direct link to Where streaming is supported')

Real-time streaming requires a streaming-capable action executor **and** a streaming output channel. See [Built-in output channels with streaming support](https://www.rasa.com/docs/reference/channels/custom-connectors/#built-in-output-channels-with-streaming-support). Rasa Pro supports streaming custom actions on:

| Transport | Real-time streaming | Notes |
| --- | --- | --- |
| **Direct custom action executor** (`actions_module`) | Yes | Actions run in-process; chunks are forwarded immediately to the output channel. |
| **gRPC action server** | Yes | Rasa opens the `WebhookStream` server-streaming RPC; chunks are forwarded as they are produced. |
| **HTTP(S) action server** | No (graceful fallback) | Rasa sends a single HTTP POST to the `/webhook` endpoint and waits for one JSON response — not the gRPC `WebhookStream` RPC. The SDK still accepts streaming calls from your action code, accumulates chunks, and replays them as individual `utter_message` responses when `stream_end()` runs. The user receives the complete response once — not token-by-token. No changes are needed in action code. |

Configure gRPC in `endpoints.yml`:

endpoints.yml

```yaml
action_endpoint:
  url: "grpc://localhost:5055"
```

Or use direct execution:

endpoints.yml

```yaml
action_endpoint:
  actions_module: "actions"
```

### HTTP action server fallback[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#http-action-server-fallback 'Direct link to HTTP action server fallback')

If your action server is reached over HTTP or HTTPS, streaming degrades automatically:

1. Rasa calls the action via a single HTTP POST to the `/webhook` endpoint — there is no streaming HTTP API equivalent to gRPC's `WebhookStream`.
2. Inside the SDK, `stream_chunk()` calls accumulate internally because no streaming sink is attached.
3. When `stream_end()` runs, each accumulated chunk is replayed as an `utter_message()` in the HTTP response payload.
4. Rasa delivers the full set of responses to the user after the action finishes.

Your action code does not need branches for HTTP vs gRPC. The same `stream_start` / `stream_chunk` / `stream_end` sequence works on every transport; only the delivery timing changes.

### Voice barge-in during streaming[​](https://www.rasa.com/docs/reference/primitives/custom-actions/#voice-barge-in-during-streaming 'Direct link to Voice barge-in during streaming')

When interruption handling is enabled on a voice stream channel and the user speaks over a streaming custom action, Rasa Pro cancels the in-flight stream instead of continuing to deliver audio. Chunks already sent are recorded in the tracker (tagged so they are not spoken again), TTS streaming is stopped cleanly, and events returned by the action (such as slot updates) are still applied.

👉 [Interruptions during streaming custom actions](https://www.rasa.com/docs/reference/primitives/patterns/#interruptions-during-streaming-custom-actions)

- [Running Custom Actions Directly by the Assistant](https://www.rasa.com/docs/reference/primitives/custom-actions/#running-custom-actions-directly-by-the-assistant)
 - [Benefits of Direct Custom Action Execution](https://www.rasa.com/docs/reference/primitives/custom-actions/#benefits-of-direct-custom-action-execution)
 - [Disadvantages of Direct Custom Action Execution](https://www.rasa.com/docs/reference/primitives/custom-actions/#disadvantages-of-direct-custom-action-execution)
 - [How to Configure the Feature](https://www.rasa.com/docs/reference/primitives/custom-actions/#how-to-configure-the-feature)
- [Streaming custom actions](https://www.rasa.com/docs/reference/primitives/custom-actions/#streaming-custom-actions)
 - [How to write a streaming action](https://www.rasa.com/docs/reference/primitives/custom-actions/#how-to-write-a-streaming-action)
 - [Where streaming is supported](https://www.rasa.com/docs/reference/primitives/custom-actions/#where-streaming-is-supported)
 - [HTTP action server fallback](https://www.rasa.com/docs/reference/primitives/custom-actions/#http-action-server-fallback)
 - [Voice barge-in during streaming](https://www.rasa.com/docs/reference/primitives/custom-actions/#voice-barge-in-during-streaming)