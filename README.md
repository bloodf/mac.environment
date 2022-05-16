# MacOS - Development setup for new Notebooks and Desktops

This are the configurations I need to setup a new MacOS development environment in a new machine.

Full Guide - https://dev.to/bloodf/macos-environment-setup-guide-developer-edition-56i
# Initial Setup

After finishing your MacOS initial setup, you will face that default screen with many default Apple apps on the docker, and nothing configured.

Now let's configure the MacOS with the basic settings.

## Settings

These are configurations done in the MacOs settings.

### Dock & Menu Bar

- Remove most applications from Dock
- Automatic Hide
- Medium Dock
- Gennie Effect (Gives me that nostalgic feeling)
- "Double-click a window's title bar to" `zoom`
- Minimize windows into application icon
- Animate opening applications
- "Show recent applications in Dock" off
- "Show indicators for open applications" on
- "Automatically hide and show the menu bar on desktop" off
- "Automatically hide and show the menu bar in full screen" on

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/mt2ipeghm4i0dmk2pwee.png)

### Display

- Nightshift
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/atf8ykvi158lqueuec4t.png)

### Security

- Touch ID
- FileVault Enabled

### Siri

- Disable

### Keyboard

- Text
- Disable "Add full stop with double-space"
- Disable "Use smart quotes and dashes"
- Use `"` for double quotes
- use `'` for single quotes

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/w3o3f4ubd45keiw601fr.png)

### Mission Control

- Hot Corners: disable all
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/x763rm6k6bj2hrdd1nm8.png)

### Finder

- Create a `Developer` folder inside your home folder `~` (It adds a custom icon to the folder)
- Sidebar:
- activate all Favorites
- move Library to Favorites
- Add Drive and Dropbox to Favorites
- Add `Developer` folder to Favorites
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/iubdw3xlz4v1o9pr4rt4.png)

- Hide all Tags
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/fke1msfpu67hr6jc53yx.png)

- Show all Filename Extensions
- Remove Items from Bin after 30 Days

 ![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/bgy7keufnu3lglp5ehwh.png)

## Terminal Settings

_(Affects Finder and other Applications)_

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

# Applications & DevTools

## AppStore

First you need to setup your apple account to be able to use the AppStore, then you will need to download some applications.

