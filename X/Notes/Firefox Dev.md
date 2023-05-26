```
clear
sudo apt-get install libgtk2.0-0 libasound2 libdbus-glib-1-2 
sudo cp -rp firefox*.tar.bz2 /opt
sudo rm -rf firefox*.tar.bz2
cd ~
cd /opt
sudo tar xjf firefox*.tar.bz2
sudo rm -rf firefox*.tar.bz2
sudo chown -R $USER /opt/firefox
nano ~/.local/share/applications/firefox_dev.desktop
chmod +x ~/.local/share/applications/firefox_dev.desktop
```