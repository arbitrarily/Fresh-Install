# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

Quote time:

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw

## Version
>
> `1.9.2`

Last Tested on `MacOS 15.1`

## App Store Applications

* [Xcode](https://apps.apple.com/us/app/xcode/id497799835)
  * `sudo xcodebuild -license accept`

## Third Party Applications

* [GPT4All](https://gpt4all.io/index.html)
* [Hyperkey](https://hyperkey.app/) Convert the caps lock key or any modifier key to the hyper key, all four modifiers combined: ⌃⌥⌘⇧ The hyper key acts as an additional modifier key that you can use in any app with keyboard shortcuts.
* [Raycast](https://www.raycast.com/) A collection of powerful productivity tools all within an extendable launcher. Fast, ergonomic and reliable. I install this with [Homebrew](https://formulae.brew.sh/cask/raycast), just wanted to highlight it here.
* [StartyParty](https://marketing.startyparty.dev/) for firefox, made by me
* [StartyParty Addons](https://github.com/arbitrarily/startyparty-addons)

## Dotfiles

Majority of configurations are stored in my [dotfiles](https://github.com/arbitrarily/dotfiles) repository; currently a **private** repository.

* [`Dotfiles`](https://github.com/arbitrarily/dotfiles) github.com/arbitrarily/dotfiles

## Non Dotfile Settings & Configs

* [`Firefox CSS`](https://github.com/arbitrarily/firefox-css) github.com/arbitrarily/firefox-css
* [`cmus Theme`](https://github.com/arbitrarily/cmus-theme) github.com/arbitrarily/cmus-theme

## Fonts

Fonts are Backed up to **/Dropbox/Resources**

* [`Nerd Fonts`](https://github.com/ryanoasis/nerd-fonts) github.com/ryanoasis/nerd-fonts

## zsh

```sh
# Install Oh-My-zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Set Up SSH Keys

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

## Set Up Git

```sh
git config --global user.name "Name"
git config --global user.email email@email.com
git config --global github.user user_name_here
git config --global github.token your_token_here
git config -l --global
git config --global core.editor "code ."
git config --global color.ui true
```

`.gitconfig` is contained within the [dotfiles](https://github.com/arbitrarily/dotfiles) repository and contains further **Git** configurations.

## Set Hostname

```sh
sudo scutil --set HostName ###
```

## Set Up Mac OS Preferences

Commands to customize Mac OS settings and preferences. Pick and choose what you want to change, make sure to run the `killall Finder Dock SystemUIServer` command after changing any settings.

### Finder

```sh
# Show hidden files in Finder
defaults write com.apple.finder AppleShowAllFiles YES

# Show the ~/Library folder
chflags nohidden ~/Library

# Finder: show all filename extensions
defaults write NSGlobalDomain AppleShowAllExtensions -bool true

# Finder: show status bar
defaults write com.apple.finder ShowStatusBar -bool true

# Finder: show path bar
defaults write com.apple.finder ShowPathbar -bool true

# When performing a search, search the current folder by default
defaults write com.apple.finder FXDefaultSearchScope -string "SCcf"
```

### Global

```sh
# Set a fast keyboard repeat rate
defaults write NSGlobalDomain KeyRepeat -int 0

# Set a shorter delay until key repeat
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Store screenshots in subfolder on desktop
mkdir ~/Screenshots
defaults write com.apple.screencapture location ~/Screenshots
killall SystemUIServer

# Skip Verify Images
defaults write com.apple.frameworks.diskimages skip-verify true

# Prevent Apple Character Press and Hold
defaults write -g ApplePressAndHoldEnabled -bool false

# Enable Text Selection in QuickLook
defaults write com.apple.finder QLEnableTextSelection -bool TRUE

# Disable the warning before emptying the Trash
defaults write com.apple.finder WarnOnEmptyTrash -bool false

# Disable shadow in screenshots
defaults write com.apple.screencapture disable-shadow -bool TRUE
```

### Dock

```sh

# Remove Animations
defaults write NSGlobalDomain NSWindowResizeTime -float 0.001

# Hide the Desktop
defaults write com.apple.finder CreateDesktop false

# Set the size of the icons on the dock
defaults write com.apple.dock tilesize -int 54

# Clear out the dock of default icons
defaults delete com.apple.dock persistent-apps
defaults delete com.apple.dock persistent-others

# Faster Dock Animation
defaults write com.apple.dock autohide-time-modifier -float 0.15

# Dull Hidden Apps in Dock
defaults write com.apple.Dock showhidden -bool TRUE

# Make Dock only Show Active Apps
defaults write com.apple.dock static-only -bool true

# Automatically hide and show the Dock
defaults write com.apple.dock autohide -bool true

# Don’t show recent applications in Dock
defaults write com.apple.dock show-recents -bool false

# Dont' show indicator lights for open applications in the Dock
defaults write com.apple.dock show-process-indicators -bool false
```

### Dashboard & Spaces

```sh

# Add a contextual menu item to show the Web Inspector in web views
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# Don’t show Dashboard as a Space
defaults write com.apple.dock dashboard-in-overlay -bool true

# Automatically rearrange Spaces based on most recent use FALSE
defaults write com.apple.dock mru-spaces -bool false

# Disable Dashboard
defaults write com.apple.dashboard mcx-disabled -bool true
```

### Login Screen

```sh
# Add Message to Login Screen
sudo defaults write /Library/Preferences/com.apple.loginwindow LoginwindowText "In found, please call ###-###-####"

```

### Siri

```sh

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

---

```sh
# Just in Case: Revert Dock to Default
defaults write com.apple.dock static-only -bool false
```

```sh
# Restart Finder, Dock, and SystemUIServer
killall Finder Dock SystemUIServer

```

---

## Install Xcode

* [https://itunes.apple.com/au/app/xcode/id497799835?mt=12](itunes.apple.com/au/app/xcode/id497799835?mt=12)

```sh
xcode-select --install
```

## Install Homebrew

* [https://brew.sh/](https://brew.sh/)

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## Install Apps Via Homebrew Cask

```sh
# Install Fonts
brew tap homebrew/cask-fonts
brew install font-hack-nerd-font

# shkd
brew install koekeishiya/formulae/skhd
```

```sh
# List Installed Extensions
code --list-extensions | xargs -L 1 echo code --install-extension
```

---

### Marko Bajlovic

* <https://marko.tech>
* * <https://marko.tech/uses>

<small>Sourced from all over and throughout the years.</small>
