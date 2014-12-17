# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw


### Version
1.0.4

### App Store Programs
* Airmail
* Balsamiq Mockups
* Better Touch Tool
* CloudApp
* iPassword
* Sitesucker
* The Unarchiver
* Xcode

### Third Party Programs
* Adium
* Adobe Illustrator
* Adobe Photoshop
* Alfred
* Bitnami
* Disk Inventory X
* DropBox
* Flow
* Google Chrome
* Google Drive
* Growl
* Hands Off!
* ImageOptim
* iTerm
* Mozilla Firefox
* Sequel Pro
* Sublime Text
* VirtualBox
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
	"color_scheme": "Packages/User/Monokai (SL).tmTheme",
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

### Sublime Text Plugins
Plugins to install:
* CSSLint
*

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
git config -l --global
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

### Install Ruby gem
https://rubygems.org/pages/download
```sh


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
