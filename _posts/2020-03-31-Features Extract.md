---
layout:     post
title:      Features Extract in Bitcoin
date:       2020-3-31
author:     Firef1y
header-img: img/post-bg-desk.jpg
catalog: true
tags:
    - paper
---

这里介绍四篇论文提取比特币地址或者实体特征的方法，作为参考。

## 0x00 Multi-Class Bitcoin-Enabled Service Identification Based on Transaction History Summarization

--2018 IEEE International Conference on Internet of Things (iThings) and IEEE Green Computing and Communications (GreenCom) and IEEE Cyber, Physical and Social Computing (CPSCom) and IEEE Smart Data (SmartData)  两颗星

![image](https://raw.githubusercontent.com/JimWongM/ImageHost/master/img/20200331100759.png)

**一天的交易频率**：一些服务经常发生交易，一些交易较少

**recieved transaction占该地址所有交易的比例**

**coinbase transaction占该地址所有交易的比例**：挖矿类型有更高的比例

**交易输入的个数**

**交易输出的个数**

**花费多少金额作为输入的频率**

**花费多少金额作为输出的频率**

**地址同时出现在输入输出的交易比例**

结合了服务类型的特征，考虑地址向量的抽取

## 0x01 An Evaluation of Bitcoin Address Classification based on Transaction History Summarization

--2019 ICBC IEEE International Conference on Blockchain and Cryptocurrency 三颗星但不是C类

这篇论文基于上一篇论文增加了一些特征

- Basic Statics
  - 基于上文的8个特征
- Extra Statics
  - lifetime
  - total received bitcoins
  - total spent bitcoins
  - 交易数量，不同类型spent、received、coinbase、payback交易的数量
  - balance
- Moments--temporal information corresponding to transaction distributions
  - first moment--mean
  - second central moment--variance 方差
  - third standardized momemt--skewness 偏度
  - fourth standardized moment--kurtosis 峰度

有图有真相
![image](https://raw.githubusercontent.com/JimWongM/ImageHost/master/img/20200331104747.png)


## 0x02 A Probabilistic Model of the Bitcoin Blockchain

--2018 CVPR Workshop paper A类workshop

**Address features**(10)
- total BTC received
- total BTC balance
- the number of input/output transactions
- address spent/received/payback transaction

**Entity features**(8)
defined at the entity level

**Temporal features**(16)
- the number of weeks,months,years of activity
- the number of entity traded with per week,month,year
- the number of receiving,sending days
- the activity period duration
- the active day ratio

**Centrality features**(42)
based on entity graph

**Motif features**
- 1-motif features(44)
  - the value of incoming/outgoing transaction
  - the number of incoming/outgoing address
  - the number of incoming/outgoing transactions per day
  - total value
  - total fee
- 2-motif features(81)
- 3-motif features(114)


## 0x03 Identifying Bitcoin Users Using Deep Neural Network

--ICA3PP 2018: Algorithms and Architectures for Parallel Processing  C类

![image](https://raw.githubusercontent.com/JimWongM/ImageHost/master/img/20200331111035.png)

**address statistical features**
- the average time interval of an address be used
- the most frequent transaction type an address involved in

**address transaction history features**

It directly shows that the patterns of an owner when interacting with the Bitcoin system.

For a simple instance, if an address has never paid any fees other than Bitcoin enforcement in its whole transaction history, it is highly unlikely that it belongs to a user that constantly pay extra transaction fees out of self-willingness to speed up the transaction conrmation.



## 0x04 Our Features Extracting 

基于API提供的JSON数据进一步解析之后，我们可以获取到的数据如下：


![image](https://raw.githubusercontent.com/JimWongM/ImageHost/master/img/20200331112032.png)

**Address features**
- 交易总数
- 作为输入的交易数，作为输出的交易数，既输入又输出的交易数
- 总收到的BTC
- 总花费的BTC
- 余额

**Temporal features**
- 一天、一周、一月的交易数
- 交易的平均时间间隔
- 最早交易和最晚交易的时间跨度
- 交易活跃天数的比例

**1-motif features**
- 交易的输入/输出个数
- 交易费
- 输入/输出金额

**Graph Topology features**

基于图结构的社区发现