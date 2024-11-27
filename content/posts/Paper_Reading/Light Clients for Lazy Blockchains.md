
+++
title = 'Light Clients for Lazy Blockchains'
date = 2024-11-27T19:35:27+08:00
draft = false
summary = "文章设计了一种协议，可以为惰性区块链创建高效的轻客户端。"
author = "Justin"
tags = ["Paper Reading","Lazy Blockchain","SPV","Light Client","blockChain"]
+++
## 关键词
`Light Client`, `Lazy Blockchain`, `SPV`,

## 概述
文章设计了一种协议，可以为惰性区块链创建高效的轻客户端。

惰性区块链(Lazy Blockchains)：将共识与交易验证和执行分离，以提高吞吐量。

### 挑战：

- Eager BlockChain：以太坊比特币这一类被称为是 Eager BlockChain，交易的验证执行与共识结合，只有正确的才包含。
- lazy BlockChain：指的是 共识与执行分离，以消除可扩展性在此的瓶颈，由全节点进行交易的执行并验证，一些现有的lazy BlockChain：Celestia (LazyLedger) 、Prism 、Parallel Chains 和 Snap-and-Chat 。

由于共识节点 不执行交易，所以类似于以太坊的那种SPV就不是很能支持。因为传统的SPV验证是验证merkle树，从而验证状态。
但是lazy的commitment 里面 没有状态，因为共识与执行分离。
>疑问：但是共识节点不执行交易，那共识什么呢？

### 主要贡献：
文章的贡献在于，构建一个可以与网络快速同步并获取余额的机制，构建一个请客户端。
- 提出了第一个惰性区块链的轻客户端，在通信和计算复杂性方面实现了对全节点的指数级改进
- 我们通过基于简化的证明来证明我们的系统是完整、健全和简洁的
- 我们实施我们的计划并衡量其绩效



