# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw


### Version
1.1.1

### App Store Applications
* CloudApp
* ReadKit
* Sitesucker
* Skitch
* Xcode

### Third Party Applications
* Adobe Illustrator
* Adobe Photoshop
* Balsamiq Mockups
* Bowtie
* Disk Inventory X
* DropBox
* Flow
* Google Chrome
* Growl
* Hands Off!
* Mozilla Firefox
* OnePassword

### Homebrew Cask Applications
* Adium
* Alfred
* Airmail Beta
* Bartender
* BetterTouchTool
* Bartender
* Google Chrome
* iTerm2
* ImageOptim
* MacVim
* Mou
* OnePassword
* Sequel Pro
* SourceTree
* Sublime Text
* The Unarchiver
* Vagrant
* Virtualbox
* VLC

### Sublime Text Preferences
```sh
{
	"auto_complete": true,
	"auto_complete_commit_on_tab": true,
	"auto_complete_with_fields": true,
	"bold_folder_labels": true,
	"caret_style": "phase",
	"close_windows_when_empty": true,
	"color_scheme": "Packages/Monokai Extended/Monokai Extended.tmTheme",
	"detect_indentation": true,
	"fade_fold_buttons": true,
	"folder_exclude_patterns":
	[
		".svn",
		".git",
		".hg",
		"CVS",
		"tmp",
		".bundle",
		".sass-cache"
	],
	"font_size": 12.0,
	"gutter": true,
	"highlight_line": true,
	"highlight_modified_tabs": true,
	"ignored_packages":
	[
		"Vintage"
	],
	"line_padding_bottom": 1,
	"line_padding_top": 1,
	"soda_classic_tabs": false,
	"soda_folder_icons": false,
	"theme": "Spacegray Eighties.sublime-theme",
	"trim_trailing_white_space_on_save": true,
	"use_tab_stops": true,
	"word_wrap": true
}
```

### Fonts
Fonts are Backed up to Dropbox/Resources/Fonts

