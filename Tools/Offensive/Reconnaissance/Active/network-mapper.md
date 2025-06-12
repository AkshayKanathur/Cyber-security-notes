# Nmap

A powerful network scanning tool used to discover live hosts, open ports, services, and OS information on a target system. Commonly used during reconnaissance to map networks and identify potential entry points.

## Description  
Performs host discovery, port scanning, service/version detection, and OS fingerprinting.

## Use Case  
Used to identify open ports, running services, and OS details to assess possible vulnerabilities or attack vectors.

---

## Common Commands  

- `nmap <target>` – Basic scan  
- `nmap -sV <target>` – Service/version detection  
- `nmap -p- <target>` – Scan all 65535 ports  
- `nmap -A <target>` – Aggressive scan (OS + version + script)  
- `nmap -Pn <target>` – No ping (assume host is up)  
- `nmap -sS -T4 <target>` – SYN scan (stealthy, fast timing)  
- `nmap -sC <target>` – Run default scripts  
- `nmap -O <target>` – OS detection  
- `nmap -T4 <target>` – Speed up scan (T1–T5, higher = faster, less accurate)  
- `nmap -iL targets.txt` – Scan multiple targets from a file  
- `nmap -oN output.txt` – Save output to a file  
- `nmap -sS -p 22,80,443 <target>` – Scan specific ports  
- `nmap --script vuln <target>` – Run vulnerability detection scripts

---

## Scan Types

- `-sS` → **SYN Scan** – Stealthy and fast (default for root)
- `-sT` → **TCP Connect Scan** – Full TCP handshake; used when not root
- `-sU` → **UDP Scan** – Scans open UDP ports (slow)
- `-sV` → **Version Detection** – Detects service versions
- `-sA` → **ACK Scan** – Maps firewall rules
- `-sF` → **FIN Scan** – May bypass some firewalls
- `-sN` → **Null Scan** – No flags; basic evasion
- `-sX` → **Xmas Scan** – FIN, PSH, URG flags set; advanced evasion
- `-sC` → **Default Scripts** – Runs built-in NSE scripts
- `-sP` → **Ping Scan** – Check which hosts are up (now `-sn`)

---

## Output Options

- `-oN output.txt` – Normal output
- `-oX output.xml` – XML output
- `-oG output.gnmap` – Grepable output
- `-oA basename` – All formats at once (basename.nmap/.xml/.gnmap)

---

## Tips

- Use `-Pn` when ICMP is blocked (e.g., cloud/VPS)
- Combine `-sS -sV -O -T4` for fast detailed scans
- Use `--top-ports 100` for quick scans of common ports
- `nmap --script-help=default` to see default script explanations

---
