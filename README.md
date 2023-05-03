# Setup a Network with Ubiquiti Equipment
Network Walkthrough | Ubiquiti
<h2>Description</h2>
Our company uses Ubiquiti products for networks we setup (when possible). We are able to set a network up within the Unifi portal very quickly due to the fact that it is easily navigable, user friendly, and we can have multiple devices managed in one location. We will be doing a basic walkthrough on how to setup a network, whether it be home or for a business, via this portal. 
<br />

<h2>Program walk-through:</h2>

<p align="center">
<br/>
•	Before starting this guide you can reference this link for the UDM Pro Quick start guide. 
<br/>
http://dl-origin.ubnt.com/qsg/UDM-Pro/UDM-Pro_EN.html
<br/>
<img src="https://i.imgur.com/Vbdy94k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<br/>
<br/>
•	Today we will be setting up a Unifi Dream Machine Pro, a 16-port Switch with POE, Unifi 6 lite Access Point, and 2 Uninfi UAP Beacons.
<br/>
<img src="https://i.imgur.com/PKgIIxs.jpg" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<br/>
<br/>
•	The first thing we need to do is setup and register a new account.
<br/>
<img src="https://i.imgur.com/9G3rSDA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<br/>
• Link your internet router (or fiber if possible) and UDM together by putting a patch cable into your UDM (port 9) from the router. <br/>
•	Download the Unifi App on your phone or you can plug directly into a port (Port 2) from your computer using a patch cable. The device will pop up and you can assign it to your account and name it.<br/>
<img src="https://i.imgur.com/HnmcfPp.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<img src="https://i.imgur.com/L1olHVS.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<img src="https://i.imgur.com/YsQLzeX.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<br/>
<br/>
•Connect to UDMP at 192.168.1.1 
<br/>
<img src="https://i.imgur.com/hXaycb6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/ <br/>
<br/>
<br/>
<br/>
• If it tells you to “Enable Config Backup”, go to Settings -> Updates <br/>
<img src="https://i.imgur.com/qvaIR2A.png" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<br/>
<br/>
• Then go to System, click on “Automate Cloud Config Backup” and provide your password to generate the encryption key  <br/>
<img src="https://i.imgur.com/XJbKcnn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
•	Now go back and update (Allow UDMP to COMPLETELY update BEFORE plugging in any other devices). 
<br/>
<br/>
<img src="https://i.imgur.com/w5yGv6s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<img src="https://i.imgur.com/Ltn5Ywb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/
<br/>
<br/>
<br/>
<br/>
•	Now go to Settings>Networks> and click on the default router <br/>
<img src="https://i.imgur.com/jltFjwM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
• Change name to MGMT, change address to 10.1.150.1/24 and click Save <br/>
<img src="https://i.imgur.com/oRC8E8c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
• Unplug your computer from UDMP, Reconnect it <br/>
• Verify that your computer is getting a DHCP address in the 10.1.150 scheme (If it is not, your switch and devices will not, so this is very important).
 <br/>
<img src="https://i.imgur.com/3csntTm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
<br/>
• Create Remaining Networks as needed.
<br/>
<img src="https://i.imgur.com/vca3Bs7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<img src="https://i.imgur.com/uuHR10R.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
•	It should now look something like this.
<br/>
<img src="https://i.imgur.com/mNcpSKY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
<br/>
•We are now going to setup Wifi Networks. Go to Settings -> Wireless Networks. <br/>
• Create Wireless Networks per VLANS above.
<br/>
<img src="https://i.imgur.com/U4cJopR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<img src="https://i.imgur.com/07GX9cJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
It should now look like this.<br/>
<img src="https://i.imgur.com/yIuRB3d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
<br/>
•	Now we can Pull in Devices <br/>
•	Plug Switches into ports on UDMP.  Ensure they get a DHCP address in the 10.1.150 scheme.  If they don’t, do not adopt them. Figure out why they are not grabbing the proper address (Port profile of their uplink port is a good place to start)—Do not adopt a Unifi device that is not properly on the MGMT LAN. 
<br/>
•	Do not adopt anything else until the switches that are plugged directly into the UDMP are completely updated and adopted.
<br/>
<img src="https://i.imgur.com/f3UEjWS.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
• Now we can adopt our Access Points. <br/>
•	REMEMBER- Ports that Switches, Access Points, Etc. are plugged into should have a port profile of ‘All’ and should be pulling an address in the 10.1.150 scheme.  If they are not, stop.  Something is wrong. <br/>
<br/>
<br/>
<br/>
<br/>
• Once all devices are adopted, set static Ips.<br/>
• Go to Network -> Static IP<br/>
•	IP address= Whatever the AP IP is, should be automatic<br/>
•	Preferred DNS= 9.9.9.9 <br/>
•	Subnet Mask= 255.255.255.0 <br/>
•	Gateway=  10.1.150.1 (the MGMT IP Range) <br/>
<br/>
<img src="https://i.imgur.com/Cayt0cE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<img src="https://i.imgur.com/8uxKeg0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
<br/>
•	For this network I have decided I will also add AC Beacons to quickly extend wireless coverage and improve throughput.
<br/>
<img src="https://i.imgur.com/l4805Aa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<br/>
•	Our network is now setup !
<br/>
<img src="https://i.imgur.com/dY0PNhu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
<br/>
<img src="https://i.imgur.com/va3EVpl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br/>
