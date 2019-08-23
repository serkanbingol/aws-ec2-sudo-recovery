
# Command for disk check
lsblk

# Create temporary Folder for original disk
sudo mkdir /mnt/tempvol

# Mount original disk to temporary disk
sudo mount /dev/xvdf1 /mnt/tempvol

# Umount original disk
sudo umount /mnt/tempvol

# Commands for reset all folder permissions
chmod -R 755 /bin /boot /dev /etc/ /home /lib /lib64 /media /mnt /opt /run /sbin /srv /usr /var
chmod -R 777 /initrd.img /vmlinuz
chmod -R 1777 /tmp
chmod -R 555 /sys
chmod -R 555 /proc
chmod -R 700 /root

#Command for check all folder permissions
stat -c '%A %a %n' /*

# Commands for check etc/ssh folder permissions
sudo chmod 600 /mnt/tempvol/etc/ssh/ssh_host_*_key 
sudo chmod 644 /mnt/tempvol/etc/ssh/ssh_host_*_key.pub /mnt/tempvol/etc/ssh/ssh_config /mnt/tempvol/etc/ssh/moduli 
sudo chmod 600 /mnt/tempvol/etc/ssh/sshd_config

# Command for reset usr/bin/sudo file permission
sudo chmod -R a=rx,u+ws /mnt/tempvol/usr/bin/sudo
