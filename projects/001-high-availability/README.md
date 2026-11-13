# Project 001 — High-availability experiment

**Status: Planning — not yet deployed or tested.**

## Objective
Evaluate service resilience under controlled node failures, measure recovery time, and identify single points of failure.

## Architecture constraint
Raspberry Pi 4 devices use ARM processors and cannot join a standard x86 Proxmox VE cluster as native Proxmox VE nodes. Experiments involving these devices will use separate Linux clustering or application-level failover rather than claiming Proxmox VE HA across them.

## Planned work
1. Verify working nodes, boot media, and networking.
2. Select a test service and redundancy architecture.
3. Establish a baseline and define failure scenarios.
4. Conduct controlled node-failure tests.
5. Measure service downtime and recovery, then document dependencies.

## Success criteria
- A clearly defined service and failure scenario
- Reproducible test procedure
- Recorded recovery times and failure outcomes
- Identified remaining single points of failure

## Results
No deployment or measurements recorded yet.
