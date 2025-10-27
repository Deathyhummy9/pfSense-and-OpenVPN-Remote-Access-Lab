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


first head over to  pfsense and install the pfsense .iso for the image for the virtual machine then head to virtual box and change the senond adpater to an interal net work you will do the same for linuxs(clients) first adapater for the lab to work head to storage and in the empty disk but the iso image

<img width="960" height="776" alt="pf1" src="https://github.com/user-attachments/assets/4bebfffd-eb3d-4496-8be7-1849c8da4f26" />
<img width="1909" height="1028" alt="pf2" src="https://github.com/user-attachments/assets/db6e92c4-607a-470a-90c1-07fe8c633feb" />



Step 2  Installing and configing pfsense
-
Start the VM go throught with the intsalltion procees as regualr  and once its donereboot and press option 2 to set the ip interface from 192.168.1.100/24 to 192.168.1.5
<br />
<img width="1917" height="1080" alt="pf3" src="https://github.com/user-attachments/assets/bede2461-9b65-4239-a104-3e117b1d50b2" />
<img width="1906" height="981" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/f8158f42-f8b8-4a23-b863-89ccbd52f567" />

Step 3 linux V
-
set up the linux VM go to netowkr setting in the first adpater choose interal make sure its the same as pfsense vm start it up and head to the ip 192.168.1.100  to make sure it has connected to pfsense the go to bash and type ifconfig and see the ip address
<img width="1914" height="1071" alt="pf4" src="https://github.com/user-attachments/assets/7d90892c-7776-4b12-827d-ccc44196ef5a" />
<img width="1917" height="1020" alt="pf6" src="https://github.com/user-attachments/assets/54cf91d0-a21f-49e7-a0c9-c8470e421277" />


