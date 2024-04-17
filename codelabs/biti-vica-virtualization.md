summary: BITI VICA - Virtualization Basics
id: biti-vica-virtualization
categories: linux, virtualization
tags: biti, vica
status: Published
authors: Daniel Drack

# BITI VICA - Virtualization Basics

<!-- ------------------------ -->

## Before We Begin

Welcome to Virtualization Basics :-)

### What You’ll Learn

- Basics of virtualization

### What You'll Need

- a notebook
- access to the internet
- a thirst for knowledge, a clear mind and an insatiable urge to learn

### Further Reading

- [KodeKloud](https://kodekloud.com/)
- [Linux Foundation LFS151x](https://training.linuxfoundation.org/training/introduction-to-cloud-infrastructure-technologies/)

## Virtualization Basics (40min)

- What is virtualization?
  - Simulation vs. Emulation - is that important for virtualization?
- Why virtualization?

brainstorm in groups, four quadrants:

- What can be virtualized?
- Where do you see virtualization in your daily life?
- Advantages
- Disadvantages

## Compute / Network / Storage (60min)

Working out in groups:

- Compute virtualization + OS virtualization
- Network virtualization
- Storage virtualization

Address at least these points:

- What's the matter? What is virtualized? How does it work roughly?
- Important types, protocols, species, representatives?
- Advantages/disadvantages and potential?
- Common products, projects, tools, vendors?
- Where and whatfor is it used?

## Server Virtualization

- Type1 Hypervisor/VMM
  - HW virtualization on bare metal
  - KVM, Microsoft Hyper-V and VMware vSphere
- Type2 Hypervisor/VMM
  - HW virtualization on OS
  - VMware Workstation and Oracle VirtualBox
- Full virtualization vs. paravirtualization
- OS virtualization
  - Docker, LXC
- Performance impact

## Storage Virtualization

- DAS - Direct Attached Storage
  - USB
  - SATA / SCSI
  - NVME
- SAN - Storage Area Network (Block)
  - LUN
  - FC, FCoE, iSCSI
- NAS (File)
  - NFS / SMB(CIFS)

## Network Virtualization

- VLAN (Virtual Local Area Network)
  - VLAN ID, Tagging, Trunk, Broadcast Domain
- VXLAN (Virtual Extensible LAN)
  - VXLAN Segment, Tunnel Endpoint (VTEP), Network Identifier (VNI), Encapsulation
- SDN (Software Defined Networking)

## Assignment #1 Topics

One one-pager per term should be created from the following topics and presented in the next classroom session (max. 5 min).

Format: AsciiDoc or Markdown. Upload as zip file incl. any additional files (images etc.)

- SAN
- NAS
- Type 1 Hypervisor
- Type 2 Hypervisor
- VLAN
- VXLAN
- SDN
- OS Virtualization
- Performance Impact with Virtualization
- Problems and Limitations of Virtualization
- History of Virtualization
- Buzzword Cheatsheet
