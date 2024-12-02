+++
title = 'A Scalable State Sharing Protocol for Low-Resource  Validator Nodes in Blockchain Networks'
date = 2024-12-02
draft = false
summary = "用带宽换取了节点存储"
author = "Justin"
tags = ["Paper Reading","Distributed storage","blockChain"]
+++
# A Scalable State Sharing Protocol for Low-Resource  Validator Nodes in Blockchain Networks


## 关键字
`Blockchain Networks`, `Distributed Hash Table`, `Low-Resource Validator Nodes,`

## 概述
背景：随着区块链的运行，存储数据也在不断增长，节点体积变大带来巨大的存储成本，随之而来的就是因为成本增加导致的独立运行节点的减少，去中心化特点变弱。

文章设计了一种协议，核心思想是将区块链网络用作复制状态机和分布式存储系统，从而实现不用在一个节点存储所有状态。
牺牲了网络带宽，换来了存储开销
通过对数据加密，也实现了安全

文章在以太坊上进行试验，稳定降低了存储，但是带来了较大的带宽开销，大约每个区块1.5-5MB左右，每个月增加大概300-1000GB的流量开销