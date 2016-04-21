# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

Quote time:

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw


### Version
1.2.6

### App Store Applications
* Airmail
* CloudApp
* Sunrise Calendar
* Tweetbot
* Quiver
* Xcode

### Third Party Applications
* Adobe Illustrator
* Adobe Photoshop
* Balsamiq Mockups
* Bowtie
* Feeds
* Google Chrome Canary

### Homebrew Cask Applications
* Arduino
* Airserver
* Alfred
* AppCleaner
* Bartender
* BetterTouchTool
* CleanMyMac
* Dropbox
* Firefox
* Flux
* Google Chrome
* Grand Perspective
* Hands Off!
* Helium
* iTerm2
* ImageOptim
* Kaleidoscope
* Mou
* OnePassword
* Querious
* Slack
* Sublime Text
* The Unarchiver
* Tower
* Transmit
* VLC
* Vox

### .vimrc
https://github.com/arbitrarily/vimrc

### .zshrc
https://github.com/arbitrarily/zshrc

### .bash_profile
https://github.com/arbitrarily/bash_profile

### Sublime Text Preferences
https://github.com/arbitrarily/sublime-settings

### Fonts
Fonts are Backed up to Dropbox/Resources/Fonts

### Google Chrome Plugins
Plugins are synced to Chrome but in case:
* [Adblock Plus](https://chrome.google.com/webstore/detail/adblock-plus/cfhdojbkjhnklbpkdaibdccddilifddb)
* [Ghostery](https://chrome.google.com/webstore/detail/ghostery/mlomiejdfkolichcflejclcbmpeaniij)
* [Google Art Project](https://chrome.google.com/webstore/detail/google-art-project/akimgimeeoiognljlfchpbkpfbmeapkh)
* [Hover Zoom](https://chrome.google.com/webstore/detail/hover-zoom/nonjdcjchghhkdoolnlbekcfllmednbl)
* [Instapaper](https://chrome.google.com/webstore/detail/instapaper/ldjkgaaoikpmhmkelcgkgacicjfbofhh) 
* [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc)
* [Postman REST Client](https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm)
* [Privacy Badger](https://chrome.google.com/webstore/detail/privacy-badger/pkehgijcmpdhfbdbbnkijodmdjhbjlgp)
* [Web Developer](https://chrome.google.com/webstore/detail/web-developer/bfbameneiokkgbdmiekhjnmfkcnldhhm)


### Configure Sublime Text Command Line
```sh
mkdir -p ~/bin && ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl
```

### zsh 
```sh
# sudo apt-get install zsh
brew install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# Make Default Shell 
chsh -s $(which zsh)
```

### Sublime Text 3 Plugin Installer
Hit Control + ` to access Console.
```sh
import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

### Sublime Text Plugins
Plugins to install via Package Control:
* Alignment
* ApacheConf.tmLanguage
* BracketHighlighter
* Color Highlighter
* EditorConfig
* GitGutter
* HTML-CSS-JS Prettify
* Monokai Extended
* PHP Syntax Checker
* Sass
* SassBeautify
* SidebarEnhancements
* SublimeLinter
* SublimeLinter-csslint
* SublimeLinter-jshint
* SublimeLinter-json
* Theme - Spacegray

### iTerm Colors
https://github.com/mbadolato/iTerm2-Color-Schemes

### Set Up SSH Keys
```
https://confluence.atlassian.com/display/BITBUCKET/Set+up+SSH+for+Git
https://help.github.com/articles/generating-ssh-keys/
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
git config --global github.user arbitrarily
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
defaults write NSGlobalDomain KeyRepeat -int 0.02

# Set a shorter delay until key repeat
defaults write NSGlobalDomain InitialKeyRepeat -int 12

# Add a contextual menu item to show the Web Inspector in web views
defaults write NSGlobalDomain WebKitDeveloperExtras -bool true

# Show the ~/Library folder
chflags nohidden ~/Library

# Store screenshots in subfolder on desktop
mkdir ~/Desktop/Screenshots
defaults write com.apple.screencapture location ~/Desktop/Screenshots
killall SystemUIServer
```

### Install Xcode
https://itunes.apple.com/au/app/xcode/id497799835?mt=12
```sh
xcode-select --install
```

### Install Homebrew
```sh
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"

brew doctor
```

### Install PHP from Homebrew
```sh
https://github.com/Homebrew/homebrew-php

brew tap homebrew/dupes
brew tap homebrew/versions
brew tap homebrew/homebrew-php
brew install php56
brew install php56-mycrypt

```

### Install Apps Via Homebrew Cask

```sh
# Install Brew Cask
brew install caskroom/cask/brew-cask

# Common Programs
brew install ack autojump automake colordiff curl git git-flow hub icoutils imagemagick libmemcached memcached openssl ossp-uuid qt readline redis tmux wget libxml2

# Cask Applications
brew cask install 1password airserver alfred appcleaner arduino bartender bettertouchtool bartender cleanmymac cyberduck dropbox firefox google-chrome grandperspective hands-off helium iterm2 imageoptim kaleidoscope mou querious slack sublime-text the-unarchiver tower vlc vox vox-preference-pane

# Install Quick Look Plugins (preview code etc)
brew cask install qlcolorcode qlstephen qlmarkdown quicklook-json qlprettypatch quicklook-csv betterzipql webp-quicklook suspicious-package && qlmanage -r
```

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
http://docs.mongodb.org/manual/tutorial/install-mongodb-on-os-x/
```sh
brew install mongodb

```

### Install Ruby Gem
https://rubygems.org/pages/download
```sh
gem update --system
gem install rubygems-update
update_rubygems

# Install Gems
gem install compass
gem install foundation
gem install sass

```

### Install PEAR/PECL
http://jason.pureconcepts.net/2012/10/install-pear-pecl-mac-os-x/
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

### Install PHP Mongo
```sh

# Install Mongo
sudo pecl install mongo

sudo cp /etc/php.ini.default /etc/php.ini
sudo chmod 644 /etc/php.ini
echo "extension=mongo.so" >> /etc/php.ini

```

[Marko Bajlovic]:http://markobajlovic.com/

Sourced from all over.
