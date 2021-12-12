# WireGuard installer
[![GitHub issues](https://img.shields.io/github/issues/TSUKER/wireguard-install)](https://github.com/TSUKER/wireguard-install/issues)
[![GitHub forks](https://img.shields.io/github/forks/TSUKER/wireguard-install)](https://github.com/TSUKER/wireguard-install/network)
[![GitHub stars](https://img.shields.io/github/stars/TSUKER/wireguard-install)](https://github.com/TSUKER/wireguard-install/stargazers)
[![GitHub license](https://img.shields.io/github/license/TSUKER/wireguard-install)](https://github.com/TSUKER/wireguard-install)
![visitors](https://visitor-badge.glitch.me/badge?page_id=TSUKER.wireguard-install)


**This project is a bash script that aims to setup a [WireGuard](https://www.wireguard.com/) VPN on a Linux server, as easily as possible!**

WireGuard is a point-to-point VPN that can be used in different ways. Here, we mean a VPN as in: the client will forward all its traffic trough an encrypted tunnel to the server.
The server will apply NAT to the client's traffic so it will appear as if the client is browsing the web with the server's IP.

The script supports both IPv4 and IPv6. Please check the [issues](https://github.com/TSUKER/wireguard-install/issues) for ongoing development, bugs and planned features!


## Requirements

Supported distributions:

- Ubuntu >= 16.04 [Second variant for Debian](https://github.com/TSUKER/wireguard-install/blob/master/debian/README.md)
- Debian >= 10 [Second variant for Ubuntu](https://github.com/TSUKER/wireguard-install/blob/master/debian/README.md)
- Fedora
- CentOS
- Arch Linux
- Oracle Linux

## Usage

Download and execute the script. Answer the questions asked by the script and it will take care of the rest.

```bash
curl -O https://raw.githubusercontent.com/TSUKER/wireguard-install/master/wireguard-install.sh
chmod +x wireguard-install.sh
./wireguard-install.sh
```
[Second variant for Debian and Ubuntu](https://github.com/TSUKER/wireguard-install/blob/master/debian/README.md)

It will install WireGuard (kernel module and tools) on the server, configure it, create a systemd service and a client configuration file.

Run the script again to add or remove clients!

## Providers

I recommend these cheap cloud providers for your VPN server:
- [Hetzner](https://hetzner.cloud/?ref=Txj9RI7g08TN): Germany and Finland and USA , IPv6, 20 TB of traffic, starting at €3/month
- [Digital Ocean](https://m.do.co/c/1a7411d7a9a1): Worldwide locations, IPv6 support, starting at \$5/month
- [Vultr](https://www.vultr.com/?ref=8813484): Worldwide locations, IPv6 support, starting at \$3.50/month
