``` shell
sudo cat /etc/default/grub
sudo apt remove linux-image-5.19.0-41-generic
sudo apt remove linux-headers-5.19.0-41-generic linux-modules-5.19.0-41-generic
sudo update-grub
dpkg -l | grep linux-image
sudo apt purge linux-image-5.19.0-41-generic
sudo apt purge linux-image-5.19.0-41-generic linux-headers-5.19.0-41-generic linux-modules-5.19.0-41-generic
sudo update-grub
dpkg -l | grep linux-image
```