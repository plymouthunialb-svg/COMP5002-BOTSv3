# COMP5002-BOTSv3

# COMP5002 – Assignment 2: BOTSv3 Incident Analysis

## Introduction
This repository contains my work for COMP5002 Assignment 2, which focuses on investigating
a simulated cyber security incident using the Boss of the SOC v3 (BOTSv3) dataset.
The analysis is conducted using Splunk to explore logs related to email, endpoint,
and network-based attacks within a simulated organisation.

The objective of this assignment is to demonstrate practical SOC investigation skills,
including log analysis, incident detection, and incident response, following
professional security operations practices.


## Environment Setup
•	Platform: VirtualBox (Linux VM)
•	SIEM Tool: Splunk Enterprise
•	Dataset: BOTSv3 (botsv3_data_set.tgz)
•	Browser: Firefox (Splunk Web UI)
•	Splunk Web Access:
http://localhost:8000

## Installation & Data Preparation
1.	Installed Splunk Enterprise on Linux VM
2.	Enabled Splunk at boot:
sudo /opt/splunk/bin/splunk enable boot-start

4.	Installed BOTSv3 App
5.	Uploaded and indexed BOTSv3 dataset
6.	Verified successful ingestion using:
eventcount summarize=false index=botsv3

## SOC Context and Incident Handling
This investigation is approached from the perspective of a Security Operations Centre (SOC).
The SOC is responsible for monitoring, detecting, analysing, and responding to security incidents.

SOC activities relevant to this investigation include:
- Initial detection of suspicious events
- Analysis and validation of alerts
- Incident escalation and response
- Post-incident review and improvement

Further analysis and reflections will be expanded as the investigation progresses.

---

## Environment Setup (In Progress)
Splunk Enterprise will be used as the primary analysis platform.
The BOTSv3 dataset will be ingested into Splunk following the official Splunk documentation.

Planned steps:

-Install git
<img width="957" height="333" alt="git install 1" src="https://github.com/user-attachments/assets/d94c4636-a69e-461f-be55-37abbf0b1f0f" />
<img width="603" height="37" alt="git install 4" src="https://github.com/user-attachments/assets/362e5c89-74bc-4d8c-9480-e0a5eb3bf92d" />
<img width="977" height="235" alt="git install 3" src="https://github.com/user-attachments/assets/587c108b-0057-44a8-9802-5e21fbdbdd1f" />
<img width="1787" height="605" alt="git install 2" src="https://github.com/user-attachments/assets/870a2323-2e5d-471c-a8f0-cb4c92fa13b8" />

- Install Splunk Enterprise
-<img width="1831" height="576" alt="splunk install 2" src="https://github.com/user-attachments/assets/fa87c919-784e-4fb8-8aca-3885dd7c5b92" />
<img width="1855" height="780" alt="splunk install 1" src="https://github.com/user-attachments/assets/d01d2892-620c-45ae-9760-0ed1dd8e2cdd" />
<img width="867" height="257" alt="splunk install 0" src="https://github.com/user-attachments/assets/86d6713a-ff3e-4812-9c8f-123df8a23d5a" />
- Download BOTSv3 dataset
  <img width="1842" height="477" alt="botsv3 run 1" src="https://github.com/user-attachments/assets/f05ddea9-1e9b-4344-ab52-0d74391338b9" />
<img width="1830" height="162" alt="botsv3 download" src="https://github.com/user-attachments/assets/627283e1-5e5f-4f5d-b777-3d25aaef5c5c" />
<img width="1833" height="187" alt="botsv3 download 1" src="https://github.com/user-attachments/assets/9fa001e0-2853-4ee2-8b91-e480166e0661" />
<img width="1552" height="771" alt="botsv3 run 2" src="https://github.com/user-attachments/assets/b07e3528-b02e-487b-8ce3-70a22fd83851" />
- Ingest logs into Splunk
<img width="1222" height="796" alt="botsv3 run 3" src="https://github.com/user-attachments/assets/5e974a66-9065-449d-ab2f-019bf68bbccb" />
<img width="1847" height="898" alt="botsv3 run 4" src="https://github.com/user-attachments/assets/f01e81d3-55eb-4ce3-8771-480b28646793" />
<img width="1737" height="732" alt="sp searc 2" src="https://github.com/user-attachments/assets/7ac28710-d128-4bbf-8a04-7df6ee6649f0" />

- Validate data sources and indexes
Data validation was conducted to confirm the successful ingestion of the BOTSv3 dataset into Splunk. The presence of the botsv3 index was verified using event count analysis, confirming active event ingestion. Multiple sourcetypes including Office 365 logs, Sysmon, Windows Security logs, netstat, and osquery results were identified, demonstrating comprehensive host and network telemetry coverage. Host-level validation further confirmed the availability of key endpoints used throughout the investigation.
<img width="733" height="522" alt="Time Range Validation" src="https://github.com/user-attachments/assets/f2e3f456-e5b6-4867-9962-cd2efb211085" />
<img width="725" height="457" alt="Validate Index Exists" src="https://github.com/user-attachments/assets/27d983a3-ab20-4539-bf1d-8d3103bbb261" />
<img width="733" height="476" alt="Validate Hosts" src="https://github.com/user-attachments/assets/d1120d73-f664-4cf6-8744-12961b7eb808" />
<img width="736" height="532" alt="Validate Data Sources (Sourcetypes)" src="https://github.com/user-attachments/assets/101536b2-e156-4790-a181-904d62da441d" />

## Guided Investigation Questions (Pending)
The BOTSv3 guided questions provided on the DLE will be answered using Splunk SPL queries.
Each answer will include:
-Question 1 – OneDrive Malicious Link Upload (User Agent)
Question:
You’re tasked to find the user agent that uploaded a malicious link file to OneDrive. What is the full user agent string that uploaded the malicious link file to OneDrive?
SPL Query:
index=botsv3 sourcetype=ms:o365:management Operation=FileUploaded FileExtension=lnk
How to identify the answer:
- Inspect returned events - Locate the UserAgent field - Copy the full user agent string
Answer:
userAgent: Mozslla/5.0 (Mlacintonh; Intel Mac 05 X 10-12; rv:61-0] Cecko/20100101 Farefox/61.@

____<img width="1728" height="806" alt="q1" src="https://github.com/user-attachments/assets/0e1141bc-aa32-454d-af1d-232242ae5109" />
__<img width="1360" height="502" alt="q1-2" src="https://github.com/user-attachments/assets/5b8f7718-dfb5-4109-be2a-3e980d59c901" />
__________________________________
Question 2 – Macro-enabled Malicious Attachment
Question:
What was the name of the macro-enabled attachment identified as malware?
SPL Query:
index=botsv3 sourcetype=stream:smtp malware
How to identify the answer:
- Look for alerts indicating malicious attachments - Check fields such as file_name or attachment
Answer:
Malware Alert Text.txt
<img width="1735" height="797" alt="q2" src="https://github.com/user-attachments/assets/a64be8a0-9f7e-4657-84e6-a4d0888fea94" />

__<img width="1717" height="868" alt="q2-1" src="https://github.com/user-attachments/assets/08444cbd-5cd4-48cb-9bed-f86a6a1f9aed" />
_____<img width="730" height="525" alt="q2-4" src="https://github.com/user-attachments/assets/d1b58280-dc83-4a06-9c60-92e2f6bbb237" />
<img width="726" height="525" alt="q2-3" src="https://github.com/user-attachments/assets/539004ff-5028-4732-932e-fe63e85dfd20" />
_________________________________
Question 3 – Embedded Executable in Malware
Question:
What is the name of the executable that was embedded in the malware?
SPL Query:
index=botsv3 sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" *.docm OR *.xlsm
How to identify the answer:
- Inspect Image or CommandLine fields - Identify the executed .exe file
Answer:
•  Sourcetype: XmlWinEventLog:Microsoft-Windows-Sysmon/Operational
•  EventID: 11
•  Host: BGIST-L
•  Malicious document:
Frothly-Brewery-Financial-Planning-FY2019-Draft[66].xlsm
•  Executable involved:
HxTsr.exe

