---
title: "Remote SSH Setup - Raspberry Pi"
date: 2026-01-17
tags:
  - raspberry
  - tailscale
  - linux
  - ssh
  - openssh-server
  - termius
draft: false
---

<!-- TIL: Remote SSH Setup - Raspberry Pi -->

# Remote SSH Setup - Raspberry Pi

- OpenSSH server helps us do ssh from same network using the local ip. It is enough if we want to quickly login from same network without too many complications. but need to be secured properly and a headache if left running without proper security configurations. so to make it easy use Tailscale
- By Using Tailscale no one can try to ssh into our pi without tailscale authentication.

## 1. OpenSSH - For quick and local test not recommended to leave running
### OpenSSH Installation and Running
1. Update the system `sudo apt update && sudo apt upgrade`
2. Install OpenSSH Server`sudo apt install -y openssh-server`
3. Enable SSH `sudo raspi-config nonint do_ssh 0`
4. Verify if its running `sudo systemctl status ssh --no-pager`

### SSH into Raspberry Pi - Same Network
1. Get host ip from raspberrypi and save `hostname -I`
2. In your other device you want to ssh from, open PowerShell and run
    ```
    ssh <username>@<ip address of pi>
    ```
    *Example: `ssh user@127.0.0.1`*

3. Enter password to login to your Pi remotely

### Uninstall and cleanup OpenSSH

1. Stop OpenSSH service
    ```
    sudo systemctl stop ssh
    sudo systemctl disable ssh
    ```
2. Remove the package `sudo apt-get purge openssh-server`
3. Cleanup dependencies `sudo apt-get autoremove`

## 2. SSH into Raspberry Pi from any Network using Tailscale

### On your other Device
1. Install Tailscale in one of your other devices and create Tailscale account 
Refer to [Tailscale's Quickstart Guide](https://tailscale.com/kb/1017/install)

### On Raspberry Pi

Ref: [Tailscale | Install Tailscale on Linux](https://tailscale.com/kb/1031/install-linux)

1. Update the system `sudo apt update && sudo apt upgrade`
2. Install tailscale in your Pi by running
```
curl -fsSL https://tailscale.com/install.sh | sh
```
3. After installation start the Tailscale client and go through the authentication steps
```
sudo tailscale up
```
4. Verify the installation
```
tailscale ip

tailscale status
```
5. Enable Tailscale SSH. This lets Tailscale control the SSH connections for the pi
```
sudo tailscale set --ssh
```
If you need to disable i.e safely rollback `sudo tailscale set --ssh=false`

**Important:** To ensure tailscale autostarts on boot. Make sure its enabled 
```
sudo systemctl enable --now tailscaled
```
## 3. SSH from iphone using Termius
1. Install Tailscale on the mobile and connect the device on the tailscale network
    - Accept ios prompt to install the VPN Configuration
2. Install Termius and connect using `ssh <username>@<magicDNS  ip of your pi>`

--- 
## Troubleshooting
### SSH using MagicDNS not working when ot on local network
Ref: https://tailscale.com/kb/1188/linux-dns#dhcp-dhclient-overwriting-etcresolvconf

On Linux, the file `/etc/resolv.conf` is the "source of truth" for which DNS servers your system uses to look up websites.

Pi's OS (DHCP/dhclient), Tailscale are figthing over the control to write in this single file. 

**Solution:** To fix this conflict you need a dedicated "referee" (like systemd-resolved) active and correctly linked.

1. Make sure systemd-resolved is running:
```
sudo systemctl enable --now systemd-resolved
```
if this fails and with the message `systemd-resolved.service does not exist` sudo update and install package using `sudo apt install systemd-resolved` and once the package is installed then run the above command again

2. Create the "Link" (The Referee): We need to tell the OS to stop using a static file and instead use the dynamic one managed by systemd.
```
sudo ln -sf /run/systemd/resolve/stub-resolv.conf /etc/resolv.conf
```
3. Now restart everything
```
sudo systemctl restart systemd-resolved
sudo systemctl restart NetworkManager
sudo systemctl restart tailscaled
```
4. Check listening ports by running `sudo ss -lptn 'sport = :22'`
The output should be empty or show process related to tailscaled