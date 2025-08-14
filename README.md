# netdata-monitoring-task7

# Netdata Server & App Monitoring

## 📌 Objective
Install and run **Netdata** to monitor system resources and applications in real-time.

## 🛠 Tools Used
- **Netdata** (open-source monitoring tool)
- **Docker** (for containerized deployment)

## 🚀 Steps Followed

### 1. Install Docker
On Ubuntu/Debian:
```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable docker --now
2. Run Netdata in Docker
docker run -d --name=netdata \
  -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata

3. Access the Dashboard

Local machine: http://localhost:19999

Remote server: http://<server-ip>:19999

4. Monitor Metrics

CPU usage

Memory usage

Disk I/O

Network activity

Docker container stats (if any running)

Alerts & logs

5. View Logs
docker exec -it netdata /bin/bash
cd /var/log/netdata
ls -l

6. Screenshot

📊 Key Learnings

Netdata provides lightweight, real-time server & application monitoring.

Using --cap-add SYS_PTRACE and --security-opt apparmor=unconfined allows deeper process-level monitoring.

The dashboard is interactive and offers per-second updates.
