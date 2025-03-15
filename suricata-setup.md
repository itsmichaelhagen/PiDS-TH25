# Suricata
### Setting up Suricata after installation (see README.md for install guide)

## Setup Suricata as a Service
To have Suricata always running in the background as a service, we will create a Suricata service using the below method so that it will always be monitoring network traffic.

Create service
``` bash
sudo nano /etc/systemd/system/suricata.service
```
Configure service settings
``` ini
[Unit]
Description=Suricata Intrusion Detection Service
After=network.target

[Service]
ExecStart=/usr/bin/suricata -c /etc/suricata/suricata.yaml -i wlan0
Restart=always
User=root
Group=root

[Install]
WantedBy=multi-user.target
```
Enable and start service
``` bash
sudo systemctl daemon-reload
sudo systemctl enable suricata
sudo systemctl start suricata
```