### Google Chrome Plugins
Plugins to install:
* [Adblock Plus](https://chrome.google.com/webstore/detail/adblock-plus/cfhdojbkjhnklbpkdaibdccddilifddb)
* [Google Drive](https://chrome.google.com/webstore/detail/google-drive/apdfllckaahabafndbhieahigkjlhalf)
* [Hover Zoom](https://chrome.google.com/webstore/detail/hover-zoom/nonjdcjchghhkdoolnlbekcfllmednbl)
* [Instapaper](https://chrome.google.com/webstore/detail/instapaper/ldjkgaaoikpmhmkelcgkgacicjfbofhh)
* [JSONView](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc)
* [Postman REST Client](https://chrome.google.com/webstore/detail/postman-rest-client/fdmmgilgnpjigdojojpjoooidkmcomcm)
* [Post To Tumblr](https://chrome.google.com/webstore/detail/post-to-tumblr/dbpicbbcpanckagpdjflgojlknomoiah)
* [Web Developer](https://chrome.google.com/webstore/detail/web-developer/bfbameneiokkgbdmiekhjnmfkcnldhhm)

### Sublime Text Plugins
Plugins to install:
* Alignment
* Color Highlighter
* GitGutter
* HTML-CSS-JS Prettify
* Monokai Extended
* Sass
* SassBeautify
* SidebarEnhancements
* Theme - Spacegray Eighties

### Configure Sublime Text Command Line
```sh
mkdir -p ~/bin && ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" ~/bin/subl
```

### Sublime Text 3 Plugin Installer
Hit Control + ` to access Console.
```sh
import urllib.request,os,hashlib; h = '7183a2d3e96f11eeadd761d777e62404' + 'e330c659d4bb41d3bdf022e94cab3cd0'; pf = 'Package Control.sublime-package'; ipp = sublime.installed_packages_path(); urllib.request.install_opener( urllib.request.build_opener( urllib.request.ProxyHandler()) ); by = urllib.request.urlopen( 'http://packagecontrol.io/' + pf.replace(' ', '%20')).read(); dh = hashlib.sha256(by).hexdigest(); print('Error validating download (got %s instead of %s), please try manual install' % (dh, h)) if dh != h else open(os.path.join( ipp, pf), 'wb' ).write(by)
```

### Set Up SSH Keys
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
sudo scutil --set HostName CakesMini
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

### Install Apps Via Homebrew Cask
```sh
# Install
brew install caskroom/cask/brew-cask

# Common Apps
brew install ack autojump automake colordiff curl git git-flow hub icoutils imagemagick libmemcached memcached openssl ossp-uuid qt readline redis tmux wget libxml2

brew cask install adium
brew cask install alfred
brew cask install appcleaner
brew cask install bartender
brew cask install bettertouchtool
brew cask install google-drive
brew cask install imageoptim
brew cask install iterm2
brew cask install macvim
brew cask install mou
brew cask install sequel-pro
brew cask install sourcetree
brew cask install sublime-text
brew cask install the-unarchiver
brew cask install vagrant
brew cask install virtualbox
brew cask install vlc

# Install Quick Look Plugins (preview code etc)
brew cask install qlcolorcode qlstephen qlmarkdown quicklook-json qlprettypatch quicklook-csv betterzipql webp-quicklook suspicious-package && qlmanage -r
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

### Install MongoDB
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

### Install Python pip
https://pip.pypa.io/en/latest/installing.html
```sh


```

### Configure Bash & Shortcuts
```sh
#alias for sublime
alias subl='/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl'

alias lexi='cd /Users/arbitrarily/Git/lexichronic-three/'
alias lexisass='cd /Users/arbitrarily/Git/lexichronic-three/wp-content/themes/lexichronic/grunt/'
alias f35='cd /Users/arbitrarily/Git/f35-elitedaily/'
alias f35sass='cd /Users/arbitrarily/Git/f35-elitedaily/f35elitedaily/wordpress/wp-content/themes/strangelove/source/src/'
alias eat='cd /Users/arbitrarily/Git/willmcavoy/public'
alias eatsass='cd /Users/arbitrarily/Git/willmcavoy/public/wp-content/themes/newsroom/source/'

export PATH=/usr/local/bin:$PATH

if [[ $COLORTERM = gnome-* && $TERM = xterm ]] && infocmp gnome-256color >/dev/null 2>&1; then
        export TERM=gnome-256color
elif infocmp xterm-256color >/dev/null 2>&1; then
        export TERM=xterm-256color
fi

if tput setaf 1 &> /dev/null; then
        tput sgr0
        if [[ $(tput colors) -ge 256 ]] 2>/dev/null; then
                MAGENTA=$(tput setaf 9)
                ORANGE=$(tput setaf 172)
                GREEN=$(tput setaf 190)
                PURPLE=$(tput setaf 141)
                WHITE=$(tput setaf 7)
        else
                MAGENTA=$(tput setaf 5)
                ORANGE=$(tput setaf 4)
                GREEN=$(tput setaf 2)
                PURPLE=$(tput setaf 1)
                WHITE=$(tput setaf 7)
        fi
        BOLD=$(tput bold)
        RESET=$(tput sgr0)
else
        MAGENTA="\033[1;31m"
        ORANGE="\033[1;33m"
        GREEN="\033[1;32m"
        PURPLE="\033[1;35m"
        WHITE="\033[1;37m"
        BOLD=""
        RESET="\033[m"
fi

export MAGENTA
export ORANGE
export GREEN
export PURPLE
export WHITE
export BOLD
export RESET

function parse_git_dirty() {
        [[ $(git status 2> /dev/null | tail -n1) != *"working directory clean"* ]] && echo "*"
}

function parse_git_branch() {
        git branch --no-color 2> /dev/null | sed -e '/^[^*]/d' -e "s/* \(.*\)/\1$(parse_git_dirty)/"
}

export PS1="\[${BOLD}${MAGENTA}\]\u \[$WHITE\]$WHITE\]in \[$GREEN\]\w\[$WHITE\]\$([[ -n \$(git branch 2> /dev/null) ]] && echo \" on \")\[$PURPLE\]\$(parse_git_branch)\[$WHITE\]\n\$ \[$RESET\]"
export PS2="\[$ORANGE\]→ \[$RESET\]"

export PATH=/bin:/sbin:/usr/bin:/usr/local/sbin:/usr/local/bin:$PATH

# For those used to subl -w
export EDITOR='subl -w'

# For me
export EDITOR='subl .'
```

[Marko Bajlovic]:http://markobajlovic.com/


Sourced from all over.
