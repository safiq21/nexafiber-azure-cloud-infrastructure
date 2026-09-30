# NEXA Azure Compute / Web Tier

## Overview

The NEXA environment uses Azure compute resources to host the application/web workload.

The compute layer forms the backend of the Load Balancer architecture and provides the resources that process incoming traffic.

## Architecture

```text
Internet
   │
   ▼
Azure Load Balancer
   │
   ▼
Backend Pool
   │
   ├── Web / VM Instance 1
   │
   └── Web / VM Instance 2
```

## Web Tier Role

The web tier is responsible for handling application or web traffic forwarded by the Azure Load Balancer.

The workload is placed within the Azure Virtual Network and associated with the appropriate subnet and network security controls.

## Network Integration

The compute resources integrate with:

- Azure Virtual Network
- Subnets
- Network Security Groups
- Azure Load Balancer
- Monitoring services

## High Availability

Multiple backend instances can be placed behind the Load Balancer.

The Load Balancer uses health-probe results to determine which backend instances are available to receive traffic.

This provides a foundation for maintaining service availability when individual backend instances become unavailable.

## Monitoring

The compute resources can be monitored through Azure Monitor.

Relevant metrics and alerts can be used to identify resource conditions that require attention.

## Security

The compute layer is protected through network-level controls such as Network Security Groups and controlled access through Azure networking.

Administrative access should be restricted to required sources and ports.

## Key Learning

Through this implementation, I gained practical experience with:

- Azure compute infrastructure
- VM/network integration
- Web-tier architecture
- Load Balancer backend integration
- Network Security Groups
- High-availability concepts
- Cloud infrastructure monitoring
