# Marko's Setup

The following is a guide I wrote to guide one through a fresh installation on a new machine. Enjoy!

Quote time:

> “To be in hell is to drift; to be in heaven is to steer.”
― George Bernard Shaw

### Version
1.8.0

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
* `1password7` (1Password) Password manager that keeps all passwords secure behind one password
* `alfred` (Alfred) Application launcher and productivity software
* `anaconda` (Anaconda Distribution) Distribution of the Python and R programming languages for scientific computing
* `apparency` (Apparency) Inspect application bundles
* `appcleaner` (FreeMacSoft AppCleaner) Application uninstaller
* `bartender` (Bartender) Menu bar icon organiser
* `discord` (Discord) Voice and text chat software
* `dropbox` (Dropbox) Client for the Dropbox cloud storage service
* `eloston-chromium` (Ungoogled Chromium) Google Chromium, sans integration with Google
* `figma` (Figma) Collaborative team software
* `firefox` (Mozilla Firefox) Web browser
* `firefox-developer-edition` (Mozilla Firefox Developer Edition) Web browser
* `font-hack-nerd-font` (Hack Nerd Font (Hack)) Developer targeted fonts with a high number of glyphs
* `iconjar` (IconJar) Icon organiser
* `iina` (IINA) Free and open-source media player
* `imageoptim` (ImageOptim) Tool to optimise images to a smaller size
* `insomnia` (Insomnia) HTTP and GraphQL Client
* `iterm2` (iTerm2) Terminal emulator as alternative to Apple's Terminal app
* `little-snitch` (Little Snitch) Host-based application firewall
* `lm-studio` (LM Studio) Discover, download, and run local LLMs
* `mimestream` (Mimestream) Native app email client for Gmail
* `miniforge` (miniforge) Minimal installer for conda specific to conda-forge
* `mongodb-compass` (MongoDB Compass) Interactive tool for analyzing MongoDB data
* `notion` (Notion) App to write, plan, collaborate, and get organised
* `qlcolorcode` (QLColorCode) Quick Look plug-in that renders source code with syntax highlighting
* `qlimagesize` (qlImageSize) Display image info and preview unsupported formats in QuickLook
* `qlmarkdown` (sbarex QLMarkdown) Quick Look generator for Markdown files
* `qlstephen` (QLStephen) Quick Look plugin for plaintext files without an extension
* `qlvideo` (QuickLook Video) Thumbnails, static previews, cover art and metadata for video files
* `querious` (Querious 4) MySQL and compatible databases tool
* `quicklook-json` (quick look JSON) Quick Look plugin for JSON files
* `quicklookase` (QuickLookASE) Quick Look generator for Adobe Swatch Exchange files
* `slack` (Slack) Team communication and collaboration software
* `sublime-merge` (Sublime Merge) Git client
* `supercollider` (SuperCollider) Server, language, and IDE for sound synthesis and algorithmic composition
* `surfshark` (Surfshark) VPN client for secure internet access and private browsing
* `suspicious-package` (Suspicious Package) Application for inspecting installer packages
* `syntax-highlight` (Syntax Highlight) Quicklook extension for source files
* `the-unarchiver` (The Unarchiver) Unpacks archive files
* `transmit` (Transmit) File transfer application
* `visual-studio-code` (Microsoft Visual Studio Code, VS Code) Open-source code editor
* `whatsapp` (WhatsApp) Native desktop client for WhatsApp
* `zed` (Zed) Multiplayer code editor

