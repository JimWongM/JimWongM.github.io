---
layout:     post
title:      Paper Reading on Bitcoin Anonymity
date:       2020-3-18
author:     Firef1y
catalog: true
tags:
    - paper
---


## 0x00 概览

[1].**An Analysis of Anonymity in the Bitcoin System**

--2011.Proceedings of the Third International Conference on Privacy,Security,Risk and Trust.

```

An attacker wishing to de-anonymize its users will attempt to construct the one-to-many mapping between users and public-keys and associate
information external to the system with the users. Bitcoin frustrates this attack by storing the mapping of a user to his or her public-keys on that user’s node only and by allowing each user to generate as many public-keys as required.


However, this flexibility comes at a price: the entire history of Bitcoin transactions is publicly available. 
In this paper we investigated the structure of two networks derived from this dataset and their implications for user anonymity
```

**摘要**
P2P电子货币系统比特币中的匿名性是个复杂的话题。系统中，用户被公钥唯一标识。攻击者为了识别出用户的身份会尝试构造用户与多个公钥的映射并且将系统外的信息与用户联系起来。为了阻止这样的攻击，比特币系统只在用户个人节点存储该用户与公钥的映射关系并且允许一个用户根据需要生成多个公钥。本文中我们研究从比特币交易历史网络中派生出的两个**拓扑结构**。这两个网络具有非凡的拓扑结构，提供了比特币系统的互补视图，并且对匿名性有意义。我们将这个**结构与外部信息和技术（例如上下文发现和流量分析）相结合**，以调查比特币盗窃案。

- 介绍比特币匿名性的背景以及文章结构
- 相关工作
- 简介比特币系统，提出交易网络和用户网络
- 构建交易网络和用户网络
- 利用两个网络拓扑图对匿名性进行研究
  - 整合线下信息
  - 根据比特币论坛14构建网络拓扑图
  - 对论坛比特币盗窃进行分析 

**核心**
多输入交易不可避免地存在某些地址联系，这必然表明他们的输入是同一所有者拥有的

**结论**
在过去的半个世纪中，未来主义者预示着无现金社会的到来。他们的许多预测已经实现，例如Anderson等人的“在线实时”付款系统和银行维护的“中央信息文件”。但是，现金仍然是一种竞争性且相对匿名的付款方式。比特币是在线世界中现金的电子类似物。它是分散的：没有中央机构负责比特币的发行，并且在进行在线转移时不需要涉及受信任的第三方。但是，这种灵活性是有代价的：整个比特币交易的历史是公开可用的。

在本文中，我们研究了从该数据集派生的两个网络的结构及其对用户匿名性的影响。使用适当的网络表示，可以将许多公钥相互关联，并与外部标识信息关联。使用适当的工具，可以详细观察已知用户的活动。这只能使用被动分析来执行。主动分析，有兴趣的各方可以在其中部署“标记”比特币并且合作的用户可以发现更多信息。我们还相信，大型集中式服务（例如交易所和钱包服务）能够识别和跟踪相当一部分用户活动。比特币社区的技术成员警告说，强匿名性并不是比特币系统的主要设计目标。但是，临时用户需要意识到这一点，尤其是在向用户和组织发送比特币时，他们不希望与其公开关联。


[2].**A fistful of bitcoins:characterizing payments among men with no names**

--2013.Proceedings of the Conference on Internet Measurement.


```
Consequently, Bitcoin has the unintuitive property that while the ownership of money is implicitly anonymous, its flow is globally visible. In this paper we explore
this unique characteristic further, using heuristic clustering to group Bitcoin wallets based on evidence of shared authority, and then using re-identification attacks
```
**摘要**
比特币是一种纯粹的在线虚拟货币，不受实物商品或主权义务的支持;相反，它依赖于加密保护和点对点协议的组合来见证定居点。因此，比特币具有不直观的特性，虽然货币的所有权是隐含的匿名，但它的流动是全球可见的。在本文中，我们进一步探索这一独特的特征，使用启发式聚类基于共享权限的证据对比特币钱包进行分组，然后使用重新识别攻击（即，商品和服务的经验性购买）来对这些集群的运营商进行分类。通过这一分析，我们描述了比特币市场的纵向变化，这些变化给系统带来的压力，以及那些寻求将比特币用于大规模犯罪或欺诈目的的人所面临的挑战。

- 从支付手段入手，介绍比特币及其匿名性
- 简单介绍本文工作
- 介绍比特币协议
- 网络统计
- 与各个机构交易，收集数据
- 构建交易图和公钥图
- 启发式聚类
- 对相关机构构建用户图
- 追踪盗窃

**核心**
1.多输入交易不可避免地存在某些地址联系，这必然表明他们的输入是同一所有者拥有的
2.考虑零钱地址，并评估零钱地址对聚类的影响，对其进行优化

**结论**
在这项研究中，我们提出了比特币网络的纵向特征，重点关注服务的兴起和比特币协议设计中可用的匿名性与当前实现的实际匿名性之间的差距 - 由于某些使用惯用语 - 由用户。为完成此任务，我们基于更改地址开发了一种新的聚类启发式，允许我们对属于同一用户的地址进行聚类。然后，使用通过我们自己与各种服务的经验交互标记的少量交易，我们确定主要机构及其之间的相互作用。即使我们相对较小的实验证明，这种方法可以对比特币经济的结构，如何使用以及参与其中的那些组织有相当的了解。


虽然我们的工作考察了当前和潜在匿名之间的差距，但人们可能会自然而然地想到 - 鉴于我们的新聚类启发式在面对变化时并不完全健壮10作者写道，“有理由相信来自其他领域的复杂结果（例如，使用网络拓扑对社交网络数据进行去匿名化的努力将很快应用于比特币交易图。“行为 - 这种差距将随着时间的推移如何演变，以及用户可以做些什么来实现更强大的匿名保证。我们认为，完全阻止我们的启发式方法需要用户做出重大努力，并且这种可用性的丧失不太可能吸引除了最有动力的用户（例如罪犯）之外的所有用户。然而，我们将这个假设的定量分析作为一个有趣的开放问题。

