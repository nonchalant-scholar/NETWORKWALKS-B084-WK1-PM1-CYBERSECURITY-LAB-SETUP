Networkwalks Cybersecurity Internship — Week 1
Project Module 1: VirtualBox and Kali Linux Lab Setup
1. Project Overview
This project documents the setup and verification of a cybersecurity lab environment using Oracle VirtualBox and Kali Linux as part of the Networkwalks Cybersecurity Internship.
The objective was to prepare a virtual machine for cybersecurity practice, configure its network connectivity, verify internet access, and organize the evidence of the completed setup.
2. Objectives

Install and configure the Kali Linux virtual machine in VirtualBox.
Configure the virtual network using a NAT Network.
Verify the Kali Linux network configuration.
Test connectivity and internet access.
Configure and verify shared-folder access between the host and virtual machine.
Create a virtual machine snapshot.
Document the setup and verification process with screenshots.

3. Lab Environment



Component
Configuration




Host operating system
Windows 11


Virtualization software
Oracle VirtualBox


Guest operating system
Kali Linux 2026.2


Network mode
NAT Network


Network subnet
10.0.0.0/24


Kali Linux IP address
10.0.0.3/24


Default gateway
10.0.0.1


Shared folder
Host Downloads folder, accessible inside Kali Linux



4. Network Configuration
The Kali Linux virtual machine was connected to a VirtualBox NAT Network.
The following network configuration was observed inside Kali Linux:

Network interface: eth0
IPv4 address: 10.0.0.3/24
Default gateway: 10.0.0.1
Network subnet: 10.0.0.0/24

The IP address was checked using:
ip -4 addr

The default route was checked using:
ip route

The observed IP address was 10.0.0.3/24. This is the address assigned to the Kali Linux virtual machine in the configured environment.

5. Connectivity Verification
Network connectivity was tested from Kali Linux.
Commands used
ping -c 4 10.0.0.2

ping -c 4 8.8.8.8

ping -c 4 google.com

The connection to 10.0.0.2 was successful. Internet connectivity was also tested, including an external IP address and a domain name.
These checks help verify local network communication, external connectivity, and DNS resolution.
Note: The results of individual tests may depend on network conditions and firewall settings.

6. Shared Folder and Virtual Machine Integration
A shared folder was configured to provide access to files from the Windows host inside Kali Linux.
The shared folder was visible on the Kali Linux desktop as:
sf_download

This setup helps transfer lab materials between the host operating system and the virtual machine.

7. Virtual Machine Snapshot
A snapshot was created after configuring the virtual machine.
A snapshot provides a recovery point that can be used to return the VM to a previously saved state if later experiments cause configuration problems.

8. Evidence and Screenshots
The following screenshots are stored in this repository's screenshots directory. GitHub uses the image paths below to display them directly in this README.
1. Successful Kali Linux Boot

Evidence of the Kali Linux virtual machine starting successfully.
2. VirtualBox Network Settings

Evidence of the virtual machine's network configuration in VirtualBox.
3. Kali Linux Network Configuration

Evidence documenting the Kali Linux network configuration.
4. Connectivity Test

Evidence of the connectivity test performed during lab verification.

9. Troubleshooting and Observations
During the setup and verification process, the following checks were useful:

Confirming that the correct virtual network was selected in VirtualBox.
Checking the assigned IP address and default gateway.
Testing local network connectivity.
Verifying internet connectivity separately from local connectivity.
Confirming that the shared folder was visible inside Kali Linux.

These checks help isolate common virtual machine networking and integration issues.

10. Learning Outcomes
Through this lab, I practised:

Configuring a Kali Linux virtual machine in VirtualBox.
Understanding NAT Network configuration and IPv4 addressing.
Inspecting network interfaces and routing information in Linux.
Testing local and external network connectivity.
Accessing shared folders between a host and guest operating system.
Using snapshots to support safer lab experimentation.
Documenting technical work with reproducible commands and screenshots.

11. Scope and Responsible Use
This environment is intended for educational cybersecurity practice. Any future scanning, testing, or exploitation activities will be conducted only against systems for which explicit authorization has been granted.

12. Conclusion
The Week 1 lab established a Kali Linux virtual machine for cybersecurity learning. Network configuration, connectivity, shared-folder access, and snapshot creation were addressed, and screenshots were organized as supporting evidence.
This repository documents the setup process and provides a foundation for subsequent authorized cybersecurity lab exercises.

Program: Networkwalks Cybersecurity Internship
Module: Week 1 — Project Module 1
Focus: VirtualBox and Kali Linux Lab Setup
