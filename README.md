<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Create Resouces (Linex/Windows)
- Download/Filter Wireshark
- Initiating Perpetual Ping/Non-stop
- Observing SSH/DHCP/DNS/RDP Traffic

<h2>Actions and Observations</h2>

<p>
<h3>Phase One</h3>
  
![Azure Compute and Network Protocols Phase 1 - Imgur](https://github.com/PhillisEssel/azure-network-protocols/assets/156061642/fa3763c7-e55d-48fd-a140-6175d33bdfb2)

<p><a href="https://imgur.com/a/eHTbMqv">More</a></p>

</p>
<p>
Open Azure and create a Resouce Group. Then Create a VM on Windows 10/11 using the resouce group and allow the VM to create a new Virtual Network(Vnet) and Subnet. Next create another VM on Linex using the same resouce group and Vnet. Then observe the Virtual Network within Network Watcher. Now open Remote Desktop to connect to Windows 10 VM, then install Wireshark Windows 64x Installer and filter ICMP traffic. Use the Private IP address of the Linex VM and ping to it from Windows VM (should see request/reply traffic from both machines). Next in Windows VM, opem command line or Powershell and ping a public website(www.google.com) and observe traffic in Wireshark. 
</p>
<br />

<p>
<h3>Phase Two</h3>
  
![Azure Compute and Network Protocols Phase 2 - Imgur](https://github.com/PhillisEssel/azure-network-protocols/assets/156061642/552356c2-74bb-489a-a4c7-3d7d4f55263c)

<p><a href="https://imgur.com/a/JE2Bu3h">More</a></p>
  
</p>
<p>
Then after clear your data and initiate perpetual/non-stop ping from Windows VM to Linex VM. Go to Network Security Group on Azure of Linex VM and disable incoming (in bound) ICMP traffic and observe the traffic in Wireshrk from Windows. Re-enable ICMP traffic in NSG and then observe the traffic in Wireshark again. Next observe ssh traffic by using Windows Powershell to input Linex private IP address. Type commands into linex SSH connection and observe the traffic then type "exit" in Powershell when done. 
</p>
<br />

<p>
<h3>Phase Three</h3>
  
![Azure Compute and Network Protocols Phase 3 - Imgur](https://github.com/PhillisEssel/azure-network-protocols/assets/156061642/9ba9f543-5e3b-41a0-8bf4-c3f5ca961b9b)

<p><a href="https://imgur.com/a/Q5jTQzW">More</a></p>
  
</p>
<p>
Next clear your data and filter for DHCP traffic in Wireshark. In Windows VM issue a new IP address (ipconfig/renew) in Powershell and observe the traffic in Wireshark. Once again clear your data to observe DNS traffic on Wireshark and use Windows VM to type nsloopup in Powershell for any public website (disney.com). To observe RDP traffic in Wireshark filter for RDP and it will be non-stop due to you being currently active on the desktop.
</p>
<br />
