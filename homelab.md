# Homelab

This file lists the virtual machines currently in scope for the homelab. Network evolution and VLAN design are documented in [network/README.md](network/README.md), while OPNsense-specific work is covered in [firewall.md](firewall.md).

## Cybersecurity Lab

The cybersecurity lab is intended for controlled practice, security monitoring, and vulnerability assessment.

- **Kali Linux VM** — security testing workstation.
- **Metasploitable VM** — intentionally vulnerable target for isolated exercises.
- **Wazuh VM** — security monitoring and host-based detection.
- **Optional vulnerability-assessment VM** — may be added for tools such as OpenVAS if resources allow.

The lab should remain isolated from personal devices and unrelated services. Intentionally vulnerable systems should not be exposed to the public Internet and should have Internet access disabled or tightly restricted unless a specific exercise requires it.

## Game Server

- **Game-server VM** — hosts the game server and its associated data.

Remote access should be limited to the required service and port. External users should not receive general access to the homelab or Proxmox management interfaces.

## Future Workloads

Additional VMs or containers may be added as the project evolves. They will be documented generically until there is a clear reason to publish their purpose and configuration.

Each new workload should be assessed for resource requirements, network placement, access needs, and backup requirements before deployment.
