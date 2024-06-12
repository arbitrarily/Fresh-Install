# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

## Setup

Quote time:

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw

### Version

1.8.2

### Last Tested on

MacOS 14.3.1

### App Store Applications

* [Apple Music](https://music.apple.com)
* [ColorSlurp](https://apps.apple.com/us/app/colorslurp/id1287239339)
* [Quiver](https://apps.apple.com/us/app/quiver-take-better-notes/id866773894)
* [Xcode](https://apps.apple.com/us/app/xcode/id497799835)
  * `sudo xcodebuild -license accept`

### Third Party Applications

* [Adobe Acrobat](https://www.adobe.com/creativecloud.html)
* [Adobe Illustrator](https://www.adobe.com/creativecloud.html)
* [Adobe Photoshop](https://www.adobe.com/creativecloud.html)
* [Adobe Aftereffects](https://www.adobe.com/creativecloud.html)
* [GPT4All](https://gpt4all.io/index.html)
* [StartyParty](https://marketing.startyparty.dev/) for firefox, made by me
* [StartyParty Addons](https://github.com/arbitrarily/startyparty-addons)

### Homebrew Cask Applications

* [blob/master/dumps/brew-cask.md](brew-cask.md)

### Homebrew Packages

* [blob/master/dumps/brew-packages.md](brew-packages.md)

### Global NPM Packages

* [blob/master/dumps/npm-global.md](npm-global.md)

### VS Code Extensions

* [blob/master/dumps/vscode-extensions.md](vscode-extensions.md)

```sh
# List Installed Extensions
code --list-extensions | xargs -L 1 echo code --install-extension
```

### DotFiles (mac)

* [`.vimrc`](https://github.com/arbitrarily/vimrc) github.com/arbitrarily/vimrc

```sh
# vimrc
ln -s ~/Git/vimrc/vimrc ~/.vimrc
```

* [`.gitconfig`](https://github.com/arbitrarily/gitconfig) github.com/arbitrarily/gitconfig

```sh
# gitconfig
ln -s ~/Git/gitconfig/.gitconfig ~/.gitconfig
```

* [`.zshrc (primary)`](https://github.com/arbitrarily/zshrc) github.com/arbitrarily/zshrc

```sh
# zsh
ln -s ~/Git/zshrc/.zshrc ~/.zshrc
```

* [`.yabairc`](https://github.com/arbitrarily/yabairc) github.com/arbitrarily/yabairc

```sh
# yabairc
ln -s ~/Git/yabairc/.yabairc ~/.yabairc
```

* [`.skhdrc`](https://github.com/arbitrarily/skhdrc) github.com/arbitrarily/skhdrc

```sh
# skhdrc
ln -s ~/Git/skhdrc/.skhdrc ~/.skhdrc
```

* [`.gitconfig`](https://github.com/arbitrarily/gitconfig/blob/master/.gitconfig) github.com/arbitrarily/gitconfig/blob/master/.gitconfig

### Settings & Configs

* [`Visual Studio Code Preferences`](https://github.com/arbitrarily/vs-code-settings) github.com/arbitrarily/vs-code-settings
* [`Zed Preferences`](https://github.com/arbitrarily/zed-settings) github.com/arbitrarily/zed-settings
* [`iTerm Profile`](https://github.com/arbitrarily/iterm-profile) github.com/arbitrarily/iterm-profile
* [`Firefox CSS`](https://github.com/arbitrarily/firefox-css) github.com/arbitrarily/firefox-css

### Scripts

* [`cmus Theme`](https://github.com/arbitrarily/cmus-theme) github.com/arbitrarily/cmus-theme
* [`Nowplaying`](https://github.com/arbitrarily/nowplaying) github.com/arbitrarily/nowplaying

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

* https://confluence.atlassian.com/display/BITBUCKET/Set+up+SSH+for+Git
* https://help.github.com/articles/generating-ssh-keys/

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

```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew doctor

# Install Cask Fonts
brew tap homebrew/cask-cask-fonts

# Dump Brews to File
brew ls --casks | xargs brew desc --eval-all
```

Just remember to change the `X` in the PHP version in the last export line to whatever the latest one you're using is.

### Install Apps Via Homebrew Cask


```sh
# Install Fonts
brew tap homebrew/cask-fonts
brew install font-hack-nerd-font

# iTermocil
brew install TomAnthony/brews/itermocil

# Yabai
brew install koekeishiya/formulae/yabai

# shkd
brew install koekeishiya/formulae/skhd

# Shopify
brew tap shopify/shopify
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

* https://marko.tech
* * https://marko.tech/uses
* https://startyparty.dev
* * https://marketingstartyparty.dev
* https://github.com/arbitrarily
* https://c.im/@des

Sourced from all over and throughout the years.
