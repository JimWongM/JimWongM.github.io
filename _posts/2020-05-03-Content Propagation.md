---
layout:     post
title:      Content Propagation
date:       2020-5-3
author:     Firef1y
catalog: true
tags:
    - paper
---

## [1]*.Partially labeled classification with markov random walks NIPS2002

To classify a large number of unlabeled examples we combine a limited number of labeled examples with a Markov random walk representation
over the unlabeled examples. The random walk representation exploits any low dimensional structure in the data in a robust, probabilistic
manner. We develop and compare several estimation criteria/algorithms suited to this representation. This includes in particular multi-way classification
with an average margin criterion which permits a closed form solution. The time scale of the random walk regularizes the representation
and can be set through a margin-based criterion favoring unambiguous classification. We also extend this basic regularization by adapting
time scales for individual examples. We demonstrate the approach on synthetic examples and on text classification problems.

利用random walk进行分类的具体算法

## [2].Scalable influence maximization for prevalent viral marketing in large-scale social networks SIGKDD2003

Influence maximization, defined by Kempe, Kleinberg, and Tardos(2003), is the problem of **finding a small set of seed nodes** in a social network that maximizes the spread of influence under certain influence cascade models. The scalability of influence maximization is a key factor for enabling prevalent viral marketing in large-scale online social networks. Prior solutions, such as the greedy algorithm of Kempe et al. (2003) and its improvements are slow and not scalable, while other heuristic algorithms do not provide consistently good performance on influence spreads. In this paper, we design a new heuristic algorithm that is easily scalable to millions of nodes and edges in our experiments. Our algorithm has a simple tunable parameter for users to control the balance between the running time and the influence spread of the algorithm. Our results from extensive simulations on several real-world and synthetic networks demonstrate that our algorithm is currently the best scalable solution to the influence maximization problem: (a) our algorithm scales beyond million-sized graphs where the greedy algorithm becomes infeasible, and (b) in all size ranges, our algorithm performs consistently well in influence spread—it is always among the best algorithms, and in most cases it significantly outperforms all other scalable heuristics to as much as 100%–260% increase in influence spread.

确定影响扩散种子节点，最大化影响扩散

## [3].Combining link and content for community detection: a discriminative approach  SIGKDD2009

In this paper, we consider the problem of combining link and content analysis for community detection from networked data, such as paper citation networks and Word Wide Web.Most existing approaches combine link and content information by **a generative model** that generates both links and contents via a shared set of community memberships.These generative models have some shortcomings in that they failed to consider **additional factors that could affect the community memberships** and isolate the **contents that are irrelevant to community memberships**. To explicitly address these shortcomings, we propose a discriminative model for combining the link and content analysis for community detection. First, we propose **a conditional model** for link analysis and in the model, we introduce hidden variables to explicitly model the popularity of nodes. Second, to alleviate the impact of irrelevant content attributes, we develop **a discriminative model** for content analysis. These two models
are unified seamlessly via the community memberships. We present efficient algorithms to solve the related optimization problems based on bound optimization and alternating projection.Extensive experiments with benchmark data sets show that the proposed framework significantly outperforms the state-of-the-art approaches for combining link and content analysis for community detection.

解释了 community membership的缺点，提出了conditional model for link analysis 和 discriminative model for content analysis

## [4]*.On approximation of real-world influence spread MLKDD2012

To find the most influential nodes for viral marketing, several models have been proposed to describe the influence propagation process.Among them, the Independent Cascade (IC) Model is most widelystudied.However, under IC model, computing influence spread (i.e., the expected number of nodes that will be influenced) for each given seed set has been proved to be #P-hard. To that end, in this paper, we propose GS algorithm for quick approximation of influence spread by solving a linear system, based on the fact that propagation probabilities in real-world social networks are usually quite small. Furthermore, for better approximation, we study the structural defect problem existing in networks, and correspondingly, propose enhanced algorithms, GSbyStep and SSSbyStep, by incorporating the Maximum Influence Path heuristic.
Our algorithms are evaluated by extensive experiments on four social networks. Experimental results show that our algorithms can get better approximations to the IC model than the state-of-the-arts.

influence propagation process 可以借鉴

## [5].Efficient community detection in large networks using content and links WWW2013

