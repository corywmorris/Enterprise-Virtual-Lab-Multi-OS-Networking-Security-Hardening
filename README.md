# Enterprise-Virtual-Lab-Multi-OS-Networking-Security-Hardening
A full-stack virtual infrastructure project on Apple Silicon featuring custom ARM64 Windows 11 and Kali Linux builds. Includes advanced bridged networking, bi-directional connectivity verification, and host-based security hardening using UFW and Windows Defender.

1. Project Overview
This project demonstrates the deployment of a cross-platform virtual infrastructure on Apple Silicon hardware. It features a custom Windows 11 Pro (ARM64) environment and a Kali Linux node, integrated via an advanced bridged network. The lab focuses on infrastructure as code, bi-directional connectivity, and defense-in-depth security hardening.

2. Network Topology
The architecture consists of a host machine (macOS) running the UTM hypervisor, which bridges the virtual nodes to the physical network. Documentation is centrally managed through a cloud-integrated shared layer.

Figure 1: High-level network topology showing cloud-integrated virtual lab architecture.

3. Technical Implementation
Phase 1: Environment Provisioning
The Windows 11 environment was synthesized using custom ARM64 build scripts to ensure compatibility with Apple Silicon hardware.

Phase 2: Network Infrastructure
I configured a Bridged (Advanced) networking mode using the virtio-net-pci driver. This allowed both VMs to receive unique IP addresses from the local DHCP server, placing them on the same subnet (192.168.4.x) as the host.

Figure 2: Verifying Windows 11 IP assignment (192.168.4.71).

Phase 3: Connectivity Verification
To ensure the bridge was functioning correctly, I performed bi-directional ICMP echo requests (pings) between the Linux and Windows nodes.

Figure 3: Bi-directional connectivity verification between Kali Linux and Windows 11.

4. Security & Hardening
A core component of this lab was implementing host-based security measures to simulate a production environment:

Windows Hardening: Configured Windows Defender Firewall to a "Least Privilege" posture, blocking all non-authorized inbound traffic.

Linux Hardening: Implemented the Uncomplicated Firewall (UFW) on the Kali Linux node to manage ingress/egress filtering.

Patch Management: Executed full kernel and package updates across both platforms to mitigate known vulnerabilities.

Figure 4: Windows Defender Firewall hardening and state verification.

5. Administrative Documentation
Project governance was maintained through a centralized Office Network Plan, tracking IP allocations, MAC addresses, and system roles within a cloud-synced repository.

Figure 5: Cloud-integrated documentation workflow for project administration.

🛠 Skills Demonstrated
Virtualization: UTM, QEMU, ARM64 Architecture.

Networking: Bridged Networking, Subnetting, ICMP Troubleshooting.

Security: Windows Defender Firewall, Linux UFW, Patch Management.

Administration: Technical Documentation (SOP), Asset Management.
