# kali-linux-grub
After windows update grub menu is missing

press escape when showing windows boot loader..then

```
sudo update-grub -y
sudo grub-install /dev/sda
```

*** where sda3 is linux mounted  ***
```
mount /dev/sda3 /mnt
mount --bind /dev /mnt/dev
mount --bind /dev/pts /mnt/dev/pts
mount --bind /proc /mnt/proc
mount --bind /sys /mnt/sys
chroot /mnt
grub-install /dev/sda
update-grub
exit
umount /mnt/dev/pts
umount /mnt/dev
umount /mnt/proc
umount /mnt/sys
umount /mnt
```
*** After restart ***
```
os-prober
update-grub

```
https://unix.stackexchange.com/questions/419773/kali-linux-is-installed-but-not-showing-in-boot-manager
