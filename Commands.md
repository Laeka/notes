# Commands

## Linux::
  - #### WIFI CONFIG
    - ip a : identify network devices
    - nmcli radio WIFI
    - nmcli dev status : network status
    - nmcli dev wifi list : list of available wifi
    - sudo nmcli --ask dev wifi connect <SSID> : connect to the wifi ssid

  - #### Utils
    - locate - whereis : need more info

## zsh::

  - alias zshrc="nvim ~/.zshrc"
  - alias ezsh="exec zsh"
  - alias cnv="cd ~/.config/nvim"
  - alias cnf="cd ~/.config/"
  - alias ilua="nvim ~/.config/nvim/init.lua"
  - alias plua="nvim ~/.config/nvim/lua/plugins.lua"
  - alias ls="ls -p -G"
  - alias la="ls -A"
  - alias ll="ls -l"
  - alias lla="ll -A"
  - alias stylan="stylua --glob '**/*.lua' -- ~/.config/nvim"
  - #### GIT:
    - alias gdotc='git -C ~/dotfiles commit -a -m'
    - alias gdots='git -C ~/dotfiles status'
    - alias gijs='git init && echo "node_modules" >> .gitignore'
    - alias ghweb='gh repo view --web'
    - alias gu='gitui'
    - alias ng='npm init -y && git init && echo "node_modules" >> .gitignore'
  - #### alias to manage .dotfiles
    - alias kittyrm="rm -rf ~/.dotfiles/kitty/.config/kitty/"
    - alias kittycp="cp -r ~/.config/kitty/ ~/.dotfiles/kitty/.config/kitty/"
    - alias neofetchrm="rm -rf ~/.dotfiles/neofetch/.config/neofetch/"
    - alias neofetchcp="cp -r ~/.config/neofetch/ ~/.dotfiles/neofetch/.config/neofetch/"
    - alias nvimrm="rm -rf ~/.dotfiles/neovim/.config/nvim/"
    - alias nvimcp="cp -r ~/.config/nvim/ ~/.dotfiles/neovim/.config/nvim/"
    - alias zshrm="rm -rf ~/.dotfiles/zsh/.zshrc"
    - alias zshcp="cp -r ~/.zshrc ~/.dotfiles/zsh/.zshrc"
    - alias dotrm="kittyrm && neofetchrm && nvimrm && zshrm"
    - alias dotcp="kittycp && neofetchcp && nvimcp && zshcp"

## NoeVim::

  - #### Impatient:
    - LuaCacheClear
    - LuaCacheLog
    - LuaCacheProfile

  - #### UndoTree
    - UndotreeToggle

  - #### Startuptime
    - Startuptime

  - #### Neogit
    - Neogit

## i3
  - i3-config-wizard :: restore config

## Stow
  - stow -nvt ~ *
  - stow --adopt -vt ~ *
  - stow -vDt ~ *
  - stow -vSt ~ *

## tmux
  - tmux new -s name :: new session
  - tmux a # :: attach
  - tmux a -t name :: attach to name
  - tmux ls :: list sessions
  - tmux kill-session -t name :: kill session
