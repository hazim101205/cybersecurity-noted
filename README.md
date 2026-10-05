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


## Lab 02: Linux Security Log Analysis with `journalctl` & `grep` 📜

- **Target OS:** Kali Linux
- **Tools Used:** `journalctl`, `grep`, `tail`
- **Objective:** Analyze system authentication logs and inspect privilege escalation events[cite: 13].

### Key Findings & Technical Workflow
1. **Systemd Journal (`journalctl`):** Modern Kali Linux uses `systemd-journald` to manage logs dynamically rather than relying solely on static flat files like `/var/log/auth.log`.
2. **Log Filtering with `grep`:** Piped log telemetry (`journalctl | grep sudo`) to isolate root administrative actions and filter out system background noise.
3. **Authentication Tracking:** Verified that `pam_unix(sudo_session)` logs every instance when a user opens or closes a root privilege session.