[3].**Quantitative analysis of the full bitcoin transaction graph**

--2013.Financial Cryptography and Data Security.

```
We downloaded the full history of this scheme, and analyzed many statistical properties of its associated transaction
graph. In this paper we answer for the rst time a variety of interesting questions about the typical behavior of users

The Bitcoin system is the best known and most widely used alternative payment scheme, but so far it was very difficult to get accurate information about how
it is used in practice. In this paper we describe a large number of statistical properties of the Bitcoin transaction graph
```

**摘要**
比特币计划是大规模全球支付系统的罕见示例，在该系统中，所有交易均可公开访问（但以匿名方式）。我们下载了该方案的完整历史记录，并分析了其相关交易图的许多统计属性。在本文中，我们首次回答了有关用户的典型行为，他们如何获取和如何使用比特币，账户中保留的比特币余额以及如何在各个账户之间转移比特币的各种有趣的问题。为了更好地保护他们的隐私。此外，我们隔离了系统中的所有大型交易，并发现几乎所有大型交易都与2010年11月发生的单个大型交易密切相关，尽管相关联的用户显然试图用许多奇怪的外观掩盖这一事实。交易图中的长链和分叉合并结构。

- 简要介绍工作
- 利用[1]进行聚类，侧重数据分析
- 展示分析结果
- 研究大数额交易

**结论**
比特币系统是最广为人知且使用最广泛的替代支付方案，但到目前为止，很难获得有关其实际使用方式的准确信息。在本文中，我们描述了比特币交易图的大量统计属性，其中包含所有用户在2012年5月13日之前进行的所有交易。我们发现，大多数铸造的比特币在从未参与任何外发交易的地址中保持休眠状态。我们发现，存在大量的微小交易，它们仅移动了单个比特币的一小部分，但是也有数百笔交易，它们移动了超过50,000个比特币。我们通过详细跟踪这些金额的累积方式和分散方式来分析所有这些大型交易，并意识到几乎所有这些大型交易都是2010年11月进行的单笔交易的后代。最后，我们注意到包含这些大笔交易及其邻域的子图具有许多奇怪的外观结构，这可能是试图掩盖这些交易之间的存在和关系的尝试，但可以通过遵循货币交易中的资金追踪来挫败这种尝试。

[4]. **Traveling the silk road: A measurement analysis of a large anonymous online marketplace**

--2013.Proceedings of the 22nd international conference on World Wide Web

```
We perform a comprehensive measurement analysis of Silk Road, an anonymous, international online marketplace that operates as a Tor hidden service and uses Bitcoin as its exchange currency
```

**摘要**
我们对Silk Road（一个匿名的国际在线市场，作为Tor隐藏服务并使用比特币作为交换货币）进行全面的度量分析。我们在2011年底至2012年底的八个月内收集和分析数据，包括2012年近六个月的每日市场爬行。我们将详细了解丝绸之路上出售的商品类型，以及卖方和丝绸之路经营者双方的收入。通过检查该站点上出售的24,400多个单独物品，我们表明，丝绸之路已被广泛用作受控物质和麻醉品的市场，并且大多数出售物品的销售时间不到三周。大多数卖家在抵达后大约三个月内消失了，但是在我们的整个评估间隔中，有112位卖家的核心存在。我们评估了所有卖家从公开发行中获得的总收入，使其略高于每月120万美元；这相当于丝绸之路运营商每月约92,000美元的佣金。我们进一步表明，市场一直在稳定运行，在我们的评估间隔内，日销售额和卖方总数总体上有所增加。我们讨论分析和结果对经济和政策的影响，包括对该领域未来研究的伦理考虑。

- 运作方式
- 收集数据
- 度量分析
- 经济影响
- 防御措施
- 相关工作

**结论**

我们对最大的匿名在线市场之一丝绸之路进行了我们认为是第一次的全面测量分析。我们进行了试点爬网，随后收集了六个月（2012年2月3日至2012年7月24日）的每日测量数据。我们分析了24,000多个项目，并解析了180,000多个反馈消息。我们在随附的网站（https://arima.cylab.cmu.edu/sr/）上提供了数据集的匿名版本。我们能够确定“丝绸之路”确实主要满足了毒品的需求（尽管也有其他商品），它由一个相对国际的社区组成，并且所有商品中有很大一部分在该网站上长期没有出售。我们进一步发现，活跃的卖家数量和销售量正在增加，相应地，在我们的评估间隔内，整个市场的平均价格略高于120万美元/月。


通过这些测量，我们讨论了一些可能的干预策略。使用适当的程序（例如，持久性进入门卫），Tor表现出对去匿名攻击的良好恢复能力，并且，除非操作员出错，否则是否有可能获得诸如丝绸之路之类的隐藏服务的确切位置的确凿证据仍然是一个公开的问题。题。经济攻击（例如，人为地造成比特币价值的大幅波动）可能会更有效地阻止此类地下市场上的商业活动，但会带来大量的附带成本。最终，减少消费者需求（例如，通过预防运动）可能是最可行的策略。

[5].**Evaluating user privacy in bitcoin**

--2013. Financial Cryptography and Data Security

```
However, in spite of its reliance on pseudonyms, Bitcoin raises a number of privacy concerns due to the fact that all of the transactions that take place are publicly
announced in the system.

In this paper, we investigate the privacy provisions in Bitcoin when it is used as a primary currency to support the daily transactions of individuals in a university
setting. More specifically...

Our findings show that the current measures adopted by Bitcoin are not enough to protect the privacy of users if Bitcoin were to be used as a digital currency in a university setting.
```

