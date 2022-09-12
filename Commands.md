# Commands

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
- #### alias to manage .dotfiles :TODO need better way to do this maybe zsh functions
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

- #### Dirvish
    - :!mkdir %foo create directory
    - :e %foo.txt create file

- #### Eunuch
    - :Remove delete a file on dish state on buffer but no longer available
    - :Delete delete from all
    - :Move Rename a buffer and the file on dish simultaneously
    - :Rename
    - :Copy
    - :Duplicate
    - :Chmod change permissions of the current file
    - :Mkdir create a directory

- #### Icon-picker
    - PickEverything

- #### Trouble - modes: document_diagnostic, workspace_diagnostics, quickfix
    - Trouble [mode]
    - TroubleClose [mode]
    - TroubleToggle [mode]
    - TroubleRefresh
