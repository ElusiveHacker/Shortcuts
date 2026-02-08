Here’s a **minimal README** that **mentions ONLY the pentesting / CTF aliases and functions**.
No shell config, no prompt, no fluff.

---

# Zsh Pentest / CTF Aliases

This Zsh profile defines a set of **offensive security–focused aliases and functions** optimized for **CTFs, labs, and pentests**.
Everything is designed for **speed, repeatability, and zero context switching**.

---

## Core Utility

| Alias | Purpose        |
| ----- | -------------- |
| `c`   | Clear terminal |

---

## Git / Tooling

| Alias           | Purpose                            |
| --------------- | ---------------------------------- |
| `getrepo <url>` | Clone exploit or tool repositories |

---

## Nmap Scanning Presets

High-speed scans with no DNS resolution and no host discovery.

| Alias                         | Description                   |
| ----------------------------- | ----------------------------- |
| `nmaptcp <IP>`                | Full TCP SYN scan (all ports) |
| `nmapudp <IP>`                | Full UDP scan (all ports)     |
| `nmaptcpversion <ports> <IP>` | TCP version + default scripts |
| `nmapudoversion <ports> <IP>` | UDP version + default scripts |

---

## Privilege Escalation Cheat Sheets

Printed directly to terminal.

| Command       | Description                                              |
| ------------- | -------------------------------------------------------- |
| `helpwindows` | Windows privilege escalation + file transfer cheatsheet  |
| `helplinux`   | Linux privilege escalation, file transfer, shell upgrade |

---

## Network Helpers

| Function        | Description                                         |
| --------------- | --------------------------------------------------- |
| `get_device_ip` | Resolve active local IP                             |
| `infostart`     | Show working dir, interface status (`eth0`, `tun0`) |

---

## File Transfer Servers

All servers run from `/home/jerry/Exploits` and auto-detect IP.

### FTP

| Command              | Description              |
| -------------------- | ------------------------ |
| `ftpstart`           | Anonymous RW FTP server  |
| `ftpstart user pass` | Authenticated FTP server |

### HTTP

| Command            | Description                       |
| ------------------ | --------------------------------- |
| `httpstart`        | Python HTTP server on port 80     |
| `httpstart <port>` | Python HTTP server on custom port |

Includes auto-printed Linux + Windows download commands.

---

## Netcat Listeners (rlwrap-enabled)

| Command | Port |
| ------- | ---- |
| `n4444` | 4444 |
| `n5555` | 5555 |
| `n443`  | 443  |
| `n80`   | 80   |
| `n53`   | 53   |

Each listener:

* Detects local IP
* Prints victim-side commands
* Uses `rlwrap` for shell usability

---

## Assumptions

* Kali / Debian-based OS
* VPN interface: `tun0`
* Working directory: `/home/jerry/Exploits`
* Tools available: `nmap`, `nc`, `python3`, `pyftpdlib`, `rlwrap`

---
