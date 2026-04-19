+++
title = "Advanced TUN Mode on Windows"
description = "Reduce DNS leak risks in Windows TUN mode through system policies and browser settings."
weight = 1

[extra]
+++

This article explains how to reduce DNS leak risks when using TUN mode on Windows.

DNS leaks can expose your real destination domains and network activity, reduce privacy, make ISP traffic profiling easier, and even weaken your proxy routing strategy.

## 1. Disable Smart Multi-Homed Name Resolution in Windows

DNS leaks may occur in environments with virtual network adapters. With multiple network interfaces active, Windows may send DNS queries through the fastest responding interface, which can bypass the virtual adapter.

It is recommended to disable this policy:

![Disable Smart Multi-Homed Name Resolution step 1](/images/windows-tun-dns-leak/step1-disable-smart-multi-homed.png)

![Disable Smart Multi-Homed Name Resolution step 2](/images/windows-tun-dns-leak/step2-group-policy.png)

![Disable Smart Multi-Homed Name Resolution step 3](/images/windows-tun-dns-leak/step3-policy-disabled.png)

## 2. Disable QUIC in the browser

Using Chrome as an example, open:

`chrome://flags/`

Search for `QUIC` and set it to `Disabled`.

![Disable QUIC in browser](/images/windows-tun-dns-leak/step4-disable-quic.png)
