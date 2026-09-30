# NEXA Azure Security Controls

## Overview

Security was considered across the NEXA Azure infrastructure at the network, identity, governance, and monitoring layers.

The objective was to reduce unnecessary exposure, control access, and provide visibility into infrastructure activity.

## Security Architecture

```text
                    Azure Environment
                           │
        ┌──────────────────┼──────────────────┐
        │                  │                  │
        ▼                  ▼                  ▼
   Network Security      Identity         Governance
        │                  │                  │
        ▼                  ▼                  ▼
       NSG                RBAC          Azure Policy
        │                  │                  │
        └──────────────────┼──────────────────┘
                           │
                           ▼
                    Azure Monitoring
                           │
                           ▼
                   Logs & Alerts
```

## 1. Network Security Groups

Network Security Groups (NSGs) were used to control network traffic at the subnet or network-interface level.

NSG rules can control traffic based on:

- Source
- Destination
- Port
- Protocol
- Direction
- Priority

The security approach is to permit only required traffic and restrict unnecessary network access.

## 2. Network Segmentation

The Azure Virtual Network was divided into logical subnets.

Subnet segmentation provides separate network boundaries for different workload tiers and allows security rules to be applied according to the requirements of each tier.

Example:

```text
Virtual Network
│
├── Web Tier
│
├── Application Tier
│
└── Management / Supporting Services
```

## 3. Role-Based Access Control

Azure RBAC was reviewed to understand existing access assignments.

The NEXA environment had an inherited **Owner** role at the subscription scope.

The review helped identify how permissions inherited from higher-level scopes can affect resources within the resource group.

Security principle:

> Access should be granted only at the scope and permission level required for the task.

## 4. Azure Policy

Existing Azure Policy assignments were reviewed before introducing additional policies.

The environment contained existing governance controls, including:

- ASC Default initiative
- Allowed resource deployment regions policy

No additional restrictive policy was unnecessarily assigned during the project.

This avoided introducing governance rules that could interfere with existing or future resources.

## 5. Load Balancer Security

The Azure Load Balancer provides a controlled traffic entry point for the backend workload.

Traffic passes through the configured frontend and load-balancing rules before reaching the backend pool.

Health probes help ensure that traffic is directed only toward backend instances that satisfy the configured health conditions.

## 6. Administrative Access

Administrative access to compute resources should be restricted to the required sources and ports.

Unnecessary management ports should not be exposed publicly.

For production environments, secure administrative access methods such as controlled network access, VPN, Bastion, or other approved mechanisms should be considered according to the organization's requirements.

## 7. Monitoring and Security Visibility

Azure Monitor and Log Analytics provide visibility into infrastructure activity.

Monitoring can help identify:

- Resource availability issues
- Performance anomalies
- Configuration changes
- Operational events
- Conditions requiring investigation

Alerts can be used to notify administrators when configured conditions are detected.

## 8. Governance and Cost Controls

Security and governance were considered together with resource management.

The project used:

- Resource tagging
- RBAC review
- Azure Policy review
- Cost Management
- Monitoring

These controls improve visibility and help administrators understand how resources are managed.

## Security Approach

The NEXA project follows a layered security approach:

```text
Network Segmentation
        ↓
NSG Traffic Control
        ↓
Identity & RBAC
        ↓
Azure Policy
        ↓
Monitoring & Logging
        ↓
Alerts & Operational Response
```

No single control is treated as the complete security solution. Multiple layers work together to reduce unnecessary exposure and improve visibility.

## Key Learning

Through this project, I gained practical experience with:

- Azure Network Security Groups
- Network segmentation
- Azure RBAC
- Azure Policy
- Load Balancer traffic control
- Azure Monitor
- Log Analytics
- Security-oriented cloud governance
- Basic cloud security architecture