In this paper we discuss a very simple approach of combining content and link information in graph structures for the purpose of community discovery, a fundamental task in network analysis. Our approach hinges on the basic intuition that many networks contain **noise in the link structure** and that **content information**
can help strengthen the community signal. This enables ones to eliminate the impact of noise (false positives and false negatives), which is particularly prevalent
in online social networks and Web-scale information networks. Specifically we introduce a measure of signal strength between two nodes in the network by fusing their link strength with content similarity. Link strength is estimated based on whether the link is likely (with high probability) to reside within a community. Content similarity is estimated through cosine similarity or Jaccard coefficient. We discuss a simple mechanism for fusing content and link similarity. We then present a biased edge sampling procedure which retains edges that are locally relevant for each graph node. The resulting backbone graph can be clustered using standard community discovery algorithms such as Metis and Markov clustering.
Through extensive experiments onmultiple real-world datasets (Flickr,Wikipedia and CiteSeer) with varying sizes and characteristics, we demonstrate the effectiveness
and efficiency of our methods over state-of-the-art learning and mining approaches several of which also attempt to combine link and content analysis for
the purposes of community discovery. Specifically we always find a qualitative benefit when combining content with link analysis. Additionally our biased graph
sampling approach realizes a quantitative benefit in that it is typically several orders of magnitude faster than competing approaches.

考虑到了噪音，一个简单的基于拓扑结构和节点内容的方法

## [6]*.Influence-based networkoblivious community detection ICDM2013

How can we detect communities when the social graphs is not available? We tackle this problem by modeling social contagion from a log of user activity, that is a dataset of tuples (u; i; t) recording the fact that user u “adopted” item i at time t. This is the only input to our problem.We propose a stochastic framework which assumes that item adoptions are governed by un underlying diffusion process over the unobserved social network, and that such diffusion model is based on community-level influence. By fitting the model parameters to the user activity log, we learn the community membership and the level of influence of each user in each community. This allows to identify for each community the “key” users, i.e., the leaders which are most likely to influence the rest of the community to adopt a certain item. The general framework can be instantiated with different diffusion models. In this paper we define two models: the extension to the community level of the classic (discrete time) Independent Cascade model, and a model that focuses on the time delay between adoptions. To the best of our knowledge, this is the first work studying community detection without the network.

user log的思想分比特币系统很契合，其中key user的概念类似于 content propagation

## [7]*.Social influence based clustering of heterogeneous information networks SIGKDD2013

Social networks continue to grow in size and the type of information hosted. We witness a growing interest in clustering a social network of people based on both their social relationships and their participations in activity based information networks. In this paper, we present a social influence based clustering framework
for analyzing heterogeneous information networks with three unique features. First, we introduce a novel social influence based vertex similarity metric in terms of both self-influence similarity and co-influence similarity. We compute self-influence and coinfluence based similarity based on social graph and its associated activity graphs and influence graphs respectively. Second, we compute the combined social influence based similarity between each pair of vertices by unifying the self-similarity and multiple co-influence similarity scores through a weight function with an iterative update method. Third, we design an iterative learning algorithm,SI-Cluster, to dynamically refine the K clusters by continuously quantifying and adjusting the weights on self-influence similarity and on multiple co-influence similarity scores towards the clustering convergence. To make SI-Cluster converge fast, we transformed a sophisticated nonlinear fractional programming problem of multiple weights into a straightforward nonlinear parametric programming problem of single variable. Our experiment results show that SI-Cluster not only achieves a better balance between
self-influence and co-influence similarities but also scales extremely well for large graph clustering.

权重的更新方法值得学习

## [8]*.Pagerank with priors:An influence propagation perspective AAAI Press

Recent years have witnessed increased interests in measuring authority and modelling influence in social networks. For a long time, PageRank has been
widely used for authority computation and has also been adopted as a solid baseline for evaluating social influence related applications. However, the
connection between authority measurement and influence modelling is not clearly established. To this end, in this paper, we provide a focused study on
understanding of PageRank as well as the relationship between PageRank and social influence analysis. Along this line, we first propose a linear social
influence model and reveal that this model is essentially PageRank with prior. Also, we show that the authority computation by PageRank can be enhanced
with more generalized priors. Moreover, to deal with the computational challenge of PageRank with general priors, we provide an upper bound for
top authoritative nodes identification. Finally, the experimental results on the scientific collaboration network validate the effectiveness of the proposed
social influence model.

一如标题，著名的Pagerank

## [9].Semantic Divergence Based Evaluation of Web Service Communities, Services Computing (SCC) 2016 IEEE International Conference C类

The number of community detection algorithms is growing continuously adopting a topological based approach to discover optimal subgraphs or communities. In this paper, we
propose a new method combining both topology and semantic to evaluate and rank community detection algorithms. To achieve this goal we consider a probabilistic topic based approach to define a new measure called semantic divergence of communities. Combining this measure with others related to prior knowledge, we compute a score for each algorithm to evaluate the effectiveness of its communities and propose a ranking method. We have evaluated our approach considering communities of real web services.

## [10].Assessment of effectiveness of content models for approximating Twitter social connection structures, Advances in Social Networks Analysis and Mining (ASONAM) 2016 IEEE/ACM International Conference

