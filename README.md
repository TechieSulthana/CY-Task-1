# Task1: Scanning Local Network for Open Ports

## objective: >
  Perform a TCP SYN scan on a target host using Nmap to identify open ports
  and running services. Helps understand the host's network footprint and potential attack surfaces.

## tools_used:
  - Nmap 7.98
  - Command line interface (Windows terminal / Linux shell)

## steps_performed:
  - Opened terminal and ran the Nmap SYN scan command:
      command: "nmap -sS -oN scan_results.txt 10.xxx.xxx.xxx"
      options:
        - "-sS: TCP SYN scan (stealth scan)"
        - "-oN scan_results.txt: Save output in normal text format"
        - "10.xxx.xxx.xxx: Target IP"
  - Analyzed the scan output to identify open ports and services

## scan_results:
  host: 10.xxx.xxx.xxx
  status: up
  open_tcp_ports:
    - port: 135
      state: open
      service: msrpc
    - port: 139
      state: open
      service: netbios-ssn
    - port: 445
      state: open
      service: microsoft-ds
    - port: 7070
      state: open
      service: realserver
  closed_ports_count: 996

## observations:
  - Common Microsoft services are running (MSRPC, NetBIOS-SSN, Microsoft-DS)
  - Port 7070 running realserver, often used for streaming/web media
  - Host is responsive and reachable

## conclusion: >
  The Nmap scan identified 4 open TCP ports, which could be potential targets
  for further network security testing or penetration testing exercises.
  Ensure scanning is authorized to avoid legal issues.

## deliverables:
  - scan_results.txt
  - README.md

