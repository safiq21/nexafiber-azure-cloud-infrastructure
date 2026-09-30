# NEXA Log Analytics

## Overview

Log Analytics Workspace was used as the centralized location for collecting and analyzing Azure monitoring logs.

It provides a platform for querying and investigating collected log data.

## Monitoring Architecture

```text
Azure Resources
       │
       ▼
Azure Monitor
       │
       ▼
Log Analytics Workspace
       │
       ▼
Log Queries / Analysis
       │
       ▼
Troubleshooting
```

## Purpose

Log Analytics can be used to:

- Collect logs
- Search and query monitoring data
- Investigate infrastructure events
- Troubleshoot operational issues
- Support monitoring and alerting

## Querying Logs

Azure Monitor Logs can be analyzed using **Kusto Query Language (KQL)**.

Example:

```kusto
AzureActivity
| where TimeGenerated > ago(1h)
| project TimeGenerated, OperationNameValue, ActivityStatusValue
| order by TimeGenerated desc
```

This type of query can be used to investigate recent Azure activity.

## Key Learning

I learned the role of Log Analytics in centralized log collection and how KQL can be used to investigate Azure infrastructure activity.
