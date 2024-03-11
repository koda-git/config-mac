# My Mac Configuration

Welcome to my Mac configuration repository! Here, you'll find everything you need to set up your Mac to mirror my development environment. This setup includes essential packages installed via Homebrew, iTerm configurations for a better terminal experience, and custom scripts for Quartz commands to enhance productivity.

## Table of Contents

- [Installation](#installation)
- [Homebrew Packages](#homebrew-packages)
- [iTerm Configuration](#iterm-configuration)
- [Additional Commands](#additional)

## Installation

To get started, clone this repository to your local machine:

```bash
git clone https://github.com/yourusername/mac-configs.git
cd mac-configs
```

## Homebrew-packages

First install homebrew on your mac by inputting the command

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Here is my list of cask (GUI) packages

```bash
brew install --cask datagrip discord iterm2 signal github obsidian visual-studio-code
```

Here is a list of my brew (CLI) packages

```bash
brew install htop openconnect neofetch nano
```

## iTerm-configuration

Import the iterm.json file inside the repo for my iTerm configuration

## Additional

```bash
# Faster dock hiding
defaults write com.apple.dock autohide-delay -float 0; defaults write com.apple.dock autohide-time-modifier -int 0;killall Dock

# Disk eject notification popup removal (Reboot after)
sudo defaults write /Library/Preferences/SystemConfiguration/com.apple.DiskArbitration.diskarbitrationd.plist DADisableEjectNotification -bool YES && sudo pkill diskarbitrationd
sudo reboot
```
