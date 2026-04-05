# Part 2 (Short part and updated regularly): Installing all packages required for Hyprland
As the title suggests, this section will cover: Installing all the packages required for Hyprland. 
Unfortunately, there won’t be any screenshots to make the explanation easier. I apologize in advance.

To get started, we'll need two packages from outside Arch Linux (yay and paru) or, more specifically, from the [AUR Helper](https://wiki.archlinux.org/title/AUR_helpers).

we'll install them as we go along

## Internet (Network manager service)
From the start, there's no internet connection. That's normal because we're using NM (Network Manager), which has the same functionality as iwd but is a bit more complicated to configure.
```bash
nmcli general status # display a physical and radio connection
nmcli radio wifi on # wifi device up
nmcli device wifi list # List Wi-Fi connections
nmcli device wifi connect "SSID" password "mdp" # connects to the network
```
## 







## Fish, Fastfetch and nano
- [Fish](https://fishshell.com/) (Friendly Interactive SHell) is an alternative shell to Bash or Zsh. Advantage: Smart autocomplete as soon as you start typing (no setup required).
- [Fastfetch](https://github.com/fastfetch-cli/fastfetch) is a tool that displays information about your system in the terminal at startup (or on demand). It is more modern than [neofetch](https://github.com/dylanaraps/neofetch). Installation and setup are simple : 
- [nano](https://linuxize.com/post/how-to-use-nano-text-editor) is an easy-to-use command line text editor for Unix and Linux operating systems.
It includes all the basic functionality you expect from a regular text editor, 
like syntax highlighting, multiple buffers, search and replace with regular expression support,
spellchecking, UTF-8 encoding, and more.
```bash
$ sudo pacman -Syu # Update and upgrade System (Debian equivalent: apt update && apt upgrade)
$ sudo pacman -S fastfetch fish nano
```

# Work in Progress
