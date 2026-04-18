# 🧠 Mini Container Runtime with Kernel Monitoring

## 📌 Overview
This project implements a lightweight container runtime in C with a supervisor process and a kernel module for memory monitoring.

---

## ⚙️ Features

- Multi-container support (alpha, beta)
- CLI commands (`run`, `ps`, `logs`)
- Supervisor using UNIX sockets (IPC)
- Container logging
- Kernel module for memory monitoring
- Soft and Hard memory limits
- CPU scheduling experiment

---

## 🏗️ System Design

- **engine.c** → CLI + Supervisor
- **monitor.c** → Kernel module
- **IPC** → UNIX domain socket (`/tmp/mini_runtime.sock`)
- **Containers** → Isolated processes using rootfs

---

## 🚀 Build

```bash
make clean
make

Run Supervisor

commands
sudo ./engine supervisor ~/rootfs-base
in terminal 1
sudo ./engine run alpha ~/rootfs-alpha /bin/sh
sudo ./engine run beta ~/rootfs-beta /bin/sh
in terminal 1
sudo ./engine ps
<img width="1156" height="285" alt="WhatsApp Image 2026-04-18 at 6 38 29 PM" src="https://github.com/user-attachments/assets/40d833a4-0408-49fa-8f9e-da40774b95d2" />


