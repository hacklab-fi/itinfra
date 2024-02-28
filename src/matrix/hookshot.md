# Matrix Hookshot

Github, Gitlab, Jira and generic webhooks!

<https://matrix-org.github.io/matrix-hookshot/latest/hookshot.html>

<https://github.com/matrix-org/matrix-hookshot>

## What?

A Matrix bot for connecting to external services like GitHub, GitLab, JIRA, and more.

# Usage

At the moment `webhooks`, `feeds` and `github` are supported.

bot user is `@hookshot:hacklab.fi` admins are `@tsw:hacklab.fi` and `@olmari:hacklab.fi`

command: `hookshot help` gives you basic information of things

## webhooks

Invite `@hookshot:hacklab.fi` to your channel, give it `moderator` rights and ask it to add a webhook endpoint for you

```chat
/invite @hookshot:hacklab.fi
/op @hookshot:hacklab.fi 50
!hookshot webhook [nameforyourwebhook]
```

See the endpoint url from the admin room and send a test message to it:

```bash
curl -X POST \
  -H 'Content-Type: application/json' \
  -d '{"username": "its a me mario", "text": "yup, message from webhook", "html": "<i>yup</i><h2>formatting</h2>"}' \
  https://matrix.hacklab.fi/hookshot/webhook/REDACTED
```

To delete a webhook

## feeds

Invite `@hookshot:hacklab.fi` to your channel, give it `moderator` rights and ask it to add a webhook endpoint for you

```chat
/invite @hookshot:hacklab.fi
/op @hookshot:hacklab.fi 50
!hookshot feed https://example.com/feed/atom/ [nameyourfeed]
```

To list existing feeds

```chat
!hookshot feed list
```

And to remove a feed

```chat
!hookshot feed remove https://example.com/feed/atom
```

## github

Github has a github app registered for us `Hacklab.fi Matrix Hookshot` to use for the integration (@tsw:hacklab.fi, github username tswfi is the owner)

Install the app <https://github.com/apps/hacklab-fi-matrix-hookshot> into your account / organisation you want to use with hookshot.

To login to your github account talk with `@hookshot:hacklab.fi` and check with `github status` if you are already logged in and with `github login` you can complete oauth with github.

Then in your channel you can bridge a github project to your room with `!hookshot github repo https://github.com/my/project`. If the connection is done successfully you will get a confirmation and you can start choosing what you want to get notified about.

Now that the channel is bridged to the repo you can use some commands to update issues and so on

Creating new issue

```chat
!gh create "Title text" "Description for the issue" "label1,label2"
```

You can omit the labels (but its best to always have some description)

Closing an issue

```chat
!gh close 3 "Yay, great job!"
```

Hookshot github app will also push changes to the channel. Managing what to show is defined in the room state. TODO: document how to change these:

Check all the available options in <https://matrix-org.github.io/matrix-hookshot/latest/usage/room_configuration/github_repo.html#configuration>

## Misc

### Telegram bot entity

For Telegram side there exist bot with userhandle `@HacklabFiHookshotBot` that is tied into this Hookshot matrix-bot entity. Its purpose is to provide an actual user for Hookshot messages in matrix-room that is bridged to Telegram.

Bot is configured as "passive" bot, it has no reading rights inside Telegram room, it's purely echoing what hookshot says in matrix side in bridged room.

To utilize this all that is needed to do is to add the bot into the bridged Telegram room in Telegram side.

# How it was installed

Running on our matrix server under user `matrix-hookshot`, home directory in `/opt/matrix-hookshot`.

Requires at least Node 16 and Rust installed. Those are installed via nvm and rustup. The base requirements for those are

```bash
sudo apt update && sudo apt upgrade
# rustup
sudo apt install curl build-essential gcc make
# node
sudo apt install build-essential libssl-dev
```

