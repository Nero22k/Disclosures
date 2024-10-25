## Broken Access Controls (CVE-2024-48293)
Interesting logic bug that allowed to bypass the privilege check for the Antivirus dashboard, potentially enabling unauthorized tampering with Antivirus settings.

### Proof Of Concept
[![PoC](https://github.com/user-attachments/assets/f2aa024e-3608-4f5e-b661-59168429f741)](https://github.com/user-attachments/assets/f2aa024e-3608-4f5e-b661-59168429f741)

### Affected Version
x >= 24.1.0.182

### Timeline
- 30.08.24 : The vulnerability was discovered
- 01.09.24 : The vulnerability was reported to Secure@quickheal.com
- 04.09.24 : The report was accepted
- 19.09.24 : The report was triaged
- 08.10.24 : The vulnerability has been patched
