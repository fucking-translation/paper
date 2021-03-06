<h2 align="center">Brewer的CAP定理</h2>

</br>

[原文](https://www.julianbrowne.com/article/brewers-cap-theorem)

</br>

1976年6月4日，星期五，在离主音乐会礼堂（auditorium）不远处的一间楼上的小房间中，性感手枪乐队（[Sex Pistols](http://en.wikipedia.org/wiki/Sex_Pistols)）在曼彻斯特的[自由贸易大厅](http://en.wikipedia.org/wiki/Free_Trade_Hall)开启了他们的第一场演出。关于那天晚上观众到底是谁的说法让人有点疑惑，部分原因是因为仅仅六周之后这里又有另一场音乐会，但主要原因是因为它被认为是一场永远[改变了西方音乐文化](http://www.bbc.co.uk/print/manchester/content/articles/2006/05/11/110506_sex_pistols_gig_feature.shtml)的音乐演出。这是如此具有标志性和重要意义的事件，以至于大卫·诺兰写了一本书《[I Swear I Was There: The Gig That Changed the World](http://www.amazon.co.uk/gp/product/0954970497?ie=UTF8&tag=julibrow-21&linkCode=as2&camp=1634&creative=19450&creativeASIN=0954970497)》，investigating just whose claim to have been present was justified。因为通常认为6月4日是朋克摇滚的起源。

在这之前（事实上自从1971年）这里就已经有了大量的原型朋克（[Proto-Punk](http://en.wikipedia.org/wiki/Protopunk)）乐队（比如：[New York Dolls](http://www.punk77.co.uk/punkhistory/newyorkdolls.htm)和[Velvet Underground](http://en.wikipedia.org/wiki/The_Velvet_Underground)）。但正是这种由性感乐队（[Sex Pistols](http://en.wikipedia.org/wiki/Sex_Pistols)）创作的音乐在民俗（folklore）界掀起了一场革命，推动了Buzzcocks弹奏吉他的热潮，如[史密斯乐队](http://en.wikipedia.org/wiki/The_Smiths)的《哀嚎（plaintive wailing）》，[The Fall](http://www.dcs.ed.ac.uk/home/cxl/fall/index.html)不拘一格的（eclectic）切分音（syncopations），[Joy Division](http://en.wikipedia.org/wiki/Joy_Division) 的《威严（rising majesty）》和《Simple Red》（我想你不可能拥有一切）。

<div align='center'><img src='./img/Sex_Pistols_by_JSaurer.png'/>
</br><div  style="font-size: 0.8em">我们知道有三个和弦，但是你只能选择其中两个</div></div>

2000年7月19日，星期三，与流行文化中的流行程度可能并不相同，但它对互联网规模的业务产生的影响与25年前性感手枪乐队对音乐的影响类似，因为这是Eric Brewer在ACM分布式计算原理研讨会（Symposium）上的主题演讲。

性感手枪乐队表明，对于他们那一代（contemporary）人来说，几乎不受约束（barely-constrained）的愤怒（fury）比艺术学院的结构主义（structuralism）更为重要，它赋予了任何拥有三和弦并想要表达自己的人组建乐队的能力。Eric Brewer，在所谓的Brewer猜想中说：随着应用程序越来越依赖于网络，我们不应该再关心数据的一致性，因为如果我们想要这些新的分布式应用具有高可用性，我们就无法保证数据的一致性。因此，任何拥有三台服务器并可以敏锐地关注到客户体验的人都可以开启互联网规模的业务。在当天或者之后成为Brewer门徒的企业包括[亚马逊](http://www.infoq.com/news/2008/01/consistency-vs-availability)，[易趣](http://www.infoq.com/articles/ebay-scalability-best-practices)，[推特](http://highscalability.com/scaling-twitter-making-twitter-10000-percent-faster)。

两年后，在2002年，麻省理工学院的[Seth Gilbert](http://lpd.epfl.ch/sgilbert/)和[Nancy Lynch](http://people.csail.mit.edu/lynch/)正式证明Brewer是正确的（论文见[👉](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.20.1495&rep=rep1&type=pdf)），因此，Brewer定理诞生了。

## Brewer的CAP定理