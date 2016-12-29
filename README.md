# super-mario
Super new Mac setup scripts

# macOS Sierra v. 10.12 Setup 

*12/29/16*

[Cloned :)](https://www.taniarascia.com/setting-up-a-brand-new-mac-for-development/)

## Preferences

- **Keyboard > Text >** Disable "Correct spelling automatically".
- **Security and Privacy > Firewall >** On
- **Security and Privacy > General >** App Store and identified developers
- **File Sharing >** Off
- **Users & Groups > Login Items >** Flux

### Show Library folder

```shell
chflags nohidden ~/Library
```

### Show hidden files

```shell
defaults write com.apple.finder AppleShowAllFiles YES
```

### Show path bar

```shell
defaults write com.apple.finder ShowPathbar -bool true
```

### Show status bar

```shell
defaults write com.apple.finder ShowStatusBar -bool true
```

## Homebrew

```shell
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Mac App Store

```shell
brew install mas
```

#### Sign in

```shell
mas signin email@email.com
```

### Brewfile

```shell
touch Brewfile
```

```shell
tap 'caskroom/cask'

brew 'ack'
brew 'git'
brew 'mongodb'
brew 'mysql'
brew 'node'
brew 'npm'
brew 'vim'

cask 'atom'
cask 'coda'
cask 'dropbox'
cask 'flux'
cask 'firefox'
cask 'gimp'
cask 'google-chrome'
cask 'google-chrome-canary'
cask 'imageoptim'
cask 'imagealpha'
cask 'iterm2'
cask 'opera'
cask 'postman'
cask 'robomongo'
cask 'sequel-pro'
cask 'slack'
cask 'torbrowser'
cask 'transmission'
cask 'vagrant'
cask 'virtualbox'
cask 'vlc'

# mas 'Slack', id: 803453959
```

## GitHub

### Config - `~/.gitconfig`


```shell
[user]
	name = First Last
	email = email@email.com
[github]
	user = username
[alias]
	a = add
	ca = commit -a
	cam = commit -am
	s = status
	pom = push origin master
	pog = push origin gh-pages
	puom = pull origin master
	puog = pull origin gh-pages
	cob = checkout -b
[credential]
	helper = osxkeychain
```


## SSH

### Config - `~./ssh/config`

```shell
Host example
    HostName example.com
    User example-user
    IdentityFile key.pem
```

### Generate SSH key

```shell
ssh-keygen -t rsa -b 4096 -C "email@email.com"
```

## Bash (ohmyzsh)

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

### Config - `~/.zshrc`

```shell
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
```

```shell
source ~/.zshrc
```

## Node Package Manager

### Gulp

```shell
npm install yarn
yarn global add babel-cli
yarn global add bower
yarn global add create-react-app
yarn global add gulp-cli
yarn global add nodemon
yarn global add react
yarn global add webpack
yarn global add yo
```
