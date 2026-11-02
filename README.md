# Network Troubleshooting & Fault Isolation Lab

## Overview
A Cisco Packet Tracer lab designed to practice network troubleshooting, fault isolation, and connectivity recovery in a small routed network.

## Objectives
- Identify and isolate network connectivity failures.
- Verify router interfaces and IP addressing.
- Troubleshoot OSPF neighbor and routing issues.
- Restore connectivity and validate the fix.

## Network Topology
PC1 — SW1 — R1 — R2 — SW2 — PC2

The lab contains:
- 2 Cisco 2911 routers
- 2 Cisco 2960 switches
- 2 PCs
- OSPF routing between the routers

## IP Addressing

| Device |   Interface   |    IP Address    |
|--------|---------------|------------------|
|   R1   |     G0/0      |  192.168.10.1/24 |
|   R1   |     G0/1      |    10.0.0.1/30   |
|   R2   |     G0/0      |  192.168.20.1/24 |
|   R2   |     G0/1      |    10.0.0.2/30   |
|   PC1  | FastEthernet0 | 192.168.10.10/24 |
|   PC2  | FastEthernet0 | 192.168.20.10/24 |

## Routing
OSPF process 1 is configured in Area 0 between R1 and R2.

## Troubleshooting Scenario 1: Inter-Router Link Failure

### Fault
The R2 interface connected to R1 was administratively shut down.

### Symptoms
- OSPF adjacency was lost.
- End-to-end connectivity between PC1 and PC2 failed.

### Troubleshooting
The router interfaces and OSPF neighbor status were checked to identify the failed link.

### Root Cause
The R2 G0/1 interface was in a shutdown state.

### Resolution
The interface was re-enabled.

### Validation
- OSPF adjacency returned to the FULL state.
- A Simple PDU from PC1 to PC2 succeeded in Packet Tracer.

## Tools
- Cisco Packet Tracer
- Cisco IOS CLI

## Project Status
This lab is being expanded with additional fault scenarios and troubleshooting documentation.
