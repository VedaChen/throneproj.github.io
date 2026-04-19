+++
title = "Windows 下 TUN 模式进阶"
description = "通过系统策略和浏览器设置，降低 Windows 下 TUN 模式的 DNS 泄露风险。"
weight = 1

[extra]
+++

本文介绍在 Windows 下使用 TUN 模式时，如何减少 DNS 泄露风险。

DNS 泄露会暴露你的真实访问目标和网络活动，可能导致隐私泄露、被网络运营商识别流量行为，甚至使代理策略失效。

## 1. 关闭 Windows 智能多宿主名称解析策略

虚拟网卡环境下可能出现 DNS 泄露。由于系统存在多网卡，Windows 可能优先使用响应更快的网卡进行解析，从而绕过虚拟网卡。

建议关闭该策略：

![关闭智能多宿主名称解析策略步骤 1](/images/windows-tun-dns-leak/step1-disable-smart-multi-homed.png)

![关闭智能多宿主名称解析策略步骤 2](/images/windows-tun-dns-leak/step2-group-policy.png)

![关闭智能多宿主名称解析策略步骤 3](/images/windows-tun-dns-leak/step3-policy-disabled.png)

## 2. 关闭浏览器 QUIC 功能

以 Chrome 为例，在地址栏输入：

`chrome://flags/`

搜索 `QUIC`，并将其设置为 `Disabled`。

![关闭浏览器 QUIC](/images/windows-tun-dns-leak/step4-disable-quic.png)
