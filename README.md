# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

## Setup

Quote time:

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw

### Version

1.9.0

### Last Tested on

MacOS 14.3.1

### App Store Applications

* [Xcode](https://apps.apple.com/us/app/xcode/id497799835)
  * `sudo xcodebuild -license accept`

### Third Party Applications

* [GPT4All](https://gpt4all.io/index.html)
* [StartyParty](https://marketing.startyparty.dev/) for firefox, made by me
* [StartyParty Addons](https://github.com/arbitrarily/startyparty-addons)

```sh
# List Installed Extensions
code --list-extensions | xargs -L 1 echo code --install-extension
```

### Dotfiles

Majority of configurations are stored in my [dotfiles](https://github.com/arbitrarily/dotfiles) repository; currently a private repository.

* [`Dotfiles`](https://github.com/arbitrarily/dotfiles) github.com/arbitrarily/dotfiles

### Non Dotfile Settings & Configs

* [`Firefox CSS`](https://github.com/arbitrarily/firefox-css) github.com/arbitrarily/firefox-css

### Scripts

* [`cmus Theme`](https://github.com/arbitrarily/cmus-theme) github.com/arbitrarily/cmus-theme

### Fonts

Fonts are Backed up to **/Dropbox/Resources**

* [`Nerd Fonts`](https://github.com/ryanoasis/nerd-fonts) github.com/ryanoasis/nerd-fonts

### zsh

```sh
# Install Oh-My-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install Oh My ZSH Plugins
curl -L https://iterm2.com/shell_integration/zsh \
-o ~/.iterm2_shell_integration.zsh
```

### Set Up SSH Keys

* <https://help.github.com/articles/generating-ssh-keys/>

```sh
# Generate SSH
ssh-keygen -t rsa -C "your_email@example.com"

# Copy
keys # shortcut
pbcopy < ~/.ssh/id_rsa.pub

# Test if worked
ssh -T git@github.com
```

### Set Up Git

```sh
git config --global user.name "Name"
git config --global user.email email@email.com
git config --global github.user user_name_here
git config --global github.token your_token_here
git config -l --global
git config --global core.editor "code ."
git config --global color.ui true
```

### Set Hostname

```sh
sudo scutil --set HostName ###
```

### Set Up Mac OS X Preferences

Some of these may be out of date, have to go through this list and update it.

```sh
# Set a fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 0

# Set a shorter delay until key repeat
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Remove Animations
defaults write NSGlobalDomain NSWindowResizeTime -float 0.001

# Hide the Desktop
defaults write com.apple.finder CreateDesktop false; killall Finder

# Skip Verify Images
defaults write com.apple.frameworks.diskimages skip-verify true

# Prevent Apple Character Press and Hold
defaults write -g ApplePressAndHoldEnabled -bool false

# Add a contextual menu item to show the Web Inspector in web views
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# Show the ~/Library folder
chflags nohidden ~/Library

# Store screenshots in subfolder on desktop
mkdir ~/Screenshots
defaults write com.apple.screencapture location ~/Screenshots
killall SystemUIServer

# Add Message to Login Screen
sudo defaults write /Library/Preferences/com.apple.loginwindow LoginwindowText "In found, please call ###-###-####"


# Enable Text Selection in QuickLook
defaults write com.apple.finder QLEnableTextSelection -bool TRUE; killall Finder

# Faster Dock Animation
defaults write com.apple.dock autohide-time-modifier -float 0.15; killall Dock

# Dull Hidden Apps in Dock
defaults write com.apple.Dock showhidden -bool TRUE; killall Dock

# Disable Dashboard
defaults write com.apple.dashboard mcx-disabled -bool true

# Make Dock only Show Active Apps
defaults write com.apple.dock static-only -bool true; killall Dock

# Just in Case: Revert Dock to Default
defaults write com.apple.dock static-only -bool false; killall Dock

# Opt-out from Siri data collection
defaults write com.apple.assistant.support 'Siri Data Sharing Opt-In Status' -int 2

# Disable 'Ask Siri'
defaults write com.apple.assistant.support 'Assistant Enabled' -bool false

# Disable Siri voice feedback
defaults write com.apple.assistant.backedup 'Use device speaker for TTS' -int 3

# Disable 'Do you want to enable Siri?' pop-up
defaults write com.apple.SetupAssistant 'DidSeeSiriSetup' -bool True

# Hide Siri from menu bar
defaults write com.apple.Siri 'StatusMenuVisible' -bool false
defaults write com.apple.Siri 'UserHasDeclinedEnable' -bool true

# Disable Siri services (Siri and assistantd)
launchctl disable "user/$UID/com.apple.assistantd"
launchctl disable "gui/$UID/com.apple.assistantd"
sudo launchctl disable 'system/com.apple.assistantd'
launchctl disable "user/$UID/com.apple.Siri.agent"
launchctl disable "gui/$UID/com.apple.Siri.agent"
sudo launchctl disable 'system/com.apple.Siri.agent'

```

### Install Xcode

* [https://itunes.apple.com/au/app/xcode/id497799835?mt=12](itunes.apple.com/au/app/xcode/id497799835?mt=12)

```sh
xcode-select --install
```

### Install Homebrew

* [https://brew.sh/](https://brew.sh/)

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### Install Apps Via Homebrew Cask

```sh
# Install Fonts
brew tap homebrew/cask-fonts
brew install font-hack-nerd-font

# Yabai
brew install koekeishiya/formulae/yabai

# shkd
brew install koekeishiya/formulae/skhd
```

### Install Alfred Cask Link

```sh
brew cask alfred link
```

### Install Yabai

Install Yabai Window Manager

First disable SIP:

```bash
csrutil disable
```

then after reboot:

```bash
brew install koekeishiya/formulae/yabai

sudo yabai --install-sa

brew services start yabai

killall Dock
```

### Marko Bajlovic

* <https://marko.tech>
* * <https://marko.tech/uses>
* <https://startyparty.dev>
* * <https://marketing.startyparty.dev>
* <https://github.com/arbitrarily>
* <https://c.im/@des>

Sourced from all over and throughout the years.
