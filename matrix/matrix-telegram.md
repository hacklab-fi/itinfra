# Matrix<->Telegram bridge

Up to date info about Mautrix-telegram itself: https://docs.mau.fi/bridges/python/telegram/index.html

## What?

An Matrix<->Telegram bridge for receiving and sending Telegram messages with Matrix-client, bridging groupchats, puppeting, relaybot... Full integration.

## Set up

### For using own Telegram through Matrix:

- On Matrix: Open chat with `@telegrambot:hacklab.fi`
- `help` gives you available commands, usually start with `login`
- There is multiple ways of using and commanding the bot, so refer [Mautrix-telegram wiki](https://docs.mau.fi/bridges/python/telegram/authentication.html)

### Double puppeting (recommended)

You can replace the Matrix puppet of your Telegram account with your Matrix account. When you do so, messages that you send from other Telegram clients will be sent from your Matrix account instead of the default puppet user.

As with the Telegram account login, you must do this in a private chat with the bridge bot.

How to get virgin Access-token: Use https://gitlab.com/vurpo/matrix-login/ for currently most effortless method.

- Log in with `login-matrix <access token>`
- After logging in, the default Matrix puppet of your Telegram account should leave rooms and your account should join all rooms the puppet was in automatically.

### For bridging Matrix channel to Telegram group:

- On Matrix: Invite `@telegrambot:hacklab.fi` to Matrix-room to be bridged
- On Telegram: invite `@hacklabbridgebot` to channel
- On Matrix: Get the ID of the Telegram chat with the `!tg id` and the Telegram-bot should answer with group ID.
- On Matrix: Run `!tg bridge <chat ID>` in the room you want to bridge.
- Refer [Mautrix-telegram wiki](https://docs.mau.fi/bridges/python/telegram/creating-and-managing-chats.html) for detailed up to date instructions
