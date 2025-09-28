# arch_install
## archinstall
1.
## firewall
ufw:
```
sudo pacman -S --noconfirm ufw
sudo ufw default deny
sudo ufw enable
sudo systemctl enable ufw
sudo systemctl start ufw
```
## mounting drives
add encrypted drive mounts:
1. 
com.bitwarden.desktop
## package management:
**flatpak**
```
sudo pacman -S --noconfirm flatpak
flatpak install -y flathub com.github.tchx84.Flatseal io.github.flattool.Warehouse
```
**paru**
```
sudo pacman -S --needed --noconfirm base-devel git
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
cd ~/
rm -rf paru
```
## system restore
**snapper**
```
sudo pacman -S --noconfirm snapper
sudo snapper -c root create-config /
sudo snapper -c home create-config /home
```
**brfs-assistant**
```
paru -S --noconfirm btrfs-assistant
```
**grub-btrfs**
```
sudo pacman -S --noconfirm grub-btrfs
sudo systemctl enable grub-btrfsd
sudo systemctl start grub-btrfsd
```
**snap-pac**

Pacman hook to automatically makes snapper snapshots before and after pacman transactions.
```
sudo pacman -S --noconfirm snap-pac
```
add the below to `/etc/snap-pac.ini`:
```
[boot]
snapshot = True

[root]
snapshot = True
```
**snap-pac-grub**

Pacman hook to automatically update GRUB entries after pacman transactions.
```
paru -S --noconfirm snap-pac-grub
```
**snapper-rollback**
Rollback to snapshots from the `grub-btrfs` snapshot menu.
```
paru S --noconfirm snapper-rollback
```
## general
content creation:
```
flatpak install -y flathub com.core447.StreamController com.obsproject.Studio
```
internet:
```
sudo pacman -S --noconfirm qbittorrent
paru -S --noconfirm mullvad-vpn-bin
flatpak install -y flathub com.discordapp.Discord io.gitlab.librewolf-community org.mozilla.firefox
```
**media**
```
sudo pacman -S --noconfirm mpv
flatpak install -y flathub org.fooyin.fooyin org.kde.gwenview
```
productivity:
```
flatpak install -y flathub org.gimp.GIMP org.inkscape.Inkscape org.libreoffice.LibreOffice
```
**development**
```
paru -S --noconfirm visual-studio-code-bin
```
**research**
```
paru -S --noconfirm zotero-bin
```
utilities:
```
flatpak install -y flathub org.bunkus.mkvtoolnix-gui io.github.peazip.PeaZip org.gnome.Boxes me.iepure.devtoolbox
# io.otsaloma.nfoview
flatpak run --command=install2dolphin io.github.peazip.PeaZip
flatpak install flathub org.kde.kalk
```
move files in `/home/v4u6h4n/.local/share/kservices5` to `/home/v4u6h4n/.local/share/kio/servicemenus/`.
3. Make files executable.
flatpak install flathub org.kde.okular
```
sudo pacman -S --noconfirm rsync mkvtoolnix-cli
```
## misc:
Dotfiles
```
sudo pacman -S --noconfirm yadm
```
drivers and hardware management:
```
sudo pacman -S amd-ucode
flatpak install -y flathub org.openrgb.OpenRGB
```
**virtual machine clients**
```
sudo pacman -Syu --needed --noconfirm spice spice-gtk spice-protocol spice-vdagent gvfs-dnssd
sudo reboot now
```
To share a folder:
1. Share `<folder name>` in virtual machine application settings.
2. Bookmark `webdav://127.0.0.1:9843/<folder name>` in Dolphin.
## boot
Add this line to `/etc/default/grub`:
```
GRUB_TOP_LEVEL="/boot/<kernel-filename>"
```
