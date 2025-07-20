# playit.gg

INSTALL PLAYIT ON LINUX
0. Pre-Setup: Run the command(s) below.
```
sudo mkdir /etc/playit/
```
2. Run the following command:
```
wget https://github.com/playit-cloud/playit-agent/releases/download/v0.15.26/playit-linux-amd64
sudo chmod +x ./playit
```

4. Move the file to /etc/playit. Run the following command:
```
sudo mv ./playit /etc/playit/playit
```
6. Make a service file (run on boot and in background). Run the following command:
```
sudo nano /etc/systemd/system/playit.service
```
In the following window that opens, paste in this text:
```
[Unit]
Description=Playit.gg client
After=network.target

[Service]
WorkingDirectory=/etc/playit
ExecStart=/etc/playit/playit
Restart=on-failure
RestartSec=5

[Install]
WantedBy=multi-user.target
```
then do ctrl + x to exit the file, press y to save, and then enter to confirm.

6. Start the service in the background. Run the following commands:
```
sudo systemctl start playit
sudo systemctl enable playit
```
7. Get the claim code from playit. Run the following commands:
```
sudo systemctl status playit
```
From here you should be able to get the claim link. Paste it into your browser and log in to start creating tunnels.
To exit this menu do CTRL + C
