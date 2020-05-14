# Matrix<->Discord bridge

## What?

An Matrix<->Discord bridge for receiving and sending Discord messages with Matrix-client.

## Set up

- Get Power Level 50 in Matrix room (not sure why bridge wants that..)
- You also need to be admin at Discord channel or have a admin to help you
- Get a invite link from one of Hacklab.fi admins at #matrix:hacklab.fi. Don't spread the link as it can be used to invite the bot to any Discord room.
- Invite the bridge to your Discord server using the link. The bridge will need all the permissions selected.
- Invite `@_discord_bot:hacklab.fi` to your Matrix room. The bot should have permissions to invite users.
- Open the text channel you'd like to bridge in the Discord web application.
- In the address bar there should be a URL like https://discordapp.com/channels/ServerID/ChannelID
- Use that as a reference to say in your Matrix room `!discord bridge ServerID ChannelID`
- The bridge will ask for confirmation on Discord side, and after approved your room should be bridged to Discord.
