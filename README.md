# CysicVerifier-Node

Operating the Verifier Node Program
Recommend Hardware Requirements for Cysic Verifier Program Installation
To ensure a smooth installation and operation of the Cysic verifier program,
make sure your device meets these minimal specifications

- CPU: Single Core
- Memory: 8 GB
- Disk: 512 MB
- Bandwidth: 100 KB/s upload/download
- - Supported Operating Systems: Windows, Linux, Mac

# Step 1: First of all your system update
 ```bash
sudo apt-get update -y && sudo apt upgrade -y && sudo apt-get install make screen build-essential unzip lz4 gcc git jq -y
```
# Step 2: 
Use the following command in the terminal to download and run the setup script
(copy and paste the following command in Powershell and press enter to run them).
`Please replace 0x-Fill-in-your-reward-address-here with your own reward address below.`
```bash
curl  -L https://github.com/cysic-labs/phase2_libs/releases/download/v1.0.0/setup_linux.sh > ~/setup_linux.sh &&  bash ~/setup_linux.sh < EVM-WALLET >
```
# Step 3: 
Step 2: After the completion of Step 2, 
use the following command in terminal to start the verifier program:
```bash
cd ~/cysic-verifier/ &&  bash start.sh
```
`Wait for the line sync data from server` Then `Press CTRL+C`

The command you provided creates and configures a systemd service unit (cysic.service) 
on a Linux system. Here's a breakdown of what each part does and how you can use it:

# Step 4: 
Simply copy then submit to your server.
```bash
sudo tee /etc/systemd/system/cysic.service > /dev/null <<EOF
[Unit]
Description=Cysic Verifier
After=network.target

[Service]
User=$USER
WorkingDirectory=/root/cysic-verifier
ExecStart=bash /root/cysic-verifier/start.sh
Restart=on-failure
RestartSec=10
LimitNOFILE=65535

[Install]
WantedBy=multi-user.target
EOF
```
# Step 5: 
Simply copy then submit to your server.
```bash
sudo systemctl enable cysic
sudo systemctl daemon-reload
sudo systemctl start cysic
```
# Step 6:
Here's the command to view the logs for the
```bash
sudo journalctl -u cysic -f --no-hostname -o cat
```
# Step 7:
if closed Powershell & putty and return to vps login again and reun below commands to check sync status 
`change directory`
```bash
cd ~/cysic-verifier
```
# Step 8:
view the logs
```bash
sudo journalctl -u cysic -f --no-hostname -o cat
```
❤️Thank You for Reading!

I hope you have completed running the node,
if you have any problem with the node run,
then you can join my telegram channel below
and then you can message I will help you as best I can.

-➡️Telegram: https://t.me/Crypto_airdropHM
