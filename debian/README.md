# Wireguard

This repository contains scripts that make it easy to configure [WireGuard](https://www.wireguard.com)
on [VPS](https://en.wikipedia.org/wiki/Virtual_private_server).


## Quick Start

### Ubuntu

```bash
wget https://raw.githubusercontent.com/TSUKER/wireguard-install/master/debian/wg-ubuntu-server-up.sh

chmod +x ./wg-ubuntu-server-up.sh
sudo ./wg-ubuntu-server-up.sh
```

### Debian

```bash
wget https://raw.githubusercontent.com/TSUKER/wireguard-install/master/debian/wg-debian-server-up.sh

chmod +x ./wg-debian-server-up.sh
sudo ./wg-debian-server-up.sh
```

To get a full instruction, please follow to the article above.

### Supported OS

* Ubuntu 18.04
* Ubuntu 20.04
* Debian 9
* Debian 10

## wg-ubuntu-server-up.sh

This script:

* Installs all necessary software on an empty Ubuntu DigitalOcean droplet
(it should also work with most modern Ubuntu images)
* Configures IPv4 forwarding and iptables rules
* Sets up [unbound](https://github.com/NLnetLabs/unbound) DNS resolver 
* Creates a server and clients configurations
* Installs [qrencode](https://github.com/fukuchi/libqrencode/)
* Runs [WireGuard](https://www.wireguard.com)


### Usage

```bash
wg-ubuntu-server-up.sh [--clients=<clients_count>] [--no-reboot] [--no-unbound]
```

Options:

* `--clients=<clients_count>` how many client's configs will be created
* `--no-unbound` disables Unbound server installation (1.1.1.1 will be used as
   a default DNS for client's configs)
* `--no-reboot` disables rebooting at the end of the script execution

### Example of usage

```bash
./wg-ubuntu-server-up.sh
```

```bash
./wg-ubuntu-server-up.sh --clients=10
```

## wg-debian-server-up.sh

This script works the same way and with the same options, that
`wg-ubuntu-server-up.sh` do.

## wg-genconf.sh

This script generate server and clients configs for WireGuard.

If the public IP is not defined, then the public IP of the machine from which 
the script is run is used.
If the number of clients is not defined, then used 10 clients.

### Prerequisites

Install [WireGuard](https://www.wireguard.com) if it's not installed.

### Usage

```bash
./wg-genconf.sh [<number_of_clients> [<dns_ip> [<server_public_ip>]]]
```

Where:

* `number_of_clients` how many client's configs will be generated
* `dns_ip` the script should use this IP as a DNS address
* `server_public_ip` the script should use this IP as a server address


### Example of usage:

```bash
./wg-genconf.sh
```

```bash
./wg-genconf.sh 10
```

```bash
./wg-genconf.sh 10 1.1.1.1
```

```bash
./wg-genconf.sh 10 1.1.1.1 157.245.73.253
```

## Providers

I recommend these cheap cloud providers for your VPN server:
- [Hetzner](https://hetzner.cloud/?ref=Txj9RI7g08TN): Germany and Finland and USA , IPv6, 20 TB of traffic, starting at €3/month
- [Digital Ocean](https://m.do.co/c/1a7411d7a9a1): Worldwide locations, IPv6 support, starting at \$5/month
- [Vultr](https://www.vultr.com/?ref=8813484): Worldwide locations, IPv6 support, starting at \$3.50/month