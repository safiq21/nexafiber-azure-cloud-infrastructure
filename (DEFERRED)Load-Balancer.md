# NEXA Azure Load Balancer
## DEFERRED Reason(Due to unavailability of Vm's or instance I skipped since Im using Azurestudents subscription)
## Overview

Azure Load Balancer is used in the NEXA architecture to distribute incoming network traffic across backend resources.

The Load Balancer provides a central traffic-distribution point between clients and the backend workload.

## Main Components

The NEXA Load Balancer consists of:

- Frontend IP configuration
- Backend pool
- Health probe
- Load-balancing rule

## Traffic Flow

```text
Client
  │
  ▼
Frontend IP
  │
  ▼
Load Balancing Rule
  │
  ▼
Backend Pool
  │
  ├── Backend Instance 1
  │
  └── Backend Instance 2
```

Health probes continuously help determine whether backend instances are available to receive traffic.

## High Availability

If multiple healthy backend instances are available, traffic can be distributed between them.

If a backend instance fails the configured health probe, the Load Balancer can avoid sending new traffic to that unhealthy instance.

## Key Learning

I learned how Azure Load Balancer components work together to distribute traffic and support a highly available application architecture.
