# Azure_SIEM_neeyam

Project Overview:
This project includes setting up a SIEM system by using Microsoft Sentinel on Azure services. 
It is configured to monitor RDP sign-ins to the Azure VM and generates alerts when a successful RDP sign in occurs.
The goal was to build a simple yet effective SIEM system using Azure's cloud security tools.

Tools/Technology Used:
- Microsoft Azure
- Microsoft Sentinel
- Azure Virual Machine
- RDP
- Azure Log Analytics
- Azure Monitor

SetUp & Configuration 
- Deploying the Virtual Machine (Using Azure)
  A windows based VM was created on Microsoft Azure using the their 1st tier Subscription. While creating this VM, RDP access was enabled to allow login attempts.
  Operating System: Windows 10 PRO
  Default Configuration, Open ports for RDP(TCP/3389)

- Configuring Microsoft Sentinel
After deploying the VM, Microsoft Sentinel was deployed as the SIEM solution to monitor logs and detect security events.
- Creating Log Analytics workspace - Default Configurations were used. 
- After creating Microsoft Sentinel it is linked with the log analytics to enable log collection and monitoring
- Installed Windows Security events (AMA) and configured data connectors in Microsoft Sentinels to pull logs from the VM.

- Created Custom alert rules to monitor RDP sign-ins and log any suspicious activity.
The custom rule detects RDP login events, involving successful RDP logins. Failed login attempts were filtered out for this rule.
The rules were configured in Microsoft Sentinel to run every 5 minutes and notify when the conditions were met.

Testing the config
- Multiple tests of manual RDP logins to the Azure Virtual machine were performed every 5 minutes.
- I tested different scenarios of successful and failed logins

Final Results:
Microsoft Sentinel Logs successfully generated RDP login alert after tests. 
The project is capable of alerting on unauthorized access attempts via RDP. 


