# MacOS - Development setup for new Notebooks and Desktops

This are the configurations I need to setup a new MacOS development environment in a new machine.

## Install

This installation guide is divided with the tools you use to make it easier for others to customize them, the list of tools you use is as follows:

- [MacOS](#macos)
- [Apps](#apps)
- [Git](#git)
- [Fonts](#fonts)
- [NVM](#nvm)
- [Yarn](#yarn)
- [SSH](#ssh)
- [ZSH](#zsh)
- [Terminal](#terminal)
- [AWS](#aws)
- [Android](#android)

## MacOs

### Intial Setup
- **Dock**
 - Remove most applications from Dock
 - Automatic Hide
 - Smaller Dock
 - Gennie Effect (Gives me that nostalgic feeling)
 - "Show recent applications in Dock" off
 - "Show indicators for open applications" on
- **Display**
 - Nightshift
- Security
 - Touch ID
 - FileVault Enabled
- **Siri**
 - Disable
- **Keyboard**
 - Text
  - Disable "Capitalise word automatically"
  - Disable "Add full stop with double-space"
  - disable "Use smart quotes and dashes"
  - Use `"` for double quotes
  - use `'` for single quotes
- **Mission Control**
 - Hot Corners: disable all
- **Finder**
 - Create a `Developer` folder inside your home folder `~` (It adds a custom icon to the folder)
 - Sidebar:
  - activate all Favorites
  - move Library to Favorites
  - Add Drive and Dropbox to Favorites
  - Add `Developer` folder to Favorites
- Hide all Tags
 - Show all Filename Extensions
 - Remove Items from Bin after 30 Days

### Terminal Settings (Affets Finder and other Applications) 

- Show Hidden Files
```bash
defaults write com.apple.finder AppleShowAllFiles YES; killall Finder;
```

- Clear .DS_Store files
```bash
sudo find / -name .DS_Store -delete; killall Finder
```

- Take screenshots as jpg (usually smaller size) and not png
```bash
defaults write com.apple.screencapture type jpg; killall Finder;
```

- Show Library folder
```bash
chflags nohidden ~/Library; killall Finder;
```

- Show path bar
```bash
defaults write com.apple.finder ShowPathbar -bool true; killall Finder;
```

- Show status bar
```bash
defaults write com.apple.finder ShowStatusBar -bool true; killall Finder;
```

## Applications (GUI & DevTools)

- Install xCode from App Store
- Disable Gatekeeper

```bash
sudo spctl --master-disable
```

- Install xCode Terminal Tools

```bash
xcode-select --install
```

- Accept xCode License

```bash
sudo xcodebuild -license accept
```

- Homebrew
```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

- Update everything in Homebrew
```bash
brew update
```

- Install applications from Homebrew
```bash
brew install --cask \
  firefox \
  google-chrome  \
  brave-browser \
  tor \
  google-drive \
  hyperswitch \
  github \
  sourcetree \
  calibre \
  visual-studio-code \
  docker \
  sequel-pro \
  rectangle \
  postman \
  insomnia \
  keka \
  kekaexternalhelper \
  caffeine \
  spotify \
  handbreak \
  skype \
  telegram \
  whatsapp \
  slack \
  discord \
  vlc \
  maccy \
  imagemagick
```

- Install applications that are not present in Homebrew
```bash
curl -s 'https://api.macapps.link/pt/firefoxdev-dropbox-1password-filezilla-istatmenus' | sh
```

- [MTMR](https://github.com/Toxblh/MTMR)
  MacBook Pro TouchBar Only

```bash
brew install mtmr
```

After installation, copy the content from the file `/mtmr/profile.json`, click in the MTMR icon in the menu bar, and click in `Preferences`, there paste the content, save and restart the application.

- [Lazy Docker](https://github.com/jesseduffield/lazydocker#installation)

```bash
brew install jesseduffield/lazydocker/lazydocker
```

## Git

- Install

```bash
# Git, Git Large File System, Git Flow
brew install git-lfs git-flow
```

- Set the configuration file

```bash
ln -s $(pwd)/git/gitconfig ~/.gitconfig
```

Após executar este comando, entre no arquivo e configure ele de acordo com os seus dados de usuário do GitHub

## Fonts

```bash
# Nerd Fonts
brew tap homebrew/cask-fonts
brew install font-hack-nerd-font
```

- Copy Fonts

```bash
cp -r "$(pwd)/fonts/"* ~/Library/Fonts
```

## NVM

```bash
# NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

## Yarn

```bash
# Yarn
curl -o- -L https://yarnpkg.com/install.sh | bash
```

## SSH

```bash
ln -s $(pwd)/ssh/config ~/.ssh/config
```

## ZSH

- Install

```bash
# Oh My ZSH
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Set the configuration file

```bash
ln -s $(pwd)/zsh/zshrc ~/.zshrc
```

Apos executar este comando, abra o arquivo e altere os dados de acordo com os dados de usuário do seu Mac

### Plugins

- zsh-autosuggestions

```bash
git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
```

- zsh-syntax-highlighting

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

- zsh-async

```bash
git clone https://github.com/mafredri/zsh-async ~/.oh-my-zsh/plugins/async
```

- zsh-nvm

```bash
git clone https://github.com/lukechilds/zsh-nvm ~/.oh-my-zsh/custom/plugins/zsh-nvm
```

- powerlevel10k

```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
ln -s $(pwd)/zsh/p10k ~/.p10k.zsh
```

## Terminal

- Set the configuration file

```bash
ln -s $(pwd)/bash/bash_alias ~/.bash_alias
ln -s $(pwd)/bash/bash_profile ~/.bash_profile
ln -s $(pwd)/bash/bashrc ~/.bashrc
ln -s $(pwd)/bash/profile ~/.profile
ln -s $(pwd)/bash/profile ~/.android
ln -s $(pwd)/bash/profile ~/.flutter
ln -s $(pwd)/bash/profile ~/.nvm-load
```
Attention, because inside the files `.android, .flutter, .nvm-load` there are specific configurations, with version based, please edit the file with the appropriate version before loading those.

### Theme

- Terminal > Settings Tab
- Click "Gear" icon
- Click Import...
- Select the materialshell-dark.terminal file
- Click Default

## Aws

- Install

```bash
brew install awscli aws-keychain aws-elasticbeanstalk
```

## Android

- Instal JDK

Visit [Oracle JDK Download](https://www.oracle.com/technetwork/java/javase/downloads/index.html) and download the latest JDK

- Install Gradle

```bash
brew install gradle
```

### Flutter

- Install

```bash
brew install flutter
brew install cocoapods
```

- Check for errors with Flutter doctor

```bash
flutter doctor
```
