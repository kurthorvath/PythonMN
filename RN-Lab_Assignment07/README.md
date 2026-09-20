# RN-Lab Übung 7 – Starting Point

## Starting topology

The supplied starting point contains only:

```text
client -- r1 -- r2 -- server
```

There is **no r3** in the starting point.

The existing path is:

```text
client -> r1 -> r2 -> server
```

## Starting configuration

The infrastructure script explicitly:

1. configures every supplied interface,
2. brings every supplied interface up,
3. configures the client and server default routes,
4. configures the static routes for the existing path,
5. enables IPv4 forwarding on the routers,
6. prints the actual interface and routing state,
7. verifies connectivity hop by hop,
8. verifies client-to-server and server-to-client connectivity.

If the initial connectivity checks fail, the Mininet CLI is not opened.

## Student task

Extend the topology with an additional router and links so that the same server can also be reached through a second path.

The intended final topology is:

```text
             r3
            /  \
           /    \
client -- r1    server
           \    /
            \  /
             r2
```

The existing path through `r2` should be replaced/deactivated when testing the alternative path.

The destination should remain the same server destination. Do not create a second server.

Students must determine and configure the additional interfaces, IP addresses, forwarding, and routes.

## Useful commands

Inspect interfaces and routes:

```bash
ip -br addr
ip route
ip neigh
```

Test connectivity:

```bash
ping -c 4 10.0.2.2
traceroute 10.0.2.2
```

Inspect forwarding:

```bash
sysctl net.ipv4.ip_forward
```

Start the lab:

```bash
sudo python3 start_lab.py
```

## Infrastructure / application separation

`topology.py` contains the Mininet infrastructure.

`start_lab.py` contains the explicit network configuration and verification.

Students modify these files when extending the topology.
