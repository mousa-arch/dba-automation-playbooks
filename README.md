# DBA Automation Playbooks

## Overview
This repository contains a curated collection of automation scripts and playbooks designed to manage, secure, and maintain enterprise database environments. These scripts reflect my approach to reducing manual overhead in mission-critical infrastructure.

## Automation Architecture

```mermaid
graph TD
    %% Define Nodes
    Scheduler[[Task Scheduler<br>Cron / Ansible Tower]]
    Script[Automation Playbook<br>Bash / Python / Ansible]
    DB[(Oracle Exadata<br>Mission-Critical DB)]
    Storage[(Backup Storage<br>ZDLRA / OCI Object)]
    Alert[Alerting System<br>Email / PagerDuty]
    
    %% Define Workflow
    Scheduler -->|Trigger Job| Script
    Script -->|1. Health Check & Validation| DB
    Script -->|2. Execute RMAN Backup| DB
    DB -->|3. Secure Data Transfer| Storage
    Script -->|4. Parse Logs & Metrics| Alert

    %% Styling
    style DB fill:#f9d0c4,stroke:#c82124,stroke-width:2px
    style Script fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    style Storage fill:#fff3e0,stroke:#e65100,stroke-width:2px
```

## Focus Areas
* **Operational Efficiency:** Automated health checks and performance monitoring scripts to identify bottlenecks before they impact production.
* **Resilience:** RMAN-based backup and restoration automation playbooks to ensure data integrity and rapid recovery.
* **Compliance & Security:** Scripted patch management and configuration drift detection for Oracle Database environments.

## Technologies Used
* **Languages:** Bash, Python
* **Automation Frameworks:** Ansible
* **Core Systems:** Oracle Exadata, Enterprise Linux, OCI

## Key Philosophy
* "If it's done twice, automate it."
* Infrastructure as Code (IaC) principles: Version-controlled configuration ensures stability across large-scale deployments.
* Security first: Automated configuration validation against enterprise compliance standards.

---
*Created by Mohamed Mousa | Lead Cloud Architect*
