```bash
sudo apt install ./onedrive_2.5.3-1+np1+1.1_amd64_2404.deb 
sudo apt-get update
sudo apt-get upgrade
onedrive
onedrive --help
onedrive --display-config
sudo cp /usr/share/doc/onedrive/config ~/.config/onedrive/
sudo chown $USER:$USER ~/.config/onedrive/config
nano ~/.config/onedrive/config
echo "/OdooBackup/" > ~/.config/onedrive/sync_list
onedrive --dry-run --synchronize
onedrive --synchronize
systemctl enable --user onedrive
systemctl start --user onedrive
onedrive --synchronize
systemctl restart --user onedrive
clear
history

```
