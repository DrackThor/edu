summary: BITI VICA - Virtualization Basics
id: biti-vica-virtualization
categories: linux, virtualization
tags: biti, vica
status: Published
authors: Daniel Drack


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

- Create a brief but complete summary of one of the topics found below.
- Present your topic in class next time, with a maximum duration of 5 minutes.
- format: markdown
  - [introduction to markdown](https://www.markdownguide.org/getting-started/#:~:text=Markdown%20is%20a%20lightweight%20markup,than%20using%20a%20WYSIWYG%20editor)
  - [markdown tutorial](https://daringfireball.net/projects/markdown/basics)
  - [markdown tutorial video](https://youtu.be/bTVIMt3XllM?si=d4Vn_alZqPAYzzGY)
- Create a pull request with the content under your assigned headline in this document.
  - branchname: abgabe-<1/2>-<Nachname>; zB "abgabe-1-drack"
  - [Github PR docu](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)
  - [PR tutorial video](https://youtu.be/jRLGobWwA3Y?si=_lUhrRWYh8sLjZbO)
  - [GitHub create account docu](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github)
  - [Git Tutorial](https://www.w3schools.com/git/)
- Questions? eMail me asap.

**assessment criteria:**

- deadline: 25% - submitted in time?
- content: 25% - well written and complete?
- visualization: 25% - sources, pictures, examples?
- presentation: 25% - convincingly presented or simply read off 

**topics:**

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
