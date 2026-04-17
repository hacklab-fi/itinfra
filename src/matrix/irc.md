# Matrix<->IRC Messages bridge

## Warning!

!!! Currently at very early stages, not yet suitable for daily driver !!!

Will replace Heisenbridge in few months (written in April 2026).

## What?

An Matrix<->IRC Messages bridge for receiving and sending IRC-messages on Matrix-client.

It is possible to be set up for any IRC-network by bridge admins, given the Network agress or facilitates the connections from our IRC-bridge -server.

Currently supported networks are:
- Ircnet
- Libera
- Oftc
- Ergo
- Quakenet

## Set up
- Start a chat with the bridge bot `@irc:hacklab.fi`. The bot should say "This room has been registered as your bridge management/status room." if you started the chat correctly.
- Write `login` to the room.
- Follow the on screen instuctions
- Finally, the bot should inform you of a successful login and the bridge should start creating portal rooms for all your SMS and RCS "chats".

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

For users from other homeservers who has access to use the bot can use 'login-matrix'-command to manually enable double-puppeting.