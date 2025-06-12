# Port Scanning

Used to identify open ports on a target system by sending probe packets. This helps attackers find potential entry points for exploitation.

## Description  
Port scanning checks which ports are open, closed, or filtered on a host.

## Tools  
- Nmap  
- Netcat  
- Masscan  

## Nmap Commands  
`nmap -p- <target>` – Scan all 65535 ports  
`nmap -p 21,22,80 <target>` – Scan specific ports  
`nmap -Pn -p- <target>` – All ports, no ping  
`nmap -sS <target>` – SYN (stealth) scan  
`nmap -sT <target>` – TCP Connect scan  
`nmap -sU <target>` – UDP scan

## Use Case  
Used to detect open and potentially vulnerable ports on the target system.
