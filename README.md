# macbook-settings

## oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## ~/.zprofile
Added below into ~/.zprofile

```
# Homebrew
eval "$(/opt/homebrew/bin/brew shellenv)"

# alias
alias ll='ls -l'
alias gs='git status'
```

## Enable continuous movement by holding down the button
Type below on Iterm2.

```
defaults write -g ApplePressAndHoldEnabled -bool false
```

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

Added below into ~/.zprofile

```
zinit light asdf-vm/asdf
fpath=(${ASDF_DIR}/completions $fpath)
autoload -Uz compinit && compinit
```

### ~/.zprofile

```sh
### Added by Zinit's installer
if [[ ! -f $HOME/.local/share/zinit/zinit.git/zinit.zsh ]]; then
    print -P "%F{33} %F{220}Installing %F{33}ZDHARMA-CONTINUUM%F{220} Initiative Plugin Manager (%F{33}zdharma-continuum/zinit%F{220})…%f"
    command mkdir -p "$HOME/.local/share/zinit" && command chmod g-rwX "$HOME/.local/share/zinit"
    command git clone https://github.com/zdharma-continuum/zinit "$HOME/.local/share/zinit/zinit.git" && \
        print -P "%F{33} %F{34}Installation successful.%f%b" || \
        print -P "%F{160} The clone has failed.%f%b"
fi

source "$HOME/.local/share/zinit/zinit.git/zinit.zsh"
autoload -Uz _zinit
(( ${+_comps} )) && _comps[zinit]=_zinit
### End of Zinit's installer chunk

zinit light asdf-vm/asdf
fpath=(${ASDF_DIR}/completions $fpath)
autoload -Uz compinit && compinit
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

~/.zprofile

```
export PATH=$HOME/.asdf/installs/golang/1.22.4/packages/bin:$PATH
```



## Intellij for golang
Enable Go modules integration and Enable vendoring support automatically

![intellij-go-module](/images/intellij-go-module.png) 

Disable GOPATH

![intellij-go-path](/images/intellij-go-path.png) 

Tab limit

![inttelij-tablimit](/images/inttelij-tablimit.png) 

