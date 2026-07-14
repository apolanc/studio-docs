# Source: https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels

On this page

Installation Requirements

To use most channel connectors, you need to install the `channels` dependency group:

```bash
pip install 'rasa-pro[channels]'
```

For more information about dependency groups, see our [Python Versions and Dependencies](https://www.rasa.com/docs/reference/python-versions-and-dependencies/) reference page.

## Connecting to A Channel[​](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#connecting-to-a-channel 'Direct link to Connecting to A Channel')

### Text & Chat[​](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#text--chat 'Direct link to Text & Chat')

Learn how to make your assistant available on:

- [Your Own Website](https://www.rasa.com/docs/reference/channels/your-own-website/)
- [Facebook Messenger](https://www.rasa.com/docs/reference/channels/facebook-messenger/)
- [Slack](https://www.rasa.com/docs/reference/channels/slack/)
- [Telegram](https://www.rasa.com/docs/reference/channels/telegram/)
- [Twilio](https://www.rasa.com/docs/reference/channels/twilio/)
- [Microsoft Bot Framework](https://www.rasa.com/docs/reference/channels/microsoft-bot-framework/)
- [Cisco Webex Teams](https://www.rasa.com/docs/reference/channels/cisco-webex-teams/)
- [RocketChat](https://www.rasa.com/docs/reference/channels/rocketchat/)
- [Mattermost](https://www.rasa.com/docs/reference/channels/mattermost/)
- [Google Hangouts Chat](https://www.rasa.com/docs/reference/channels/hangouts/)
- [Custom Connectors](https://www.rasa.com/docs/reference/channels/custom-connectors/)

### Voice[​](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#voice 'Direct link to Voice')

Learn how to build voice assistants with:

- [Audiocodes VoiceAI Connect](https://www.rasa.com/docs/reference/channels/audiocodes-voiceai-connect/)
- [Jambonz](https://www.rasa.com/docs/reference/channels/jambonz/)
- [Twilio Voice](https://www.rasa.com/docs/reference/channels/twilio-voice/)
- [Twilio Media Streams](https://www.rasa.com/docs/reference/channels/twilio-media-streams/)
- [CHIRP](https://www.rasa.com/docs/reference/channels/chirp/)
- [Signalwire](https://www.rasa.com/docs/reference/channels/signalwire/)
- [Vonage](https://www.rasa.com/docs/reference/channels/vonage/)

To learn more about integration ASR and TTS engines, head over to [Speech Integrations](https://www.rasa.com/docs/reference/integrations/speech-integrations/).

For how Rasa spaces consecutive bot audio on voice stream channels (minimum gaps and silence between messages), see [Minimum pacing between bot messages (voice streams)](https://www.rasa.com/docs/reference/config/overview/#minimum-pacing-between-bot-messages-voice-streams).

Only some channels deliver assistant text incrementally. Voice stream connectors and the REST channel (with `?stream=true`) support real-time streaming when paired with a streaming-capable action executor; most messaging channels do not. See [Built-in output channels with streaming support](https://www.rasa.com/docs/reference/channels/custom-connectors/#built-in-output-channels-with-streaming-support).

## Testing Channels on Your Local Machine[​](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#testing-channels-on-your-local-machine 'Direct link to Testing Channels on Your Local Machine')

If you're running a Rasa server on `localhost`, most external channels won't be able to find your server URL, since `localhost` is not open to the internet.

To make a port on your local machine publicly available on the internet, you can use [ngrok](https://ngrok.com/). Alternatively, see this [list](https://github.com/anderspitman/awesome-tunneling) tracking and comparing other tunneling solutions.

After installing ngrok, run:

```bash
ngrok http 5005; rasa run
```

When you follow the instructions to make your assistant available on a channel, use the ngrok URL. Specifically, wherever the instructions say to use `https://<host>:<port>/webhooks/<CHANNEL>/webhook`, use `<ngrok_url>/webhooks/<CHANNEL>/webhook`, replacing `<ngrok_url>` with the randomly generated URL displayed in your ngrok terminal window. For example, if connecting your bot to Slack, your URL should resemble `https://26e7e7744191.ngrok.io/webhooks/slack/webhook`.

caution

With the free-tier of ngrok, you can run into limits on how many connections you can make per minute. As of writing this, it is set to 40 connections / minute.

Alternatively you can make your assistant listen on a specific address using the `-i` command line option:

```bash
rasa run -p 5005 -i 192.168.69.150
```

This is particularly useful when your internet facing machines connect to backend servers using a VPN interface.

- [Connecting to A Channel](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#connecting-to-a-channel)
 - [Text & Chat](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#text--chat)
 - [Voice](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#voice)
- [Testing Channels on Your Local Machine](https://www.rasa.com/docs/reference/channels/messaging-and-voice-channels/#testing-channels-on-your-local-machine)