# Matrix<->Signal bridge

Up to date info about Mautrix-signal itself: https://github.com/tulir/mautrix-signal
## What?

An Matrix<->signal bridge for receiving and sending signal messages with Matrix-client, bridging groupchats, puppeting.. At the time of writing still pretty early version, but basic functionality exist and should work, like start chat from matrix, using as primary or linked device (signal stuff), direct messaging and group chats

## Set up
- On matrix: Open chat with `@signalbot:hacklab.fi`
- Issue _either_
  - `link [device name]` to link the bridge as a secondary device
  - `register <phone>`to sign into Signal as the primary device, international format.