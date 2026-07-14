# Source: https://rasa.com/docs/pro/testing/trying-assistant

On this page

Once you're ready to talk to your newly built flow, train your assistant by running:

```jsx
rasa train
```

After you have trained your assistant successfully, start talking to it in your browser by running:

```jsx
rasa inspect
```

This command opens **Inspector**, a browser-based tool that launches a local version of your assistant, allowing you to chat with it and watch what happens under the hood in real time. By default, Inspector opens in chat-only mode. Click the **Inspect** button in the header to reveal the Flow, History, and Memory panels alongside the conversation.

As of Rasa Pro 3.17, `rasa inspect` opens the new Inspector by default — a unified inspection experience for both chat and voice that gives you a single, consistent interface for understanding _what happened_ and _why it happened_. It brings clearer execution traces, better failure visibility, and flow history into the same view.

The previous Inspector remains available as a temporary fallback by adding the `--legacy` flag:

```text
rasa inspect --legacy
```

## Interface Description[​](https://rasa.com/docs/pro/testing/trying-assistant/#interface-description 'Direct link to Interface Description')

The `rasa inspect` command starts an assistant based on the last trained model and opens a new tab in the browser. On large screens with inspect mode active, the interface shows three panels side by side:

- **Preview** (left) — chat with your assistant and see inline conversation events,
- **Flow** (center) — a live flowchart of the currently active flow, and
- **History and Memory** (right) — a chronological record of flow invocations and the slots collected so far.

### Preview[​](https://rasa.com/docs/pro/testing/trying-assistant/#preview 'Direct link to Preview')

The Preview panel is where you chat with your assistant. Each message exchange is shown in the conversation log along with inline events (slot sets, action executions, and similar). The header provides quick actions:

- **Copy** — copies the conversation to the clipboard.
- **Download** — exports the conversation as E2E test cases or raw tracker logs.
- **Langfuse** _(visible when configured)_ — opens the Langfuse trace for the current session. Enable it by adding a Langfuse tracer to `endpoints.yml`:

    ```yaml
    tracers:
      - type: langfuse
        host: https://cloud.langfuse.com
        public_key: ${LANGFUSE_PUBLIC_KEY}
        private_key: ${LANGFUSE_PRIVATE_KEY}
    ```

- **Restart** — discards the current session and starts a new conversation.

Clicking any conversation event in the log — a slot set, an action, a sub-agent call — opens the **Event Details** panel for that event.

The conversation log also surfaces the assistant's execution trace, making autonomous behavior legible rather than a black box:

- **Sub-agent iterations, tool calls, and MCP tool activity** are shown inline, so you can see exactly what the agent did and in what order.
- **Failures and ambiguous turns** are surfaced clearly — what the agent attempted, where it broke, and why — so root-cause discovery is faster and doesn't rely on manual guesswork.

### Flow[​](https://rasa.com/docs/pro/testing/trying-assistant/#flow 'Direct link to Flow')

The Flow panel visualizes the currently active flow as a flowchart. As the conversation progresses, the active node is highlighted and the view scrolls to follow it. Clicking any node opens the **Event Details** panel, where you can inspect the specific event associated with that step.

### History[​](https://rasa.com/docs/pro/testing/trying-assistant/#history 'Direct link to History')

The History panel shows a chronological timeline of every flow invocation in the current session. Each entry displays:

- **Flow name** — the human-readable name of the invoked flow, or `Sub-agent: <id>` for autonomous sub-agent calls.
- **Status badge** — the current state of the invocation: `Active`, `Interrupted`, `Completed`, or `Cancelled`.
- **Start time and duration** — when the invocation began and how long it ran.

Clicking an entry opens the Event Details panel for that invocation, showing exactly what happened at that point in the conversation.

The test conversation carried out in the chat widget is represented here in the [end-to-end test format](https://rasa.com/docs/reference/testing/e2e/test-cases/). This helps to quickly transform the conversation into a test case which when added to your end-to-end test set can enhance the robustness of the assistant.

### Memory[​](https://rasa.com/docs/pro/testing/trying-assistant/#memory 'Direct link to Memory')

The Memory panel shows the slots collected during the conversation, organized by scope:

- **Current flow** — slots set within the flow that is currently active.
- **Session** — slots set at session level, outside of any single flow.
- **System** — internal system slots (locale, session metadata, and similar).

Clicking a slot value opens the event that set it, so you can trace exactly where a value came from.

## Inspecting Voice Assistants[​](https://rasa.com/docs/pro/testing/trying-assistant/#inspecting-voice-assistants 'Direct link to Inspecting Voice Assistants')

Rasa Inspector can also be used for testing voice conversations. The local Inspector runs with voice enabled automatically — no extra flag is required. It uses Deepgram for speech recognition, so the only thing you need to set is the `DEEPGRAM_API_KEY` environment variable. Then launch the Inspector as usual:

```text
rasa inspect
```

Checkout the [speech integrations](https://rasa.com/docs/reference/integrations/speech-integrations/) page for the full list of supported ASR and TTS providers and their environment variables.

## Inspecting Conversations over External Channels[​](https://rasa.com/docs/pro/testing/trying-assistant/#inspecting-conversations-over-external-channels 'Direct link to Inspecting Conversations over External Channels')

Rasa Inspector can also be used to debug conversations happening on external channels. When you have certain channels defined in `credentials.yml`, you can run Rasa with Inspector using the command `rasa run --inspect`. To use the legacy Inspector for external channel debugging, add the `--legacy` flag: `rasa run --inspect --legacy`.

Rasa will create Inspector URLs for each channel. You can start a conversation over the external channel and view the conversation on Rasa Inspector along with all the relevant information about the conversation. It can be used to inspect conversations over any external channel including voice channels (like Twilio Media Streams).

For example, to inspect conversations over Rest channel. Ensure that `credentials.yml` contains the channel you would like to inspect:

credentials.yml

```yaml
rest:
```

Launch Rasa Server with Inspector with the command `rasa run --inspect`. Open the inspector URL mentioned in the logs:

```text
Development inspector for channel rest is running.
To inspect conversations, visit http://localhost:5005/webhooks/rest/inspect.html?projectUrl=http%3A%2F%2Flocalhost%3A5005&channel=rest
```

With the legacy Inspector (`rasa run --inspect --legacy`), the URL is the plain form:

```text
Development inspector for channel rest is running.
To inspect conversations, visit http://localhost:5005/webhooks/rest/inspect.html
```

Now, the first conversation started over the REST channel will be visible on the Inspector. You can try it with the following cURL request:

```bash
curl  -X POST \
  'http://localhost:5005/webhooks/rest/webhook' \
  --header 'Content-Type: application/json' \
  --data-raw '{
  "sender": "test_user",
  "message": "I would like to transfer money"
}'
```