- [1Password](https://apps.apple.com/br/app/1password-7-password-manager/id1333542190?l=en&mt=12)

- [Magnet](https://apps.apple.com/br/app/magnet/id441258766?l=en&mt=12) (There is an alternative `rectangle`) -

- [Xcode](https://apps.apple.com/br/app/xcode/id497799835?l=en&mt=12)

> After installing the Xcode, you need to open it for the first time accept some licenses to use it fully.

- Install xCode Terminal Tools

```bash
xcode-select --install
```

- Accept xCode License

```bash
sudo xcodebuild -license accept
```

## Applications (GUI & DevTools)

First we need to disable Gatekeeper in order to use non-Apple signed applications.

```bash
sudo spctl --master-disable
```

- Homebrew

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Now we need to update everything in Homebrew, after the first installation.

```bash
brew update
```

### Homebrew Installation

Here the list is divided into categories so you can know what kind of application you are installing.

#### Browsers

- [Firefox](https://www.mozilla.org/en-US/firefox/new/)
- [Chrome](https://www.google.com/chrome/)
- [Brave](https://brave.com/)
- [Tor](https://brave.com/)

```bash
brew install --cask \
  firefox \
  google-chrome  \
  brave-browser \
  tor \
```

#### Multimedia

- [Calibre](https://calibre-ebook.com/)
- [Spotify](https://www.spotify.com/)
- [Handbreak](https://handbrake.fr/)
- [VLC](https://www.videolan.org/)
- [imagemagick](https://www.imagemagick.org/)

```bash
brew install --cask \
  calibre \
  spotify \
  handbreak \
  vlc \
  imagemagick
```

#### DevTools

- [GitHub DesktopApp](https://desktop.github.com/)
- [Sourcetree DesktopApp](https://www.sourcetreeapp.com/)
- [VSCode](https://code.visualstudio.com/)
- [Docker](https://www.docker.com/)
- [SequelPro](http://sequelpro.com/)
- [Postman](https://www.postman.com/)
- [Insomnia](https://insomnia.rest/)

```bash
brew install --cask \
  github \
  sourcetree \
  visual-studio-code \
  docker \
  sequel-pro \
  postman \
  insomnia \
```

#### Chat & IM

- [Skype](https://www.skype.com/en/)
- [Telegram](https://web.telegram.org/)
- [Whatsapp](https://www.whatsapp.com/)
- [Slack](https://slack.com/)
- [Discord](https://discord.com/)

```bash
brew install --cask \
  skype \
  telegram \
  whatsapp \
  slack \
  discord \
```

#### Utilities

- [HyperSwitch](https://bahoom.com/hyperswitch)
- [Rectangle](https://rectangleapp.com/)
- [Keka](https://www.keka.io/)
- [Caffeine](https://caffeine.en.softonic.com/mac)
- [Maccy](https://maccy.app/)

```bash
brew install --cask \
  hyperswitch \
  rectangle \
  keka \
  kekaexternalhelper \
  caffeine \
  maccy \
```

_For the applications that don't have an install cask present in Homebrew_

- [Firefox Developer Edition](https://www.mozilla.org/en-US/firefox/developer/)
- [Dropbox](https://www.dropbox.com/)
- [Filezilla](https://filezilla-project.org/)
- [iStatsMenus](https://bjango.com/mac/istatmenus/)

```bash
curl -s 'https://api.macapps.link/pt/firefoxdev-dropbox-filezilla-istatmenus' | sh
```

**For the touchbar MacBook only**

- [MTMR](https://github.com/Toxblh/MTMR)

```bash
brew install mtmr
```

> After installation, copy the content from the file `/mtmr/profile.json`, click in the MTMR icon in the menu bar, and click in `Preferences`, there paste the content, save and restart the application.

#### Extra

- [Lazy Docker](https://github.com/jesseduffield/lazydocker#installation)

```bash
brew install jesseduffield/lazydocker/lazydocker
```

# Git

## Git LFS & Flow

- Install

```bash
brew install git-lfs git-flow
```

## Configuring the client

- Set the configuration file

```bash
ln -s $(pwd)/git/gitconfig ~/.gitconfig
```

After executing this commands, configure your Git user settings

```bash
git config --global user.name "Your Name"
git config --global email "you@your-domain.com"
```

### Improving Git Log

You can add more colors to your git log output by executing this command.

```bash
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

## SSH

```bash
ln -s $(pwd)/ssh/config ~/.ssh/config
```

# Terminal & Oh My Zsh

## Fonts

The first step is to install the basic fonts needed in our terminal.

```bash
# Nerd Fonts
brew tap homebrew/cask-fonts
brew install font-hack-nerd-font
```

- Copy Fonts

```bash
cp -r "$(pwd)/fonts/"* ~/Library/Fonts
```

## ZSH

The [oh my Zsh](https://ohmyz.sh/) project is a good terminal add-on to be added in our development environment.

- Install

```bash
# Oh My ZSH
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Set the configuration file

```bash
ln -s $(pwd)/zsh/zshrc ~/.zshrc
```

### Plugins

Here are some plugins that can be used alognside with Oh My Zsh, and make your experience much better.

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
```


```bash
ln -s $(pwd)/zsh/p10k ~/.p10k.zsh
```

- yarn-auto-complete
```bash
git clone https://github.com/g-plane/zsh-yarn-autocompletions ~/.oh-my-zsh/custom/plugins/zsh-yarn-autocompletions
```

## Terminal

To add some new configurations and special tools to the terminal, you can execute the following command to import those.

- Set the configuration file

```bash
ln -s $(pwd)/bash/bash_alias ~/.bash_alias
ln -s $(pwd)/bash/bash_profile ~/.bash_profile
ln -s $(pwd)/bash/bashrc ~/.bashrc
ln -s $(pwd)/bash/android ~/.android
ln -s $(pwd)/bash/flutter ~/.flutter
ln -s $(pwd)/bash/nvm-load ~/.nvm-load
ln -s $(pwd)/bash/yarn-autocompletions.yml ~/.yarn-autocompletions.yml
```

>Attention, because inside the files `.android, .flutter, .nvm-load` there are specific configurations, with version based, please edit the file with the appropriate version before loading those.

### Theme

You can change the Mac Terminal application appearance with some quick steps.

1. Terminal > Settings Tab
2. Click "Gear" icon
3. Click Import...
4. Select the `materialshell-dark.terminal` file
5. Click Default

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/77pu4602w1cusup0rlj1.png)

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gfk6ihhzv4nabghz4z51.png)
  
# Node, NVM, Yarn
## NVM

There is no better way to manage node than using [NVM](https://github.com/nvm-sh/nvm)

```bash
# NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

### Updating NVM

To update NVM to a newer version, you can use this command without losing your globals. Remember to change `<version>` to the version you want installed.

```bash
nvm install <version> --reinstall-packages-from=$(nvm current)
nvm use <version>
nvm alias default <version>
```

## Yarn

I prefer to use Yarn as the package manager, but this is a personal selection.

```bash
# Yarn
curl -o- -L https://yarnpkg.com/install.sh | bash
```

## NPMJS.com

Set the defaults value for your NPM user

```bash
npm set init.author.name "your name"
npm set init.author.email "you@example.com"
npm set init.author.url "example.com"
```

Then login into NPM with

```bash
npm adduser
```

# Extra

## Android

- Instal JDK

Visit [Oracle JDK Download](https://www.oracle.com/technetwork/java/javase/downloads/index.html) and download the latest JDK

- Install Gradle

```bash
brew install gradle
```

## Flutter

- Install

```bash
brew install flutter
brew install cocoapods
```

- Check for errors with Flutter doctor

```bash
flutter doctor
```

## Aws

- Install

```bash
brew install awscli aws-keychain aws-elasticbeanstalk
```
