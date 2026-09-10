<img width="929" height="500" alt="421245" src="https://github.com/user-attachments/assets/c5403f00-49c5-4c8d-b7ca-b8ac3603c7f2" /># NETWORKWALKS-SANDRA-B083-WK1-MP1-CYBERSECURITY-LAB-SETUP
Virtual cybersecurity Lab setup using virtual Box &amp; Kali Linux for ethical Hacking and cybersecurity practice(Networkwalks B083 Week1).


_____
  🔐 Cybersecurity Lab Environment Setup.
  
Building an isolated virtual lab for penetration testing and ethical hacking practice

____
  📌 Project OverView
  
This project focuses on setting up a virtual cybersecurity and penetration-testing laboratory using VirtualBox and Kali Linux.

The purpose of the lab is to create a controlled environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely and repeatedly.
The lab is configured on a private virtual network so that additional machines can be added later and used as targets for authorized security testing.


🎯 OBJECTIVES

The main objectives of this project are to:

. Install and configure VirtualBox.

. Install/import Kali Linux as a virtual machine.

. Create a private NAT Network for the cybersecurity lab.

. Configure network connectivity for Kali Linux.

. Assign a consistent IP address to the Kali VM.

. Verify network connectivity and DNS resolution.

. Take a clean VM snapshot for recovery.

. Document the complete setup process.

. Prepare the environment for future cybersecurity projects.


 🛡️ PURPOSE OF THE LAB
 
The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:
. Network reconnaissance

. Port scanning

. Vulnerability assessment

. Packet analysis

. Web security testing

. Exploitation practice

. Security-tool experimentation

    ⚠️ Disclaimer: This laboratory must only be used for systems that you own or have explicit permission to test. Do not use the lab or its tools to attack unauthorized systems.
                                                                                                                                                             
  
  🪜 Lab Setup Procedure
  
  
 Step 1. Install WinRAR
WinRAR was installed to extract the Kali Linux virtual-machine package, which is distributed as a compressed archive.

Tool: WinRAR
<img width="728" height="404" alt="421248" src="https://github.com/user-attachments/assets/79569bb9-e75f-4dbe-b73b-01a88d82c703" />


Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

Tool: VirtualBox
<img width="952" height="516" alt="421247" src="https://github.com/user-attachments/assets/cf082307-50a1-45ad-b0a8-d4070d56929e" />
<img width="598" height="260" alt="421255" src="https://github.com/user-attachments/assets/2076ccd5-65a5-4fce-b369-696f54f30b7b" />


  Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration:

. Network Name: NatNetwork

. IPv4 Prefix: 10.0.0.0/24

. DHCP: Enabled

. IPv6: Disabled

<img width="947" height="506" alt="421237" src="https://github.com/user-attachments/assets/cb23af59-edf7-4450-9c5d-2d1f4e910c25" />

A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with one another while also having outbound network connectivity. This will allow future attacker and target VMs to communicate within the lab.



 Step 4. Import Kali Linux VM
The Kali Linux virtual machine was downloaded and imported into VirtualBox as a pre-built appliance.

Tool: Kali Linux VirtualBox Images
A pre-built Kali image was used instead of a manual install to save setup time and ensure a stable, verified base image for the lab.



Step 5. Attach Kali to the NAT Network
The Kali VM's network adapter was configured to connect to the custom NAT Network created in Step 3.

. Configuration:Adapter 1: Enabled

. Attached to: NAT Network

. Name: NatNetwork

. Promiscuous Mode: Allow All

Promiscuous Mode was set to "Allow All" so Kali can capture and analyze traffic from other VMs on the same network — this is required for packet sniffing and network scanning tools to work correctly in the lab.
<img width="959" height="538" alt="421240" src="https://github.com/user-attachments/assets/9ea72150-a8a3-4989-b79f-174e3833e135" />

Step 6. Assign a Static IP to Kali
DHCP was disabled on the Kali VM and a static IP was configured instead, to keep the machine's address consistent across reboots.

.🧩 Setting     . ⚙️ Value

.Method          . Manual

.Address         .10.0.0.2

.Netmask         . 24 (255.255.255.0)

.Gateway         . 10.0.0.1

.DNS             .  8.8.8.8

A static IP was used instead of DHCP because tools like Nmap, Metasploit, and Wireshark rely on knowing the exact IP of the attacking machine — a changing IP would break repeatability of the lab.

Step 7. Verify Network Connectivity
Connectivity was tested between Kali and the gateway/DNS to confirm the network was functioning correctly.

.ping 10.0.0.1

.ping 8.8.8.8

.ping google.com

.<img width="904" height="524" alt="421243" src="https://github.com/user-attachments/assets/71ec0282-86ba-4a27-a1aa-f21d70f37558" />


A successful ping to the gateway confirms local network connectivity, while a successful ping to an external domain confirms both internet access and DNS resolution are working.

⚠️ Known Issue (Kali 2026.1+): If internet connectivity fails after setting a static IP, run:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

Step 8. Take a Clean Snapshot:
Once networking was confirmed to be working, a VirtualBox snapshot was taken of the Kali VM.

A snapshot at this stage provides a clean, working checkpoint to restore to if the VM is later broken by tool installs, misconfigurations, or testing activity.

Step 9. Document the Setup:
Each configuration step was recorded with screenshots to create a repeatable reference for rebuilding or extending the lab.
