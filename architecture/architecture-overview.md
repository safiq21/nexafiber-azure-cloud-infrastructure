# NEXA Azure Architecture

## Overview

The NEXA project is a production-style Microsoft Azure infrastructure environment designed to demonstrate cloud networking, compute, high availability, monitoring, security, governance, and cost management.

The infrastructure is organized within the `NEXA-PROD-RG` resource group.

## Architecture Components

The environment includes:

- Azure Resource Group
- Azure Virtual Network (VNet)
- Multiple subnets
- Network Security Groups (NSGs)
- Azure Load Balancer
- Backend compute/web tier
- Azure Monitor
- Log Analytics Workspace
- Monitoring alerts
- Azure Policy
- Role-Based Access Control (RBAC)
- Resource tagging
- Cost Management / Budget

## High-Level Architecture

```text
                         Internet
                            │
                            ▼
                   Azure Load Balancer
                            │
                  ┌─────────┴─────────┐
                  │                   │
                  ▼                   ▼
             Web / VM Tier       Web / VM Tier
                  │                   │
                  └─────────┬─────────┘
                            │
                            ▼
                    Azure Virtual Network
                            │
             ┌──────────────┼──────────────┐
             │              │              │
             ▼              ▼              ▼
          Web/Subnet    Application    Management
                         Subnet          / Services
             │              │              │
             └──────────────┼──────────────┘
                            │
                            ▼
                 Azure Monitor / Logs
                            │
                            ▼
                   Log Analytics
                            │
                            ▼
                       Alerts
```

> **Note:** The diagram represents the logical architecture. Resource names, subnet names, and traffic paths should match the actual Azure deployment.

## Networking

The Azure Virtual Network provides the private network boundary for the NEXA environment.

The network is divided into subnets to separate workloads and control traffic between different tiers.

Network Security Groups are used to control inbound and outbound network traffic according to the required security rules.

## High Availability

Azure Load Balancer distributes incoming traffic across the backend compute resources.

Health probes are used to determine whether backend instances are available before traffic is forwarded to them.

This provides a foundation for improving application availability and preventing traffic from being sent to unhealthy instances.

## Monitoring

Azure Monitor and Log Analytics are used to observe infrastructure activity and collect relevant monitoring data.

Alerts can be configured to identify conditions that require attention.

## Governance

The environment uses Azure governance controls including:

- Resource tagging
- Azure Policy review
- RBAC
- Resource-group organization

These controls help maintain consistency, visibility, and access management across the environment.

## Cost Management

Cost Management is used to monitor Azure spending and establish budget-based alerts for the project.

This provides a basic FinOps control for identifying unexpected cost increases.

## Security

Security controls are implemented across multiple layers:

- Network Security Groups
- RBAC
- Azure Policy
- Monitoring and alerts
- Controlled network segmentation

## Technologies Used

- Microsoft Azure
- Azure Virtual Network
- Azure Load Balancer
- Azure Virtual Machines
- Azure Monitor
- Log Analytics
- Azure Policy
- Azure RBAC
- Azure Cost Management

## Key Learning Outcomes

Through this project, I gained practical experience with:

- Azure networking and subnet design
- Network traffic control
- Load balancing and health probes
- Cloud infrastructure monitoring
- Azure governance
- Identity and access management
- Cloud security fundamentals
- Azure cost management
- Production-oriented cloud infrastructure design