**摘要**
比特币正在迅速成为一种流行的数字支付系统。但是，尽管依赖假名，但由于所有发生的交易都是在系统中公开宣布的事实，比特币仍引起了许多隐私问题。在本文中，我们研究了比特币用作主要货币以支持大学环境中个人日常交易时的隐私条款。更具体地说，我们评估（i）通过分析真正的比特币系统，以及（ii）通过忠实模拟**大学中使用比特币的模拟器**来评估比特币提供的隐私。在这种情况下，我们的结果表明，即使用户采用比特币建议的隐私措施，也几乎可以恢复近40％用户的个人资料。据我们所知，这是全面分析和评估比特币隐私隐患的第一项工作。

- 建立隐私量化模型
- 活动不可链接性、配置文件不可区分性
- 启发式聚类 多输入与影子地址
- 模拟大学的比特币使用情况根据量化指标衡量聚类算法

**结论**
在本文中，我们评估了比特币用作主要货币以支持大学环境中个人日常交易时的隐私条款。
我们的发现表明，如果在大学环境中将比特币用作数字货币，则比特币当前采取的措施还不足以保护用户的隐私。更具体地说，我们依赖于模拟现实世界中大学环境中使用比特币的模拟器。我们的结果表明，如果在典型的大学环境中将比特币用作一种数字货币来支持用户的日常交易，则基于行为的聚类技术可以在很大程度上揭示40％的比特币用户的个人资料，即使这些用户尝试通过手动创建新地址来增强其隐私。最后，我们讨论了比特币开发人员可以集成以增强用户隐私的许多解决方案。



[6].**Structure and anonymity of the bitcoin transaction graph**

--2013.Future Internet.

```
In the currently used Bitcoin clients, the full transaction history is available at each node of the network to prevent double spending without the need for a central authority, forming a valuable source for empirical research on network structure, network dynamics, and the implied anonymity challenges, as well as guidance on the future evolution of complex payment systems. We found dynamical effects of which some increase anonymity while others decrease it.
```

在本文中，我们根据经验研究了比特币交易图的重要全局属性。在我们的分析中，我们使用比特币块链的数据高达块编号215399，这是2013年1月6日创建的。与现有作品相反，我们关注自比特币出现以来这些属性的时间演变，以便捕获交易网络的动态。此外，我们评估了这些属性对比特币用户实现匿名性的实际水平的影响；与先前的工作相比，我们专注于全球网络属性，依赖于经验数据并且不执行模拟。

结合了[1]和[5]中的方法
- 研究了随着时间演变实体数量、公钥数量的变化
- 休眠比特币的变化
- 进一步研究地址可链接性

[7].**A Graph-based  investigation of Bitcoin transactions**

--2014

```
This chapter describes a graph-based method for analyzing the identity clustering and currency flow properties of Bitcoin transactions.


The graph-based method for analyzing the identity clustering and currency flow properties of Bitcoin transactions can expedite forensic investigations of criminal cases such as Mt. Gox that involve doublespending, theft, money laundering or fraudulent transactions.
```

**摘要**

本章介绍了一种基于图的方法，用于分析比特币交易的身份聚类和货币流量属性。该方法可扩展至大型比特币图，专注于与刑事案件。

- 介绍比特币系统
- 考虑多输入、coinbase、找零地址进行聚类
- 谷歌LEVELDB利用
- 利用BFS进行货币流量分析
- Mt. Gox案例研究

**结论**

基于图的分析比特币交易的身份聚类和货币流量属性的方法可以加快对诸如Mt.涉及双重支出，盗窃，洗钱或欺诈性交易的行为。使用两年的比特币交易数据进行的实验表明，可以有效地聚类属于同一实体的不同比特币地址，以减少跟踪参与犯罪活动的比特币用户所需的法证费。此外，基于图的比特币交易分析可以帮助辨别涉及比特币用户的可疑交易行为和货币流量。

未来的工作将集中于增强地址组数据库以适应新的交易流。此外，将通过实际的比特币实体来完善比特币地址库，以帮助减少法证调查期间地址集的大小。


[8]**BitIodine: Extracting intelligence from the Bitcoin network**

--2014

```
However, the complete history of all transactions ever performed, called \blockchain",is public and replicated on each node. The data it contains is difficult to
analyze manually, but can yield a high number of relevant information.In this paper we present a modular framework, BitIodine, which parses the blockchain, clusters addresses that are likely to belong to a same user or group of users, classies such users and labels them, and nally visualizes complex information extracted from the Bitcoin network.
```
Spagnuolo还开发了一个强大的工具BitIodine来对比特币地址进行聚类，并将其与bitcointalk.org和bitcoin-otc中使用的标识符绑定，bitcointalk.org是比特币的场外交易市场。他们通过使用自己的工具识别由丝绸之路和由CryptoLocker引起的赎金付款的创建者和运营商Ross William Ulbricht拥有的比特币地址，证明了其有效性

在本文中，我们提出了一个模块化框架BitIodine，该框架解析区块链，将可能属于同一用户或一组用户的地址聚类，对这些用户进行分类并标记它们，最后可视化从比特币网络中提取的复杂信息

我们发布了BitIodine的早期原型，作为用于构建更复杂的比特币取证分析工具的库。



[9].**Zerocash: Decentralized Anonymous Payments from Bitcoin**
--2014，IEEE

```
Zerocoin (Miers et al., IEEE S&P 2013) tackles some of these privacy issues by unlinking transactions from the payment’s origin. Yet, it still
reveals payments’ destinations and amounts, and is limited in functionality.
In this paper, we construct a full-fledged ledger-based digital currency with strong privacy guarantees.
```

更改比特币协议，实现更强的匿名性。

比特币是广泛采用的第一种数字货币。虽然支付是在假名之间进行的，但比特币无法提供强有力的隐私保证：支付交易记录在公共分散的分类账中，从中可以推断出大量信息。Zerocoin（Miers et al。，IEEE S＆P 2013）通过取消交易与付款来源的关联来解决其中一些隐私问题。然而，它仍然显示付款的目的地和金额，并且功能有限。

在本文中，我们构建了一个完整的基于分类帐的数字货币，具有强大的隐私保障。我们的结果利用了零知识简洁非交互式知识论证（zk-SNARKs）的最新进展。

