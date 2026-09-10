# NETWORKWALKS-SANDRA-B083-WK1-MP1-CYBERSECURITY-LAB-SETUP
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

    ⚠️ Disclaimer: This laboratory must only be used for systems that you own or have explicit permission to test           Do not use the lab or its tools to attack unauthorized systems.
                                                                                                                       
                                                                                                                       
  
  🪜 Lab Setup Procedure
  
  
 Step 1. Install WinRAR
WinRAR was installed to extract the Kali Linux virtual-machine package, which is distributed as a compressed archive.

Tool: WinRAR


Step 2. Install VirtualBox
VirtualBox was installed as the hypervisor.

Tool: VirtualBox


  Step 3. Create the NAT Network
A dedicated NAT Network was created in VirtualBox.

Configuration:

. Network Name: NatNetwork

. IPv4 Prefix: 10.0.0.0/24

. DHCP: Enabled

. IPv6: Disabled


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
