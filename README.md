# homelab-kvm-hypervisor

# homelab-kvm-hypervisor
 
> Production-grade KVM/QEMU hypervisor lab built during SIWES industrial training at Nigerian Navy QUORRA. Three VMs, three physical disks, full Active Directory domain, Docker services stack.
 
## Lab Architecture
 
**Host:** Ubuntu 24.04.3 LTS | KVM/QEMU 8.2.2 | libvirt 10.0.0
 
VM
OS
IP
vCPU
RAM
Role
DC01
Windows Server 2022
192.168.10.10
2
8GB
AD DS, DNS, DHCP
SRV01
Ubuntu 24.04
192.168.10.120
4
10GB
Services (Ubuntu 24)
SRV02
Ubuntu 20.04
192.168.10.121
4
10GB
Docker, Apache, DB
 
## Storage Layout
 
• nvme0n1 (238.5GB SSD) — Ubuntu host + /var/lib/libvirt/images (active VMs)
• sda (465.6GB HDD) — /mnt/data — ISO storage, file shares, backups
• sdb (465.6GB HDD) — /mnt/backup — VM snapshots, AD backups, DB dumps
 
## Network
 
• Virtual network: labnet (192.168.10.0/24) — NAT mode via libvirt
• DHCP served by DC01 — range 192.168.10.50–200
• DNS: DC01 (192.168.10.10) primary, 8.8.8.8 fallback
• Host bridge: br0 on enp2s0
 
## What's in This Repo
 
• Day 1 Journal — KVM/libvirt installation, storage setup, network troubleshooting
• Day 2 Journal — DC01 deployment, Windows Server 2022, AD DS promotion
• Day 3 Journal — SRV01 verification, OS downgrade decision, SRV02 deployment
• Errors & Resolutions — 15+ documented incidents with root causes and fixes
 
## Key Skills Demonstrated
 
• KVM/QEMU hypervisor configuration on bare metal Ubuntu
• libvirt storage pool and virtual network management (virsh)
• Windows Server 2022 deployment and Active Directory configuration
• VirtIO driver installation for paravirtualized disk and network
• Active Directory Domain Services — forest creation and DC promotion
• DHCP scope configuration and AD authorization
• SSH tunneling for VNC console access through NAT networks
• Multi-disk storage architecture with persistent fstab mounts
• VM XML configuration editing for hardware changes
• Docker infrastructure planning and Ubuntu 20.04 server deployment
 
## Stack
 
• Hypervisor: KVM/QEMU 8.2.2 + libvirt 10.0.0
• Host OS: Ubuntu 24.04.3 LTS
• VM1: Windows Server 2022 Standard Evaluation
• VM2: Ubuntu Server 24.04.3 LTS
• VM3: Ubuntu Server 20.04.6 LTS
• Networking: libvirt NAT + Linux bridge (br0)
• Storage: qcow2 disk images + ext4 HDD mounts
 
## About
 
Built by Demilade — Cybersecurity student at Lead City University, Nigeria. Currently on SIWES industrial training at Nigerian Navy QUORRA. Aspiring SOC Analyst and Digital Forensics specialist. Security+ in progress.
 
