# Errores
## Linux
  - Not permission to write files because owner file
    - Need to change owner file with chown mod
## Nvim
  - Treesitter ld o cc error:
    - brew unlink binutils para usar el ld de usr/bin
  - Treesitter cannot execute cc1plus
    - yum install gcc-c++
  - no telescope greb search
    - install ripgrep
    - if you using fzfwriter + instal fzf
  - telescope no find libsqlite3.so
    - sudo dnf install sqlite
    - sudo dnf install sqlite-devel sqlite-tcl

## Terminal
  - no brew after reboot
    - put brew in your path

## Docker
  - EECONREFUSED o ENOTFOUND
    - check hostname: docker-compose.yml
  - Fetching server api filenotfounderror
    - need to start docker : systemctl start docker
