- install fedora iso
-sudo usermod -aG sudo <user> : add user to sudo group
- install git - xinput - vim
- upgrade system : sudo dnf upgrade --refresh -y
- dependecyes requires : sudo dnf install dnf-plugins-core -y
- update system : sudo dnf update --refresh
- install edge
- dnf conf : /etc/dnf/dnf.conf
- clean cache : sudo dnf clean all or dbcache
- enable rmp fusion / sudo dnf groupupdate core
- add flatpak
- change hostname: sudo hostnamectl set-hostname name
- install media core : sudo dnf groupupdate multimedia --setop="install_weak_deps=False" --exclude=PackageKit-gstreamer-plugin
- install dnf polybar picom dunst sxhkd
- git clone dotfiles if you have
- install stow
- stow i3 - polybar - picom - dunst
- screen tearing i3 /etc/X11/xorg.conf.d/20-intel.conf
Section "Device"
 
    Identifier "Intel Graphics"
 
    Driver "intel"
 
    Option "TearFree" "true"
 
EndSection

- install rofi
- stow rofi
- install nautilus
- install nerd font mono ~/.local/share/fonts : fc-cache -f -v
- list fonts : fclist | grep 
- stow alacritty - zsh - oh my zsh - p10k
- sudo dnf install zsh - git clone oh my zsh - p10kconfigure
- change terminal to zsh
- reboot
- install neovim from source
- install req - git clone neovim - upnvim zsh function
- stow neovim - delete packer_compiled 
- install sqlite for telescope
- install ripgrep - fzf
- install homebrew - add brew to you shell
echo '# Set PATH, MANPATH, etc., for Homebrew.' >> ~/.config/zsh/.zshrc
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.config/zsh/.zshrc
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
- sudo updatedb : for use locate command
- install fnm with script dont forget to get chmod +x to the script
- install node with fnm
- install lua-languag-server with brew - tssserver and jsonls with npm
- try to fix some errors
- git clone oh my tmux - stow tmux
- check scripts
