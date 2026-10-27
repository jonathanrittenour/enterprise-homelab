# JWR Commerce LLC — IT Resale AI Assistant

## Project Overview

A self-hosted AI assistant developed to support IT asset sourcing, inventory evaluation, supplier research, and resale operations for JWR Commerce LLC.

The application runs within a remotely hosted enterprise virtualization environment, combining Linux administration, Docker containerization, cloud-based AI inference, and business-specific AI configuration.

## Business Problem

Bulk IT equipment purchasing requires evaluating inventory from multiple suppliers and auction platforms while accounting for equipment condition, resale demand, acquisition costs, shipping, and potential profitability.

The objective of this project is to develop an AI-assisted workflow that makes these purchasing decisions more efficient, consistent, and financially disciplined.

## Technology Stack

| Component | Technology |
|---|---|
| Physical infrastructure | Dell PowerEdge T440 |
| Virtualization | Proxmox VE |
| Operating system | Ubuntu Server |
| Containerization | Docker |
| AI user interface | Open WebUI |
| AI API gateway | OpenRouter |
| AI model | Recursive: Flint (free) |
| Remote connectivity | Tailscale and SSH |
| Business application | JWR Commerce IT Resale AI |

## Implemented Features

### Custom AI Assistant

Configured a dedicated AI assistant in Open WebUI with business-specific instructions for:

- Evaluating bulk laptop and enterprise IT equipment opportunities.
- Estimating acquisition costs, resale profitability, and ROI.
- Identifying purchasing risks, including BIOS locks, device management enrollment, and missing components.
- Supporting supplier outreach and purchasing negotiations.
- Distinguishing active inventory listings from historical auction results.

### Business Knowledge Integration

Created a dedicated supplier intelligence knowledge collection to provide business-specific context for sourcing and resale workflows.

### Web Research Configuration

Configured web search and page retrieval capabilities to support external inventory research.

Live listing availability and pricing must be verified before making purchasing recommendations.

## Technical Architecture

The application follows a hybrid architecture:

1. Proxmox VE hosts the Ubuntu Server virtual machine.
2. Docker runs the Open WebUI application.
3. Open WebUI provides the custom AI interface and business-specific configuration.
4. OpenRouter routes inference requests to an externally hosted AI model.
5. Tailscale and SSH provide secure remote administration.

AI inference is currently cloud-hosted rather than performed locally on the physical server.

## Challenges and Lessons Learned

- Configured and troubleshot containerized application access.
- Established secure remote access using SSH port forwarding.
- Integrated an external AI model provider through an API.
- Encountered free-tier API request limits during extensive inventory research.
- Improved assistant instructions to distinguish verified active listings from expired or completed auctions.
- Evaluated local AI inference as a potential future expansion, subject to hardware and resource constraints.

## Planned Improvements

- Evaluate alternative AI models and inference options.
- Improve sourcing research efficiency and API usage.
- Develop inventory monitoring and supplier follow-up workflows.
- Add structured purchase evaluation and profitability reporting.
- Explore additional automation and integration capabilities.

These items are planned improvements, not completed implementations.

## Security and Confidentiality

This public repository documents architecture, implementation decisions, and technical experience.

It does not contain API keys, passwords, private supplier records, customer information, or confidential business documents.

## Project Status

**Active development**

The initial self-hosted application, custom AI assistant, knowledge integration, and external AI connectivity have been configured. Further development will focus on reliability, research accuracy, and operational automation.
