# Matrix<->Meta (Facebook chat and Instaram chat) bridge

This instance uses Mautrix-Meta software

Up to date info about bridge itself: <https://docs.mau.fi/bridges/go/meta/index.html>

## What?

An Matrix<->Facebook+Instagram chat bridge for receiving and sending Facebook and Instagram chat messages with Matrix-client.

## Set up

- Start a chat with `@meta:hacklab.fi`.
- Send `login`
- Follow any instructions bot gives.
- Recent chats should now get portals automatically. Other chats will get portals as you receive messages.

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

For users from other homeservers who has access to use the bot can use 'login-matrix'-command to manually enable double-puppeting.