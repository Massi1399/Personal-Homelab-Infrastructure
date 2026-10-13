# OPNsense Firewall

This file documents the OPNsense firewall work only. The broader network-design history and VLAN plan are in [network/README.md](network/README.md).

## Purpose

OPNsense is intended to provide the homelab's routing, firewall policy enforcement, and network-segmentation capabilities. The target policy is **deny by default, allow by exception**.

## Hardware Adaptation

The firewall was built by repurposing an existing small-form-factor system. It initially had only one physical Ethernet interface, which was insufficient for a conventional WAN/LAN setup.

An external USB Ethernet adapter was tested to provide a second interface, but compatibility and stability issues made it unsuitable for dependable use.

The hardware was then adapted by replacing the wireless card with an **M.2 Ethernet adapter**, providing separate physical interfaces for WAN and LAN.

The firewall now has an **M.2 SSD** installed for system storage. Specific device models, identifiers, and firmware details are intentionally omitted from this public documentation.

## Planned Security Improvements

A **memory upgrade** is planned to provide more headroom for additional security services.

One goal is to evaluate **Zenarmor** alongside the existing OPNsense capabilities, moving toward more NGFW-like functionality such as application visibility and policy controls. The final feature set will depend on hardware capacity, compatibility, and measured performance.

Adding storage alone does not increase packet-inspection performance; CPU and memory capacity also matter. Security features should therefore be enabled incrementally and tested for their impact on throughput, latency, and stability.

## Policy Principles

- Deny unsolicited inter-network traffic by default.
- Allow only the ports and destinations required by a documented use case.
- Keep management interfaces accessible only from authorized devices.
- Restrict the cybersecurity lab from reaching personal networks and unrelated workloads.
- Keep intentionally vulnerable targets isolated and restrict their Internet access.
- Review and remove rules that are no longer needed.

These are design goals. Public documentation does not include exported configurations, credentials, public IP addresses, device identifiers, or other sensitive operational details.
