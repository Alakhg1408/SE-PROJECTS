# Lab 3 – Software Architecture & Component Modeling

**Student:** Alakh Gupta  
**SRN:** PES2UG24CS051  
**Class:** 5A  
**Problem Statement:** #47 – Domain & SSL Certificate Expiry Alert System  

---

## Overview

This lab addresses architecture style selection, architectural justification, and component-level modeling for the monitoring system.

## Architectural Justification: Microservices Architecture

1. **Independent Deployment & Scaling:** WHOIS auditing, SSL/TLS auditing, alerting, and reporting services can be developed, scaled, and deployed independently according to monitoring load.
2. **Fault Isolation:** External failures (e.g. rate-limited WHOIS lookup or slow DNS) are isolated and do not block SSL/TLS certificate scans or notification dispatch.
3. **Security Advantage:** Security-sensitive alert escalation and credential management are isolated behind defined service boundaries with strict audit logs.
4. **Performance Benefit:** Audit workers can process domains concurrently to comfortably satisfy the requirement of scanning 1,000 domains in under 3 minutes.

## Key Components

- **Monitoring Scheduler:** Triggers periodic daily audit jobs.
- **Audit Engine:** Coordinates scan targets and dispatches tasks.
- **WHOIS Service:** Performs domain registration queries.
- **SSL/TLS Audit Service:** Initiates handshakes and verifies certificates.
- **Alert & Escalation Service:** Manages notification logic, thresholds, and escalation queues.
- **Monitoring Database & Reports:** Persists historical audit results and domain inventories.

## Deliverables

- **Component Diagram:** [`PES2UG24CS051_Lab3_Component_Diagram.pdf`](./PES2UG24CS051_Lab3_Component_Diagram.pdf)
- **Architecture Justification:** [`PES2UG24CS051_Lab3_Justification.pdf`](./PES2UG24CS051_Lab3_Justification.pdf)
