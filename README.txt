COMP5002 – BOTSv3 Incident Analysis
=================================

Author: Jitha Nipunika  
Module: COMP5002 – Security Operations & Incident Management  
Institution: Plymouth University  
Tool Used: Splunk Enterprise  
Dataset: BOTSv3 (Boss of the SOC v3)

------------------------------------------------------------

1. Introduction
---------------

This repository contains coursework for COMP5002 – Security Operations & Incident Management. 
The assignment focuses on analysing a simulated cyber security incident using the Boss of the SOC v3 (BOTSv3) dataset.

The investigation is carried out using Splunk Enterprise to analyse email, endpoint, and network-based security events.
The aim is to demonstrate practical SOC investigation skills, log analysis techniques, and incident response processes.

------------------------------------------------------------

2. SOC Context & Incident Handling
---------------------------------

A Security Operations Centre (SOC) is responsible for continuous monitoring, detection, investigation, and response to cyber security incidents.

In this assignment, the SOC activities include:
- Monitoring logs across multiple sources
- Detecting suspicious activity
- Investigating attack techniques
- Identifying compromised users and systems
- Extracting evidence using Splunk SPL queries

The BOTSv3 dataset simulates a real-world enterprise environment, allowing investigation of realistic attacker behaviour.

------------------------------------------------------------

3. Roles & Responsibilities
---------------------------

SOC Analyst responsibilities demonstrated in this project include:
- Event monitoring and alert analysis
- Incident triage and validation
- Log correlation across platforms
- Evidence collection and reporting
- Post-incident analysis and reflection

------------------------------------------------------------

4. Environment Setup & Installation
-----------------------------------

Environment:
- OS: Ubuntu Linux (VirtualBox)
- Splunk Enterprise (Linux .deb package)

Installation steps:
1. Install Ubuntu in VirtualBox
2. Install Splunk Enterprise
3. Enable Splunk web interface
4. Configure Splunk to start at boot

Splunk Web Interface:
http://localhost:8000

------------------------------------------------------------

5. Data Preparation
-------------------

Dataset Used:
- BOTSv3 dataset (botsv3_data_set.tgz)

Steps:
1. Download BOTSv3 dataset
2. Extract dataset files
3. Upload data into Splunk
4. Verify data ingestion
5. Confirm index=botsv3 exists
6. Validate sourcetypes (Sysmon, O365, SMTP, Netstat, Osquery)

Screenshots were taken to show:
- Successful data upload
- Index validation
- Sourcetype verification

------------------------------------------------------------

6. Guided Questions (BOTSv3 Q&A)
-------------------------------

Question 1: OneDrive Malicious Link Upload
- Identified malicious .lnk file upload to OneDrive
- Extracted full User-Agent string using O365 logs

Question 2: Macro-enabled Malicious Attachment
- Analysed SMTP logs
- Identified macro-enabled malware attachment

Question 3: Embedded Executable in Malware
- Used Sysmon Event ID 11
- Identified executable embedded in malicious document

Question 4: Linux User Creation
- Investigated Osquery logs
- Identified user creation by root
- Extracted password used during account creation

Question 5: Compromised Endpoint User
- Analysed Windows Security Event ID 4720
- Identified newly created user after compromise

Question 6: Group Assignments
- Analysed Event IDs 4728 and 4732
- Identified groups assigned to compromised user

Question 7: Leet Port Process
- Analysed Netstat / Osquery logs
- Identified process listening on leet ports

Question 8: Network Scanner MD5 Hash
- Analysed Sysmon process execution events
- Extracted MD5 hash of scanning tool

Each question includes:
- SPL query
- Evidence screenshots
- Explanation of findings

------------------------------------------------------------

7. Reflection
-------------

This investigation provided hands-on experience with SOC-style incident handling.
Key learning outcomes include:
- Practical Splunk SPL usage
- Log correlation across platforms
- Understanding attacker persistence techniques
- Importance of endpoint visibility
- Evidence-based incident reporting

------------------------------------------------------------

8. Conclusion
-------------

This project demonstrates the application of security operations knowledge in a realistic incident investigation scenario.
Using Splunk and the BOTSv3 dataset, multiple attack stages were successfully identified and analysed.

The assignment highlights the importance of SOC processes, log visibility, and structured investigation methods in responding to cyber security incidents.

------------------------------------------------------------

9. References




