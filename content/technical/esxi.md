---
title: VMware ESXi Server
date: 2020-04-27T16:47:57.198Z
---

This server runs the macOS and Solaris builds. In is an Apple
server machine, hosted at MacStadium.

## Network

The server has two IP addresses, one for the ESXi management,
and the other one is used for all VMs, via NAT.

It has two virtual switches. The first one is connected to
* the phyisical adapter,
* the management network,
* the 'NAT' network, which contains the VM that works as the
firewall.

{{< figure src="switch0.png" alt="" >}}

The second switch has all the real VMs, plus the firewall
that does the NAT.

{{< figure src="switch1.png" alt="" >}}

## Firewall

The firewall is a community edition pfsense, the WAN IP needs
to set manually, and it auto-detects the LAN:

{{< figure src="pf-if.png" alt="" >}}
