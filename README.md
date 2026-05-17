<h1>Microsoft Defender Endpoint -Onboarding a VM & Alert Investigation</h1>

<H2>Creating a VM in Windows</H2>

<b>Process:</b> `Azure Services - Virtual Machines - Create + - Select Resource Group - Give VM Name - Select Region - Select Zone - Select Image - Select OS Disk Type - Select VM - Select Subnet - Select public inbound ports (Allow Selected Ports) - Select Port 3389 (If Testing) - Review & Create`

<H2>Onboarding VM to MDE</H2>

<b>Process:</b> `MDE - Settings - Endpoints - Device Management - Onboarding - Download Onboarding Package - Click Zip File (Download as Administrator) - Type Y to run in PowerShell - Go back to MDE - Assets - Devices - Check Name of VM - Check active onboarded status`

<H2>VM Isolation & Investigation</H2>

 <p>
<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/53908e60559f2b54e183f6e7ffba2da37afafa41/Screenshot%202026-05-16%20at%2016.12.57.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/4cd6150275b1246cfe0c50bea12c6219cafaa430/Screenshot%202026-05-16%20at%2016.19.12.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/4cd6150275b1246cfe0c50bea12c6219cafaa430/Screenshot%202026-05-16%20at%2016.19.12.png" width="300" height="300" /> 
</p>

<b>Screenshot1:</b> Shows me sending a PING to the VM's IP address checking whether the host is reachable and responding on the network using ICMP echo requests and replies.<br>
<b>Screenshot2:</b> Shows a table for distinct action types within the log, you can then find using "where" for deeper analysis<br>
<b>Screenshot3:</b> Shows a table the number of failed login from external IP addresses, IoC of a brute force attack <br>
