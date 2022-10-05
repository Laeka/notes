# DEV-WORKFLOW

## Fedora
  - terminal file manager: ranger

## Firefox
  - ``` sudo dnf install firefox ```
  - search about:config - legacy - make true stylesheets  
  - in terminal cd .mozilla/firefox look for cd profile.default-release
  - mkdir chrome
  - nvim userChrome.css - steal for others css(linux method)
  - dark reader please
  - spellchecker
  - tabs-groups

## Kitty / Alacritty
  - Rofi : window siwtcher, application launcher and dmenu replacement
  - Zsh :
    - HOME – Represents the home directory for the current user.
    - SHELL – Shows the path of the current user’s shell.
    - USER – Shows the currently logged-in user.
    - PATH – Contains a list of directories to be searched for executable files when a command is executed.
    - LANG – Shows locale settings, including character encoding
    - TERM – Refers to the current terminal emulation.
    - _ – Shows the previously executed command for that user.

## I3
  - ``` sudo dnf install i3 i3status dmenu i3lock xbacklight feh conky ```
    - i3 is the main window manager package.
    - i3status is a utility to generate a string with information to be displayed in the i3bar.
    - dmenu is a utility to launch our apps in the i3 desktop.
    - xbacklight is a utility to set our laptop’s screen brightness.
    - feh is a utility to set a wallpaper.
    - conky is a utility to display information of the system in a awesome way.
  - ``` sudo dnf install xss-lock picom network-manager-applet light maim xclip dunst polkit-gnome polybar rofi ```
    - xss-lock - Handles lock and idle stuff
    - picom - Compositor for window transparencies and stuff
    - network-manager-applet - Tray tool for network stuff
    - light - Display brightness controls
    - maim - screenshot utility
    - xclip - clipboard stuff
    - dunst - Notifications
    - polkit-gnome - Hook up for authentication/elevation stuff
    - polybar - A configurable status bar
      - make bar transparent put 00 - aa - bb ... to begining of the hexcode
    - rofi - A sweet sweet launcher (alternative to dmenu)

    - Manage monitor

## Tmux
  - ``` sudo dnf install tmux ripgrep```
    - ~/.tmux/${archivos de conf}
  - oh my tmux - github/gepakosz/tmux
  - TMP : tmux plugin 
  - Detaching session es mandar la session a background y attach es traerla

## Neovim
