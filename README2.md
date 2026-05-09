
---

# README FOR PRACTICAL 2 (FIREWALL & LOG ANALYSIS)

```markdown
# Firewall Rule Optimization and Log Analysis Using iptables

## Overview
This practical focuses on analyzing, correcting, and optimizing firewall rules using iptables on a Linux system. The lab also demonstrates traffic logging and packet analysis using Wireshark.

---

## Objectives
- Identify conflicts in firewall rule sets
- Resolve shadow rule problems
- Optimize firewall performance
- Implement logging for denied traffic
- Analyze traffic using Wireshark

---

## Problem Identified
The original firewall configuration contained an overly permissive rule:

```bash
PERMIT ANY ANY ANY
