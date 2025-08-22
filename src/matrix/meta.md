# Matrix<->Meta (Facebook chat and Instaram chat) bridge

This instance uses Mautrix-Meta software

Up to date info about bridge itself: <https://docs.mau.fi/bridges/go/meta/index.html>

## What?

An Matrix<->Facebook+Instagram chat bridge for receiving and sending Facebook and Instagram chat messages with Matrix-client.

## Set up

There are two flavours of this bridge, here are their main differences:

### Logging in

- Open chat with either `@meta:hacklab.fu`.
- Send `login`
- Follow any instructions bot gives.
- Recent chats should now get portals automatically. Other chats will get portals as you receive messages.

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

## Note

Info taken and adapted to our use from [Mautrix-meta wiki](https://docs.mau.fi/bridges/go/meta/index.html), so in case of info gets outdated, try refer there.
