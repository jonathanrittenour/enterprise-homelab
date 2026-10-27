# Virtual Machine Infrastructure

This directory documents the virtual machines deployed within my remotely hosted Dell PowerEdge T440 enterprise lab, running Proxmox VE.

## Current Virtual Machines

### Ubuntu Server — AI and Container Services

| Component | Configuration |
|---|---|
| Hypervisor | Proxmox VE |
| Operating System | Ubuntu Server |
| CPU | Intel Xeon Silver 4208 (host processor) |
| Memory | 3.8 GiB allocated |
| Container platform | Docker |
| AI interface | Open WebUI |
| AI model access | OpenRouter |
| Remote administration | Tailscale and SSH |
| Web access | SSH port forwarding |

### Applications and Services

**Open WebUI**
- Self-hosted AI chat interface running in Docker.
- Configured with OpenRouter for AI model access.
- Includes a custom JWR Commerce LLC IT Resale AI assistant.
- Supports supplier intelligence, inventory research, and resale analysis.

**Docker**
- Hosts containerized applications.
- Provides isolated application environments and simplified service management.

**Tailscale**
- Provides private remote connectivity to the Ubuntu VM.
- Enables secure administration without exposing SSH directly to the public internet.

## Future Expansion

Additional virtual machines will be documented here as they are deployed, including their operating systems, resource allocations, applications, security configurations, and operational purposes.

## Documentation and Security

This repository documents infrastructure architecture and implementation experience. Passwords, API keys, authentication tokens, private business records, and sensitive configuration details are excluded from public documentation.
