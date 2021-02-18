# Install Latest [Ubuntu LTS](https://ubuntu.com/download/desktop)
- with minimal installation and property driver
- Optional: backup os-release file with `sudo cp /etc/os-release /etc/os-release.bkp`
- Optional: add apt proxy with followwing lines in file `/etc/apt/apt.conf`
```
Acquire::http::Proxy "http://127.0.0.1:7780";
Acquire::https::Proxy "http://127.0.0.1:7780";
```
- switch apt source to "main server" in "software and updates"

# Install KDE Neon desktop
```
wget -q -O - http://archive.neon.kde.org/public.key | sudo apt-key add -
sudo apt-add-repository http://archive.neon.kde.org/user
sudo apt-get update
sudo apt-get upgrade
sudo apt install plasma-desktop
# sudo tasksel install neon-desktop
# to delete ppa, use `sudo apt-add-repository --remove http://archive.neon.kde.org/user`
# to delete key, use `sudo apt-key list` to check the key value and `sudo apt-key del "<key value>"` to remove key
```
# Install some utility packages
- KDE network manager `sudo apt-get install plasma-nm`
- KDE qml prison (clipboard module) `sudo apt install qml-module-org-kde-prison`
- KDE NEON Grub theme `sudo apt install grub-theme-breeze`
- KDE Dropdown console `sudo apt install yakuake`

# Remove broken packages
- remove Gnome driver utilities (broken)`sudo apt purge software-properties-gtk`
- Optional: reinstall emoji package if it's not working `sudo apt reinstall fonts-noto-color-emoji`
- Optional: remove Gnome snap shop (redundent) `sudo snap remove snap-store`
- Optional: restore os-release file with `sudo cp /etc/os-release.bkp /etc/os-release`

# Install sogou input
- install fcitx
- download sogoupinyin for 20.04 and run with `dpkg -i sogoupinyin`
- install steam with `sudo apt install steam-installer`

# Install Qv@ray GUI client
- `sudo apt-get install gnupg ca-certificates curl`
- `curl -sSL https://qv2ray.net/debian/pubkey.gpg | sudo apt-key add -`
- `echo "deb [arch=amd64] https://qv2ray.net/debian/ stable main" | sudo tee /etc/apt/sources.list.d/qv2ray.list`
- `sudo apt-get update`
- `sudo apt-get install qv2ray`

# Use local time zone instead of motherboard
- `timedatectl set-local-rtc 1`

# adjust monitor relative position
- `xrandr` to check monitor name and current position
- `xrandr --output eDPI1 --pos <x>x<y>`to amend position
- e.g.: 

```
xrandr --output HDMI-2 --mode 1920x1080 --pos 0x1080 --rotate normal \
--output HDMI-0 --mode 1920x1080 --pos 1920x1080 --rotate normal \
--output DVI-D-0 --mode 1920x1080 --pos 0x0 --rotate normal \
--output DP-1 --mode 1920x1080 --pos 1920x0 --rotate normal
```
