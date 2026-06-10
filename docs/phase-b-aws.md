# Phase B1 — Week 3 (AWS architecture, VM not required)

## Diagram
``text
[ Internet ] 
      │
      ▼  (Port 80 / 5000)
[ Security Group (Firewall) ]
      │
      ▼
[ EC2 Instance (Ubuntu VM) ] ──▶️ [ Nginx (Reverse Proxy) ] ──▶️ [ Flask API (Python) ]

(Drawing or ASCII: Internet → security group → EC2 → nginx or Docker)

## Inbound ports (security group)

| Port | Protocol | Source | Usage |
|------|----------|--------|--------|
| 22 | TCP | | SSH |My-IP-Address
| 80 or 5000 | TCP | | HTTP |0.0.0.0/0

**Why is opening SSH (22) to 0.0.0.0/0 dangerous in production?**
Opening port 22 to 0.0.0.0/0 means anyone on the internet can attempt to connect to your server. This exposes your production environment to continuous brute-force attacks, automated bot scans, and potential unauthorized access exploits. In production, SSH access should always be restricted strictly to your trusted administrator IP address.

## Commands you would run on the VM
# SSH connection to the virtual machine
ssh -i key.pem ubuntu@PUBLIC_IP

# 1. Update system package index
sudo apt update && sudo apt upgrade -y

# 2. Install Python 3, pip, and Nginx
sudo apt install python3 python3-pip nginx -y

# 3. Clone the CloudShop code repository
git clone [https://github.com/tamenkamjerryff5-a11y/cloudshop-tp.git](https://github.com/tamenkamjerryff5-a11y/cloudshop-tp.git)

# 4. Navigate to project folder and install python requirements
cd cloudshop-tp
pip3 install -r requirements.txt

# 5. Start the Flask application in the background
nohup python3 app.py > output.log 2>&1 &
```bash
ssh -i key.pem ubuntu@PUBLIC_IP
sudo apt update && sudo apt install -y nginx
curl http://localhost
```

Explain the role of: **SSH key**, **public IP**, **security group**.

## Technical choices

- AWS region and why:
- Instance type (e.g. t2.micro):
- Why **terminate** the instance after a lab:
