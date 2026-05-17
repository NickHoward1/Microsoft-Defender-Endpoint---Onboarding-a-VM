<h1>Microsoft Defender Endpoint -Onboarding a VM & Alert Investigation</h1>

<H2>Creating a VM in Windows</H2>

<b>Process:</b> `Azure Services - Virtual Machines - Create + - Select Resource Group - Give VM Name - Select Region - Select Zone - Select Image - Select OS Disk Type - Select VM - Select Subnet - Select public inbound ports (Allow Selected Ports) - Select Port 3389 (If Testing) - Review & Create`

<H2>Onboarding VM to MDE</H2>

<b>Process:</b> `MDE - Settings - Endpoints - Device Management - Onboarding - Download Onboarding Package - Click Zip File (Download as Administrator) - Type Y to run in PowerShell - Go back to MDE - Assets - Devices - Check Name of VM - Check active onboarded status`

<H2>VM Isolation & Investigation</H2>

 <p>
<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/53908e60559f2b54e183f6e7ffba2da37afafa41/Screenshot%202026-05-16%20at%2016.12.57.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/4cd6150275b1246cfe0c50bea12c6219cafaa430/Screenshot%202026-05-16%20at%2016.19.12.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/077bfbf206952b8c57e81ddb1f6d8ed105a2b33f/Screenshot%202026-05-16%20at%2016.27.31.png" width="300" height="300" /> 
</p>

<b>Screenshot1:</b> Shows me sending a PING to the VM's IP address checking whether the host is reachable and responding on the network using ICMP echo requests and replies.<br>
<b>Screenshot2:</b> Shows a how I isolate the VM/device from the network. If we have a host that has been compromised and malware has been detected it is critical that we contain the virus to prevent it from spreading across the network, we can do this by isolating in MDE and then begin the remediation process of eradication, recovery and lesson learned.<br>
<b>Process:</b> `MDE - Assets - Devices - More action (Top right) - Isolate Device - PING IP address on terminal/powerShell to see ICMP has timed out.` <br>
<b>Screenshot3:</b> Shows the host has been released from isolation.<br>
<b>Process:</b> `MDE - Assets - Devices - More action (Top right) - Release Device - PING IP address on terminal/powerShell to see if the host is reachable.` <br>

<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/1c0d30b5e51bf06979fe721fa71341326baf0b06/Screenshot%202026-05-17%20at%2010.21.53.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

The screenshot above shows how I collected an investigation package, which would be required when escalating a confirmed true positive incident to a senior SOC analyst for further investigation and response activities.

<b>Process:</b> `MDE - Assets - Devices - More action (Top right) - Collect Investigation Package - Download`<br>

<H2>VM Creating logs & Searching using KQL</H2>

<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/8c8b7ef97cf1ea695fb0542e40f4484356f25159/Screenshot%202026-05-17%20at%2011.43.14.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/8c8b7ef97cf1ea695fb0542e40f4484356f25159/Screenshot%202026-05-17%20at%2011.43.14.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;

Above, you will see that I generated various logs by creating and deleting .txt files, as well as using Test-NetConnection across different ports to simulate network activity. In the second screenshot, I demonstrate how I used `DeviceFileEvents`, `DeviceProcessEvents`, `DeviceNetworkEvents`, and `DeviceEvents` within Microsoft Defender to identify and investigate the generated telemetry and activity logs.

<H2>Remote Code Execution Detection</H2>

<img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/8c8b7ef97cf1ea695fb0542e40f4484356f25159/Screenshot%202026-05-17%20at%2011.43.14.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img src= "https://github.com/NickHoward1/Microsoft-Defender-Endpoint---Onboarding-a-VM/blob/8c8b7ef97cf1ea695fb0542e40f4484356f25159/Screenshot%202026-05-17%20at%2011.43.14.png" width="300" height="300"/> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;






