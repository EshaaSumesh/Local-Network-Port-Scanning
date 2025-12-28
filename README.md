
# Local Network Port Scanning

## Objective
To perform a local network scan using Nmap to identify live devices, open ports, running services and assess potential risks.

## Tools Used
- **Nmap** for port scanning
- **Kali Linux VM** (hosted via VirtualBox/NAT mode)

## Scanned Network
- **IP Range Scanned:** 10.0.2.0/24
- **Scan Type:** TCP SYN Scan (`-sS`)

##  Scan Results Summary

| IP Address | Open Ports | Services |
|------------|------------|----------|
| 10.0.2.2 | 135, 445, 902, 912, 3306, 5357 | msrpc, microsoft-ds, iss-realsecure, apex-mesh, mysql, wsdapi |
| 10.0.2.3 | Same as above | Same as above |
| 10.0.2.4 | Same as above | Same as above |
| 10.0.2.16 | 80 | http (web server on Kali) |

##  Risk Analysis

- **Port 445 (SMB)** is often exploited (e.g., EternalBlue).
- **Port 3306 (MySQL)** open can lead to data leakage if not protected.
- **Port 80** on Kali should be locked down if unnecessary.
- Unused services (902, 912, 5357) may increase attack surface.

##  Output
See `scan_results.txt` for raw Nmap output.

##  Additional Nmap Scans Performed

- `connect_scan.txt` — Full TCP Connect scan (`-sT`)
- `udp_scan.txt` — UDP port scan (`-sU`)
- `os_version_detection.txt` — OS and service detection (`-A`)
- `advanced_scan.txt` — Miscellaneous advanced scan output


