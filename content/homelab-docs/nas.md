+++
author = "Ananta Srikar"
title = "homelab-docs: NAS Setup"
date = "2025-01-01"
description = "Project - Homelab-Docs: NAS Setup"
tags = [
    "homelab",
    "nas",
    "nextcloud",
]
+++

This document outlines the complete hardware and software setup I implemented for my NAS.

I use Proxmox as it offers significant flexibility, allowing the deployment of both VMs and LXCs.

The storage setup includes 4 x Seagate IronWolf 2TB 3.5-inch Internal Hard Drives (ST2000VN004) configured in RAIDz1 (a ZFS equivalent to RAID5). The resulting ZFS pool is shared via NFS wherever required.

To set up OpenMediaVault (OMV) within a Linux Container (LXC), I used the [Proxmox VE Helper-Scripts](https://tteck.github.io/Proxmox/). The previously mentioned NFS share was mounted using the `openmediavault-remotemount` plugin. 

This NFS share serves as the home directory for users.

Additionally, I installed Nextcloud using Docker within the same LXC environment. 

Future plans include running more Docker containers managed through Portainer, with potential applications such as Plex, Ubiquiti, and others that I have yet to finalize.

## Notes
To address an issue during bulk shutdown where the NFS server was terminated before the container could unmount the NFS share, I made adjustments to the `nfs-server.service` and `pve-container@<container_number>.service` files.

The following configurations were applied:

```bash
root@mainserver:~# cat /etc/systemd/system/pve-container@<container_number>.service.d/override.conf 
[Unit]
Requires=nfs-server.service
After=nfs-server.service

root@mainserver:~# cat /etc/systemd/system/nfs-server.service.d/override.conf 
[Unit]
PartOf=pve-container@<container_number>.service
```

For example, if your container number is 120, the service name would be `pve-container@120.service`.

## TODO
- Add detailed setup for Nextcloud.
- Document the configuration for SMB shares.