# Creating new system user for daemons and bots etc

We use /opt/ for base home folder for system users, give it nologin as shell, etc

```bash
sudo useradd --shell /usr/sbin/nologin \
  --system --user-group \
  --create-home \
  --comment "Service longname" \
  --home-dir /opt/servicehomedir username
```

# Getting shell as system user for admin to do thing as the user

```bash
sudo -Hu username /bin/bash -l
```

Same can be used to run psql on postgres user directly

```bash
sudo -Hu postgres psql
```

# Software installations

We've used apt repositories where possible and rest is "directly on the host" installations, following given documentation per bot or automaton, provides update instructions too

Links to most of them:

* mautrix-bridges: <https://docs.mau.fi/bridges/index.html>
* mx-puppet-discord: <https://github.com/matrix-discord/mx-puppet-discord>
* appservice-slack: <https://matrix-appservice-slack.readthedocs.io/en/latest/getting_started/>
* heisenbridge: <https://github.com/hifi/heisenbridge>

# SSH related

We allow only publickey auth and user needs to belong into `ssh-user` group in order to connect into server with SSH

SSH server related settings resides in `/etc/ssh/sshd_config.d/` "confd" directory, edit settings in files under that dir and **not** directly `/etc/ssh/sshd_config` file. Same goes for possible client settings (ssh_config.d/).

# DNS resolving

We run Bind9/named as resolving DNS-server to provide credible DNSSEC resolving and OCSP-stapling.

If you need to define DNS-server to some service, use `localhost` or it's IP-variations `127.0.0.1` and `::1`.
