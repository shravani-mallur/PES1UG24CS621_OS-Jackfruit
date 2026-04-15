# Multi-Container Runtime Project

## Team Information

Name: Shravani Mallur
SRN: PES1UG24CS610

---

## Objective

To implement a lightweight container runtime using OS concepts like process management, IPC, and kernel modules.

---

## Components

* engine.c (User-space runtime)
* monitor.c (Kernel module)
* monitor_ioctl.h
* Workloads: cpu_hog, memory_hog, io_pulse

---

## Build Instructions

```bash
make
```

---

## Load Kernel Module

```bash
sudo insmod boilerplate/monitor.ko
ls -l /dev/container_monitor
```

---

## Run Supervisor

```bash
sudo ./boilerplate/engine supervisor ./rootfs-base
```

---

## Run Containers

```bash
sudo ./boilerplate/engine start alpha ./rootfs-alpha /bin/sh
sudo ./boilerplate/engine start beta ./rootfs-beta /bin/sh
```

---

## List Containers

```bash
sudo ./boilerplate/engine ps
```

---

## View Logs

```bash
sudo ./boilerplate/engine logs alpha
```

---

## Stop Containers

```bash
sudo ./boilerplate/engine stop alpha
```

---

## Memory Monitoring

```bash
sudo dmesg | tail
```

---

## Scheduling Demo

```bash
./boilerplate/cpu_hog
./boilerplate/io_pulse
```
<img width="1280" height="313" alt="image" src="https://github.com/user-attachments/assets/57664ea0-dad8-4ac4-89cc-a9e83a46b89f" />

<img width="1280" height="505" alt="image" src="https://github.com/user-attachments/assets/2e384ffe-dc53-4428-9847-6682345c2006" />



---

## Cleanup

```bash
sudo rmmod monitor
```

---

## Features

* Supervisor process
* CLI commands (start, ps, logs, stop)
* Kernel module for monitoring
* Scheduling experiments

