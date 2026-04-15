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

<img width="1280" height="50" alt="image" src="https://github.com/user-attachments/assets/444f9d9c-2b62-4c4a-af4b-884abce3f8d1" />

---

## List Containers

```bash
sudo ./boilerplate/engine ps
```
<img width="1130" height="98" alt="image" src="https://github.com/user-attachments/assets/b48a622c-f579-4e88-944e-4b3af7464d71" />



---

## View Logs

```bash
sudo ./boilerplate/engine logs alpha
```
<img width="1134" height="78" alt="image" src="https://github.com/user-attachments/assets/a51ff498-de66-40e9-9782-2259271dacbe" />


---

## Stop Containers

```bash
sudo ./boilerplate/engine stop alpha
```
<img width="1136" height="46" alt="image" src="https://github.com/user-attachments/assets/542f8e67-febc-4a5f-9839-f373a46d2bb7" />


---

## Memory Monitoring

```bash
sudo dmesg | tail
```
<img width="1280" height="656" alt="image" src="https://github.com/user-attachments/assets/0bf77818-04be-49d4-8335-11984659738e" />


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

