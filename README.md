<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>Actions and Observations</h2>

<p>
<img src=https://i.imgur.com/13YzSfe.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create two Virtual Machines, one will be microsoft 10 and the other will be linx 20.04. Once created, connect to your Windows 10 virtual machine &
install Wireshark. 
</p>
<br />

<p>
<img src=https://i.imgur.com/3HKrN2v.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Launch Wireshark and filter ICMP traffic only. ICMP stands for Internet Control Message Protocol, it diagnoses network communication issues. Next we will get the Ubuntu virtual machine's private IP address and try to ping it from the Windows 10 virtual machine by using windows powershell. To ascertain the connectivity of the remote servers, ping sends (ICMP) echo packets and gets echo packets in response to determine the connectivity of the remote servers.
</p>
<br />

<p>
<img src=https://i.imgur.com/FnMCnQs.png height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br /v>
<p>
<img src=https://i.imgur.com/6hIPjP9.png height="80%" width="80%" alt="Disk Sanitization Steps"/>  
</p>
<p>  
Next we will use the command ping -t to the Linux computer private ip address. The response from this command will be continuous or non-stop until we stop it.To stop the continuous pinging, we will go to the Linux virtual machine in azure and block inbound ICMP traffic on its firewall. We do this by creating a Network security group that block or deny any incoming traffic from ICMP. 
</p>
<br />

<p>
<img src= https://i.imgur.com/nWpAY6L.png height="80%" width="80%" alt="Disk Sanitization Steps"/>   
</P>
<p>
We will now explore into SSH traffic. SSH, short for secure shell,is a network protocol and a secure way of accessing a remote computer and communicate with another remote computer over an unsecured network. Next we will use SSH to connect with Linux Machine, go back to wireshark to filter SSH packets only.In your windows 10 vm use powershell to use command "ssh,username of Linux machine@private Ip address for connection".
