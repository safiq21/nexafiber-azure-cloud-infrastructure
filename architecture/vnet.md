# NEXA Azure Virtual Network

## Overview

The NEXA Azure environment uses an Azure Virtual Network (VNet) as the primary private networking boundary.

The VNet provides network isolation and enables communication between workloads deployed within the Azure environment.

## Purpose

The VNet provides:

- Private IP addressing
- Network segmentation
- Subnet-based workload separation
- Controlled communication between resources
- Integration with Network Security Groups

## Network Architecture

```text
Azure Virtual Network
│
├── Web Subnet
│
├── Application Subnet
│
└── Management / Supporting Subnet
```

## Key Learning

I learned how Azure Virtual Networks provide the foundation for cloud networking and how subnet segmentation can be used to organize workloads.
