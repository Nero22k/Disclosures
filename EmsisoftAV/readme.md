# CVE-2024-XXXX: Link Following Local Privilege Escalation in Emsisoft Antivirus

https://github.com/user-attachments/assets/17e8bb0b-ebd5-4bb3-b569-7e3373f5a992

## Description
A vulnerability in Emsisoft Antivirus allows local attackers to escalate privileges. The flaw exists within the Emsisoft service `a2service.exe`, which runs with `NT AUTHORITY\SYSTEM` privileges. By creating a symbolic link, an attacker can manipulate the service to delete folders or files, leading to privilege escalation and enabling arbitrary code execution in the SYSTEM context.

## Vulnerability Type
Local Privilege Escalation

## Vendor
Emsisoft

## Affected Product
- Emsisoft Anti-Malware Home

## Affected Version
- Versions >= 2024.10.0.12557

## Attack Type
Local

## Impact
Escalation of privileges to SYSTEM, granting full control over the system.

## Attack Vector
To exploit this vulnerability, an attacker must have the ability to execute low-privileged code on the target system. By creating a symbolic link, the attacker can abuse `a2service.exe` to delete arbitrary files or folders, leading to privilege escalation.

## Reference
[Emsisoft Antivirus](https://www.emsisoft.com/en/)
