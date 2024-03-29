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
    - cd - : go to the before folder
    - ctrl + r : search some commands
    - ctrl + k : delete cursor to the end
    - ctlr + u : delete all the line


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
  - stow -nvt ~ * : simulation mode
  - stow --adopt -vt ~ * : move and link 
  - stow -vDt ~ * : unlink 
  - stow -vSt ~ * : link

## tmux
  - tmux new -s name :: new session
  - tmux a # :: attach
  - tmux a -t name :: attach to name
  - tmux ls :: list sessions
  - tmux kill-session -t name :: kill session
