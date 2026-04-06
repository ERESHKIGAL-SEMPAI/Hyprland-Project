# Part 2 (Short part and updated regularly): Installing all packages required for Hyprland
As the title suggests, this section will cover: Installing all the packages required for Hyprland. 
Unfortunately, there won’t be any screenshots to make the explanation easier. I apologize in advance.

To get started, we'll need two packages from outside Arch Linux (yay and paru) or, more specifically, from the [AUR Helper](https://wiki.archlinux.org/title/AUR_helpers).

we'll install them as we go along

## Internet (Network manager service)
From the start, there's no internet connection. That's normal because we're using NM (Network Manager), which has the same functionality as iwd but is a bit more complicated to configure.
```bash
$ nmcli general status # display a physical and radio connection
$ nmcli radio wifi on # wifi device up
$ nmcli device wifi list # List Wi-Fi connections
$ nmcli device wifi connect "SSID" password "mdp" # connects to the network
```

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
$ chsh -S /usr/bin/fish # change of interpreter for fish
$ sudo chsh -S /usr/bin/fish root # change of interpreter for fish
$ sudo nano /etc/fish/config.fish # Uncomment and add the `fastfetch` argument to line 9 of the file
```

## Hyprland and system Essential Package
The installation will be performed using the following packages
```bash
$ sudo pacman -S sddm waybar pipewire pipewire-pulse kitty hyprcursor hypre hyprgraphics hypridle hyprland hyprland-guiutils hyprland-protocols hyprland-qt-support hyprlang hyprlauncher hyprlock hyprpaper hyprpicker hyprpolkitagent hyprpwcenter hyprshot hyprsunset hyprtoolkit hyprutils hyprwayland-scanner hyprwire qt5-wayland qt6-wayland xdg-desktop-portal-hyprland xdg-user-dirs xdg-utils htop thunar dunst firefox intel-media-driver libva-intel-driver mesa vulkan-intel xorg-server xorg-xinit
```

## Enabling the SDDM login screen and accessing Hyprland
```bash
$ systemctl enable sddm && reboot
```

## AUR Helper Installation
Install Paru and Yay as follows : 
### yay
```bash
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/yay.git
cd yay
makepkg -si
```

### paru
```bash
sudo pacman -S --needed git base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
```

## Final
After the system restarts, log in to your account and follow the instructions in the pop-up window; it will guide you through how Hyprland works. 
The most important part is where it lists all the required and optional packages—make sure everything is marked in green. This concludes Section Two.

# End section
