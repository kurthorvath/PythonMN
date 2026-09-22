<img width="300" height="110" alt="image" src="https://github.com/user-attachments/assets/5ad51202-8431-4e29-a828-b2662f86443f" />
<img width="245" height="300" alt="image" src="https://github.com/user-attachments/assets/5f40e21d-4881-42c4-adfe-b7677926a616" />


# Rechnernetze und Netzwerkprogrammierung – RN Lab

This repository contains the laboratory infrastructure and supporting code for the practical exercises of the course **Rechnernetze und Netzwerkprogrammierung**.

The exercises use **Python, Linux networking, and Mininet**. You will work with real Linux network namespaces, virtual Ethernet links, routers, Open vSwitch, and Python network applications.

> **Important:** The provided files contain the laboratory environment and supporting/example code. They are not complete solutions. Follow the corresponding exercise sheet for the individual tasks.

---

## Assignments

### [Assignment 04 – Introduction to Mininet](./RN-Lab_Assignment04)

The first Mininet exercise introduces the laboratory environment and the separation between network infrastructure and application code.

You will work with:

- Mininet hosts and network namespaces
- Linux interfaces and IP addresses
- routing tables
- ARP
- UDP client/server applications
- TCP client/server applications
- Wireshark and packet captures
- network delay and packet loss
- the separation between application and network infrastructure

The provided topology consists of a **client, router, and server**.

**Main focus:** Mininet, Linux networking, UDP/TCP, sockets, and the relationship between applications and network infrastructure.

---

### [Assignment 05 – TCP and Network Performance](./RN-Lab_Assignment05)

This exercise investigates TCP behaviour and network performance using Mininet and packet captures.

Topics include:

- TCP three-way handshake
- TCP byte streams
- sequence and acknowledgement numbers
- TCP retransmissions
- packet loss
- RTT and throughput
- network delay
- TCP versus UDP
- performance measurements with `iperf3`
- Wireshark/tcpdump analysis

You will change network conditions and observe how TCP reacts to them.

**Main focus:** TCP reliability, packet loss, latency, throughput, and performance measurement.

---

### [Assignment 06 – IP, Subnetting and Routing](./RN-Lab_Assignment06)

This exercise moves to the **network layer** and introduces a topology with multiple routers and IP networks.

You will work with:

- IPv4 addresses and interfaces
- routing tables
- static routes
- IP forwarding
- subnetting
- VLSM
- multi-router communication
- TTL
- traceroute
- packet capture with `tcpdump`
- IP packet analysis with Wireshark

The topology contains a client, two routers, and a server connected through different IP networks.

Later parts of the exercise introduce modifications to the Mininet topology.

**Main focus:** IPv4 addressing, subnetting, routing, forwarding, and packet-path analysis.

---

### [Assignment 07 – Multi-Path Routing and Topology Modification](./RN-Lab_Assignment07)

This exercise extends the routing environment and investigates how communication changes when multiple paths exist between networks.

You will work with:

- Mininet topology modification
- additional routers
- alternative network paths
- IP forwarding
- routing tables
- next-hop decisions
- traceroute
- packet-path analysis
- Wireshark

A central task is to extend the existing topology with an additional router and create an **alternative path** through the network.

The application itself should remain independent of the underlying topology.

**Main focus:** topology changes, routing decisions, alternative paths, forwarding, and network-layer analysis.

---

### [Assignment 08 – Ethernet, ARP and Switching](./RN-Lab_Assignment08)

This exercise introduces the **link layer** using an Ethernet LAN with an Open vSwitch.

The topology consists of multiple hosts connected to a single Ethernet switch.

You will investigate:

- Ethernet frames
- source and destination MAC addresses
- ARP requests and replies
- broadcast traffic
- unicast traffic
- flooding
- MAC address learning
- the switch forwarding database (FDB)
- Open vSwitch
- communication within a LAN

You will observe how the switch learns where hosts are located and how this affects packet forwarding.

**Main focus:** Ethernet, MAC addresses, ARP, switching, learning, unicast, broadcast, and flooding.

---

### [Assignment 09 – Network Forensics](./RN-Lab_Assignment09)

The final exercise is a **network troubleshooting and forensic investigation**.

You are given a network consisting of:

- two clients
- Ethernet switches
- a router
- a server
- a Python TCP application

The network contains an intentional configuration problem.

Instead of being told where the problem is, you investigate the network systematically.

You will:

1. establish a baseline
2. inspect interfaces and IP addresses
3. inspect routing tables
4. inspect ARP/neighbor information
5. test connectivity
6. capture network traffic
7. analyse TCP communication
8. formulate and test hypotheses
9. identify the cause of the failure
10. apply the smallest necessary correction
11. verify that communication works again

**Main focus:** network diagnostics, fault localization, routing and ARP analysis, packet captures, and systematic troubleshooting.

---

## Getting started

The exercises are designed to run inside the provided **Mininet VM**.

For each assignment:

1. Open a terminal in the corresponding assignment directory.
2. Read the local `README.md`, if provided.
3. Start the laboratory environment as specified in the exercise sheet.
4. Use the provided host terminals to inspect the network.
5. Run the provided Python applications where required.
6. Use Linux networking commands and Wireshark/tcpdump to analyse the traffic.
7. Modify infrastructure files only when the exercise explicitly asks you to do so.

If Mininet contains stale state from a previous run:

```bash
sudo mn -c
