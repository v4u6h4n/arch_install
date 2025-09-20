# arch_install
## firewall
ufw:
```
sudo pacman -S ufw
sudo ufw default deny
sudo ufw reload
sudo systemctl enable ufw
sudo systemctl start ufw
```
## package managers:
```
# flatpak
sudo pacman -S flatpak
# paru
sudo pacman -S --needed base-devel
git clone https://aur.archlinux.org/paru.git
cd paru
makepkg -si
rm -rf paru
```
## system restore
snapper:
```
sudo pacman -S snapper
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
## misc:
```
sudo pacman -S amd-ucode
```
