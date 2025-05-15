# macbook-settings

## oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Enable continuous movement by holding down the button
Type below on Iterm2.

```
defaults write -g ApplePressAndHoldEnabled -bool false
```

## ~/.zprofile
[.zprofile](zprofile)


## github

```
ssh-keygen -t rsa -f esfahan_id_rsa 
```

- Add SSH keys
    - https://github.com/settings/keys

~/.ssh/config

```ini
Host github.com
    User git
    Hostname ssh.github.com
    Port 443
    IdentityFile ~/.ssh/esfahan_id_rsa
```

## Input Sources

![system-keyboard-input_sources](/images/system-keyboard-input_sources.png) 


## karabiner

```
cp karabiner/karabiner.json ~/.config/karabiner
```

```
mkdir ~/.config/karabiner/assets/complex_modifications/
cp karabiner/intellij.json ~/.config/karabiner/assets/complex_modifications/intellij.json
```

Enable the setting for Intellij

![karabiner-complex-modifications](/images/karabiner-complex-modifications.png) 

## iterm2
Specify a path of plist at following.

`General -> Setteing -> Load preferences from a custom folder or URL`

![iterm-load-setting](/images/iterm-load-setting.png) 

keybind

![iterm-keybind](/images/iterm-keybind.png) 

Disable beep

![iterm-beep](/images/iterm-beep.png) 

## zinit
https://github.com/zdharma-continuum/zinit#install

```
bash -c "$(curl --fail --show-error --silent --location https://raw.githubusercontent.com/zdharma-continuum/zinit/HEAD/scripts/install.sh)"
```

```
source ~/.zprofile
```

```
zinit self-update
```


## asdf

```
zinit light asdf-vm/asdf
```

## go
https://github.com/asdf-community/asdf-golang

```
asdf plugin add golang
asdf list all golang
asdf install golang 1.22.4
```

Set version

```
asdf local golang 1.22.4
```

```
asdf current
```

### swag

```
asdf plugin add swag
asdf list-all swag
asdf install swag latest
```

### golangci-lint

```
asdf plugin add "golangci-lint" "https://github.com/kc-workspace/asdf-golangci-lint.git"
```

### golang-migrate

```bash
go install -tags 'mysql' github.com/golang-migrate/migrate/v4/cmd/migrate@v4.15.1

# ~/.asdf/installs/golang/1.22.4/packages/bin/migrate
```

Installed location

```
$HOME/.asdf/installs/golang/1.22.4/packages/bin
```


## Intellij for golang
Enable Go modules integration and Enable vendoring support automatically

![intellij-go-module](/images/intellij-go-module.png) 

Disable GOPATH

![intellij-go-path](/images/intellij-go-path.png) 

Tab limit

![inttelij-tablimit](/images/inttelij-tablimit.png) 


## mysql-cli

```
brew install mysql-client
```

Installed localtion

```
/opt/homebrew/opt/mysql-client/bin/mysql
```

## NodeJS

```
asdf plugin add nodejs
asdf list all nodejs
asdf install nodejs 18.20.4

# Check installed
asdf list nodejs
```

yarn

```
brew install gpg
asdf plugin add yarn https://github.com/twuni/asdf-yarn.git
asdf list all yarn
asdf install yarn 1.22.22

corepack enable
asdf reshim nodejs
```

## vimrc

```ini
autocmd FileType * setlocal formatoptions-=ro
set ambiwidth=double
highlight Comment ctermfg=lightblue
set enc=utf-8
set paste
set hlsearch

set tabstop=2 shiftwidth=2 expandtab

set term=xterm-256color
syntax on
```


## Intellij for Python

Get your python path with poetry

```
$ poetry env info
# Virtualenv -> Executable
```

- Open the Project settings
    - `command + ;`
    - Project settings -> Project -> SDK -> python path with poetry




