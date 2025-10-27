<p align="center">
<img width="3060" height="900" alt="pfpick" src="https://github.com/user-attachments/assets/8e087e93-1923-46e5-b633-ad0a6734fc2d" />

</p>

<h1>pfSense and OpenVPN remote access lab</h1>
This project demonstrates how to configure pfSense as an OpenVPN server and connect a Linux client to securely route traffic through the VPN.
It simulates a typical remote employee VPN scenario, showcasing networking, firewall, and routing fundamentals<br />




<h2>Environments and Technologies Used</h2>

- pfSense
- virtual box
- Linux Mint (VirtualBox)
- OpenVPN

<h2>Operating Systems Used </h2>

- linux mint

- pfsense


<h2>List of Prerequisites</h2>

- pfSense ISO installed in VirtualBox

- installed Linux Mint and configured

- OpenVPN client installed on Linux

- pfSense firewall and LAN configured

- Internet connectivity verified

Step 1 getting the virtual machine read
-
Download the pfSense ISO image and create a new VirtualBox VM.

For the pfSense VM: set the second adapter to “Internal Network.”

For the Linux (client) VM: set the first adapter to the same internal network as pfSense.

Go to Storage and mount the pfSense ISO on the pfSense VM.

<img width="960" height="776" alt="pf1" src="https://github.com/user-attachments/assets/4bebfffd-eb3d-4496-8be7-1849c8da4f26" />
<img width="1909" height="1028" alt="pf2" src="https://github.com/user-attachments/assets/db6e92c4-607a-470a-90c1-07fe8c633feb" />



Step 2  Installing and configing pfsense
-
Start the pfSense VM and go through the installation process normally.

After installation and reboot, select Option 2 in the console to configure the LAN IP.

Change the IP from 192.168.1.100/24 to 192.168.1.5.

Confirm you can access pfSense at https://192.168.1.5 from the host client machine once installed
<br />
<img width="1917" height="1080" alt="pf3" src="https://github.com/user-attachments/assets/bede2461-9b65-4239-a104-3e117b1d50b2" />
<img width="1906" height="981" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/f8158f42-f8b8-4a23-b863-89ccbd52f567" />

Step 3 Setting up linux VM(client)
-
Configure the Linux VM network settings:

First adapter = Internal Network (same as pfSense)

Boot the VM and open the browser to https://192.168.1.5 to verify connectivity to pfSense.

In the terminal, run: if config should be the ip address assigend 192.168.1.100

<img width="1914" height="1071" alt="pf4" src="https://github.com/user-attachments/assets/7d90892c-7776-4b12-827d-ccc44196ef5a" />
<img width="1917" height="1020" alt="pf6" src="https://github.com/user-attachments/assets/54cf91d0-a21f-49e7-a0c9-c8470e421277" />

Step 4 Estahblishing OpenVPN
-
Log in to pfSense web UI.

Go to VPN → OpenVPN and add a new server.

Create a new Certificate Authority (CA) and Server Certificate during setup.

For Local IP, use 192.168.1.100; for the Remote Tunnel IP, use something like 192.168.1.200 (or your VPN tunnel network).

Next, go to System → User Manager and create a new user.

Link the user to the CA you created.

 Note: Each user should have their own certificate of authority .

<img width="1911" height="1023" alt="pf7" src="https://github.com/user-attachments/assets/5d2c2cde-1f8b-4d48-b523-e86927994f5b" />
<img width="1911" height="1037" alt="pf8" src="https://github.com/user-attachments/assets/bfca3e22-4574-48d0-a845-37a0c4b3b9a1" />

Step 5 Confriming connection
-
On the Linux client, run:

ip route

 It should show the default route going through pfSense.

Then run:

curl ifconfig.me

 It should display your public IP from the pfSense WAN.

Finally, run:

mtr 8.8.8.8

It should show traffic going from the Linux client → pfSense VPN → Internet
 
<img width="1929" height="1046" alt="pf9" src="https://github.com/user-attachments/assets/b2ae3223-55e6-42bb-8175-759ed64e6d9e" />
<img width="1914" height="1080" alt="pf10" src="https://github.com/user-attachments/assets/2d561416-1a0b-4242-ad92-f85c18b82f1b" />


### why it matters
This lab simulates a realistic remote access VPN deployment. It demonstrates skills in VPN configuration, firewall rules, routing, and network troubleshooting — all of which are directly relevant to IT Support, SysAdmin, and Network Admin roles

 Lab Environment Info
- pfSense Version: 2.7.1
- OpenVPN Version: 2.6.x
- Linux Mint 21.2
- VirtualBox 7.0