____<img width="730" height="532" alt="q3-2" src="https://github.com/user-attachments/assets/e2f78377-1f73-4ce1-a244-5051873e1bb9" />
<img width="742" height="542" alt="q3-1" src="https://github.com/user-attachments/assets/3226120c-b3d3-4376-96aa-ddc446ab8fa9" />
____________________________________
Question 4 – Linux User Creation Password
Question:
What is the password for the user that was successfully created by the user “root” on the on‑premises Linux system?
SPL Query:
index=botsv3 sourcetype=osquery:results host=hoth "useradd" "root"
How to identify the answer:
- Look for useradd or passwd commands - Inspect command output carefully
Answer:
On August 20, 2018 at 16:54:54, a new user account named tomcat7 was created on the system using the useradd command executed by root. The account was assigned UID 0, granting full root privileges, and a password was set directly via the command line. This behavior is highly suspicious and indicates attacker persistence through the creation of a privileged backdoor account.


<img width="723" height="528" alt="q4 3" src="https://github.com/user-attachments/assets/19ab1d16-0798-4db6-93ec-11bdb2f4ad9b" />
<img width="786" height="593" alt="q4" src="https://github.com/user-attachments/assets/0c1ed71a-8724-4890-981f-c42dff345f8b" />
<img width="753" height="557" alt="q4 2" src="https://github.com/user-attachments/assets/38c48d18-0312-4c8c-97d6-25e22d532d85" />
__________________________________
Question 5 – Compromised Endpoint User Creation
Question:
What is the name of the user that was created after the endpoint was compromised?
SPL Query:
index=botsv3 sourcetype="WinEventLog:Security" EventCode=4720
How to identify the answer:
- Locate the TargetUserName field
Answer:
•  EventCode: 4720 (User account created)
•  Host: FYODOR-L
•  Sourcetype: WinEventLog:Security

<img width="731" height="520" alt="q5-1" src="https://github.com/user-attachments/assets/a3993fcd-33a9-4e01-a492-4b659234535e" />

________________________________________
Question 6 – Groups Assigned to the User
Question:
What groups was this user assigned to after the endpoint was compromised?
SPL Query:
index=botsv3 sourcetype="WinEventLog:Security" EventCode=4728 OR EventCode=4732
How to identify the answer:
- Collect all group names - Sort alphabetically - Present as comma-separated (no spaces)
Answer:
Administrators,Remote Desktop Users
<img width="735" height="538" alt="q6-2" src="https://github.com/user-attachments/assets/2a6c909a-25c4-4aa7-b285-1e7f93f4ce45" />
<img width="730" height="540" alt="q6-1" src="https://github.com/user-attachments/assets/ce348e26-559a-4ddb-93b4-35135055c43a" />

________________________________________
Question 7 – Leet Port Process ID
Question:
What is the process ID of the process listening on a “leet” port?
SPL Query:
sourcetype=osquery host=hoth leet
How to identify the answer:
- Identify ports such as 1337 - Note the corresponding pid
Answer:
1337 and 31337
<img width="723" height="466" alt="q7-2" src="https://github.com/user-attachments/assets/4aba3f2a-6d06-4b65-a6f0-05d029dd1820" />
<img width="731" height="527" alt="q7-1" src="https://github.com/user-attachments/assets/e8ea0347-9d0e-4a3c-90ee-7c23467f7311" />

________________________________________
Question 8 – MD5 Hash of Network Scanner
Question:
What is the MD5 value of the file downloaded to Fyodor’s endpoint system and used to scan Frothly’s network?
SPL Query:
index=botsv3 sourcetype="XmlWinEventLog:Microsoft-Windows-Sysmon/Operational" | stats count by EventCode
How to identify the answer:
- Inspect Hashes field - Extract the MD5 value
Answer:
BCC8F29B929DABF5489C9BE6587FF66D
<img width="728" height="477" alt="q8 2" src="https://github.com/user-attachments/assets/792d2dcc-fc39-4221-97b5-8ff2f0088202" />

___<img width="735" height="512" alt="q8 1" src="https://github.com/user-attachments/assets/e342f7c3-c33f-4731-8f14-89ca3c4bbad6" />
_____________________________________


---

## Conclusion (To be completed)
This investigation successfully demonstrated a structured SOC-style incident analysis using the BOTSv3 dataset and Splunk. The findings reveal a multi-stage attack involving malicious email delivery, macro-enabled malware execution, privilege escalation, account persistence, and network reconnaissance.

By correlating logs across multiple data sources, the investigation highlights the importance of centralised logging, continuous monitoring, and skilled analysis in detecting and responding to cyber threats. The techniques used in this investigation closely mirror real-world SOC operations and reinforce the value of practical security analytics in modern organisations

## References
References will be added where appropriate.


