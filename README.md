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

- Show Hidden Files
```bash
$ defaults write com.apple.finder AppleShowAllFiles YES
```

- Clear .DS_Store files

```bash
$ sudo find / -name .DS_Store -delete; killall Finder
```

## Apps

- Install xCode from App Store
- Disable Gatekeeper

```bash
$ sudo spctl --master-disable
```

- Install xCode Terminal Tools

```bash
$ xcode-select --install
```

- Accept xCode License

```bash
$ sudo xcodebuild -license accept
```

```bash
# Homebrew
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

```bash
# Firefox, Firefox Developer, Dropbox, Google Drive, SequelPro, VsCode, Docker, Postman, Insomnia, Keka, 1Password, Filezilla, AppCleaner, Ccleaner, Caffeine, iStatesMenu, Duet, Spotify, Calibre, Handbrake, mpegStreamclip, Skype, Telegram, Slack, Whatsapp, Discord
$ curl -s 'https://api.macapps.link/pt/firefox-firefoxdev-chrome-dropbox-drive-github-sequelpro-vscode-docker-postman-insomnia-keka-1password-filezilla-appcleaner-ccleaner-caffeine-istatmenus-duet-spotify-calibre-handbrake-mpegstreamclip-skype-telegram-slack-whatsapp-discord' | sh
```

- [MTMR](https://github.com/Toxblh/MTMR)
MacBook Pro TouchBar Only

```bash
$ brew cask install mtmr
```

Após instalado, para instalar a configuração, copie o conteúdo do arquivo (/mtmr/profile.json), clique no ícone do MTMR que irá aparecer na barra do topo do Mac, clique em `Preferences`, cole o conteúdo, salve, e reinicie o aplicativo.

- [Lazy Docker](https://github.com/jesseduffield/lazydocker#installation)

```bash
$ brew install jesseduffield/lazydocker/lazydocker
```

## Git

- Install

```bash
# Git, Git Large File System, Git Flow
$ brew install git-lfs git-flow
```

- Set the configuration file

```bash
$ cp -r $(pwd)/git/gitconfig $HOME/.gitconfig
```

Após executar este comando, entre no arquivo e configure ele de acordo com os seus dados de usuário do GitHub

## Fonts

```bash
# Nerd Fonts
$ brew tap homebrew/cask-fonts
$ brew cask install font-hack-nerd-font
```

- Copy Fonts

```bash
$ cp -r "$(pwd)/fonts/"* ~/Library/Fonts
```

## NVM

```bash
# NVM
$ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

## Yarn

```bash
# Yarn
$ curl -o- -L https://yarnpkg.com/install.sh | bash
```


## SSH

```bash
$ cp -r $(pwd)/ssh/config $HOME/.ssh/config
```

## ZSH

- Install

```bash
# Oh My ZSH
$ sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

- Set the configuration file

```bash
$ cp -r $(pwd)/zsh/zshrc $HOME/.zshrc
```

Apos executar este comando, abra o arquivo e altere os dados de acordo com os dados de usuário do seu Mac

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
$ cp -r $(pwd)/zsh/p10k $HOME/.p10k.zsh
```

## Terminal

- Set the configuration file

```bash
$ cp -r $(pwd)/bash/bash_alias $HOME/.bash_alias
$ cp -r $(pwd)/bash/bash_profile $HOME/.bash_profile
$ cp -r $(pwd)/bash/bashrc $HOME/.bashrc
$ cp -r $(pwd)/bash/profile $HOME/.profile
```

Atenção, pois dentro do arquivo `.bash_profile` há apontamentos para os arquivos do SDK do ANDROID e do Gradle, caso seja feito a instalação de uma versão mais nova, você deve fazer a alteração do apontamento para a versão correta.

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
$ brew install flutter
$ brew cask install cocoapods
```

- Check for errors with Flutter doctor

```bash
$ flutter doctor
```
