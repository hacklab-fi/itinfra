# Matrix<->Telegram bridge

Up to date info about Mautrix-telegram itself: <https://docs.mau.fi/bridges/go/telegram/index.html>

## What?

An puppeting Matrix<->Telegram bridge for receiving and sending Telegram messages with Matrix-client, has relaybot possibility.

## Set up
- Start a chat with the bridge bot `@telegrambot:hacklab.fi`. The bot should say "This room has been registered as your bridge management/status room." if you started the chat correctly.
- Issue `login` to see login possibilities
- Follow instructions bot tells you

### Double puppeting (recommended)

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

For users from other homeservers who has access to use the bot can use 'login-matrix'-command to manually enable double-puppeting.