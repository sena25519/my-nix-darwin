# Installation

> Purely handwritten. No AI. #NPD

```bash
# System Preferences
defaults write com.apple.screencapture type jpg && \ # take screenshots as jpg (usually smaller size) and not png
    defaults write com.apple.Preview ApplePersistenceIgnoreState YES && \ # do not open previous previewed files (e.g. PDFs) when opening a new one
    chflags nohidden ~/Library && \ # show Library folder
    defaults write com.apple.finder AppleShowAllFiles YES && \ # show hidden files
    defaults write com.apple.finder ShowPathbar -bool true && \ # show path bar
    defaults write com.apple.finder ShowStatusBar -bool true && \ # show status bar
    killall Finder;

# Install fish
curl -L https://github.com/fish-shell/fish-shell/releases/download/4.1.2/fish-4.1.2.pkg -o ~/Downloads/fish.pkg # manually install by clicking the bundle

# Setup fish
curl -sL https://raw.githubusercontent.com/jorgebucaran/fisher/main/functions/fisher.fish | source && fisher install jorgebucaran/fisher && \
    fisher install jorgebucaran/autopair.fish && \
    fisher install joseluisq/gitnow@2.13.0 && \
    fisher install acomagu/fish-async-prompt && \
    fisher install catppuccin/fish && \
    fish_config theme save "Catppuccin Mocha"

# Install xcode cmdline
xcode-select --install

# or install Xcode from app store then
sudo xcode-select -switch /Applications/Xcode.app/Contents/Developer

# Install Homebrew Package Manager
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Install Nix Package Manager
curl -L https://github.com/NixOS/experimental-nix-installer/releases/download/0.27.0/nix-installer.sh | sh -s -- install

# Clone this repo to /etc/nix-darwin
sudo git clone https://github.com/sena25519/my-nix-darwin.git /etc/nix-darwin

# Install Nix-Darwin
sudo nix run nix-darwin/master#darwin-rebuild -- switch

# Import gpg keys
gpg --import /path/to/gpgkey

# configure git
git config --global init.defaultBranch main
git config --global user.name sena
git config --global user.name sena@lichtlabs.org
git config --global user.signingkey \<YOUR_GPG_KEY_ID\>
git config --global commit.gpgsign true
```
