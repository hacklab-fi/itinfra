# Matrix<->Facebook bridge

This instance uses Mautrix-Meta software

Up to date info about bridge itself: <https://docs.mau.fi/bridges/go/meta/index.html>

## What?

An Matrix<->Facebook chat bridge for receiving and sending Facebook chat messages with Matrix-client.

## Set up

There are two flavours of this bridge, here are their main differences:

#### @facebookbot

Uses facebook.com, requires user to have activated Facebook account, but works without any additional software needed at setup time.

#### @messengerbot

Uses messenger.com, allows user to have deactivated Facebook account and still use Facebook Messenger, but needs Messenger phone application at least once to succeed.

### Logging in

- Open chat with either `@messengerbot:hacklab.fi` or `@facebookbot:hacklab.fi` based on your flavour of bot
- Send `login`
- Follow any instructions bot gives.
- Recent chats should now get portals automatically. Other chats will get portals as you receive messages.

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

## Note

Info taken and adapted to our use from [Mautrix-meta wiki](https://docs.mau.fi/bridges/go/meta/index.html), so in case of info gets outdated, try refer there.
