sa-vpn-wireguard
================

[![Build Status](https://travis-ci.com/softasap/sa-vpn-wireguard.svg?branch=master)](https://travis-ci.com/softasap/sa-vpn-wireguard)

Simple

```YAML
  roles:
    - {
        role: "sa-vpn-wireguard"
      }
```

Advanced:

```YAML
  roles:
    - {
        role: "sa-vpn-wireguard"
      }
```

## Using mobile clients

So far, one of mobile clients we are aware of is not yet officially released   https://play.google.com/store/apps/details?id=com.wireguard.android

If you want to pass configuration to mobile you can use https://github.com/fukuchi/libqrencode (accessible via apt in debian flavour)

Than your command might look like

```sh
  ./wg_add_peer.sh > out
  # edit out if needed
  cat out | qrencode -t ANSIUTF8
  # scan with phone
█████████████████████████████████████████████████████████████████████
█████████████████████████████████████████████████████████████████████
████ ▄▄▄▄▄ █ ▀▄███▄▀███▀ █▀▄█▄▀█▀██  █ ██▀ ▄██▄▄█▀▀█  █  █ ▄▄▄▄▄ ████
████ █   █ █  ▄ █▀▄ ▄ █▄  █▀ █▄▀▄▀▄▀▄ ▄ ▄▄   ▀▄▀▄█  ▀▄ ▄ █ █   █ ████
████ █▄▄▄█ █▀▀█▄█ ▄▀█▀█▀▄▀█▄  ▀█ ▄▄▄ █▄ █ █ ██▀▀█▄▄▀█▀ ▄██ █▄▄▄█ ████
████▄▄▄▄▄▄▄█▄▀ ▀▄█▄▀▄▀ ▀▄█▄█ ▀▄▀ █▄█ ▀▄▀ █ ▀ ▀▄█ █▄▀ █▄▀▄█▄▄▄▄▄▄▄████
████ ▄█▀▄▄▄█▀ ▀▄█▀▀██▄▀▀ █▀██▄ ▄  ▄   ██▀▄▄▄▀▀█▄▄█▀  █ █ ▀▀ █▄ ▄ ████
█████▄▀▀▄▄▄██▀▄  █ █▀  ▄██▄▄ ▀▄▄▄██▄ ▄▀▀▄▀▄▀ ▀▀█▀▄▀ ▄█ ▄▄  ▄█ ██▀████
████ █▄█▀ ▄█ ▀▀▀█  ▀█▄▄▄ ███ ▀ ▀ █▀▀█████▀▀█▀█▀████▀▄ ▄▀█ ▄ ▄▀ ██████
██████ █ ▀▄  ██▄▄▄ ▄█▄▄▄█▄    ▄ ▀▀██  ▄ █▄▀ ▀▄██▄▄▄▀▀▀▀▀ ▄▄▄█▀▄▄ ████
████▀▀██▀█▄ ▀ ▄ ▀▀▀▀▀██ ▄▀█▄  ▀ ▄▄▄▀▀▄▀ ▄ ▀▄▄▄▀█▀▄█▀▄▄▀▀██▀▄▄▀█▄▄████
██████▄▀▄█▄ █▄▄▀█▄█▄██▄▀▄▀█▀█ ▄ █▄█▄█    ▀▀▀█ ██▄▄▀ █▀  █▄██    ▄████
█████   ▄▀▄▄▄▀█▄▄ ▄█▀█▀ ▄▄ █▄  █ ██▀▀███▀▄ ▄▀█ █ ▄▄ ▀█▄▀█ ▄▀ █▀██████
████ ██ ▀▀▄▄█ █▄██▄▄▄▄██ ▀▄▀▀▄ ▄▄  ██▄▄▀▄█▀▀ ▄ █▀▄▄▀▄▀█▀  ██ █ ▄▄████
████▄▀ ▀ █▄▄▀ ▀ ▄▀▄█▀▀ ▄▄█▄▀█▀▀▀▀█▄█ █▀██  ▄ ▄▄█▄▄▄█▀▄ ▀█  ▀▄█ ▀▀████
████▄ █▀▀▄▄▀█▄ █  ▄ █▀ ▀ ██▀▀▀ ▀   ▀█▄▀▀▄█▄▀▀█▀▄▄▄▀▀▄█ ▄█  ██ ▀██████
████▄ ▀█ ▄▄▄     █▀▀▄▄  █▄██▀ ▄▄ ▄▄▄ ▄ █▀█  ██▄ ▀▄ █ █▄▀ ▄▄▄ █▀▄ ████
████▀██▄ █▄█ ██▄█ █▄▄▀▄ ▄▀█▀ ▄▀  █▄█ ▄▀ █▀ ▄   █▄ ▀█▀▀▀▄ █▄█ ▀  █████
████▀ █▄▄ ▄ ▄██▀ ▄▀▄██▄ ▀▄▄▀▄▀██ ▄▄  █ ██▄▀███▄▀▀██ ▄▀   ▄ ▄▄▀█▄ ████
████▄▄▄ ▄█▄▀▄▄█▄█▄▀▀ █▄▀▄ ▀▄ ▀▄  ▀ ▀▀▄▄  ▀▀  ▄█▄▄█  ▀▀▀  ▀  █ ▀  ████
████▄█▀█▄█▄▀▀▄ █▀▄▄█ █▀ ▀▄█▀▀ ▄▄▀▄▀█▄▀   ▀▄▄ ▄█▄▄ ▀▀  ▄█  ▄▄▀▀▀██████
████▀▄    ▄▀  █ ▀▄ ▄▄▀ █▀ ██▀▀█▄▄▀▀▀ ▄▄  █▀▀█▀  ▀▄ ▀ ▀█▀   ▀ ▄▀██████
████▄▀▄█▄ ▄▄█▄ ▀██ █ ▄▀▀ ▄▀▀ ▄  ██▄▄▄▄▄█ ▄ ▀█▀  ▀███▀▄ ▀▀▄▄ █  ▀▀████
█████ █▀ █▄▄▀▀▄▀  ██▄▀ ▄█▄▀▀   ▀▄▀▄█ ▄▀▀▄█▀▀█▄ ▄ ▄ ▀ ▄    █▀▀▄█ █████
████ ▄ ▀██▄ ▀█  █▄▄▀██▀▄▀█ ▀▀ ▄▄▀▄▀█▀███  ▀▀ █▄ ███▀█▄▀▀█▀▄█▀▀██▄████
████   ▄▀▀▄▄▀ ▄▄▄▄█ █  ▀ ▄    ▄█▄  ▀▀▄▄ █▀▀ ▀▄ ██ ▄█▀▀ ▀ ▀▀ █▀▀▀▀████
████▄█ █▄ ▄▀▀ ▀▀ ▀ ▀▀▄ ▄█▀█▄  ▄ ▀▄█▄█▀▀▀▀▀ █▄▀▄  ▄      ▀▄▄  ▀█▄▀████
████▀▀ ▄ ▄▄  ▄▀█ ▀▄▄██▄▄▀▄█▀█▄▀▀ ▄██▄ ▀  ▀  ▀ ▄▄██ ▀▀▀  █▀▀▀▄█▄  ████
████▄▄▄▄██▄▄ ██▀▀  ▀ ▄█▄▀███ ▀▄▄ ▄▄▄ ▄█▄ ▀ ███▀█▀▄▄ ▀ ▀▀ ▄▄▄ ▀█▄ ████
████ ▄▄▄▄▄ █▀▄▀ ▄█▀▄█▄█ █ ▀█ ▄ █ █▄█ █ ▀▄▀  ▄▄▀▄█▄ ▀▄██▄ █▄█ ▄  ▀████
████ █   █ █▄█▀██▄ ██▀ ▄▄▄██▀▀▀█ ▄   ██▄█  ▀█▄▀█ ▄ ▄▄▄▀█ ▄  ▄█ █▀████
████ █▄▄▄█ █▀ ▄▀ ▀█ █▀▀▀  ▀▄▄█  █▀▀█▄ ▄▀▄█▄ ▀▄▀ ▀▄▀▀▄▀▄█▀██ ▄▄  █████
████▄▄▄▄▄▄▄█▄▄▄██▄████▄▄▄█▄█▄▄▄█▄███▄▄▄█▄█▄▄████▄▄██▄▄▄▄██▄█▄█▄▄▄████
█████████████████████████████████████████████████████████████████████
█████████████████████████████████████████████████████████████████████
root@wireguard:/etc/wireguard# 


```



Copyright and license
---------------------

Code is dual licensed under the [BSD 3 clause] (https://opensource.org/licenses/BSD-3-Clause) and the [MIT License] (http://opensource.org/licenses/MIT). Choose the one that suits you best.

Reach us:

Subscribe for roles updates at [FB] (https://www.facebook.com/SoftAsap/)

Join gitter discussion channel at [Gitter](https://gitter.im/softasap)

Discover other roles at  http://www.softasap.com/roles/registry_generated.html

visit our blog at http://www.softasap.com/blog/archive.html
