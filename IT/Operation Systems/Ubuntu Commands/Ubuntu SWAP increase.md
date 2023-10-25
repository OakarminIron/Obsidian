``` shell
sudo swapon --show
free -h
df -h
sudo fallocate -l 6G /swapfile1
ls -lh /swapfile1
sudo chmod 600 /swapfile1
ls -lh /swapfile1
sudo mkswap /swapfile1
sudo swapon /swapfile1
sudo swapon --show
free -h
sudo cp /etc/fstab /etc/fstab.bak
echo '/swapfile1 none swap sw 0 0' | sudo tee -a /etc/fstab
cat /proc/sys/vm/swappiness
sudo sysctl vm.swappiness=20
sudo nano /etc/sysctl.conf
cat /proc/sys/vm/vfs_cache_pressure
sudo sysctl vm.vfs_cache_pressure=60
sudo nano /etc/sysctl.conf
clear
history
```

https://linuxhint.com/add-swap-space-ubuntu-22-04/