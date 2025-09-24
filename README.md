# arch_install
## firewall
ufw:
```
sudo pacman -S --noconfirm ufw
sudo ufw default deny
sudo ufw enable
sudo systemctl enable ufw
sudo systemctl start ufw
```
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
## general
content creation:
```
flatpak install -y flathub com.core447.StreamController com.obsproject.Studio
```
internet:
```
flatpak install -y flathub com.discordapp.Discord org.mozilla.firefox
```
media:
```
flatpak install -y flathub org.fooyin.fooyin
```
productivity:
```
flatpak install -y flathub org.gimp.GIMP org.inkscape.Inkscape org.libreoffice.LibreOffice
```
utilities:
```
flatpak install -y flathub org.bunkus.mkvtoolnix-gui io.github.peazip.PeaZip org.gnome.Boxes me.iepure.devtoolbox io.otsaloma.nfoview
```
## misc:
```
sudo pacman -S amd-ucode
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
Add this line to `/etc/default/gub`:
```
GRUB_TOP_LEVEL="/boot/<kernel-filename>"
```