basic steps for creating the user, installing necessary stuff and so on (note, the curl commands are taken from <https://github.com/nvm-sh/nvm#installing-and-updating> and <https://rustup.rs/>)

### Create user

```bash
# create user
sudo useradd --shell /usr/sbin/nologin --system --user-group --create-home --comment "Matrix Hookshot" --home-dir /opt/matrix-hookshot matrix-hookshot
```

### Install node

```bash
# become the user
sudo -Hu matrix-hookshot /bin/bash -l
# install nvm and rustup
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
# logout and relogin to load nvm
logout
sudo -Hu matrix-hookshot /bin/bash -l
# install node 20 (latest LTS as of writing this 20231110)
nvm install 20
# logout and relogin to load nvm with the new default node 20 config
logout
sudo -Hu matrix-hookshot /bin/bash -l
# check that node works
node -v
logout
```

the `node -v` command should output something like `v20.9.x`

### install rustup

```bash
# become the user
sudo -Hu matrix-hookshot /bin/bash -l
# start rustup installation
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
# and logout login to activate the profile
logout
sudo -Hu matrix-hookshot /bin/bash -l
# and check that you have rust
rustc -V
logout
```

The `rustc -V` command should output something like `rustc 1.xx.xx (xxxxxx yyyy-mm-ddd)`

### now we can setup the bot

```bash
# become the user
sudo -Hu matrix-hookshot /bin/bash -l
npm install -g yarn
cd
git clone https://github.com/matrix-org/matrix-hookshot.git
cd matrix-hookshot
yarn
```

And wait while it fetches few gigs of node-modules and compiles the rust stuff

### Configurations

Basically copy the registration.sample.conf and configuration.sample.conf to registration.conf and configuration.conf and change all the settings.

For this instance the configuration files can be found from the server and backups in the home directory of `matrix-hookshot`

### appservice conf (aka registration.sample.conf or registration.conf)

on our server all the appservice configurations are collected in `/etc/matrix-synapse/app_service_config_files/`. the file in the `matrix-hookshot` folder also as the service will read it too.

so always modify the `registration.yml` and then copy it to into `/etc/matrix-synapse/app_service_config_files/matrix-hookshot.yml`

```bash
sudo cp /opt/matrix-hookshot/matrix-hookshot/registration.yml /etc/matrix-synapse/app_service_config_files/matrix-hookshot.yaml
sudo chown matrix-synapse:matrix-synapse /etc/matrix-synapse/app_service_config_files/matrix-hookshot.yaml
sudo chmod 600 /etc/matrix-synapse/app_service_config_files/matrix-hookshot.yaml
```

And reload `matrix-synapse` after modifications.

### nginx conf

add two new location blocks

```nginx
        # hookshot
        location /[YOUR]/ {
                include snippets/matrix-proxy-headers.conf;
                include snippets/matrix-proxy-headers-client.conf;
                proxy_pass http://localhost:[PORT]/;
        }
        location /[YOUR]/oauth {
                include snippets/matrix-proxy-headers.conf;
                include snippets/matrix-proxy-headers-client.conf;
                proxy_pass http://localhost:[PORT]/oauth/;
        }
        location /[YOUR]/[PREFIX]/ {
                include snippets/matrix-proxy-headers.conf;
                include snippets/matrix-proxy-headers-client.conf;
                proxy_pass http://localhost:[PORT]/webhook/;
        }
        # end hookshot
```

where [YOUR]/[PREFIX] is what you defined in config.yml and port is the port you defined in config.yml for webhooks

And /[YOUR]/ is something that you can choose. Values `hookshot` and `webhook` are quite obvious choices.

### unit file

add unit file for this service

```conf
[Unit]
Description=Matrix Hookshot
After=matrix-synapse.service

[Service]
Type=exec
User=matrix-hookshot
WorkingDirectory=/opt/matrix-hookshot/matrix-hookshot
Environment=NODE_VERSION=20
ExecStart=/opt/matrix-hookshot/.nvm/nvm-exec yarn start
Restart=on-failure
RestartSec=60s

[Install]
WantedBy=multi-user.target
```

## start everything

first validate hookshot the config in $HOME/matrix-hookshot with
```bash
yarn validate-config
```

Then:

* restart synapse to get the new appservice onboard
* restart nginx to get the proxy configuration
* restart matrix-hookshot to restart the bridge

# secrets

check secrets in the users home folder
