# Matrix<->Signal bridge

17.2.2024:
!!! THE OLD VERSION OF THIS BRIDGE IS REPLACED WITH BETTER/NEWER VERSION, USERS NEED TO LINK/LOGIN AGAIN !!!

Most notable change is that there is no primary device method available in the bridge.

Up to date info about Mautrix-signal itself: <https://docs.mau.fi/bridges/go/signal/index.html>

## What?

An Matrix<->Signal bridge for receiving and sending signal messages with Matrix-client, bridging groupchats, puppeting.. Using as linked device (signal stuff), direct messaging and group chats.

## Set up

- On matrix: Open chat with `@signalbot:hacklab.fi`
- Issue `login` to link the bridge as a secondary device
- Follow instructions bot tells you

You can use your Signal app on an phone as your primary device, or run Signal app in Virtual Android, or there is also 3rd alternative: signal-cli, which usage is explained out in [Mautrix-signal wiki](https://docs.mau.fi/bridges/go/signal/authentication.html)

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

## Note

Info taken and adapted to our use from [Mautrix-signal wiki](https://docs.mau.fi/bridges/go/signal/index.html), so in case of info gets outdated, try referring there.