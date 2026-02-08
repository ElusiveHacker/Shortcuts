# Zsh Profile - Custom Aliases for pentest & Options Explained

## Core Zsh Options (setopt)
These configure fundamental shell behavior for better usability:

| Option | Explanation |
|--------|-------------|
| `autocd` | Change directory by typing just the directory name (no `cd` needed) |
| `interactivecomments` | Allow `#` comments on interactive command lines |
| `magicequalsubst` | Expand `anything=expression` arguments (e.g., `app=/path/to/app`) |
| `nonomatch` | Silently ignore unmatched globs instead of erroring |
| `notify` | Report background job status immediately |
| `numericglobsort` | Sort filenames numerically (e.g., `file2.txt` before `file10.txt`) |
| `promptsubst` | Enable command substitution (`$(...)`) in prompts |

## Custom Aliases

### Security/Pentesting Aliases
Quick access for cybersecurity workflows (Kali Linux style):

- `c='clear'` – Fast screen clear
- `getrepo='git clone'` – Quick repository cloning
- `nmaptcp='sudo nmap -n -Pn -d -sS --open -p- -T4 --min-rate=10000'`  
  **Flags**: No DNS (`-n`), skip host discovery (`-Pn`), debug (`-d`), SYN scan (`-sS`), open ports only (`--open`), all ports (`-p-`), aggressive timing (`-T4`), high rate
- `nmapudp='sudo nmap -n -Pn -d -sU --open -p- -T4 --min-rate=10000'`  
  **Like above but UDP scan** (`-sU`)
- `nmaptcpversion='sudo nmap -d -sCSV -T4 --min-rate=10000 -p'` – TCP version scan (CSV output; specify ports)
- `nmapudoversion='sudo nmap -d -sCUV -T4 --min-rate=10000 -p'` – UDP + scripts + versions (specify ports)

### Interactive/File Aliases
Productivity shortcuts with color support:

| Alias | Command | Purpose |
|-------|---------|---------|
| `history="history 0"` | `history 0` | Show **complete** history (no limit) |
| `ls` | `ls --color=auto` | Colored directory listing |
| `ll` | `ls -l` | Long format listing |
| `la` | `ls -A` | List all except `.` and `..` |
| `l` | `ls -CF` | Classified list (executable appends `*`) |
| `grep` | `grep --color=auto` | Colored pattern search |
| `fgrep`/`egrep` | Fixed/extended regex with color | Pattern variants |
| `diff` | `diff --color=auto` | Colored file comparison |
| `ip` | `ip --color=auto` | Colored network interface info |
