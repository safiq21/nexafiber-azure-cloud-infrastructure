# NEXA Resource Tags

## Overview

Resource tagging was implemented to organize and identify Azure resources within the NEXA environment.

The primary resource group used for the project is:

`NEXA-PROD-RG`

## Purpose of Tagging

Tags help with:

- Resource identification
- Environment classification
- Cost tracking
- Ownership identification
- Resource organization
- Governance

## NEXA Tagging Strategy

| Tag | Purpose |
|---|---|
| Environment | Identifies the deployment environment |
| Project | Identifies the NEXA project |
| Owner | Identifies the responsible owner |
| CostCenter | Supports cost tracking |

## Governance Approach

Tags were applied according to the project's organizational requirements without changing the underlying resource configuration.

Resource tagging provides a simple governance layer that can be used alongside Azure Policy and RBAC.

## Key Learning

I learned how Azure resource tags can be used to organize cloud infrastructure and support governance and cost-management activities.
