# Hacklab.fi Matrix general instructions

## What?

Matrix is versatile federated instant messaging protocol and we offer Matrix homeserver and services to Finnish hacklab members. 

Matrix also supports bridges, both puppeted and relaybot, to various other networks and systems, like IRC, Telegram, Whatsapp, SMS, etc for example.

## Contents

[General about matrix terminology](#general-about-matrix-terminology)\
[Registering an user](#registering-an-user)\
[Clients](#clients)\
[Login](#login)\
[Bridges](#bridges)

## General about matrix terminology

### MXID

Matrix user id is called MXID, and it constructs from username and domain part, which are inseparable. This means that where ever in you need to input your MXID it should be in format: `@example:hacklab.fi`

### User domain

User domain is the designated domain name in MXID, in our case `hacklab.fi`

### Homeserver

Homeserver is the matrix-server catering hacklab.fi users, in our case `matrix.hacklab.fi`

### Users, rooms and communities

In Matrix usernames allways starts with `@` -sign, rooms with `#` -sign and communities with `+` -sign

## Registering an user

- Surf to [hacklab.fi Matrix user registration](https://matrix.hacklab.fi/register) website
- Fill out your details
  - Figure an username (only name, no domain here)
  - Figure out password
  - Provide an known Invite token, this can be acuired from your hacklab
- Press register

## Clients

There are many clients programs for diffirent platforms and personal tastes available. Reference client is Element, which is available for computers, phones and we also offer an web-instance at https://chat.hacklab.fi

## Login

Most matrix clients supports automatic discovery of server settings when you give your full MXID as username, so often times it is enough to type in the `@example:hacklab.fi` as username and your password.

If manual server settings are needed, they are:
- Homeserver URL: `https://matrix.hacklab.fi`
- Identity Server URL: blank/none

## Bridges

Matrix has awesome integration for various other Chat/IM networks and services, called bridges, which makes using matrix an killer thing. IRC is offered pretty much baked in into Matrix, and for finnish Hacklab members we offer also bridges for Telegram, Whatsapp and SMS. There is also on-going effort to offer Slack bridging, and more can be added if installable bridge-services exists.

Hacklab member using `hacklab.fi` homeserver, thus having MXID of `@user:hacklab.fi`, has automatic access to use bridges trough hacklab.fi servers, hacklab members using some other homeserver need to ask to be added into bridge(s) manually, ask more in Matrix channel: [#general:hacklab.fi](https://matrix.to/#/#general:hacklab.fi)

Links to specific bridge instructions:

- IRC: https://github.com/matrix-org/matrix-appservice-irc/wiki
- Telegram: [matrix-telegram.md](matrix-telegram.md)
- Whatsapp: [matrix-whatsapp.md](matrix-whatsapp.md)
- Facebook: [matrix-facebook.md](matrix-facebook.md)
- Signal: [matrix-signal.md](matrix-signal.md)
- SMS: [matrix-smsbot.md](matrix-smsbot.md)
- Slack: [matrix-slack.md](matrix-slack.md)
- Discord: [matrix-discord.md](matrix-discord.md)
