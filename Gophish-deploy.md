# GoPhish Installation — Ubuntu 24.04 (Lab Deployment Commands)

## Update System

sudo apt update

sudo apt upgrade -y

---

## Install Dependencies

sudo apt install unzip wget ufw


## Enable Firewall

sudo ufw allow OpenSSH

sudo ufw allow 3333/tcp

sudo ufw allow 80/tcp

sudo ufw allow 443/tcp

sudo ufw enable

These are required to download and extract the release package.

## Download Latest GoPhish Release

From official releases page:

wget https://github.com/gophish/gophish/releases/latest/download/gophish-v0.12.1-linux-64bit.zip

(Version number may change in future releases.)

## Extract Archive
unzip gophish-v0.12.1-linux-64bit.zip

## Move into directory:

cd gophish

## Make Binary Executable

chmod +x gophish

## Start GoPhish Server

sudo ./gophish

Starting admin server at https://127.0.0.1:3333
## Access Admin Interface

Open browser:

https://SERVER-IP:3333

Login using credentials shown in terminal output.

## (Recommended) Run GoPhish as Background Service

### Create systemd service file:

sudo nano /etc/systemd/system/gophish.service

Paste:

[Unit]
Description=GoPhish Service
After=network.target

[Service]
WorkingDirectory=/home/awarenesslab/gophish
ExecStart=/home/awarenesslab/gophish/gophish
Restart=always
User=awarenesslab

[Install]
WantedBy=multi-user.target

## Reload daemon:

sudo systemctl daemon-reload

## Enable service:

sudo systemctl enable gophish

## Start service:

sudo systemctl start gophish

## Check status:

sudo systemctl status gophish
## Allow Firewall Access (If Needed)
sudo ufw allow 3333/tcp

sudo ufw allow 80/tcp


## Check service running:

sudo systemctl status gophish

## Or check process:

ps aux | grep gophish