首先，我们制定和构建分散的匿名支付计划（DAP计划）。DAP方案使用户能够私下直接相互支付：相应的交易隐藏了支付的来源，目的地和转移金额。我们提供建筑安全的正式定义和证明。


其次，我们构建了Zerocash，这是我们DAP方案构建的实际实例。

[10].**An analysis of anonymity in bitcoin using P2P network traffic**

--2014.International Conference on Financial Cryptography and Data Security

```
Although previous work has analyzed the degree of anonymity Bitcoin offers using clustering and flow analysis, 
none have demonstrated the ability to map Bitcoin addresses directly to IP data. We propose a novel approach to ...
```

**摘要**
在过去的4年中，去中心化的P2P加密货币比特币受到了广泛关注。使用比特币创建伪匿名金融交易的能力使该货币对重视隐私的用户具有吸引力。尽管以前的工作已经使用聚类和流量分析方法分析了比特币所有者的匿名程度，但没有人展示出将比特币地址直接映射到IP数据的能力。我们提出了一种仅使用5个月内收集的实时交易记录来创建和评估此类映射的新颖方法。我们开发了启发式算法来识别比特币地址和IP地址之间的所有权关系。我们讨论了这些关系变得明显的情况，并演示了如何利用异常中继行为将近1,000个比特币地址映射到其可能的所有者IP。

- 剪裁数据
- 假设交易者IP
- 计算配对统计信息
- 确定配对
- 消除低于阈值的配对

IP级别的去匿名不受混合交易服务的影响

[11].**There’s No Free Lunch, Even Using Bitcoin: Tracking the Popularity and Profits of Virtual Currency Scams**

--2015.International Conference on Financial Cryptography and Data Security

```
We present the first empirical analysis of Bitcoin-based scams: operations established with fraudulent intent.
```

**摘要**
我们对基于比特币的欺诈行为进行首次实证分析：以欺诈意图建立的运营。通过将自愿人员收集的报告汇总并在在线论坛中进行跟踪，我们发现了192个诈骗并将其分为四类：庞氏骗局，采矿诈骗，诈骗钱包和欺诈性交易。在21％的情况下，我们还找到了相关的比特币地址，这使我们能够跟踪进出骗局的付款。我们发现，至少有1100万美元来自13000名不同受害者的骗局。此外，我们提供的证据表明，最成功的骗局取决于极少数受害者的大量捐款。最后，我们讨论了应对欺诈的方法。

- 识别欺诈的方法
- 高收益投资计划(HYIP)
- 具体介绍采矿投资骗局
- 诈骗钱包和交易所
- 比较不同的诈骗

