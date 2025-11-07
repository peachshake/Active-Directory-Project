# Active-Directory-Project

## Objective

To gain practical experience in Active Directory operations, log analysis, and security monitoring by configuring a full lab setup that includes an AD domain controller, Windows clients, Splunk SIEM, and an attacker machine for controlled testing. 

### Skills Learned

- Private Active Directory lab for hands-on domain administration and troubleshooting
- Splunk instance collecting and correlating logs from the AD domain controller and a target Windows host
- Kali Linux attacker VM running controlled brute-force tests and Atomic Red Team simulations to generate telemetry
- Architecture diagram illustrating components and telemetry/log flow

### Tools Used

- Splunk (SIEM) — Central log collection and analysis platform that ingests Windows Event Logs, forwards from Universal Forwarders, and hosts searches/dashboards for detection and forensic investigation.
- Kali Linux — Attacker VM used to run controlled offensive simulations against the lab to generate telemetry and test detection rules.
- Brute-force attack (lab-only, controlled) — Simulated credential-guessing activity used to produce authentication failure events and stress-test alerting and telemetry coverage (performed only inside an isolated lab environment).
- Atomic Red Team — MITRE ATT&CK–aligned test cases for reproducible adversary technique simulation, used to generate realistic telemetry and validate Splunk detections.

### Machines Used
- Windows Server
- Windows 10
- Kali 
- Splunk
- Sysmon 

## Steps
*Ref 1: Network Diagram*
<img width="1350" height="1126" alt="image" src="https://github.com/user-attachments/assets/28766758-f6f6-477b-9120-f5158de873f5" />

*Ref 2: Set up virtual machines using Virtualbox*
- Virtualbox: https://www.virtualbox.org/
- Window Server: https://www.microsoft.com/en-us/software-download/windows10
- Window 10: https://www.microsoft.com/en-us/software-download/windows10%20
- Splunk: https://www.splunk.com/en_us/download.html

*Ref 3: Download Sysmon *
- Sysmon : https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon
- Sysmon Config: https://github.com/olafhartong/sysmon-modular/blob/master/sysmonconfig.xml
<img width="1919" height="1035" alt="image" src="https://github.com/user-attachments/assets/cbda7f6d-4c4b-46d7-a4d8-4613483cc921" />

*Ref 3: Download and configure Splunk Universal Forwarder *
- https://www.splunk.com/en_us/download/universal-forwarder.html
- Instructing the Splunk Forwarder on what I want to send over to my Splunk Server by cretae and configure a file called inputs.conf located in C:> Program Files> SplunkUniversalForwarder> etc> system> local (do not edit the inputs file under the default directory
- Splunk inputs.config: https://github.com/MyDFIR/Active-Directory-Project
<img width="1106" height="1142" alt="image" src="https://github.com/user-attachments/assets/ddd6e369-9e7e-43b3-8198-14f7ff67e9e3" />
- index = endpoint: all the events are under the Application, Security, System, and Microsoft Windows Sysmon categories will be sent over to Splunk and placed under the index endpoint







