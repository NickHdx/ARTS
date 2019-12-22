## Algorithm
[Palindrome Number](https://leetcode.com/problems/palindrome-number/)

Source code: 
https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_9.java

## Review
[How Netflix microservices tackle dataset pub-sub](https://medium.com/netflix-techblog/how-netflix-microservices-tackle-dataset-pub-sub-4a068adcc9a)

Netflix微服务如何处理数据集的发布-订阅？

Netflix内部正在使用的数据集发布-订阅系统是
Gutenberg，它允许广播有版本号的数据集，消费者可以订阅数据并且当数据发布的时候这些数据会被更新到最新的版本。数据集的每个版本都是不可更改的，每个版本也代表着数据的一个完整的视图，即每个版本和前一个版本之间不存依赖关系。对于一些使用场景，Gutenberg允许浏览数据的历史版本，比如调试，数据相关意外问题的快速缓解，机器学习模型的重新训练。

这篇文章概述了Gutenberg的设计和架构，以及未来的改进方向。有兴趣的同学可以读一下，里面还讲到了Netflix的一些开源项目。
## Tip
[如何重构“箭头型”代码](https://coolshell.cn/articles/17757.html)
## Share
[开发团队的效率](https://coolshell.cn/articles/11656.html)

>1）软件工程师分工分得越细这个团队就越没效率，团队间的服务化是关键的关键。
>
>2）你总需要在一个环节上认真，这个环节越往前就越有效率，越往后你就越没效率。
>
>3）“小而精的团队”+“条件和资源受限”是效率的根本。
>
>4）技术债是不能欠的，要残酷无情地还债。
>
>5）软件架构上要松耦合，团队组织上要紧耦合。
>
>6）工程师文化是关键，重视过程就是重视结果。

可以根据自己的工作情况，好好琢磨琢磨。
