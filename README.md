# MacOS - Development setup for new Notebooks and Desktops

This are the configurations I need to setup a new MacOS development environment in a new machine.

## Install

This installation guide is divided with the tools you use to make it easier for others to customize them, the list of tools you use is as follows:

- [Apps](#apps)
- [Git](#git)
- [Fonts](#fonts)
- [Yarn](#yarn)
- [NVM](#nvm)
- [SSH](#ssh)
- [ZSH](#zsh)
- [Terminal](#terminal)
- [AWS](#aws)
- [Android](#android)

## Apps

```bash
$ curl -s 'https://api.macapps.link/pt/firefox-firefoxdev-chrome-dropbox-drive-github-sequelpro-vscode-docker-postman-insomnia-keka-1password-filezilla-appcleaner-ccleaner-caffeine-istatmenus-duet-spotify-calibre-handbrake-mpegstreamclip-skype-telegram-slack-whatsapp-discord' | sh
$ brew cask install mtmr
```

## Git

- Install

```bash
$ brew install git git-lfs gitflow
```

- Set the configuration file

```bash
$ ln -sv $(pwd)/git/gitconfig.symlink $HOME/.gitconfig
```

## Fonts

```bash
$ brew tap homebrew/cask-fonts
$ brew cask install font-hack-nerd-font
```

- Copy Fonts

```bash
$ cp -r "$(pwd)/fonts/"* ~/Library/Fonts
```

## Yarn

```bash
$ curl -o- -L https://yarnpkg.com/install.sh | bash
```

## NVM

```bash
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

## SSH

```bash
$ ln -sv $(pwd)/ssh/config $HOME/.ssh/config
```

## ZSH

- Install

```bash
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Set the configuration file

```bash
$ ln -sv $(pwd)/zsh/zshrc.symlink $HOME/.zshrc
```

### Plugins

- zsh-autosuggestions

```bash
$ git clone https://github.com/zsh-users/zsh-autosuggestions ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions
```

- zsh-syntax-highlighting

```bash
$ git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting
```

- zsh-async

```bash
$ git clone https://github.com/mafredri/zsh-async ~/.oh-my-zsh/plugins/async
```

- powerlevel10k

```bash
$ git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
$ ln -sv $(pwd)/zsh/p10k.symlink $HOME/.p10k.zsh
```

## Terminal

- Set the configuration file

```bash
$ ln -sv $(pwd)/bash/bash_alias.symlink $HOME/.bash_alias
$ ln -sv $(pwd)/bash/bash_profile.symlink $HOME/.bash_profile
$ ln -sv $(pwd)/bash/bashrc.symlink $HOME/.bashrc
$ ln -sv $(pwd)/bash/bashrc.symlink $HOME/.bashrc
$ ln -sv $(pwd)/bash/profile.symlink $HOME/.profile
```

### Theme

- Terminal > Settings Tab
- Click "Gear" icon
- Click Import...
- Select the materialshell-dark.terminal file
- Click Default

## Aws

- Install

```bash
$ brew install awscli aws-keychain aws-elasticbeanstalk
```

## Android

- Instal JDK

Visit [Oracle JDK Download](https://www.oracle.com/technetwork/java/javase/downloads/index.html) and download the latest JDK

- Install Gradle

```bash
$ brew install gradle imagemagick
```

### Flutter

- Install

```bash
$ brew tap MiderWong/flutter
$ brew cask install flutter
$ brew cask install cocoapods
```

- Check for errors with Flutter doctor

```bash
$ flutter doctor
```
