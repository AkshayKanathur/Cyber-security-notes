# Network Mapping

The process of discovering hosts, identifying services, and building a layout of the target network.

## Description  
Network mapping gives an overview of live systems, services running, and the operating system behind them.

## Tools  
- Nmap  
- Netdiscover  
- ARP-scan  

## Nmap Commands  
`nmap <target>` – Basic scan  
`nmap -sV <target>` – Detect service versions  
`nmap -O <target>` – Detect operating system  
`nmap -A <target>` – Aggressive scan (OS, version, scripts)  
`nmap -sS -T4 <target>` – Fast stealth scan  
`nmap -sn <target>` – Ping scan only (host discovery)

## Use Case  
Used to map out the network layout, identify hosts, detect services and OS to support later attack planning.
