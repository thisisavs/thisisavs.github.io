---
title: "WSL Setup - Installation and Uninstallation "
date: 2026-01-15
tags:
  - wsl
  - windows
  - linux
  - setup
draft: false
---

<!-- TIL: Installing and uninstalling WSL(Windows Subsystem for Linux) -->

# Installing and Uninstalling  WSL (Windows Subsystem for Linux)

Ref: https://learn.microsoft.com/en-us/windows/wsl/install

## Installing wsl

### 1. Install Ubuntu - the default wsl distro
1. Open PowerShell in Administrator mode
2. Run `wsl --install`
    - wsl installs *Ubuntu* by default. 
    - Once Ubuntu is installed it will run automaticlly. 
3. Enter username and setup password (btw while entering password nothing shows up on the screen)
4. first things to do when inside Ubuntu is to update and upgrade packages Run
```
sudo apt update && sudo apt upgrade
```
### 2. Install wsl with different distro

1. If you dont want Ubuntu the default distro and need to install any other distros start by installing wsl with --no-distribution
```
wsl --install --no-distribution

```
2.  Then you can get the list of available distros and then select a distro to install
```
# list available distributions
wsl --list --online

# install the selected distro
wsl --install -d Debian
```
3. Change the default option

```
# set Debian as default
wsl --set-default Debian

```

## Uninstalling wsl

Ref: https://gist.github.com/4wk-/889b26043f519259ab60386ca13ba91b

1. Open PowerShell in Administrator mode
2. List all the installed distros
```
# list all the installed distros
wsl -l -v
```
3. Uninstall the distro
```
#uninstall the distro
wsl --unregister Ubuntu
```

4. Uninstall wsl
```
#uninstall wsl
wsl --uninstall
```