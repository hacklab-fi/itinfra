# Matrix<->Signal bridge

Up to date info about Mautrix-signal itself: https://docs.mau.fi/bridges/python/signal/index.html
## What?

An Matrix<->signal bridge for receiving and sending signal messages with Matrix-client, bridging groupchats, puppeting.. At the time of writing still pretty early version, but basic functionality exist and should work, like start chat from matrix, using as primary or linked device (signal stuff), direct messaging and group chats

## Set up
- On matrix: Open chat with `@signalbot:hacklab.fi`
- Issue _either_
  - `link [device name]` to link the bridge as a secondary device
  - `register <phone>`to sign into Signal as the primary device, international format.

### Double puppeting (recommended)

You can replace the Matrix puppet of your Signal account with your Matrix account. When you do so, messages that you send from other Signal clients will be sent from your Matrix account instead of the default puppet user.

How to get virgin Access-token: Use https://gitlab.com/vurpo/matrix-login/ for currently most effortless method.

As with the Signal account login, you must do this in a private chat with the bridge bot.

- Log in with `login-matrix <access token>`
- After logging in, the default Matrix puppet of your Signal account should leave rooms and your account should join all rooms the puppet was in automatically.

## Note

Info taken and adapted to our use from [Mautrix-signal wiki](https://docs.mau.fi/bridges/python/signal/authentication.html), so in case of info gets outdated, try refer there.