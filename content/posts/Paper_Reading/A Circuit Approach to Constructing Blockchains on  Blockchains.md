+++
title = 'A Circuit Approach to Constructing Blockchains on  Blockchains'
date = 2024-11-25T19:05:27+08:00
draft = false
summary = "对一组给定的区块链，如何通过读写操作来构建更安全的覆盖区块链系统"
author = "Justin"
tags = ["Paper Reading","consensus","blockChain"]
+++
# A Circuit Approach to Constructing Blockchains on  Blockchains

## 关键字
`interchian consensus protocols`, `serial composition`, `traiangular composition`

## 概述
### 核心问题:
how can we build a more secure overlay blockchain by reading from and writing to a given set of blockchains?

对一组给定的区块链，如何通过读写操作来构建更安全的覆盖区块链系统( overlay blockchain)

### 文章动机：
- 活性与安全性对区块链会产生不同的影响，如何区分这些影响
- 那在构建复杂的覆盖区块链时，底层的活性与安全性会对上层产生什么影响
- 能否将对于活性与安全的依赖分开，实现更大的弹性，并更好的权衡

### 主要贡献：
文章类比电路中的开关，设计了两种基本区块链组合操作：
- 串型组合(serial)：两个区块链系统串型组合
- 三角组合(triangular)：三个区块链系统并行组合

### 核心内容： 
文章主要证明了三件事
- 对于串型组合：
	- 一个链安全，上层就安全
	- 两个链存活，上层才有活性
- 对于三角组合：
	- 三个都安全，上层才安全
	- 一半以上存活，上层就有活性
- 重复组合串型和三角结构可以构建任意数量组合覆盖区块链系统

文章从安全性(safe)与活性(live)两个角度来证明覆盖区块链系统的安全性

<div align=center>
<img src="http://image.justin955.top/A%20Circuit%20Approach%20to%20Constructing%20Blockchains%20on%20%20Blockchains-2.png" style="zoom:33%;" title="比例图"/>
</div>

当底层区块链满足图中所示的安全与活性比例时，覆盖区块链系统是安全的

通过组合，可以实现更复杂更通用的覆盖区块链系统，可以用于平衡在大规模区块链组合时 对于活性和安全的需求