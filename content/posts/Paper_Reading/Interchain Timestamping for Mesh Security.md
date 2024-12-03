+++
title = 'Interchain Timestamping for Mesh Security'
date = 2024-11-25T19:35:27+08:00
draft = true
summary = "文章设计了名为“Interchain Timestamping”的协议，使得可以底层链获取最优的安全性"
author = "Justin"
tags = ["Paper Reading","timestamping","blockChain"]
+++



## 关键字
`Interchain timestamping`, `mesh security`

## 概述

**背景与动机**：
在当前的多链世界中，通过对多条链的读写可以达到多链场景下的最佳安全性是什么？
提出一个很基本的问题：多链环境下，可否通过现有的跨链协议来借出安全性？跨链协议除了可以转移资产，能否转移安全性？

**主要贡献：**
文章设计了名为“Interchain Timestamping”的协议，使得可以底层链获取最优的安全性，并且可以量化。

**核心原理：**
![](http://image.justin955.top/202412031517543.png)

**Timestamps**：指将一个区块头签名后 作为一笔交易发送到另一条链上，作为一个 checkpoint 这种形式就称为是Timestamps
文章通过这设计协议，实现了通过Timestamps保证Consumer链的安全性，并且加强了 网格安全性(mesh scurity)

**部分内容：**
文章提供了 这样一个 场景：
![|325](http://image.justin955.top/202412031519675.png)
>区块高度向右增长

一个消费者链，k个提供者链：
消费者链定期向提供者链上打时间戳，然后k个提供者链之间，也是层层递进，

文章指出，存在两类跨链bridgs：
- multi-signature bridges：这种桥接方式依赖一个外部委员会（committee）进行签名，这个委员会通常不是发送链和接收链的验证者（validators），而是独立存在的第三方
- light-client based bridges：这种桥接方式依赖发送链的验证者签署区块头信息（block headers），并将这些区块头传递给接收链上的一个轻客户端（light client）进行验证。

并且 轻客户端 实际上 就是接收区块头 并提交到本链上，所以来说 天然支持了时间戳这个操作，不需要额外的开销


作者基于“Slashable Safety”框架，从安全性的角度来说，有两个指标：
>这两个指标还有待学习其含义
- Slashable Safety Resilience：现安全性违规（safety violation）时，可以被追责并削减质押（slashing）的验证者数量。换言之，数量越多，意味着攻击成本越高，协议的经济安全性越强。
- Liveness Resilience：需要多少验证者参与攻击才能导致区块链失去活性（无法出块

并得出来4个安全性方面的结论：
> 说实话，只看懂了1和3 ，2和4两个讲述经济安全性的暂时没有看懂
- 只要消费者链或提供者链中至少有一个是安全的，链间时间戳就可以确保带有时间戳的消费者链的安全
- 通过链间时间戳实现的这种经济安全性是所有可能的链间共识协议中最大的
- 如果消费者链和所有提供者链都处于liveness，则链间时间戳可以保证带有时间戳的消费者链的liveness。
- 在所有仅从消费者链向提供商链发送简洁承诺的链间协议中，如果独立消费者链的审查阻力小于每个提供商链的审查阻力，则链间时间戳可以实现最佳的审查阻力

实际上最后就推导出：在消费者链的各方面安全性低于k条链的情况下，可以通过这种方式，增加些安全性，并且不需要发送数据，只是发送承诺，也保证了数据的安全。