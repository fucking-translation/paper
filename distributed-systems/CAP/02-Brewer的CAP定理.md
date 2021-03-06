<h2 align="center">Brewer的CAP定理</h2>

</br>

[原文](https://www.julianbrowne.com/article/brewers-cap-theorem)

</br>

1976年6月4日，星期五，在离主音乐会礼堂（auditorium）不远处的一间楼上的小房间中，性感手枪乐队（[Sex Pistols](http://en.wikipedia.org/wiki/Sex_Pistols)）在曼彻斯特的[自由贸易大厅](http://en.wikipedia.org/wiki/Free_Trade_Hall)开启了他们的第一场演出。关于那天晚上观众到底是谁的说法让人有点疑惑，部分原因是因为仅仅六周之后这里又有另一场音乐会，但主要原因是因为它被认为是一场永远[改变了西方音乐文化](http://www.bbc.co.uk/print/manchester/content/articles/2006/05/11/110506_sex_pistols_gig_feature.shtml)的音乐演出。这是如此具有标志性和重要意义的事件，以至于大卫·诺兰写了一本书《[I Swear I Was There: The Gig That Changed the World](http://www.amazon.co.uk/gp/product/0954970497?ie=UTF8&tag=julibrow-21&linkCode=as2&camp=1634&creative=19450&creativeASIN=0954970497)》，investigating just whose claim to have been present was justified。因为通常认为6月4日是朋克摇滚的起源。

在这之前（事实上自从1971年）这里就已经有了大量的原型朋克（[Proto-Punk](http://en.wikipedia.org/wiki/Protopunk)）乐队（比如：[New York Dolls](http://www.punk77.co.uk/punkhistory/newyorkdolls.htm)和[Velvet Underground](http://en.wikipedia.org/wiki/The_Velvet_Underground)）。但正是这种由性感乐队（[Sex Pistols](http://en.wikipedia.org/wiki/Sex_Pistols)）创作的音乐在民俗（folklore）界掀起了一场革命，推动了Buzzcocks弹奏吉他的热潮，如[史密斯乐队](http://en.wikipedia.org/wiki/The_Smiths)的《哀嚎（plaintive wailing）》，[The Fall](http://www.dcs.ed.ac.uk/home/cxl/fall/index.html)不拘一格的（eclectic）切分音（syncopations），[Joy Division](http://en.wikipedia.org/wiki/Joy_Division) 的《威严（rising majesty）》和《Simple Red》（我想你不可能拥有一切）。

<div align='center'><img src='./img/Sex_Pistols_by_JSaurer.png'/>
</br><div  style="font-size: 0.8em">我们知道有三个和弦，但是你只能选择其中两个</div></div>

2000年7月19日，星期三，与流行文化中的流行程度可能并不相同，但它对互联网规模的业务产生的影响与25年前性感手枪乐队对音乐的影响类似，因为这是Eric Brewer在ACM分布式计算原理研讨会（Symposium）上的主题演讲。

性感手枪乐队表明，对于他们那一代（contemporary）人来说，几乎不受约束（barely-constrained）的愤怒（fury）比艺术学院的结构主义（structuralism）更为重要，它赋予了任何拥有三和弦并想要表达自己的人组建乐队的能力。Eric Brewer在所谓的Brewer猜想中说：随着应用程序越来越依赖于网络，我们不应该再关心数据的一致性，因为如果我们想要这些新的分布式应用具有高可用性，我们就无法保证数据的一致性。因此，任何拥有三台服务器并可以敏锐地关注到客户体验的人都可以开启互联网规模的业务。在当天或者之后成为Brewer门徒的企业包括[亚马逊](http://www.infoq.com/news/2008/01/consistency-vs-availability)，[易趣](http://www.infoq.com/articles/ebay-scalability-best-practices)，[推特](http://highscalability.com/scaling-twitter-making-twitter-10000-percent-faster)。

两年后，在2002年，麻省理工学院的[Seth Gilbert](http://lpd.epfl.ch/sgilbert/)和[Nancy Lynch](http://people.csail.mit.edu/lynch/)正式证明Brewer是正确的（论文见👉[Brewer's Conje
ture and the Feasibility of
Consistent, Available, Partition-Tolerant Web
Servi
es](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.20.1495&rep=rep1&type=pdf)），因此，Brewer定理诞生了。

## Brewer的CAP定理

Brewer的定理到底是什么，为什么它可以与1976年曼彻斯特的朋克演出相提并论呢？

Brewer在2000年的演讲是基于他在伯克利大学的理论研究工作和观察[Inktoml](http://en.wikipedia.org/wiki/Inktomi)软件的运行状态所得到的结论。尽管Brewer和其他人谈论的是在此之前的几年，必须在高度可扩展的系统中作出取舍（trade off）（例如1997年SOSP的“Cluster-Based Scalable Network Services”和1999年的“Harvest, yield, and scalable tolerant systems”）。因此演示文稿中的内容不是最新的，并且与许多想法一样，它们是许多聪明人的工作（我相信Brewer本人会很快指出这一点）。

Brewer说：在分布式环境中设计和部署应用程序时，存在特殊关系中的三个核心系统需求（他专门针对网络进行讨论，但如今许多的公司业务都是多站点且遍布多个国家，所以这三个核心系统需求同样适用于你的数据中心/LAN/WAN网络）。

这三个需求是：**一致性**，**可用性**和**分区容错性**，为Brewer定理起了另一个名字：CAP。

为了让这些和现实世界联系起来，我们用一个简单的例子来表示：你想购买一份[托尔斯泰](http://en.wikipedia.org/wiki/Leo_Tolstoy)的《[战争与和平](http://en.wikipedia.org/wiki/War_and_Peace)》，以便在明天开始的一个特别漫长的假期中阅读。你最喜欢的网络书店还有一本库存（stock）。你进行搜索并在离开前检查是否可以交货，然后将其添加到购物车（basket）中。因为记得你还需要其他的一些东西，你可以在该网站停留一段时间（你是否曾在网上购买过一件东西？要最大化包裹（parcel）的价值）。当你阅读客户对防晒霜（suntan lotion）产品的评论时，其他地方的人访问该网络书店，并将唯一的副本添加到他们的购物车中，然后直接转到结账流程（他们急需修理摇晃的，一条腿比另一条腿短得多的桌子）。

- **一致性**

<p style="margin-left: 20px">服务是否完全在运转或者全都不运转。在Gilbert和Lynch的证明中，他们使用了“原子性（atomic）”一词而不是“一致性（consistent）”，从技术上讲，这更有意义。因为严格来说，一致性（consistent）是ACID中的C，它在数据库事务中应用于一些合理的属性，这意味着数据将永远不会持久保存，从而不会破坏一些预设的约束。但是，如果你认为它是分布式系统的预设约束，即不允许同一段数据有多个值，那么我认为抽象的漏洞就被堵住了。此外，如果Brewer使用了“原子性（atomic）”一词，则需将其称为AAP定理，这么发音迟早会将我们都送进医院。</p>

<p style="margin-left: 20px">在买书的例子中，你可以将书添加到购物车中，否则失败。买或不买，你不能只添加书的一半并只付一半的钱。库存中只剩下一个副本，并且第二天只能有一个人可以买到它。如果两个客户都可以继续进行订购直到最后（即付款），则库存和系统之间缺乏一致性会引发问题。这个案例可能不是一个大问题，它只会导致有的人会在假期中感到无聊或者会浪费汤水。但是当这种情况扩大到成千上万个不一致之处，并给它们提供货币价值时（例如，在金融交易时，你购买或出售的商品与交易记录中的内容不一致），这将是一个很大的问题。</p>

<p style="margin-left: 20px">我们可以利用数据库解决不一致的问题。在订购过程中，《战争与和平》的库存量将会减一。当其他客户来买书时，橱柜里光秃秃的，订购过程将会提醒他已无存货，无需继续付款。第一个操作流程完全执行，第二个完全不执行。</p>

<p style="margin-left: 20px">数据库在这一点上非常有用，因为它们关注于ACID的特性并给我们提供一致性和隔离性。因此，当客户一将书的库存减一，同时又将购物车中书的数量加一时，任何中间状态都和客户二隔离，客户二必须等待几毫秒的时间直到数据存储执行了一致性操作。</p>

- **可用性**

可用性的意思是 - 服务是可用的（如上所述：流程是否能够完整运行）。当你买书的时候你希望得到一个响应，而不是一些关于网站不能连接的浏览器信息。Gilbert和Lynch在他们的CAP定理证明中指出，可用性经常在你最需要它的时候将你抛弃 - 站点在繁忙时段掉线恰恰（precisely）就是因为它太繁忙了。