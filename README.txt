GROUP 36 — CYBER SECURITY CA-II
Project: Network Reconnaissance and Security Assessment Using Nmap: A Practical Case Study

STUDENTS
Akarsh Khot — PRN 23070123012
Amreet Anooj — PRN 23070123018

PURPOSE AND SCOPE
This package documents an authorized local assessment on the student's own Windows laptop. All Nmap scans targeted 127.0.0.1 (localhost). This checks the same computer only; it does not prove reachability from another device or the internet. No third-party host was scanned.

TOOLS
- Microsoft Windows
- Nmap 7.992
- Windows PowerShell

HOW TO REPEAT THE PRACTICAL
1. Install Nmap for Windows from https://nmap.org/download.html
2. Open Command Prompt or PowerShell.
3. Verify the installation:
   nmap --version
4. Run the initial localhost scan:
   nmap -sT -Pn 127.0.0.1
5. Save the initial output:
   nmap -sT -Pn 127.0.0.1 -oN nmap_results.txt
6. Run service/version detection on the observed ports:
   nmap -sT -Pn -sV --version-light -p 135,445,1042,7778 127.0.0.1 -oN nmap_service_verification.txt
7. After confirming firewall profiles are enabled, repeat the scan:
   nmap -sT -Pn 127.0.0.1 -oN nmap_after_firewall.txt
8. Use documentation/powershell_checks.txt to review local listening ports, processes, firewall profiles and SMB settings.

OBSERVED RESULTS (16 OCTOBER 2026)
- Nmap version 7.992; target 127.0.0.1.
- Initial scan found four open TCP ports: 135, 445, 1042 and 7778; 996 of the default 1,000 common TCP ports were closed.
- Service detection identified Microsoft Windows RPC on port 135. The other service labels were not all conclusively verified.
- PowerShell linked ports 1042 and 7778 to ASUS-related processes bound to 127.0.0.1.
- SMB1 was disabled and SMB2 enabled.
- Firewall profiles were later verified as enabled for Domain, Private and Public.
- The repeated localhost scan returned the same four open ports.

GITHUB LINK
No GitHub repository link was provided for this project. If you have a repository, add its real URL here. Do not invent a link. If the project is not on GitHub, this README and the included source/evidence files provide the local execution instructions.

CONTENTS
scan_results/     Saved Nmap output files (copy the actual .txt outputs here if they are not already included)
screenshots/      Screenshots from the practical session
documentation/    PowerShell checks and methodology notes

SAFETY
Only scan systems for which you have explicit permission. Do not interpret a localhost scan as proof of remote exposure.
