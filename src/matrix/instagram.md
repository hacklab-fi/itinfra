# Matrix<->Instagram bridge

This instance uses Mautrix-Meta software

Up to date info about bridge itself: <https://docs.mau.fi/bridges/go/meta/index.html>

## What?

An Matrix<->Instagram chat bridge for receiving and sending Instagram chat messages with Matrix-client.

## Set up

### Logging in

- Open chat with `@instagrambot:hacklab.fi`
- Send `login`
- Follow any instructions bot gives.
- Recent chats should now get portals automatically. Other chats will get portals as you receive messages.

### Double puppeting (recommended)

You can replace the Matrix puppet of your Instagram account with your Matrix account. When you do so, messages that you send from other Messenger clients will be sent from your Matrix account instead of the default puppet user.

How to get virgin Access-token: Use <https://gitlab.com/vurpo/matrix-login/> for currently most effortless method.

As with the Messenger account login, you must do this in a private chat with the bridge bot.

- Log in with `login-matrix <access token>`
- After logging in, the default Matrix puppet of your Messenger account should leave rooms and your account should join all rooms the puppet was in automatically.

## Note

Info taken and adapted to our use from [Mautrix-meta wiki](https://docs.mau.fi/bridges/go/meta/index.html), so in case of info gets outdated, try refer there.
