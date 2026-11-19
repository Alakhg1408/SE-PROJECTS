# Lab 1 – Software Requirements Engineering

**Student:** Alakh Gupta  
**SRN:** PES2UG24CS051  
**Class:** 5A  
**Problem Statement:** #47 – Domain & SSL Certificate Expiry Alert System  

---

## Overview

This lab covers requirement engineering and UML use-case modeling for a domain and SSL certificate expiration monitoring and alerting system.

## Key Contents

- **Functional Requirements:**
  - `FR-001`: Daily TLS handshake against monitored domains to extract certificate expiration dates and alert at 30, 15, and 3 days.
  - `FR-002`: Daily WHOIS lookup on monitored domains for registration expiration date alerting.
  - `FR-003`: SysAdmin configurable alert thresholds (per-domain or globally).
  - `FR-004`: Automatic alert escalation to Security Officer after 24 hours of inactivity.
  - `FR-005`: Adding/removing domains from the monitoring inventory via dashboard.
- **Non-Functional Requirements:**
  - `NFR-001` (Performance): Scan list of 1,000 domains and SSL endpoints in under 3 minutes.
  - `NFR-002` (Reliability & Availability): 99.9% uptime with exponential backoff retry on failed WHOIS/TLS handshakes (up to 2 retries).
- **UML Diagrams & Specifications:**
  - Complete UML Use Case Diagram with actors (`SysAdmin`, `Security Officer`, `WHOIS/TLS Endpoint`, `Notification Gateway`).
  - Detailed Use Case Flow Specification for `UC-01: Monitor SSL Certificate Expiry` (preconditions, main success scenario, and alternate/exception flows).

## Deliverables

- **Lab Report:** [`SE_LAB1_PES2UG24CS051.pdf`](./SE_LAB1_PES2UG24CS051.pdf)
