# Matrix<->Discord bridge

## Note:

This bridge will get an ["megafied"](https://mau.fi/blog/2024-h1-mautrix-updates/#introducing-megabridge) update in couple months (written in April 2026), it will likely be in-place update, but nothing is guaranteed until ready.

## What?

A Matrix<->Discord bridge for receiving and sending Discord messages with Matrix-client.

## Set up

Channel refers to the Discord channel to be bridged.

ChannelID is a string of numbers used internally to identify the Channel, such as `1234567890123456789`.

Server refers to the Discord server which contains Channel.

Room refers to the Matrix room to be bridged.

1. Get Power Level 50 (Moderator) in the Room
2. Inviting the Discord bot requires "application (bot) management" permissions in the Channel's Server
3. Get a Discord bot invite link from one of Hacklab.fi admins at `#matrix:hacklab.fi`. Keep the link private as it can be used to invite the bot to any Server
4. Invite the Discord bot to your Server using the link. The bridge will need all the preselected permissions
5. Invite `@discordbot:hacklab.fi` to your Room. The bot should have permissions to invite users
6. Obtain the ChannelID of the Channel with any method such as:
    - Any client:
        - Open the Channel
        - Select any message there and "Copy Message Link"
        - Your clipboard should now contain `https://discordapp.com/channels/ServerID/ChannelID/MessageID`
    - Any client:
        - Right click the Channel in the channel list and "Copy Channel ID"
        - Requires enabling Developer Mode (Settings -> Advanced -> Developer Mode)
    - Web Browser:
        - Open the Channel in the Discord web application
        - In the address bar there should be a URL like `https://discordapp.com/channels/ServerID/ChannelID`
7. Use ChannelID obtained above as a reference to say in your Room `!discord bridge ChannelID`
8. To bridge Matrix messages to Discord using webhooks say `!discord set-relay --create Matrix`
9. The bridge may ask for confirmation on Discord side (deprecated?), after an approval your Channel and Room should be bridged Matrix<->Discord

### Double puppeting

For hacklab.fi homeserver users this bridge does double-puppeting automatically.

For users from other homeservers who has access to use the bot can use 'login-matrix'-command to manually enable double-puppeting.