# Matrix<->Whatsapp bridge

Up to date info about Mautrix-whatsapp itself: <https://docs.mau.fi/bridges/go/whatsapp/index.html>

## What?

An Matrix<->Whatsapp bridge for receiving and sending Whatsapp messages with Matrix-client, purely for bringing your personal Whatsapp to your Matrix-client, does have relaybot support.

## Special notes
This bridge uses the web API, so your phone must be connected to the internet for the bridge to work. The WhatsApp app doesn't need to be running all the time, but it needs to be allowed to wake up when receiving messages (should work by default). The web API is used instead of the main client API to avoid bans (WhatsApp will ban unofficial clients).

There also exist instructions how to run Android in virtual machine so you could get rid of Whatsapp alltogether from your actual phone, read more at [Mautrix-whatsapp wiki, Android VM Setup](https://docs.mau.fi/bridges/go/whatsapp/android-vm-setup.html)

## Set up
- Start a chat with the bridge bot `@whatsappbot:hacklab.fi`. The bot should say "This room has been registered as your bridge management/status room." if you started the chat correctly.
  - To log in by entering a 8-letter code on your phone, enter: `login +358123456789`.
  - To log in by scanning the QR code, enter: `login`. If the code expires before you scan it, the bridge will send an error to notify you.
- Open WhatsApp on your phone.
- Tap Menu  or Settings  and select Linked devices.
  - Log in by QR-code: Point your phone at the image sent by the bot to capture the code.
  - Log in with pairing code: Tap "Link with a phone number instead".
- Finally, the bot should inform you of a successful login and the bridge should start creating portal rooms for all your WhatsApp groups and private chats.

### Double puppeting (recommended)

For hacklab.fi homeserver users this bridge does double-puppeting automatically.
