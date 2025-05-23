# My Mac Configuration

Welcome to my Mac configuration repository! Here, you'll find everything you need to set up your Mac to mirror my development environment. This setup includes essential packages installed via Homebrew, iTerm configurations for a better terminal experience, and additional commands you might find useful.

## Table of Contents

- [Installation](#installation)
- [Homebrew Packages](#homebrew-packages)
- [iTerm Configuration](#iterm-configuration)
- [Additional Commands](#additional)

## Installation

To get started, clone this repository to your local machine:

```bash
git clone https://github.com/koda-git/config-mac.git
cd mac-configs
```

## Homebrew-packages

First install homebrew on your mac by inputting the command

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Here is my list of cask (GUI) packages

```bash
brew install --cask discord iterm2 signal github obsidian visual-studio-code shottr
```

Here is a list of my brew (CLI) packages

```bash
brew install htop openconnect fastfetch nano vim
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

Java Installation (Save as \*.sh and chmod +x the file )

```bash
#!/bin/bash

# Define the URL and the target directory
JDK_URL="https://download.java.net/java/GA/jdk21.0.2/f2283984656d49d69e91c558476027ac/13/GPL/openjdk-21.0.2_macos-aarch64_bin.tar.gz"
TARGET_DIR="/Library/Java/JavaVirtualMachines/"

# Download the JDK archive
echo "Downloading JDK from $JDK_URL..."
curl -L $JDK_URL -o openjdk.tar.gz

# Extract the downloaded file
echo "Extracting the JDK..."
tar -xzf openjdk.tar.gz

# Assuming the folder that starts with "jdk" is the JDK directory.
# Note: This approach assumes only one directory in the extracted tar.gz starts with "jdk".
JDK_DIR=$(find . -type d -name "jdk*" -print -quit)

# Check if JDK_DIR is not empty
if [[ -n $JDK_DIR ]]; then
    # Move the JDK directory to the target location
    echo "Moving $JDK_DIR to $TARGET_DIR"
    sudo mv "$JDK_DIR" "$TARGET_DIR"
    echo "JDK has been successfully moved to $TARGET_DIR"
else
    echo "JDK directory not found."
fi

# Cleanup the downloaded archive
rm openjdk.tar.gz

echo "Installation completed successfully."
```

Rustup
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
