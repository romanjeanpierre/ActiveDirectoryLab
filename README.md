<h1>Global Heat Map: Honeypot - Failed RDP Logins</h1>


<h2>Brief Description</h2>
This project involves the implementation of a vulnerable virtual machine configured to allow unrestricted inbound and outbound traffic without constraints on the Firewall. A Powershell script is then used to continuously extract security event ID 4625 (indicating failed log-on attempts) from the Windows Event Viewer. Additionally, the script captures API requests to "ipgeolocation", translating source IP addresses into Longitude and Latitude data. This data is then ingested into Microsoft Sentinel to be mapped out for visualization. 

<h2>Project Objective</h2>
This project aims to vividly illustrate the instantaneous exploitation of misconfigured workstations exposed on the web. Threat actors globally engage in rapid brute-force attacks, highlighting the inherent risks to organizational security.

<h2>Overview</h2>
<p align="center">
<img src="https://i.imgur.com/y3Aqek1.png" height="80%" width="80%">

<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>
- <b>Kusto Query Language (KQL)</b>
- <b>Windows 10</b>
- <b>Microsoft Azure</b>
- <b>Log Analytics Workspace<b>
- <b>Azure Sentinel (SIEM)<b>

<h2>Project walk-through:</h2>
Step 1: Deploy Virtual Machine
<p align="center">
Instance Details: <br/>
<img src="https://i.imgur.com/F8fdKPW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Networking Details:  <br/>
<img src="https://i.imgur.com/oGd6m6h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Misconfigure the VM to allow RDP traffic, create a new NIC network security group, remove existing inbound rules, and add a new inbound rule allowing any protocol
<br />
<br />
<br />
<br /></p>

Step 2: Config Environment
<p align="center">
<br/> Microsoft Defender: <br/>
<img src="https://i.imgur.com/OnKGVRq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Log Analytics Workspace:  <br/>
<img src="https://i.imgur.com/YP977ZY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Disable Firewall in VM:  <br/>
<img src="https://i.imgur.com/GyhISce.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Use Host Machine to verify if ICMP packets is reachable ping -t <VM IP address> 
<br />
<br />
<br />
<br /></p>

Step 3: Script Execution
 <p align="center">  <br/>
Powershell: Use Powershell script from github.com/Joshmadakor1 and input API key from IPGeolocation  <br/> <br/>
<img src="https://i.imgur.com/D7thSgi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<br/> 
<br/>
This script establishes a custom XML filter to detect failed Remote Desktop Protocol (RDP) logins in Windows Security Events. It involves setting variables, testing with a sample log, and storing output logs on the guest machine. The script further ingests event logs into Log Analytics workspaces, enriching the output with geographical data. The process initiates by defining variables, including the geolocation API key, log file details, and an XML filter targeting specific Security log events. The `write-Sample-Log` function generates sample log entries for training in Log Analytics workspaces. The primary script continuously monitors Windows Event Viewer logs using an infinite loop, extracting relevant details for each failed RDP login event, such as timestamp, event ID, destination host, username, source host, and source IP. Geolocation data is obtained via an API, and if the log entry is missing, the script appends the gathered data to a custom log file.

<br />
<br /> </p>

Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<br />


<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
