summary: BITI VICA - Virtual Machines and IaC
id: biti-vica-vm-iac
categories: linux, virtualization, iac
tags: biti, vica, iac
status: Published
authors: Daniel Drack

# BITI VICA - Virtual Machines and IaC

<!-- ------------------------ -->

## Before We Begin

Welcome to Virtual Machines and IaC :-)

### What You’ll Learn

- Basics of Virtual Machines and IaC
- Basics of ExoScale

### What You'll Need

- a notebook
- access to the internet
- `terraform` installed locally
- Exoscale access
- a thirst for knowledge, a clear mind and an insatiable urge to learn

### Further Reading

- [KodeKloud](https://kodekloud.com/)
- [Exoscale Docs](https://community.exoscale.com/)
- [HasciCorp Tutorials](https://developer.hashicorp.com/terraform/tutorials)

## Infrastructure-as-Code: Basics

<aside class="negative">
Let's provision a virtual machine in the cloud, manually! :D
</aside>

- access [https://portal.exoscale.com/](https://portal.exoscale.com/)
- "Compute" -> "Instances" -> "ADD"
- provide a name
- select the `template`: "Linux Ubuntu 22.04 LTS 64-bit"
- select `zone`: "AT-VIE-1"
- select `instance type`: "Standard - Small"
- select `disk size`: "50GB"
- "ADD"

- "Compute" -> "Security Groups" -> "ADD"
- `name`: "public"
- "ADD"
- "Compute" -> "Security Groups" -> "public"
- "ADD RULE" -> "SSH"
- "Instances" (Tab) -> "ATTACH" -> "<my-machine>"

<aside class="negative">
Now let's reset the password and access the machine via SSH. <br>
Recap: What do we see under the hood?
</aside>

```shell
# show me all attached block devices
lsblk

# show me all filesystems
df -h

# show me all network interfaces
ip a

# are we a VM?
systemd-detect-virt
dmesg | grep -i kvm
lscpu
# Virtualization features:
#   Virtualization:        VT-x
#   Hypervisor vendor:     KVM
#   Virtualization type:   full
```

## Why IaC?

- What's the issue with "UI" clicking?
- What's so cool about Code?
  - Idempotecy
  - Versioning
  - Distribution
  - Desired State
  - Reproducability
  - Time
  - CRUD

Prerequisites:

- API! Examples?
- Tooling

## Exoscale API

<aside class="negative">
Now, let's we do the same thing as before, but as code! :D
</aside>

- first we need to create a proper role
  - "IAM" -> "ROLES" -> "ADD"
  - `name`: demo
  - "ADD SERVICE CLASS": `compute`
  - "CREATE"
- then we need to create an API key pair
  - "IAM" -> "KEYS" -> "ADD"
  - `name`: demo
  - `Role`: demo

- create a new folder on your local machine
- create the follwing files in that folder

```hcl
# terraform.tf
terraform {
  required_providers {
    exoscale = {
      source = "exoscale/exoscale"
    }
  }
}

provider "exoscale" {
  key      = "EXO9a94805185b8e58bd27d0227"
  secret   = "lAkUIGH_LbGNCuOYbe2Rl840CV9xUGXOlDp2dJngJTU"
}
```

```hcl
# sg.tf
resource "exoscale_security_group" "sg_ssh_only" {
  name = "ssh-only"
}

resource "exoscale_security_group_rule" "sg_rule_ssh_ingress" {
  security_group_id = exoscale_security_group.sg_ssh_only.id
  type              = "INGRESS"
  protocol          = "TCP"
  cidr              = "0.0.0.0/0" # "::/0" for IPv6
  description       = "Allow SSH access from anywhere"
  start_port        = 22
  end_port          = 22
}
```

```hcl
# vm.tf
data "exoscale_template" "linux_22_vie" {
  zone = "at-vie-1"
  name = "Linux Ubuntu 22.04 LTS 64-bit"
}

resource "exoscale_compute_instance" "vm" {
  zone = "at-vie-1"
  name = "demo-2"

  template_id        = data.exoscale_template.linux_22_vie.id
  type               = "standard.small"
  disk_size          = 50
  security_group_ids = [exoscale_security_group.sg_ssh_only.id]
}
```

```shell
terraform init
terraform plan
# let's discuss the output a little
terraform apply
terraform destroy
```

## Discussion

- Security aspects of IaC and VMs
  - governance, policies, cost management
  - RBAC
- GDPR and legal stuff
- building virtual cloud infrastructure with code
- running VMs in an enterprise environment
  - introduction to HCI

## Assignment #2 Topics

One one-pager per term should be created from the following topics and presented in the next classroom session (max. 5 min).

Format: AsciiDoc or Markdown. Upload as zip file incl. any additional files (images etc.)

- IaC - Overview
- Terraform
- IaaS/PaaS/SaaS
- RBAC
- Cloud Init
- Governance and Policies
- Virtual Machines
- HCI - Hyperconverged Infrastructure
- GDPR - a brief overview
- Benefits and examples of doing things as Code
- Selected Security Buzzwords of the Cloud
- What does "Cloud Native" mean?