<h1>Global Heat Map: Honeypot - Failed RDP Logins</h1>


<h2>Brief Description</h2>
This project involves the implementation of a vulnerable virtual machine configured to allow unrestricted inbound and outbound traffic without constraints on the Firewall. A Powershell script is then used to continuously extract security event ID 4625 (indicating failed log-on attempts) from the Windows Event Viewer. Additionally, the script captures API requests to "ipgeolocation," translating source IP addresses into Longitude and Latitude data. This data is then ingested into Microsoft Sentinel to be mapped out for visualization. 

<h2>Project Objective</h2>
This project aims to vividly illustrate the swift exploitation of misconfigured workstations exposed on the web. Threat actors globally engage in rapid brute-force attacks, highlighting the inherent risks to organizational security.


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 

<h2>Environments Used </h2>

- <b>Azure</b> (21H2)
- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
