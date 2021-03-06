---
title: Migrating a Hosted Private Cloud service 
excerpt: Find out how to manage all aspects of migrating a Hosted Private Cloud service
slug: service-migration
section: Getting started
order: 6
hidden: true
---

**Last updated 18th November 2020**

## Objective

There are two aspects to migrating a Hosted Private Cloud service:

- The Hosted Private Cloud context (OVHcloud), which includes the customer's side of administrating an infrastructure.
- The VMware context, which includes the entire VMware eco-system, on the infrastructure itself.

**This guide explains how to cover all aspects of migrating a Hosted Private Cloud service.**

## Requirements

- a [Hosted Private Cloud infrastructure](https://www.ovhcloud.com/en-gb/enterprise/products/hosted-private-cloud/)
- access to the [OVHcloud Control Panel](https://www.ovh.com/auth/?action=gotomanager) (`Private Cloud`{.action} in the `Hosted Private Cloud`{.action} section)

## Instructions

This guide will utilise the notions of an **origin Hosted Private Cloud** and a **destination Hosted Private Cloud**.

### Hosted Private Cloud context

#### Security

##### **Hosted Private Cloud access**

For connections to the VMware platform, you can choose to block access to vSphere by default. Please refer to our guide on the [vCenter access policy](../modify-vcenter-access-policy/) for details.

If the access policy has been changed to "Restricted", you will need to apply the same connection IPs to the destination Hosted Private Cloud as to the origin Hosted Private Cloud service.

##### **Hosted Private Cloud users**

In the lifecycle of the origin Hosted Private Cloud, a list of users may have been created for business or organisational needs. You must therefore create them again on the destination Hosted Private Cloud and assign them the appropriate rights, depending on the configuration of the destination Hosted Private Cloud.

To do this, please refer to our guides on [Changing user rights](../change-users-rights/), [Changing the User Password](../changing-user-password/) and [Associating an email with a vSphere user](../associate-email-with-vsphere-user/).

##### **Key Management Server (KMS)**

If virtual machines are protected by encryption and this is a prerequisite for the destination Hosted Private Cloud, it will be necessary to recreate the encryption context on the destination Hosted Private Cloud.
Please refer to our guide on [Enabling Virtual Machine Encryption](../vm-encrypt/) in order to enable KMS on the destination Hosted Private Cloud.

##### **Certifications**

For compliance reasons, [PCI DSS](https://www.ovhcloud.com/en-gb/enterprise/products/hosted-private-cloud/safety-compliance/pci-dss/) and [HDS](https://www.ovhcloud.com/en-gb/enterprise/products/hosted-private-cloud/safety-compliance/hds/) options may have been enabled on the origin Hosted Private Cloud.

These options must therefore be reactivated on the destination Hosted Private Cloud. To do this, please refer to our [guide on activating them](../activate-pci-dss-option/).

#### Network

##### **vRack**

> [!warning]
>
> VMnetworks located in the same region cannot be interconnected in a vRack.
>

As part of a migration process, you can link your Hosted Private Cloud services within the same vRack. Please consult our guide to [Using Private Cloud within a vRack](../using-private-cloud-with-vrack/).


##### **Public network**

> [!warning]
>
> If your Hosted Private Cloud/PCC offer pre-dates 2016, please contact our support teams to verify the requirements.
>

If the public IP addresses attached to the origin Hosted Private Cloud are required on the destination Hosted Private Cloud, it will be necessary to transfer them.

Please consult our guide to [Migrate an IP block between two Hosted Private Cloud services](../add-ip-block/#migrate-an-ip-block-between-two-hosted-private-cloud-solutions).

### VMware context

#### Cluster configuration

##### **Configuring VMware HA**

The migration involves reconfiguring VMware High Availability (HA), including boot order and priority. Please consult our guide about [VMware HA configuration](../vmware-ha-high-availability/).

##### **Configuring VMware DRS**

The migration involves reconfiguring the VMware Distributed Resource Scheduler (DRS) feature, including the host and VM groups. Please consult our guide about [configuring VMware DRS](../vmware-drs-distributed-ressource-scheduler/).

##### **Resource pools**

The migration requires rebuilding resource pools including reservations, shares, and vApps.

For more information, consult [VMware's documentation for managing resource pools](https://docs.vmware.com/en/VMware-vSphere/6.7/com.vmware.vsphere.resmgmt.doc/GUID-60077B40-66FF-4625-934A-641703ED7601.html){.external}.

#### Inventory organisation

For organisational reasons, the VMs, hosts or datastores may have been placed in directories.

If you still need this organisation, you will need to create it again in the destination Hosted Private Cloud.

#### VM

There are several ways of migrating VMs from one Private Cloud to another. We offer to migrate using the Veeam solution and Veeam Replication technology.

The following elements are required:

- SPLA licences (on origin and destination Hosted Private Cloud)
- A Veeam licence
- An IP address available on the origin and destination Hosted Private Cloud services
- A [Veeam Backup & Replication](../../storage/veeam-backup-replication/) virtual machine on the origin Hosted Private Cloud
- [Authorising the Veeam Backup & Replication virtual machine to connect](../authorise-ip-addresses-vcenter/) to the origin and destination vCenter

Please refer to our guide on setting up [Veeam Backup & Replication](../../storage/veeam-backup-replication/).

The video below shows how to configure Hosted Private Cloud with the Veeam Backup & Replication solution.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/f8ufrsP4PQw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>The following video explains how to replicate your Hosted Private Cloud infrastructure with the Veeam Backup & Replication solution.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/NqNtKrJSH8w" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

<br>You can also refer to the [Veeam documentation](https://www.veeam.com/veeam_backup_10_0_user_guide_vsphere_pg.pdf){.external} (PDF).

#### vSAN

If vSAN was enabled on your origin Hosted Private Cloud, you will need to enable it again on the destination Hosted Private Cloud. Please refer to our guide on [Using VMware Hyperconvergence with vSAN](../vmware-vsan/).

#### Backup

If you have activated the Veeam Managed Backup solution on the origin Hosted Private Cloud, you will need to create the backup jobs again on the destination Hosted Private Cloud.

Please refer to our guide on [activating and using Veeam Managed Backup](../veeam-backup-as-a-service/).

## Go further

Join our community of users on <https://community.ovh.com/en/>.
