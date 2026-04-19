# Ubuntu 24.04 Deployment Notes

## Update System

sudo apt update
sudo apt upgrade -y

---

# Install Dependencies

sudo apt install unzip wget ufw

---

# Enable Firewall

sudo ufw allow OpenSSH
sudo ufw allow 3333/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw enable

---

# Optional Reverse Proxy

Install nginx:

sudo apt install nginx

Used for TLS termination and access logging.