基于交易关联的区块链数据分析
![eb417280533dc78cbcca97dd4f725ba7.png](en-resource://database/822:1)


[12].**Bitcoin over Tor isn't a Good Idea**

--2015. IEEE Symposium on Security and Privacy (SP)

```
While Bitcoin provides some level of anonymity (or rather pseudonymity) by encouraging the users to have any number
of random-looking Bitcoin addresses, recent research shows that this level of anonymity is rather low.
```

证实通过Tor使用比特币提供了有限的匿名性，容易收到中间人攻击
通过在用户计算机上设置cookie为比特币用户提供指纹技术

基于IP层嗅探

[13].**Bitcoin Transaction Graph Analysis**

--2015

```
While Bitcoin's presumed anonymity offers new avenues for commerce, several recent studies raise user-privacy concerns. 
We explore the level of anonymity in the Bitcoin system. Our approach is two-fold:...


In conclusion, we showed that by leveraging several sources of publicly available information via web-scraped forums and Bitcoin's transaction ledger, 
the bitcoin transaction network is shown to be not entirely anonymous.
```

探索比特币系统匿名程度
- 通过确定性或统计性将比特币公钥连接到真实的实体来注释交易图
- 利用图分析框架运行来注释的交易图，总结用户活动

区块链解析 Armony (还有其他几种过时的工具)
网页爬取 Scrpy6 爬取bitcointalk.org
交易指纹
开发图框架
构造交易用户图 http://compbio.cs.uic.edu/data/bitcoin
排名
去匿名

[14].**Data-driven de-anonymization in bitcoin**

--2015.

```
We analyse the performance of several clustering algorithms in the digital peer-to-peer currency Bitcoin.
Our results demonstrate that even modern wallet software can not protect its users properly.


Our objective for this project is to assess the effect of blockchain analysis on theprivacy of Bitcoin participants.
```

使用Connection Bloom Filtering 中实施的漏洞捕获比特币钱包与地址数据
对钱包地址进行聚类，四种启发式进行聚类
https://github.com/btcsuite/btcutil
对传统钱包和现代钱包进行分开研究

[15].**Privacy-enhancing overlays in bitcoin**

--2015. Financial Cryptography and Data Security.

```
In this paper, we explore the role of privacy-enhancing overlays in Bitcoin.

In this paper, we presented a denitional framework for the anonymity that virtual currencies such as Bitcoin provide. We then provided constructive solutions
for achieving this new notion of anonymity, and analyzed the extent to which it was already being achieved by existing Bitcoin overlays.
```

虚拟货币的正式定义框架，提出了可以满足的匿名型 防污性，提出了增强匿名性的方法

[16].**Behind closed doors:measurement and analysis of CryptoLocker ransoms in Bitcoin**

--2016.Proceedings of the Symposium on Electronic Crime Research.

```
We perform a measurement analysis of CryptoLocker, a family of ransomware that encrypts a victim’s files until a ransom
is paid, within the Bitcoin ecosystem from September 5, 2013 through January 31, 2014.
```


[17].**The Unreasonable Effectiveness of Address Clustering**

--2016,IEEE

```
Address clustering tries to construct the one-to-many mapping from entities to addresses in the Bitcoin system. Simple heuristics based on
the micro-structure of transactions have proved very effective in practice.In this paper we describe the primary reasons behind this effectiveness

```

解释为什么基于多输入的地址聚类是有效的
利用该方法进行数据分析与统计

[18].**A Bayesian Approach to Identify Bitcoin Users**

--2016

```
One of its most important properties is the high level of anonymity it provides for its users.
Monitoring the propagation of these messages and analyzing them carefully reveal hidden relations. 
In this paper,we develop a mathematical model using ...

While Bitcoin provides a signicant level of anonymity as Bitcoin addresses can be generated freely and without providing
any form of personal identication, the requirement to announce new transactions on the peer to peer network opens up the possibility of 
linking Bitcoin addresses to the IP addresses of clients.
```

使用概览方法开发数学模型，将比特币地址与IP相关联，进而确定地理位置
有公开数据

 

[19].**Blockchain Transaction Analysis Using Dominant Sets**

--2017,IFIP International Conference on Computer Information Systems and Industrial Management

```
It is important to know the in depth structure of blockchain by identifying common behaviors of the transactions and the effect of these behaviors on the nodes of the network. Dominant set approach can categorize the blockchain transactions into different clusters without mentioning number of clusters in advance.
```

使用优势集方法进行聚类，替代传统中心聚类方法
进行结果评估，未分析具体案例

[20].**A Survey on Security and Privacy Issues of Bitcoin**

--2017,IEEE

```
This exponential growth in the market value of Bitcoin motivates adversaries to exploit weaknesses for profit, 
and researchers to discover new vulnerabilities in the system, propose countermeasures, and predict upcoming trends.
In this paper, we present a systematic survey that covers the security and privacy aspects of Bitcoin
```

在本文中，我们提出了一项全面的调查，专门针对比特币及其相关概念的安全和隐私方面。我们讨论了最先进的攻击媒介，其中包括各种用户安全和交易匿名威胁，这些威胁限制（或威胁）实际应用和服务中比特币的适用性（或连续性）。我们还讨论了多年来提出的各种安全解决方案的效率，以解决比特币中现有的安全和隐私挑战。特别是，我们主要关注比特币的主要组成部分的安全挑战及其对策。此外，我们还讨论了用户隐私和交易匿名的问题，以及为实现隐私和提高比特币匿名性而进行的大量研究


在第二部分中，我们简要介绍了比特币，其中包括对主要组件的描述及其功能和相互作用。在第三节中，我们讨论了与比特币的开发，实施和使用相关的许多安全威胁。在第四部分，我们将讨论最先进的提案，这些提案可以对抗安全威胁或增强比特币的现有安全性。在第五节中，我们将讨论使用比特币及其现有解决方案的匿名性和隐私威胁。我们在第六节中提供了从我们的调查中获得的观察和未来研究方向的摘要

[21].**Behavior pattern clustering in blockchain networks**
--2017

```
However, blockchain faces its own problems and challenges. One key problem is to automatically cluster the behavior patterns of all the blockchain nodes
into categories. In this paper, we introduce the problem of behavior pattern clustering in blockchain networks and propose a novel algorithm termed BPC for this problem.


In this paper, we have introduced the problem of behavior pattern clustering in blockchain networks and have proposed a novel algorithm termed BPC to address this problem.
```
行为模式聚类BPC算法
与经典的中心化聚类算法进行比较

[22]**Visualizing dynamic Bitcoin transaction patterns**

--2017

```
However, retaining visual fidelity to the underlying data to retain a fuller understanding of activity within the network remains challenging, particularly in real time.
We expose an effective force-directed graph visualization employed in our large-scale data observation facility to accelerate this data exploration and derive useful insight among domain experts and the general public alike.
```
McGinn开发了一种工具来可视化比特币交易模式

github: bitcoin visualize


[23]**Tracking bitcoin users activity using community detection on a network of weak signals**

--2017

```
There is an ongoing debate on the question of users’ anonymity: while the Bitcoin protocol has been designed to ensure that the activity of individual users could not be tracked, some methods have been proposed to partially bypass this limitation. 
In this article, we show how the Bitcoin transaction network can be studied using complex networks analysis techniques, and in
particular how community detection can be efficiently used to re-identify multiple addresses belonging to a same user.

In this article, we have shown how community detection could be used to improve
re-identification of users in bitcoins.
```



[24].**Data-driven analysis of bitcoin properties: exploiting the users graph**

--2017.International Journal of Data Science and Analytics volume

```
Data analytics has recently enabled the uncovering of interesting properties of several complex networks. Among these, it is worth considering the bit-
coin blockchain, because of its peculiar characteristic of reflecting a niche, but also a real economy whose transactions are publicly available. In this paper we
present the analyses we have performed on the users graph inferred from the bitcoin blockchain
```

利用用户图对比特币系统属性进行分析
采用完整的中心聚类算法

数据收集
https://developers.google.com/protocol-buffers
https://blockchain.info/tags28

分析了聚类系数 中心度等属性



[25].**Identifying Bitcoin Users Using Deep Neural Network**

--2018

```
In Bitcoin user identification, an important challenge is to accurately link Bitcoin address to their owners.
In this paper, we propose a deep learning method to achieve address-user mapping.

After the test experiments of address verication, recognition and clustering on our test dataset, 
we conclude that the embedded address behaviors indeed conceal information of its owner.
```


[26].**Multi-Class Bitcoin-Enabled Service Identification Based on Transaction History Summarization**

--2018.IEEE

```
In recent years, Bitcoin has been used for many services and purposes, e.g. gambling, marketplace, but also even as an investment scam. In order to clarify how Bitcoin is used, it is in great importance to identify what kind of services are operated by Bitcoin addresses. In this paper, we propose a multiclass service identification scheme in Bitcoin based on novel transaction history summarization.
```

多类服务识别
提出如何检索历史交易，给定比特币地址，计算其历史交易特征

比特币标记 blockchain.info/tags WalletExplore
特征提取
训练机器学习分类器
性能评估

[27].**Characterizing Entities in the Bitcoin Blockchain**

--2018

```
A number of studies have shown that, in this pseudonymous context,identities can be leaked based on transaction features or offnetwork
information. In this work, we analyze the information revealed by the pattern of transactions in the neighborhood of a given entity transaction.


We formulate the problem of analyzing Bitcoin Blockchain transaction graph anonymity properties as a classification problem over a set of categories of Bitcoin users.
```

实体表征，关注链上信息泄露

从图邻居交易的角度实现实体分类
分析性能
将交易匿名型问题转化为比特币用户分类问题

[28].**Learning to Classify Blockchain Peers According to Their Behavior Sequences**

--2018

```
A key challenge that blockchain faces is to precisely classify the blockchain peers into categories with respect to their behavior patterns, which will not only
enable deeper insights into the blockchain network but also facilitate more effective maintenance of the various peers (in private chains). In this paper, we introduce and formulate the problem of behavior pattern classification in blockchain networks and propose a novel deep-learning-based method

In this paper, we have introduced the problem of behavior pattern classification in blockchain networks and have proposed a novel deep learning based approach termed PeerClassifier to address this issue.
```

制定了区块链网络中行为模式分类方法，基于深度学习的PeerClassifiner
不同分类方法进行比较
关注算法
- k邻近算法
- 决策树算法
- 支持向量机
- 神经网络


[29].**Bitcoin Users Deanonimization Methods**

--2018.Proceedings of the Institute for System Programming

```
Bitcoin is gaining more and more popularity in criminal society. That is why Bitcoin is often used as money laundering tool or payment method for illegal products and services. In this paper we explore various methods for Bitcoin users deanonimization, which is an important task in anti-money laundering process and cybercrime investigation.


Bitcoin privacy is an emergent field of research, which is gaining more and more attention from researchers all over the world. Being a popular payment tool along
criminals, the society needs tools and suitable laws to fight with illegal usage of bitcoin.
```

总结了各种去匿名化方法 地址划分 IP层识别
对图学习方法进行展望

[30].**Breaking Bad: De-Anonymising Entity Types on the Bitcoin Blockchain Using Supervised Machine Learning**

--2018.Proceedings of the 51st Hawaii International Conference on System Sciences 2018

```
Therefore, Bitcoin is widely assumed to provide a high degree of anonymity, which is a driver for its frequent use for illicit activities. This paper presents a novel approach for reducing the anonymity of the Bitcoin Blockchain by using Supervised Machine Learning to predict the type of yet-unidentified entities.
```

**摘要**

本文提出了一种新颖的方法，通过使用监督机器学习来预测尚未识别的实体的类型，从而减少比特币区块链的匿名性。我们使用了434个实体（约2亿笔交易）的样本，这些样本的身份和类型已被揭示，它们是训练集数据并建立了区分10个类别的分类器。我们的主要发现是，我们确实可以预测尚未确定的实体的类型。使用梯度提升算法，我们可以实现77％的精度和≈0.75的F1分数。我们讨论了监督机器学习的新颖方法，以发现比特币区块链匿名性及其在取证和财务合规性方面的潜在应用及其社会意义，概述了研究局限性并提出了未来的研究方向

我们的研究旨在确定我们是否可以预测尚未确定的集群属于以下预先定义的类别之一：交易，赌博，托管钱包，商家服务，采矿池，混合，勒索软件，欺诈，tor市场或其他
在多大程度上可以预测比特币区块链上尚未识别的集群的类别？


本研究中使用的数据集由Chainalysis公司[11]提供

总结了聚类算法和监督机器学习算法



[31].**Data Mining for Detecting Bitcoin Ponzi Schemes**

--2018

```
Despite being illegal in many countries, Ponzi schemes are now proliferating on
Bitcoin, and they keep alluring new victims, who are plundered of millions of dollars. We apply data mining techniques to
detect Bitcoin addresses related to Ponzi schemes.

However,
since all currency transfers are recorded on a public ledger, surveillance authorities can analyse them, trying to detect anomalous or suspect behaviours.
```

我们应用数据挖掘技术来检测与庞氏骗局有关的比特币地址。我们的出发点是真实庞氏骗局特征的数据集，我们通过在比特币区块链上分析用于执行骗局的交易来构建。我们使用该数据集尝试各种机器学习算法，并通过标准验证协议和性能指标评估其有效性。我们尝试过的最好的分类器可以识别出数据集中的大多数庞氏骗局，假阳性率低。

1)比特币庞氏骗局的地址和特征的公共数据集：goo.go/ToCho7
2)可以从区块链中提取数据集的开源工具github.com/bitcoinponzi
3）系统评估和比较用于分类比特币庞氏骗局的不同学习策略； 
4）在一个独立的数据集上对最佳分类器（包括我们所进行的实验）进行评估，该分类器能够识别出数据集中的大多数庞氏骗局，且误报率较低；
5）估计哪些是检测比特币上庞氏骗局的最有区别的功能

