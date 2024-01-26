# Matrix<->Google Messages bridge

Up to date info about Mautrix-gmessages itself: <https://docs.mau.fi/bridges/go/gmessages/index.html>

## What?

An Matrix<->Google Messages bridge for receiving and sending Google Messages (both SMS and RCS) with Matrix-client, Pairs with [Google Messages app](https://play.google.com/store/apps/details?id=com.google.android.apps.messaging) included in most Android phones, also installable from Play-store.

## Special notes
This bridge uses the GMessages API, so your phone must be connected to the internet for the bridge to work. This is not stand alone bridge.

## Set up
- Start a chat with the bridge bot `@gmessagesbot:hacklab.fi`. The bot should say "This room has been registered as your bridge management/status room." if you started the chat correctly.
- Write `login` to the room.
- Log in by scanning the QR code with Google Messages app. If the code expires before you scan it, the bridge will send an error to notify you.
  - Open Google Messages on your phone.
  - Tap Burger-menu and select Device pairing.
  - Tap "QR code scanner" -button.
  - Point your phone at the image sent by the bot to capture the code.
- Finally, the bot should inform you of a successful login and the bridge should start creating portal rooms for all your SMS and RCS "chats".

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.
