# Matrix<->Slack bridge

## 2 Options

Now we have 2 options, there is the older Appservice-slack (mostly for bridging channels), and newer Mautrix-slack (puppeting bridge, channel bridging is coming), Mautrix-slack is recommended for new setups, Appservice-slack will be deprecated in the future.

## Mautrix-slack:

Up to date info about Mautrix-slack itself: https://docs.mau.fi/bridges/go/slack/index.html

## What?

An Matrix<->Slack bridge for individial using Slack through Matrix. appservice-slack style Channel bridging is upcoming feature, eventually Hacklab will move everything to Mautrix-slack when things ready.

## Set up
- General setup finds from: https://docs.mau.fi/bridges/go/slack/authentication.html
- Ask details Matrix-channel: `#general:hacklab.fi` if unsure.

## Appservice-slack

Up to date info about matrix-appservice-slack itself: https://github.com/matrix-org/matrix-appservice-slack

## What?

An Matrix<->Slack bridge for bridging Slack-room to Matrix-room; puppets Slack-users to Matrix and for Slacks side an relaybot mimicks Matrix-user as Slack user. Also medias (mostly pictures tested) will work too. This will be deprecated once Mautrix-slack is "complete".

## Set up
- General setup finds from: https://github.com/matrix-org/matrix-appservice-slack
- Ask details Matrix-channel: `#general:hacklab.fi` if you want to bridge Slack-room(s) to Matrix, as this needs collaboration from Slack workspace admin and hacklab.fi Matrix-admin.

### Double puppeting (recommended)

You can replace the Matrix puppet of your Slack account with your Matrix account. When you do so, messages that you send from other Slack clients will be sent from your Matrix account instead of the default puppet user.

How to get virgin Access-token: Use https://gitlab.com/vurpo/matrix-login/ for currently most effortless method.

As with the Slack account login, you must do this in a private chat with the bridge bot.

- Log in with `login-matrix <access token>`
- After logging in, the default Matrix puppet of your Slack account should leave rooms and your account should join all rooms the puppet was in automatically.

## Note

Info taken and adapted to our use from [Mautrix-slack wiki](https://docs.mau.fi/bridges/python/slack/authentication.html), so in case of info gets outdated, try refer there.