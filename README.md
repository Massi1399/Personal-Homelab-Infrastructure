# Personal Homelab Infrastructure

## Overview

This repository documents the development of a small homelab built around Proxmox VE and a dedicated OPNsense firewall. The project focuses on virtualization, controlled cybersecurity experimentation, network segmentation, and incremental infrastructure improvements.

The documentation is split by topic to keep the main page concise and implementation details easy to maintain.

## Documentation

- [Homelab](homelab.md) — cybersecurity virtual machines, the game-server VM, and a generic approach to future workloads.
- [Network project](network/README.md) — network-design evolution, current limitations, and the target segmented architecture.
- [Firewall](network/firewall.md) — OPNsense setup, hardware adaptation, and planned security-feature improvements.

## High-Level Design

The intended architecture uses OPNsense for routing and firewall policy enforcement, a managed switch for VLAN transport, and Proxmox for hosting isolated workloads.

```text
Internet
   |
OPNsense
   |
Managed switch (planned)
   |
Proxmox
   |
VLAN-aware virtual networking (planned)
   +-- Cybersecurity lab
   +-- Game server
   +-- Local LLM Model
   +-- Future workloads
```

This is the target direction, not a claim that every component is already deployed.

## Design Principles

- **Least privilege:** allow only the access required by each service.
- **Segmentation:** separate the cybersecurity lab from personal and other workloads.
- **Default deny:** permit inter-network traffic only when explicitly required.
- **Incremental development:** record constraints, tests, and design decisions as the setup evolves.
- **Privacy by design:** avoid publishing credentials, public addresses, device identifiers, detailed hardware models, firmware versions, or private network configuration.

Segmentation helps reduce exposure and limit the impact of a compromise; it cannot guarantee that a system will never affect another system.