This paper explores the social quality (goodness) of community structures formed across Twitter users, where social links within the structures are estimated based upon semantic properties of user-generated content (corpus). We examined the overlap of the community structures of the constructed graphs, and followership-based social communities, to find the social goodness of the links constructed. Unigram, bigram and LDA content models were empirically investigated for evaluation of effectiveness, as approximators of underlying social graphs, such that they maintain the community social property. Impact of content at varying granularities, for the purpose of predicting links while retaining the social community structures, was investigated. 100 discussion topics, spanning over 10 Twitter events, were used for experiments. The unigram language model performed the best, indicating strong similarity of word usage within deeply connected social communities. This observation agrees with the phenomenon of evolution of word usage behavior, that transform individuals belonging to the same community tending to choose the same words, made by [1], and raises a
question on the literature that use, without validation, LDA for content-based social link prediction over other content models. Also, semantically finer-grained content was observed to be more effective compared to coarser-grained content.

social quality问题

## [11]*.An Efficient Algorithm for Community Detection in Attributed Social Networks, Proceedings of the 10th International Conference on Informatics and Systems2016.

Community detection in real-world social networks has gained significant attention in the last decade. With the increase of rich attribute information associated with nodes, identifying meaningful communities becomes more challenging. In this paper, we propose a new algorithm for detecting communities that considers the structure of the network as well as node actions and attributes. The proposed algorithm first detects leaders of the social network then forms communities around those leaders. Experimental results on data from a real world social network shows that our algorithm can effectively improve the quality of the communities identified compared with other algorithms.

拓扑结构和属性信息的结合，优先寻找leader 节点

## [12]*.Joint Identification of Network Communities and Semantics via Integrative Modeling of Network Topologies and Node Contents AAAI2017


The objective of discovering network communities, an essential step in complex systems analysis, is two-fold: identification of functional modules and their semantics at the same time. However, most existing community-finding methods have focused on finding communities using network topologies, and the problem of extracting module semantics has not been well studied and node contents, which often contain semantic information of nodes and networks, have not been fully utilized. We considered the problem of identifying network communities and module semantics at the same time. We introduced a novel generative model with two closely correlated parts, one for communities and the other for semantics. We developed a co-learning strategy to jointly train the two parts of the model by combining a nested **EM algorithm and belief propagation**. By extracting the latent correlation between the two parts, our new method is not only robust for finding communities and semantics, but also able to provide more than one semantic explanation to a community. We evaluated the new method on artificial benchmarks and analyzed the semantic interpretability by a case study. We compared the new method with eight stateof- the-art methods on ten real-world networks, showing its superior performance over the existing methods.

belief propagation 的过程

## [13].Semantic Community Identification in Large Attribute Networks,AAAI 2016

Identification of modular or community structures of a network is a key to understanding the semantics and functions of the network. While many network community detection methods have been developed, which primarily explore network topologies, they provide little semantic information of the communities discovered. Although structures and semantics are closely related, little effort has been made to discover and analyze these two essential network properties together.By integrating network topology and semantic information on nodes, e.g., node attributes, we study the problems of detection of communities and inference of their semantics simultaneously.
We propose a novel nonnegative matrix factorization (NMF) model with two sets of parameters, **the community membership matrix and community attribute matrix**,
and present efficient **updating rules to evaluate the parameters with a convergence guarantee**. The use of node attributes improves upon community detection and provides a semantic interpretation to the resultant network communities. Extensive experimental results on synthetic and real-world networks not only show the superior performance of the new method over the state-of-the-art approaches, but also demonstrate its ability to semantically annotate the communities.

## [14].Graph Clustering Based on Attribute-Aware Graph Embedding ASONAM 2017

Graph clustering is a fundamental problem in social network analysis, the goal of which is to group vertices of a graph into a series of densely knitted clusters with each cluster well separated from all the others. Classical graph clustering methods take advantage of the graph topology to model and quantify vertex proximity. With the proliferation of rich graph contents, such as user profiles in social networks, and gene annotations in protein interaction networks, it is essential to consider both
the structure and content information of graphs for high-quality graph clustering. In this paper, we propose a graph embedding approach to clustering content-enriched graphs. The key idea is to **embed each vertex of a graph into a continuous vector space** where the localized structural and attributive information of vertices can be encoded in a unified, latent representation. Specifically, we quantify vertex-wise attribute proximity into **edge weights, and employ truncated, attribute-aware random walks** to learn the latent representations for vertices. We evaluate our attribute-aware graph embedding method in real-world attributed graphs, and the results demonstrate its effectiveness in comparison with state-of-the-art algorithms.

## [15]*.Adaptive Community Detection Incorporating Topology and Content in Social Networks, Advances in Social Networks Analysis and Mining (ASONAM) 2017 