为此，我们可以利用基于以太坊的庞氏骗局[44]的公共数据集，该数据集收集152个庞氏骗局的地址和其他相关数据

[32] **A Probabilistic Model of the Bitcoin Blockchain**

--2018

```
The Bitcoin transaction graph is a public data structure organized as transactions between addresses, each associated with a logical entity. In this work, we
introduce a complete probabilistic model of the Bitcoin Blockchain.
```


[33]**Cascading Machine Learning to Attack Bitcoin Anonymity**

--2018

```
Its unregulated nature and inherent anonymity of users have led to a dramatic increase in its use for illicit activities. This calls for the development of novel methods capable of characterizing different entities in the Bitcoin network.
```


[34].**Research on de-anonymization techniques of bitcoin trading network**

--2019.Proceedings of the ACM Turing Celebration Conference

```
The Bitcoin system is an anonymous, decentralized crypto-currency. There are some deanonymizating techniques to cluster Bitcoin addresses and to map them to users’ identifications in the two research directions of Analysis of Transaction Chain (ATC) and Analysis of Bitcoin Protocol and Network (ABPN).

```

当前关于比特币去匿名的研究集中在两种方法上。一种是交易链分析（ATC），它是从公共区块链数据中获取交易，根据比特币匿名性的弱点对比特币地址进行分类[3-8]，并将比特币地址与个人身份相关联[7- 8]。另一种方法是分析比特币协议和网络（ABPN）。这利用了比特币交易的传播特性来推断新交易的源IP地址[9-13]，已知的攻击包括比特币协议嗅探器，Sybil攻击[10-12]，伪造的比特币节点[13]。抵制ATC攻击的方法是硬币混合[14-30]，而针对APBN攻击的方法是洋葱路由器（TOR）[32]，隐形互联网（I2P）[33]和交易远程发布（TRR）[34]。

    
[35].**Regulating Cryptocurrencies: A Supervised Machine Learning Approach to De-Anonymizing the Bitcoin Blockchain**

