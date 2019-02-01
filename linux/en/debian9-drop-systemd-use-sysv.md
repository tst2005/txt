OVH dedicated server

* make a default install debian9 amd64 (with systemd)
* ssh root@serv
* apt-get install sysv-rc sysvinit-core sysvinit-utils
* (need nonfree enable in apt sources list)
* apt-get install firmware realtek netxen firmware-misc-nonfree
* update-initramfs -u
* update-grub
* Fix the OVH buggy hook ... /etc/initramfs-tools/hooks/netdevnames
* apt-get purge systemd dbus
