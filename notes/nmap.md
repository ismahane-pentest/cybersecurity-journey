# Nmap Notes

## Basic Commands
- `nmap <target>` — Basic scan
- `nmap -sV <target>` — Version detection
- `nmap -sC <target>` — Default scripts
- `nmap -p- <target>` — Scan all ports

## Advanced
- `-Pn` — Skip host discovery
- `-vv` — Verbose level 2
- `--script=vuln` — Vulnerability scripts
- `-oN`, `-oX`, `-oG` — Output formats

## Key Learnings
- SYN scan (`-sS`) is the default when root.
- NULL/FIN/Xmas scans work on Unix, not Windows.
- Firewalls may drop packets silently.