--2019

```
Because of Bitcoin’s comparably high level of anonymity, it has been labelled as the go-to currency for illicit activity.
Our paper aims to better understand the different kinds of transactions in the Bitcoin ecosystem in order to better inform managerial and organizational aspects of regulation and compliance.
```

[36].**Market Manipulation of Bitcoin: Evidence from Mining the Mt. Gox Transaction Network**

--2019

```
It is of great importance for investors and regulators to recognize whether there are market manipulation and its manipulation patterns. 
This paper proposes an approach to mine the transaction networks of exchanges for answering this question.
```


本文提出了一种挖掘交易所交易网络的方法来回答这个问题。通过获取山的泄漏的交易历史。以Gox比特币交易所为例，我们首先根据其特征将账户分为三类，然后将交易历史记录构建为三张图。通过分析构造图可以得到许多观察和发现。为了评估账户交易行为对比特币交易价格的影响，将这些图重建为系列，并重塑为矩阵。通过在矩阵上使用奇异值分解（SVD），我们确定了许多与价格波动有很大相关性的基础网络。在进一步分析基础网络中最重要的帐户时，会发现大量的市场操纵模式。根据这些发现，我们得出的结论是，山中存在严重的市场操纵。Gox交易所和加密货币市场必须加强监管


在介绍了第二部分中的数据集之后，我们将在第三部分中详细介绍静态网络分析，并在第四部分中详细介绍时间网络。最后，我们在第五节中提供了一些相关的工作，并在第六节中总结了本文

[37].**Blockchain Intelligence: When Blockchain Meets Artificial Intelligence**

--2019

区块链由于提供了安全和分散的资源共享方式而受到广泛关注。然而，现有的区块链系统在运营维护，智能合约的质量保证以及区块链数据的恶意行为检测方面也面临许多挑战。人工智能的最新进展为克服上述挑战带来了机遇。区块链与人工智能的集成可能有益于增强当前的区块链系统。本文介绍了区块链和人工智能（即区块链智能）的融合。本文还提供了一个案例研究，以进一步证明区块链智能的可行性并指出未来的方向

[38].**Deanonymizing Cryptocurrency With Graph Learning: The Promises and Challenges**

--2019.IEEE

```
Rooted from the nature of decentralization and anonymity of blockchain, the cryptocurrencies have, unfortunately, been leveraged for illicit activities by the criminals. The good news is that typical cryptocurrencies, such as Bitcoin, have to publicly publish their transactions, known as a graph, to retain their ultimate goal of trustless and decentralized transaction verification, which lends law enforcement a means to deanonymizing cryptocurrencies
```

图学习是一种非常强大的工具，可以提取图中每个顶点的潜在特征来完成各种任务，例如对图顶点进行分类。在这项工作中，我们讨论了利用图学习对匿名货币进行匿名化的前景和挑战，这可以帮助网络使用者规避基于加密货币的非法活动

总而言之，图学习是一种使加密货币去匿名的有前途的工具，但在计算领域却面临着越来越多的挑战。为了社会利益，未来的网络执法人员和研究人员应朝这个方向投资


[39]**The bow tie structure of the Bitcoin users graph**

--2019 Applid Network Science

```
The availability of the entire Bitcoin transaction history, stored in its public blockchain, offers interesting opportunities for analysing the transaction graph to obtain insight on users behaviour. 
This paper presents an analysis of the Bitcoin users graph, obtained by clustering the transaction graph, to highlight its connectivity structure and the economical meaning of the different obtained components
```

[40]**BitScope:Scaling Bitcoin Address De-anonymization using Multi-Resolution Clustering**

--2019

```
However,by analyzing the transaction pattern, tracking the fund flow, and associating addresses with real entities, it is possible to defeat this anonymity. One of the key challenges is scalability - it is difficult to produce useful results in a short time, while keeping up with terabytes of increasingly large blockchain data. We propose BITSCOPE, a de-anonymization system that uses a layered approach and exploits the domain-specific structures in Bitcoin transaction network.
```

[41].**An Evaluation of Bitcoin Address Classification based on Transaction History Summarization**

--2019

```
Unfortunately, some criminal behaviors which took advantage of this platform were not identified. This has discouraged many governments to support
cryptocurrency. Thus, the capability to identify criminal addresses becomes an important issue in the cryptocurrency network. In this paper, we propose new features in addition to those commonly used in the literature to build a classification model for detecting abnormality of Bitcoin network addresses.
```

在本文中，除了文献中常用的功能以外，我们还提出了一些新功能，以建立用于检测比特币网络地址异常的分类模型。这些功能包括各种高阶的交易时间（以区块高度表示），可以高效地总结交易历史。通过监督的机器学习方法在标签类别数据集上训练提取的特征。实验评估表明，这些功能显着提高了比特币地址分类的性能。我们在八个分类器下评估结果，并使用LightGBM达到87％/ 86％的最高Micro-F1 / Macro-F1


在第二部分，我们解释了比特币网络。接下来，我们将在第三节中研究有关比特币地址的识别或去匿名化的一些相关研究。第四部分说明了我们提出的方法：交易历史摘要。第五节详细介绍了数据收集，特征提取，分类和其他培训细节。然后，我们在第六节中评估分类结果，并在第七节中结束本文


