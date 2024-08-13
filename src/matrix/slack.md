# Matrix<->Slack bridge

Up to date info about Mautrix-slack itself: <https://docs.mau.fi/bridges/go/slack/index.html>

## What:
An puppeting Matrix<->Slack bridge for receiving and sending Slack messages with Matrix-client, has relaybot possibility.

## Set up
- Start a chat with the bridge bot `@slackbot:hacklab.fi`. The bot should say "This room has been registered as your bridge management/status room." if you started the chat correctly.
  - Write `help` to see all commands and options available to you.
- Write `login` to the room.
- Follow on-screen instuctions
- If something doesn't work, up to date details finds from: <https://docs.mau.fi/bridges/go/slack/authentication.html>

### Double puppeting (recommended)

For hacklab.fi homeserver users this bridge does double-puppeting automatically.
