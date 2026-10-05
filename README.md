# Cybersecurity Noted & Lab Write-ups
Welcome to my cybersecurity learning portfolio! This repository documents my hands-on labs, system configurations, and security research

## Lab 01: Kali Linux VM Setup & Storage Expansion 💽
- **Target OS:** Kali Linux
- **Hypervisor:** VirtualBox 7
- **Objective:** Resolve "No space left on device" errors and expand the main system partition (`sda1`).

### Troubleshooting & Steps Taken
1. **Virtual Disk Resizing:** Expanded `KaliLinux_.vdi` from 20 GB to 80 GB in VirtualBox Virtual Media Manager.
2. **Terminal Recovery:** Booted into TTY (`Ctrl`+`Alt`+`F3`) and freed immediate cache space using `sudo apt clean`
3. **Partition Adjustment:** Used `GParted` to remove swap barriers and resized `/dev/sda1` to utilize the full 80 GB capacity.