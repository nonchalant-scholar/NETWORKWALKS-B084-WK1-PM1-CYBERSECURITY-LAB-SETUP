Networkwalks Cybersecurity Internship — Week 1
Project Module 1: VirtualBox and Kali Linux Lab Setup
1. Project Overview
This project documents the setup and initial verification of a cybersecurity lab environment using Oracle VirtualBox and Kali Linux. The objective was to prepare a working virtual machine for cybersecurity practicals and verify its network connectivity.
The lab setup includes Kali Linux, a VirtualBox NAT Network, internet connectivity, and a shared folder for accessing files from the host system.
2. Objectives

Set up and boot Kali Linux in Oracle VirtualBox.
Configure the virtual machine's network adapter using a NAT Network.
Verify the assigned IP address, subnet, and default gateway.
Test network and internet connectivity.
Configure clipboard, drag-and-drop, and shared-folder settings.
Create a virtual machine snapshot for future lab work.
Document the configuration and verification evidence.

3. Lab Environment



Component
Configuration




Virtualization software
Oracle VirtualBox


Guest operating system
Kali Linux 2026.2


Network mode
NAT Network


NAT Network name
NatNetwork


Network subnet
10.0.0.0/24


Network mask
255.255.255.0


Kali network interface
eth0


Kali IPv4 address observed
10.0.0.3/24


Default gateway observed
10.0.0.1


DHCP server observed
10.0.0.2


Host shared-folder mount
sf_download


Snapshot
Created after lab setup



4. Network Configuration
The Kali Linux virtual machine was connected to the VirtualBox NAT Network named NatNetwork.
The configured network subnet was 10.0.0.0/24, with the subnet mask 255.255.255.0. The Kali Linux network interface eth0 received the IPv4 address 10.0.0.3/24.
The observed default gateway was 10.0.0.1. The VirtualBox DHCP server was identified at 10.0.0.2, with the DHCP address pool beginning at 10.0.0.3.
Observed configuration

Network interface: eth0
IPv4 address: 10.0.0.3/24
Subnet: 10.0.0.0/24
Default gateway: 10.0.0.1
DHCP server: 10.0.0.2

Configuration note: The project instructions specify 10.0.0.2/24 for Kali Linux. In this setup, VirtualBox uses 10.0.0.2 as its DHCP server address, and Kali received 10.0.0.3/24 dynamically. The actual working configuration is documented here rather than assigning the DHCP server's address to the Kali guest.
5. Network and Connectivity Verification
The following commands were used to inspect and verify the network configuration.
Check the IPv4 address
ip -4 addr

The output showed the Kali network interface eth0 with the address 10.0.0.3/24.
Check the routing table
ip route

The default route was observed through gateway 10.0.0.1, and the local network route covered 10.0.0.0/24.
Test connectivity to the NAT Network DHCP server
ping -c 4 10.0.0.2

Replies were received from 10.0.0.2, confirming connectivity to that address.
Test internet connectivity and DNS resolution
ping -c 4 google.com

The test returned four replies with zero packet loss, confirming that internet connectivity and hostname resolution were working at the time of testing.
6. Shared Folder and Virtual Machine Integration
A shared folder was configured to provide access to files from the Windows host system inside Kali Linux.
The shared folder appeared on the Kali Linux desktop as sf_download, and the files from the host's Downloads folder were visible inside it.
Clipboard and drag-and-drop options were also configured in the virtual machine settings to support interaction between the host and guest systems.
7. Virtual Machine Snapshot
A snapshot was created after the initial lab setup. This provides a restore point that can be used to return the virtual machine to its prepared state before performing further practical exercises.
8. Evidence and Screenshots
The following screenshots document the Kali Linux lab setup and network verification. All four images are stored in the repository's screenshots/ directory.
1. Kali Linux Startup

This screenshot documents the successful startup of the Kali Linux virtual machine.
2. VirtualBox Network Settings

This screenshot documents the virtual machine's network configuration.
3. Network Configuration

This screenshot provides evidence of the network configuration.
4. Connectivity Test

This screenshot documents the connectivity test performed during setup.
9. Troubleshooting and Observations
Observation 1: Kali received 10.0.0.3 instead of 10.0.0.2
The VirtualBox NAT Network DHCP configuration showed 10.0.0.2 as the DHCP server address and the dynamic address pool beginning at 10.0.0.3.
Resolution: The existing DHCP-assigned address was retained. Connectivity was verified, and the actual configuration was documented. The DHCP server address was not manually assigned to Kali.
Observation 2: Verifying internet access
An IP address alone does not establish that internet access is working.
Resolution: The command ping -c 4 google.com was used to test connectivity and hostname resolution. Four replies were received with zero packet loss during the test.
10. Learning Outcomes
Through this lab, I practised:

Preparing a Kali Linux virtual machine using Oracle VirtualBox.
Understanding NAT Network configuration and IPv4 addressing.
Inspecting network interfaces and routing information in Linux.
Identifying the role of a DHCP server and default gateway.
Verifying connectivity using the ping command.
Configuring shared-folder access between a host and guest operating system.
Maintaining a snapshot as a recovery point for future lab activities.
Recording technical evidence and documenting configuration observations.

11. Scope and Responsible Use
This environment was prepared for educational cybersecurity training and authorised lab exercises. Future testing will be conducted only on systems and networks for which permission has been granted.
12. Conclusion
The Kali Linux lab environment was successfully started and configured in Oracle VirtualBox. The NAT Network was operational, the guest received an IPv4 address, internet connectivity was verified, and shared-folder access was established.
The initial environment is ready for subsequent authorised cybersecurity practicals, subject to any additional requirements specified in future project modules.

Program: Networkwalks Cybersecurity Internship 2026
Week: 1
Module: Project Module 1 — Lab Setup: VirtualBox and Kali Linux
