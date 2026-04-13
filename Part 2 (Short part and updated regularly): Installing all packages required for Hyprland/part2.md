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

```bash
$ sudo pacman -Syu
$ sudo pacman -S fastfetch fish neovim
$ chsh -S /usr/bin/fish
$ sudo chsh -S /usr/bin/fish root

$ sudo nvim /etc/fish/config.fish # Uncomment and add the `fastfetch` argument to line 9 of the file
```

## Hyprland and system Essential Package
The installation will be performed using the following packages
```bash
$ sudo pacman -S hyprland kitty sddm noto-fonts noto-fonts-cjk noto-fonts-emoji noto-fonts-extra
```

## Enabling the SDDM login screen and accessing Hyprland
```bash
$ systemctl enable sddm && hyprland
```

```bash
// after login
$ sudo pacman -S hyprpolkitagent kitty hyprpaper dunst hyprlauncher yazi pipewire xdg-desktop-portal-hyprland waybar wl-clipboard 

// graphics & pilot
$ sudo pacman -S intel-media-driver libva-intel-driver mesa vulkan-intel qt5-wayland qt6-wayland

// plus
$ sudo pacman -S zathura mpv imv bat fd ripgrep p7zip
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