## [16].Enhancing Network Embedding with Auxiliary Information: An Explicit Matrix Factorization Perspective DASFAA 2018 B类

Recent advances in the field of network embedding have shown the low-dimensional network representation is playing a critical role in network analysis. However, most of the existing principles of network embedding do not incorporate auxiliary information such as content and labels of nodes flexibly. In this paper, we take a matrix factorization perspective of network embedding, and incorporate structure, content and label information of the network simultaneously. For structure, we validate that the matrix we construct preserves high-order proximities of the network. Label information can be further integrated into the matrix via the process of random walk sampling to enhance the quality of embedding in an unsupervised manner, i.e., without leveraging downstream classifiers. In addition, we generalize the Skip-Gram Negative Sampling model to integrate the content of the network in a matrix factorization framework. As a consequence, network embedding can be learned in a unified framework integrating network structure and node content as well as label information simultaneously. We demonstrate the efficacy of the proposed model with the tasks of semi-supervised node classification and link prediction on a variety of real-world benchmark network datasets.

## [17].Temporally Evolving Community Detection and Prediction in Content-Centric Networks  ECML PKDD 2018 B类

In this work, we consider the problem of combining link, content and temporal analysis for community detection and prediction in evolving networks. Such temporal and content-rich networks occur in many real-life settings, such as bibliographic networks and question answering forums. Most of the work in the literature (that uses both content and structure) deals with static snapshots of networks, and they do not reflect the dynamic changes occurring over multiple snapshots. Incorporating dynamic changes in the communities into the analysis can also provide useful insights about the changes in the network such as the migration of authors across communities. In this work, we propose Chimera1, a shared factorization model that can simultaneously account for graph links, content, and temporal analysis. This approach works by extracting the latent semantic structure of the network in multidimensional form, but in a way that takes into account the temporal continuity of these embeddings. Such an approach simplifies temporal analysis of the underlying network by using the embedding as a surrogate. A consequence of this simplification is that it is also possible to use this temporal sequence of embeddings to predict future communities. We present experimental results illustrating the effectiveness of the approach.

## [18].Dynamic Topical Community Detection in Social Network: A Generative Model Approach, Access IEEE2019

Social networks that are dynamic contain rich network structure and content information. In dynamic networks, it is necessary to discover communities and their topical meanings. However, existing methods either only discover communities with ignoring their topical meaning in dynamic networks, or they discover communities and their topics in static networks. In this paper, we identify the problem of dynamic topical community detection and propose a dynamic topical community detection (DTCD) method to detect communities and their topical meanings in dynamic networks. The DTCD is a generative model integrating network structure, text, and time. The DTCD considers a community as a mixture of topics and generates the neighbors and documents of the node and their time stamps at the same time via the community. The latent variables are learned by collapsed Gibbs sampling. The DTCD not only can nd communities and their topics, but also capture the temporal variations of communities and topics. The experimental results on two real-world datasets demonstrate the effectiveness of DTCD.

上面两篇皆是考虑了时间因素，形成一个动态的系统

## [19]*.Community Detection by Motif-Aware Label Propagation TKDD2020 A类

Community detection (or graph clustering) is crucial for unraveling the structural properties of complex networks. As an important technique in community detection, **label propagation** has shown the advantage of finding a good community structure with nearly linear time complexity. However, despite the progress
that has been made, there are still several important issues that have not been properly addressed. First, the label propagation typically proceeds over **the lower order structure of the network** and **only the direct one-hop connections between nodes are taken into consideration**. Unfortunately, the higher order structure
that may encode design principle of the network and be crucial for community detection is neglected under this regime. Second, the **stability** of the identified community structure may also be seriously affected by the inherent randomness in the label propagation process. To tackle the above issues, this article proposes a
**Motif-Aware Weighted Label Propagation method for community detection**. We focus on triangles within the network, but our technique extends to other kinds of motifs as well. Specifically, the motif-based higher order structure mining is conducted to capture structural characteristics of the network. First, the motif of interest
(locally meaningful pattern) is identified, and then, the motif-based hypergraph can be constructed to encode the higher order connections. To further utilize the structural information of the network, a re-weighted network is designed, which unifies both the higher order structure and the original lower order structure.
Accordingly, a novel voting strategy termed NaS (considering both Number and Strength of connections) is proposed to update node labels during the label propagation process. In this way, the random label selection can be effectively eliminated, yielding more stable community structures. Experimental results on multiple
real-world datasets have shown the superiority of the proposed method.

one-hop的说法不绝对，利用random walk可解决， low order问题确实存在

re-weighted的想法不谋而合

新的label propagation 过程，投票

motif的想法并不新颖，但似乎第一次用到community detection