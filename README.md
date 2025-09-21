# arch_install
## firewall
ufw:
```
sudo pacman -S ufw
sudo ufw default deny
sudo ufw enable
sudo systemctl enable ufw
sudo systemctl start ufw
```
## package management:
flatpak
```
sudo pacman -S flatpak
flatpak install flathub com.github.tchx84.Flatseal io.github.flattool.Warehouse
```
paru
```
sudo pacman -S --needed base-devel git
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
cd ~/
rm -rf paru
```
## system restore
snapper:
```
sudo pacman -S snapper
sudo snapper -c boot create-config /boot
sudo snapper -c home create-config /home
sudo snapper -c root create-config /
```
brfs-assistant
```
paru -S btrfs-assistant
```
grub-btrfs:
```
sudo pacman -S grub-btrfs
sudo systemctl enable grub-btrfsd
sudo systemctl start grub-btrfsd
```
snap-pac:
```
sudo pacman -S snap-pac
```
snap-pac-grub:
```
paru -S snap-pac-grub
```
## general
content creation:
```
flatpak install flathub com.core447.StreamController com.obsproject.Studio
```
internet:
```
flatpak install flathub com.discordapp.Discord org.mozilla.firefox
```
media:
```
flatpak install flathub org.fooyin.fooyin
```
productivity:
```
flatpak install flathub org.gimp.GIMP org.inkscape.Inkscape org.libreoffice.LibreOffice
```
utilities:
```
flatpak install flathub org.bunkus.mkvtoolnix-gui io.github.peazip.PeaZip org.gnome.Boxes me.iepure.devtoolbox io.otsaloma.nfoview
```
## misc:
```
sudo pacman -S amd-ucode
```
