---
title: Technical capabilities
slug: hpc-limits
excerpt: 'Learn the technical capabilities and limitations of the OVHcloud Hosted Private Cloud'
section: FAQ
order: 1
---

**Last updated 27th October 2020**

## Objective

**This page provides an overview of the technical capabilities and limitations of OVHcloud Hosted Private Cloud services.**

## Capabilities and known limits


| Item | Value | Description |
|:-----:|:-----:|:----------:|
| Max. number of PCCs per customer ID |   No limit | Number of vCenters or packs per organisation |
| Number of linked PCCs |  0 (not allowed) | vCenters linked (Enhanced Linked Mode) |
| Minimum hosts per PCC (SLA) |  2 | Number of hosts per vCenter to maintain SLA |
| Minimum hosts per PCC (no SLA) |  0 | Bare minimum hosts to work with vCenter without SLA |
| Max. number of hosts per cluster |  64 | Hosts per cluster |
| Max. number of clusters per PCC |  No limit | Number of cluster within the same virtual data centre |
| Max. number of vDCs per PCC |  400 | Virtual data centres customers can add per vCenter |
| Max. number of hosts per PCC |  range **Hosts**: 340 hosts, 70 zpools<br>range **Hybrid**: 241 hosts, 120 zpools<br>range **BigDS**: 76 hosts, 205 zpools | Limits of hosts per vCenter |
| Max. number of VMs per SDDC |  25000 | VMs managed by the same vCenter |
| Max. number of VMs per host |  1024 | VMs hosted on the same physical host |
| Max. number of IPs per PCC |  1 x  /23 | Max. number of Public IPs assignable and usable per vCenter  |
| vCPUs, RAM and disk consumed by regular vCenter |  4 vCPU, 16GB RAM, 290GB Disk | Resources assigned to vCenter (VCSA) |
| vCPUs, RAM and disk consumed by regular NSX |  4 vCPU, 4GB RAM, 60GB Disk; 4 vCPU, 2GB RAM, 28GB Disk | Resources assigned to NSX Manager and Controller |
| vCPUs, RAM and disk consumed by regular vROPS |  4 vCPU, 16GB RAM | Resources assigned to vROPS |
| Max. number of edge nodes |  2000 | Max. number of edge devices to be deployed per NSX |
| Max. number of IPSec VPN Tunnels |  512 compact edge, 1600 large edge, 4096 quad large edge, 6000 extra large edge | Max. number of VPN tunnels per edge |
| Max. number of vRack per vDC |  1 | Max. number of private networks per virtual data centre |
| Max. number of L2 VPN Clients |  5 | Number of VPN clients to connect |



## Go further

Join our community of users on <https://community.ovh.com/en/>.
