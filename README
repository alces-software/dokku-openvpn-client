# dokku-openvpn-client

Configures openvpn for a dokku app's web containers.

Each time one of the app's web processes starts this plugin will

 - Copy any files located at `/home/dokku/${APP}/DOKKU_FILES/openvpn-client-*` on the dokku host to `/etc/openvpn/` on the container.  The
   `openvpn-client-` prefix will be stripped.
   
 - Any required tun/tap devices will be created.

 - openvpn will be started.

## Requirements

- dokku 0.4.0+
- docker 1.6.x

## Installation

Install dependencies, if they have not already been installed.

```shell
# on 0.4.x
dokku plugin:install https://github.com/dokku/dokku-copy-files-to-image copy-files-to-image
dokku plugin:install https://github.com/F4-Group/dokku-apt
```

Install this plugin

```shell
# on 0.4.x
dokku plugin:install https://github.com/alces-software/dokku-openvpn-client  openvpn-client
```

## Setup

 - Add `openvpn` to the file `apt-packages` in your app's git repo.  The dokku-apt plugin will install `openvpn` in your container.

 - Set the app's dokku configuration to include `CONFIGURE_OPENVPN_CLIENT=true`.

 - Add your openvpn configuration files, auth files and certs to `/home/dokku/${APP}/DOKKU_FILES/`.  Each should be prefixed with `openvpn-client-`.  These will be copied into your container at
   `/etc/openvpn/` and the `openvpn-client-` prefix will be stripped.
