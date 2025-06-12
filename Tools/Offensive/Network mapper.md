# Nmap

A powerful network scanning tool used to discover live hosts, open ports, services, and OS information on a target system. Commonly used during reconnaissance to map the network and identify potential entry points.

## Description  
Performs port scanning, service/version detection, and OS fingerprinting.

## Command  
`nmap <target>` – Basic scan  
`nmap -sV <target>` – Service/version detection  
`nmap -p- <target>` – Scan all ports  
`nmap -A <target>` – Aggressive scan (OS + version + script)  
`nmap -Pn <target>` – No ping (treat host as up)  
`nmap -sS -T4 <target>` – Stealth scan, faster timing

## Scan Types

- `-sS` → **SYN Scan** (stealthy, fast, default for root)
- `-sT` → **TCP Connect Scan** (full TCP handshake; used when not root)
- `-sU` → **UDP Scan** (scans for open UDP ports)
- `-sV` → **Version Detection** (detects service versions)
- `-sA` → **ACK Scan** (maps firewall rules)
- `-sF` → **FIN Scan** (stealthy, may bypass firewalls)
- `-sN` → **Null Scan** (no flags; evasion technique)
- `-sX` → **Xmas Scan** (FIN, PSH, URG flags set; firewall evasion)

## Use Case  
Used to identify open ports, running services, and OS details to assess possible vulnerabilities or attack vectors.