### DotFiles (mac)
* [`.vimrc`](https://github.com/arbitrarily/vimrc) https://github.com/arbitrarily/vimrc
* [`.gitconfig`](https://github.com/arbitrarily/gitconfig) https://github.com/arbitrarily/gitconfig
* [`.zshrc (primary)`](https://github.com/arbitrarily/zshrc) https://github.com/arbitrarily/zshrc
* [`.yabairc`](https://github.com/arbitrarily/yabairc) https://github.com/arbitrarily/yabairc
* [`.skhdrc`](https://github.com/arbitrarily/skhdrc) https://github.com/arbitrarily/skhdrc
* [`.gitconfig`](https://github.com/arbitrarily/gitconfig/blob/master/.gitconfig)  https://github.com/arbitrarily/gitconfig/blob/master/.gitconfig)

### Settings & Configs
* [`Visual Studio Code Preferences`](https://github.com/arbitrarily/vs-code-settings) https://github.com/arbitrarily/vs-code-settings
* [`Zed Preferences`](https://github.com/arbitrarily/zed-settings) https://github.com/arbitrarily/zed-settings
* [`iTerm Profile`](https://github.com/arbitrarily/iterm-profile) https://github.com/arbitrarily/iterm-profile
* [`Firefox CSS`](https://github.com/arbitrarily/firefox-css) https://github.com/arbitrarily/firefox-css

### Scripts
* [`cmus Theme`](https://github.com/arbitrarily/cmus-theme) https://github.com/arbitrarily/cmus-theme
* [`Nowplaying`](https://github.com/arbitrarily/nowplaying) https://github.com/arbitrarily/nowplaying

### Link Dotfiles
```sh
# zsh
ln -s ~/Git/zshrc/.zshrc ~/.zshrc
# skhdrc
ln -s ~/Git/skhdrc/.skhdrc ~/.skhdrc
# yabairc
ln -s ~/Git/yabairc/.yabairc ~/.yabairc
# vimrc
ln -s ~/Git/vimrc/vimrc ~/.vimrc
# gitconfig
ln -s ~/Git/gitconfig/.gitconfig ~/.gitconfig
```

### Fonts
Fonts are Backed up to **/Dropbox/Resources**

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

# Syntax Highlighting
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

# Auto Complete
git clone --depth 1 -- https://github.com/marlonrichert/zsh-autocomplete.git ~/Git/zsh-autocomplete
```

### Visual Studio Code Plugins
```sh
# List Installed Extensions
code --list-extensions | xargs -L 1 echo code --install-extension

# Install Extensions
* bmewburn.vscode-intelephense-client
* davidanson.vscode-markdownlint
* dbaeumer.vscode-eslint
* dsznajder.es7-react-js-snippets
* eamodio.gitlens
* ecmel.vscode-html-css
* editorconfig.editorconfig
* esbenp.prettier-vscode
* firefox-devtools.vscode-firefox-debug
* formulahendry.auto-close-tag
* formulahendry.auto-complete-tag
* formulahendry.auto-rename-tag
* github.copilot
* github.copilot-chat
* gurumukhi.selected-lines-count
* kamikillerto.vscode-colorize
* kvncnls.monokai-pro-new-kc
* loczek.next-js-ts-snippets
* mrmlnc.vscode-duplicate
* ms-python.debugpy
* ms-python.python
* ms-python.vscode-pylance
* ms-toolsai.jupyter
* ms-toolsai.jupyter-keymap
* ms-toolsai.jupyter-renderers
* ms-toolsai.vscode-jupyter-cell-tags
* ms-toolsai.vscode-jupyter-slideshow
* ms-vscode.sublime-keybindings
* nomicfoundation.hardhat-solidity
* nucllear.vscode-extension-auto-import
* oderwat.indent-rainbow
* shazbot.select-lines
* shd101wyy.markdown-preview-enhanced
* sirmspencer.vscode-autohide
* steoates.autoimport
* vscode-icons-team.vscode-icons
* vue.volar
* zignd.html-css-class-completion
* zobo.php-intellisense

```

### Visual Studio Themes
Theme: `Monokai Pro New KC`
Font: `'Hack Nerd Font', 'Hack', 'Fira Mono', Menlo Bold, Monaco, 'Courier New', monospace`

### Set Up SSH Keys
* https://confluence.atlassian.com/display/BITBUCKET/Set+up+SSH+for+Git
* https://help.github.com/articles/generating-ssh-keys/

```sh
# check if installed
ls -al ~/.ssh

# Actually generate it
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
git config --global core.editor "subl ."
git config --global color.ui true
```

### Set Hostname
```sh
sudo scutil --set HostName ###
```

### Set Up Mac OS X Preferences

Some of these may be out of date, have to go through this list and update it.

```sh

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
* https://itunes.apple.com/au/app/xcode/id497799835?mt=12
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

### NPM Stuff
```sh
# Install NPM Packages
/opt/homebrew/lib
├── addons-linter@6.27.0
├── eslint-cli@1.1.1
├── eslint-plugin-prettier@4.2.1
├── eslint@8.21.0
├── fkill-cli@7.1.0
├── gatsby-cli@4.20.0
├── is-up-cli@4.0.0
├── json@11.0.0
├── npm@10.7.0
├── prettier@2.7.1
├── surge@0.23.1
└── zoom-to-web-link@2.1.1

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
