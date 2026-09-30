# NEXA Azure Monitor

## Overview

Azure Monitor was used as the central monitoring service for the NEXA Azure environment.

It provides visibility into the performance and health of Azure resources through metrics, logs, and monitoring capabilities.

## Monitoring Scope

The monitoring environment can be used to observe:

- Virtual machines
- Network resources
- Load Balancer
- Application infrastructure
- Resource activity

## Monitoring Flow

```text
Azure Resources
       │
       ▼
Azure Monitor
       │
 ┌─────┴─────┐
 ▼           ▼
Metrics      Logs
 │           │
 ▼           ▼
Analysis    Log Analytics
       │
       ▼
     Alerts
```

## Purpose

Azure Monitor helps identify:

- Resource performance issues
- Availability problems
- Abnormal activity
- Infrastructure conditions requiring attention

## Key Learning

I learned how Azure Monitor provides centralized visibility into Azure infrastructure and how monitoring data can be used for operational troubleshooting.
