# super-mario
Super new Mac setup scripts

# macOS Setup 

*12/29/16*

[Cloned :)](https://www.taniarascia.com/setting-up-a-brand-new-mac-for-development/)

## Preferences

- **Siri >** Disable
- **Keyboard >** Key Repeat = Fast; Delay Until Repeat = Short;
- **Keyboard > Text >** Disable "Correct spelling automatically".
- **Security and Privacy > Firewall >** On
- **Security and Privacy > General >** App Store and identified developers
- **File Sharing >** Off
- **Users & Groups > Login Items >** Flux

### Don't Phone Home

[`$ echo 127.0.0.1 ocsp.apple.com | sudo tee -a /etc/hosts`](https://sneak.berlin/20201112/your-computer-isnt-yours/)

### Show Library folder

```$
chflags nohidden ~/Library
```

### Show hidden files

```$
defaults write com.apple.finder AppleShowAllFiles YES
```

### Show path bar

```V
defaults write com.apple.finder ShowPathbar -bool true
```

### Show status bar

```$
defaults write com.apple.finder ShowStatusBar -bool true
```

## Homebrew

```$
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

### Mac App Store

```$
brew install mas
```

#### Sign in

```$
mas signin email@email.com
```

### Brewfile

```$
touch Brewfile
```

```$
tap 'caskroom/cask'

brew 'ack'
brew 'git'
brew 'mongodb'
brew 'mysql'
brew 'node'
brew 'npm'
brew 'wget'
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

mas 'Xcode', id: 497799835
```

#### Execute Brewfile

`$ brew bundle install`

## [GitHub](https://github.com/GitAlias/gitalias)

### Config - `~/.gitconfig`


```$
[user]
	name = First Last
	email = email@email.com
	
[github]
	user = username
	
[alias]
	a = add
	b = branch        
	c = commit    
	ca = commit -a
	cam = commit -am
	s = status
	pom = push origin master
	pog = push origin gh-pages
	puom = pull origin master
	puog = pull origin gh-pages
	cob = checkout -b
	branch-name = rev-parse --abbrev-ref HEAD
        up = !git fetch origin && git pull
        kill = "!f(){ git branch -d $@; git push origin --delete $@; }; f"
        co = checkout
	l = log --graph --oneline
        log-graph = log --graph --all  --decorate --oneline        
	lg = log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit        lg1 = log --graph --abbrev-commit --decorate --date=relative --format=format:'%C(bold blue)%h%C(reset) - %C(bold green)(%ar)%C(reset) %C(white)%s%C(reset) %C(dim white)- %an%C(reset)%C(bold yellow)%d%C(reset)' --all
        lg2 = log --graph --abbrev-commit --decorate --format=format:'%C(bold blue)%h%C(reset) - %C(bold cyan)%aD%C(reset) %C(bold green)(%ar)%C(reset)%C(bold yellow)%d%C(reset)%n''
   %C(white)%s%C(reset) %C(dim white)- %an%C(reset)' --all
   
[credential]
	helper = osxkeychain
	
[color]
  	ui = auto
	
[color "branch"]
  	current = yellow reverse
  	local = yellow
  	remote = green
	
[color "diff"]
  	meta = yellow bold
  	frag = magenta bold
  	old = red bold
  	new = green bold
	
[color "status"]
  	added = yellow
  	changed = green
  	untracked = cyan
```


## SSH

### Config - `~./ssh/config`

```$
Host example
    HostName example.com
    User example-user
    IdentityFile key.pem
```

### Generate SSH key

```$
ssh-keygen -t rsa -b 4096 -C "email@email.com"
```

## Bash (ohmyzsh)

`sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"`

### Config - `~/.zshrc`

```$
source $HOME/.profile
alias brewup='brew update; brew upgrade; brew prune; brew cleanup; brew doctor'
```

```$
source ~/.zshrc
```

## Node Package Manager

### Gulp

```$
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

# VSCode Config

```
{
    "window.zoomLevel": 1,
    "editor.fontSize": 14,
    "editor.tabSize": 2,
    "search.exclude": {
        "**/node_modules": true,
        "**/bower_components": true,
        "**/vendor": true,
    },
    "terminal.integrated.fontSize": 14,
    "workbench.colorTheme": "Abyss",
    "explorer.confirmDelete": false,
    "terminal.integrated.fontFamily": "Monaco",
    "editor.renderWhitespace": "boundary",
    "typescript.experimental.syntaxFolding": true,
    "python.linting.pep8Enabled": true,
}
```
