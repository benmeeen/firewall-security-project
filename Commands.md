# Commands Used – Ubuntu Firewall 

## 1. Install and Update
sudo apt update && sudo apt upgrade -y
sudo apt install ufw -y

## 2. Configure UFW
sudo ufw enable
sudo ufw allow 22
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw status verbose

## 3. Logging
sudo ufw logging on
sudo less /var/log/ufw.log
sudo journalctl -k | grep UFW
sudo dmesg | grep UFW

## 4. Disable Unnecessary Services
sudo systemctl stop cups
sudo systemctl disable cups
sudo systemctl stop cups-browsed

## 5. Testing Firewall Rules
```bash
curl http://localhost:22
curl http://localhost:9999
curl http://localhost:8080
telnet localhost 9999
telnet localhost 8080
```



## 6. Save Outputs to Files
sudo ufw status verbose > ufw_rules.txt
nmap localhost > nmap_scan.txt
sudo journalctl -k | grep UFW > logs_sample.txt
