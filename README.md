# Netdata-server
## Task 7: Monitor System Resources Using Netdata
🎯 Objective
Install Netdata on an AWS EC2 instance using Docker to monitor and visualize real-time system and application performance metrics.
🧰 Tools Used
- Netdata (open-source performance monitoring tool)
- Docker (container platform)
- AWS EC2 (Ubuntu instance)
⚙️ Setup Steps
1. 🖥️ Launched EC2 Instance
Created a new Ubuntu EC2 instance. Updated and upgraded packages.
2. 🐳 Installed Docker
Commands used:

sudo apt update
sudo apt install -y docker.io
sudo usermod -aG docker $USER

Reconnected via SSH after applying Docker group changes.
# 3. 🚀 Ran Netdata Container

Docker command:
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined  netdata/netdata

4. 🔐 Configured EC2 Security Group
Allowed TCP Port 19999 for public access.
5. 🌐 Accessed Dashboard
Visited: http://<EC2-PUBLIC-IP>:19999
Successfully viewed live system metrics:
- CPU usage
- RAM usage
- Disk I/O
- Network traffic
- Docker containers (if running)

📊 Dashboard Screenshot:
![dashbord net data](https://github.com/user-attachments/assets/2be20eaa-0209-4958-a675-e7256394e275)

📸 Included below:
![alert explore](https://github.com/user-attachments/assets/b23246e7-809e-4130-b8ed-64640b7c5ac7)

🔔 Explored Alerts & Chart Panels
- Viewed real-time health alerts (OK, Warning, Critical)
- Navigated through chart panels like CPU, memory, disk, system load
- Zoomed into individual charts and used hover to view data points

# 📁 Explored Logs in /var/log/netdata
Inside the container:
![lst net ss](https://github.com/user-attachments/assets/c4001ef0-39e0-4170-8473-6308151427df)

docker exec -it netdata bash
cd /var/log/netdata
ls
cat error.log

Viewed system logs and verified Netdata is running smoothly.
✅ Outcome
Successfully deployed and used Netdata for real-time monitoring on a cloud server. Gained understanding of lightweight observability for Linux systems and containers.
