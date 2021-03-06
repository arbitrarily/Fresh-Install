# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

Quote time:

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw

### Version
1.5.1

### Last Tested on
MacOS 10.15.5

### App Store Applications
* [Apple Music](https://music.apple.com)
* [ColorSlurp](https://apps.apple.com/us/app/colorslurp/id1287239339)
* [NepTunes](https://apps.apple.com/us/app/neptunes-for-lastfm/id1006739057)
* [Quiver](https://apps.apple.com/us/app/quiver-take-better-notes/id866773894)
* [Toothfairy](https://apps.apple.com/us/app/toothfairy/id1191449274)
* [Tweetbot](https://tapbots.com/tweetbot/mac/)
* [Xcode](https://apps.apple.com/us/app/xcode/id497799835)

### Third Party Applications
* [Adobe Acrobat](https://www.adobe.com/creativecloud.html)
* [Adobe Illustrator](https://www.adobe.com/creativecloud.html)
* [Adobe Photoshop](https://www.adobe.com/creativecloud.html)
* [Adobe Dimension](https://www.adobe.com/creativecloud.html)
* [Adobe Aftereffects](https://www.adobe.com/creativecloud.html)
* [Backup & Sync from Google](https://www.google.com/intl/en_fj/drive/download/)
* Docker

### Homebrew Cask Applications
* 1Password
* Alfred 3
* Bartender
* BetterTouchTool
* Blender
* CleanMyMac
* Dropbox
* Figma
* Firefox Developer Edition
* IconJar
* iTerm2
* ImageOptim
* Kaleidoscope (may replace with Sublime Merge)
* Kodi
* Little Snitch
* Postman
* Querious
* Slack
* Steam
* Sublime Text
* Sublime Merge
* The Unarchiver
* Thunderbird
* Tower
* Transmit
* Ungoogled Chromium
* VLC

### .vimrc
* https://github.com/arbitrarily/vimrc

### .zshrc (primary)
* https://github.com/arbitrarily/zshrc

### .bash_profile
* https://github.com/arbitrarily/bash_profile

### Sublime Text Preferences
* https://github.com/arbitrarily/sublime-settings

### Yabai
* https://github.com/arbitrarily/yabairc

### cmus Theme
* https://github.com/arbitrarily/cmus-theme

### Neofetch Settings
* https://github.com/arbitrarily/neofetch-settings

### Nowplaying
* https://github.com/arbitrarily/nowplaying

### Thunderbird Theme
* https://github.com/arbitrarily/monterail-fulldark

### Fonts
Fonts are Backed up to Dropbox/Resources/

### Configure Sublime Text Command Line
```sh
mkdir -p ~/bin && ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl
```

### zsh
```sh
# sudo apt-get install zsh
brew install zsh
sh -c "$(c
* DaisyDiskurl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Make Default Shell
chsh -s $(which zsh)

# Install Oh-My-zsh
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Install Oh My ZSH Plugins
curl -L https://iterm2.com/shell_integration/zsh \
-o ~/.iterm2_shell_integration.zsh

git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

### Sublime Text 3 Plugin Installer

Just hit **Command + Shift + P** then hit install `Package Control` and we're set to install plugins again.

### Sublime Text Plugins
Plugins to install via Package Control:
* A File Icon
* Alignment
* All Autocomplete
* AutoFileName
* AutoSetSyntax
* Babel
* Better JavaScript
* BracketHighlighter
* Color Highlighter
* Dockerfile Syntax Highlighting
* DotENV
* EditorConfig
* File Icons Mono
* GitGutter
* GitOpenChangedFiles
* HTML-CSS-JS Prettify
* Liquid
* Monokai Extended
* nginx
* Pane Pane
* Pretty JSON
* Sass
* SassBeautify
* SidebarEnhancement
* Theme - Spacegray

### iTerm Colors
* https://github.com/mbadolato/iTerm2-Color-Schemes

### Set Up SSH Keys
* https://confluence.atlassian.com/display/BITBUCKET/Set+up+SSH+for+Git
* https://help.github.com/articles/generating-ssh-keys/

```sh
# check if installed
ls -al ~/.ssh

# Actually generate it
ssh-keygen -t rsa -C "your_email@example.com"

# Copy
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
git config --global core.editor "subl ."
git config --global color.ui true
```

### Set Hostname
```sh
sudo scutil --set HostName ###

```

### Set Up Mac OS X Preferences
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
mkdir ~/Documents/Screenshots
defaults write com.apple.screencapture location ~/Screenshots
killall SystemUIServer

# Add Message to Login Screen
sudo defaults write /Library/Preferences/com.apple.loginwindow LoginwindowText "In case of loss, please call ###-###-####"

# Make Sublime Default Text Editor
defaults write com.apple.LaunchServices LSHandlers -array-add '{LSHandlerContentType=public.plain-text;LSHandlerRoleAll=com.sublimetext.3;}'

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

# Recents & Favorites in Dock (Favorite Items & Recent Docs)
defaults write com.apple.dock persistent-others -array-add '{ "tile-data" = { "list-type" = 1; }; "tile-type" = "recents-tile"; }'; killall Dock
defaults write com.apple.dock persistent-others -array-add '{ "tile-data" = { "list-type" = 1; }; "tile-type" = "recents-tile"; }'; killall Dock

# Just in Case: Revert Dock to Default
defaults write com.apple.dock static-only -bool false; killall Dock

```

### Install Xcode
* https://itunes.apple.com/au/app/xcode/id497799835?mt=12
```sh
xcode-select --install
```

### Install Homebrew
```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew doctor

# Install Cask Fonts
brew tap caskroom/fonts
```

### Install Python 3
```sh
http://python-guide-pt-br.readthedocs.io/en/latest/starting/install3/osx/

brew install python3
# python3 for python3 command line

# Common Programs
brew install ack autojump automake bash-completion bat bower colordiff cmus cmusfm curl exa fd ffmpeg gifsicle git git-flow googler hub httpie icoutils imagemagick itermocil jq libmemcached libxml2 memcached neofetch openssl ossp-uuid qt readline redis ripgrep terminal-notifier themekit tmux watch wget wp-cli yabai yarn youtube-dl z
```

### Install PHP from Homebrew
```sh
https://medium.com/zenchef-tech-and-product/how-to-upgrade-your-version-of-php-to-7-0-on-macos-sierra-e1bfdea55a63

brew update && brew upgrade
brew untap homebrew/php
brew tap homebrew/dupes
brew tap homebrew/versions
brew tap homebrew/homebrew-php
# brew unlink php56 (this is redundant now)
brew install php
brew cleanup
brew doctor

export PATH=”$(brew — prefix homebrew/php/php7X)/bin:$PATH”

```

Just remember to change the `X` in the PHP version in the last export line to whatever the latest one you're using is.

### Install Apps Via Homebrew Cask

```sh
# Install Brew Cask
brew cask
brew tap homebrew/cask-versions

# Install Fonts
brew tap homebrew/cask-fonts
brew cask install font-hack-nerd-font

# iTermocil
brew install TomAnthony/brews/itermocil

# Yabai
brew install koekeishiya/formulae/yabai

# Shopify Themekit
brew tap shopify/shopify

# Cask Applications
brew cask install 1password alfred arduino bartender bettertouchtool blender cleanmymac discord dropbox eloston-chromium figma firefox-developer-edition font-hack-nerd-font iterm2 imageoptim kaleidoscope little-snitch poedit postman querious robo-3t sketch slack steam sublime-text sublime-merge the-unarchiver thunderbird tower vlc vox

# Install Quick Look Plugins (preview code etc)
brew cask install qlcolorcode qlstephen qlmarkdown quicklook-json qlprettypatch quicklook-csv betterzipql webp-quicklook suspicious-package && qlmanage -r
```

### Install Docker
* https://docs.docker.com/docker-for-mac/install/#download-docker-for-mac
* https://docs.docker.com/compose/install/

### Alfred Cask Link
```sh
brew cask alfred link

```

### Install MySQL
```sh
# Install
brew install mysql

# Check & Start
mysql.server start

# If Installation Failed
brew remove mysql
brew cleanup
sudo rm -rf /usr/local/var/mysql/
brew install mysql
mysql.server start

# Check MySQL Info
brew info mysql

```

### Install MongoDB
* http://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/
```sh
brew install mongodb

```

### Install Ruby Gem
* https://rubygems.org/pages/download
```sh
gem update --system
gem install rubygems-update
update_rubygems

# Install Gems
gem install compass
gem install foundation
gem install sass
gem install istats

```

### NPM Stuff
```sh
# Install NPM Packages
npm install -g eslint eslint-cli eslint-plugin-prettier gatsby-cli grunt-cli gulp-cli is-up-cli prettier vtop surge fkill-cli json
```

### Install PEAR/PECL
* http://jason.pureconcepts.net/2012/10/install-pear-pecl-mac-os-x/
```sh

curl -O http://pear.php.net/go-pear.phar
sudo php -d detect_unicode=0 go-pear.phar

# Type 1 and press return.
# Enter:

/usr/local/pear

# Type 4 and press return.
# Enter:

/usr/local/bin

# Press return

pear version

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

Sourced from all over and throughout the years.