[42]**BitCoiduite:Visualizing and Analyzing Entity Activity on the Bitcoin Network**

--2019
```
Yet, despite the fact that all financial transactions in Bitcoin are available in an openly accessible online ledger—the blockchain—not much is known about how different types of actors in the network (we call them entities) actually use Bitcoin. BitConduite offers an entity-centered view on transactions, making the data accessible to non-technical experts through a guided workflow for classification of entities according to several activity metrics.
```

[43]**Identifying the vulnerabilities of bitcoin anonymous mechanism based on address clustering**

-- 2019,Science China Information Science 

```
However, the relation among bitcoin transactions can be used to analyze the bitcoin privacy information, which seriously jeopardizes the bitcoin anonymity. Herein, we describe the vulnerabilities associated with the anonymity mechanism of bitcoin, including the relation among bitcoin addresses and the relation among bitcoin users.
```

[44]**Targeted Address Identification for Bitcoin with Network Representation Learning**

--2019


```
The anonymity and decentralization of Bitcoin make it widely accepted in illegal transactions, such as money laundering,drug and weapon trafficking, gambling, to name a few, which has already caused significant security risk all around the world. The obvious de-anonymity approach that matches transaction addresses and users is not possible in practice due to limited annotated data set. In this paper, we divide addresses into four types
```



[45]**A survey of Anonymity of Cryptocurrencies**

-- 2019
```
However, many studies have identified several problems associated with the privacy and anonymity of Bitcoin. 
Consequently, a large number of attempts have been made to address these issues, yet it has been proven that many such solutions do not provide an acceptable level
of anonymity. This survey presents an account of the level of anonymity achieved through those and attempts to provide a comparative evaluation across different constructions.

Our findings showed that despite numerous attempts to achieve complete anonymity and privacy of cryptocurrencies, 
limitations exist in their practical implementations and hence they had been unable to realise true anonymity in practice.
```


[46].**A Novel Methodology for HYIP Operators’Bitcoin Addresses Identification**

--2020

```
However, it has been widely reported that it can be used for investment scams, 
which are referred to as high yield investment programs (HYIP)
Although from the security forensic point of view it is very important to identify the HYIP operators' Bitcoin addresses, 
so far in the open technical literature no systematic method which reliably collects and identifies such Bitcoin addresses has been proposed. 
In this paper, a novel methodology is introduced which ...

```

本文介绍了一种新颖的方法，可以有效地收集大量HYIP运营商的比特币地址，并根据对他们的交易历史的新颖分析来识别它们。特别是，首先提出了一种基于抓取的方法，该方法能够从Internet收集2,000多个HYIP运营商的比特币地址，从而提供了大量的HYIP样本。其次，介绍了一种有监督的机器学习技术，该技术对特定的比特币地址是否属于HYIP运算符进行分类，并对其性能进行评估。所提出的分类方法基于两种新颖的方法，即减轻比特币价格波动影响的速率转换技术和减少计算量而不牺牲分类性能的采样技术。通过使用近30,000个实际比特币地址，通过计算机仿真实验获得的广泛性能评估结果表明，所提出的方法具有出色的性能，即，可以正确分类95％的HYIP地址，同时减少误报率。高于4.9％。为了进一步验证建议的分类器检测HYIP运营商的比特币地址的能力，我们针对最近发布的HYIP地址列表进行了测试，以达到93.75％的成功率，从而保持了其出色的检测准确性

Fleder[12]开发了一个系统，通过抓取最大的比特币论坛bitcointalk.org的主题，将真实姓名或实体与比特币地址联系起来
Bitcoin transaction graph analysis



## 0x01 总结

为了明确研究的问题，重新翻阅了论文的```abstract```和```conclusion```,学长提出的however方法真的香，初次阅读时总是关注论文的方法，往往容易忽略其研究的问题。有时候相同的方法研究的问题会有很大不同。探究比特币系统到底有多大程度的匿名性，探究比特币系统是否存在市场操作行为，研究庞氏骗局的识别，这些问题都可以用交易图分析对地址进行cluster,对用户进行cluster来实现。cluster的方法林林总总，作为论文叙述的核心部分。


however说白了是逻辑的一种转折，所以我们也关注```unfortunately、yet、despite、although、while```附近的论述，同时另一种定位方法是```In this paper```之前的一句话。

经过调研，给出两个版本的摘要与结论

**版本一**

比特币是一种基于点对点网络的去中心化的加密货币。由于其去中心化的不受监管的特性以及固有的匿名性而收到广泛的使用，然而，近期的研究表明比特币系统的匿名性并没有其声称的那么强，基于公开的交易记录，我们可以defeat匿名性。In this paper,我们提出了一个方法...基于用户交易行为进行user identification(classification)去展示通过公开的交易数据进行复杂网络分析比特币系统到底有多大程度的匿名性，更具体地，展示结合节点属性的社区发现算法如何应用于比特币系统进行去匿名化的研究。


我们把去匿名化问题定义为一个用户识别问题
我们提出了一个...方法，它的结果...,实验证明即使一个具备少量数据挖掘技巧的攻击者也可以轻易地破坏比特币系统的匿名性，这促使我们...我们未来的工作...


**版本二**

比特币是一种基于点对点网络的去中心化的加密货币。由于其去中心化的不受监管的特性以及固有的匿名性，比特币系统成为了犯罪行为活跃的平台。所以需要一个新颖的方法 to de-anonymizing bitcoin.In this paper,我们提出了一个方法...



我们把去匿名化问题定义为一个用户识别问题
我们提出了一个...方法，它的结果...,我们的结果可以实现犯罪行为的识别，为相关犯罪行为的取证调查提供帮助，同时也证实比特币系统的匿名性程度。我们未来的工作...


**主要差别**就是是否侧重违法犯罪，但研究的问题就是去匿名化

版本一的问题可以具体到通过公开的交易数据，发现比特币系统能够实现多大程度的匿名性

版本二不强调多大程度的匿名性，而是为了监管犯罪行为(目的)，我要去匿名化，我用了什么方法
