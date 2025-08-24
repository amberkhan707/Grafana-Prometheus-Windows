# Grafana & Prometheus Monitoring Setup on Windows  

Easily install and configure **Grafana + Prometheus** on **Windows Server / Windows 10/11**, with support for:  

- ✅ **Windows Exporter / WMI Exporter** (System metrics: CPU, Memory, Disk, Network, Services)  
- ✅ **Python Exporter** (Custom metrics)  
- ✅ **Redis Exporter** (Redis monitoring)  
- ✅ Pre-built **Grafana Dashboards** for Node Exporter & Process Exporter  

This repository contains all required files and instructions to set up a complete **Windows Monitoring Stack** with **Grafana + Prometheus**.  

---

## 🚀 Features  

- Full **Prometheus + Grafana Monitoring** setup on Windows.  
- Collects metrics via **Windows Exporter (WMI)**, **Python Exporter**, and **Redis Exporter**.  
- Ready-to-use **Grafana Dashboards** for system performance & process monitoring.  
- Step-by-step installation guide optimized for **Windows environment**.  
- Works on **Windows Server 2022 / 2019 / 2016 / Windows 10 / Windows 11**.  

---

## 📂 Files in This Repository  

- `Prometheus/` → Prometheus binaries + configuration (`prometheus.yml`)  
- `windows_exporter/` → Windows Exporter (WMI)  
- `python_exporter/` → Python Exporter  
- `redis_exporter/` → Redis Exporter  
- `Grafana Dashboard JSONs/` → Importable dashboards for Grafana  
- `Installation_procedure.one` → Original installation guide  

---

## ⚡ Installation  

### 1. Install Grafana  
- Copy `grafana-enterprise-10.4.2.windows-amd64` into `Downloads` folder and run installer.  
- Or copy Grafana folder from another PC:  
  - From: `C:\Program Files\GrafanaLabs\`  
  - To: `C:\Program Files\`  

### 2. Install Prometheus  
- Copy entire `Prometheus` folder into:  
  ```powershell
  C:\Prometheus
  ```

### 3. Install Windows Exporter (WMI Exporter)  
- Copy `windows_exporter` into:  
  ```powershell
  C:\Program Files\
  ```

### 4. Install Python Exporter  
- Copy `python_exporter` into:  
  ```powershell
  C:\Program Files\
  ```

### 5. Install Redis Exporter  
- Copy `redis_exporter` into:  
  ```powershell
  C:\Program Files\
  ```

---

## ▶️ Running the Stack  

### Start Grafana  
```powershell
C:\Program Files\GrafanaLabs\grafana\bin\grafana-server.exe
```
Open: [http://localhost:3000](http://localhost:3000)  

### Start Prometheus  
```powershell
C:\Prometheus\prometheus.exe
```
Open: [http://localhost:9090](http://localhost:9090)  

### Start Windows Exporter  
```powershell
cd "C:\Program Files\windows_exporter"
windows_exporter.exe --collectors.enabled "cpu,cs,logical_disk,net,os,service,system,tcp"
```
Open: [http://localhost:9182](http://localhost:9182)  

### Start Python Exporter  
```powershell
cd "C:\Program Files\python_exporter"
python_metric.py
```
Open: [http://localhost:8000](http://localhost:8000)  

### Start Redis Exporter  
```powershell
cd "C:\Program Files\redis_exporter"
redis_exporter.exe
```
Open: [http://localhost:9121](http://localhost:9121)  

---

## 🔧 Post-Installation Setup  

1. Replace Prometheus config:  
   - File: `C:\Prometheus\prometheus.yml`  
   - Update target IP addresses inside `prometheus.yml`.  

2. Verify in Prometheus UI:  
   - [http://localhost:9090](http://localhost:9090)  
   - Check `windows_exporter`, `redis_exporter`, `python_exporter` targets are **UP**.  

3. Configure Grafana Data Source:  
   - Open: [http://localhost:3000](http://localhost:3000)  
   - Go to: **Home → Connections → Add new source → Prometheus**  
   - URL: `http://localhost:9090` → **Save & Test**  

4. Import Dashboards:  
   - Go to: **Home → Dashboard → New → Import**  
   - Import provided JSON files (Node Exporter, Process Exporter, Windows Monitoring).  

---

## 📊 Example Dashboards  

- **System Overview (CPU, Memory, Disk, Network)**  
- **Process Monitoring Dashboard**  
- **Redis Metrics Dashboard**  

--- 

---

## 🔑 Keywords (SEO Optimized)  

Grafana Windows installation, Prometheus Windows setup, Grafana Prometheus Windows monitoring, Windows Exporter WMI, Redis Exporter Windows, Python Exporter, Grafana Dashboard Import, Windows Server monitoring Grafana, Prometheus exporters Windows, Node Exporter alternative Windows.  
