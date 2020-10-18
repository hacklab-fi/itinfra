# Matrix<->Signal bridge

Up to date info about Mautrix-signal itself: https://github.com/tulir/mautrix-signal
## What?

An Matrix<->signal bridge for receiving and sending signal messages with Matrix-client, bridging groupchats, puppeting.. At the time of writing still pretty early version, most notably at the moment initiating new chat is not posible on matrix-side, but that doesn't stop you using it when others talk to you first, and also:

## Set up
- On matrix: Open chat with `@signalbot:hacklab.fi`
- Issue _either_
  - `link [device name]` to link the bridge as a secondary device
  - `register <phone>`to sign into Signal as the primary device, international format.