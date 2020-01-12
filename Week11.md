## Algorithm
[Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)

题目描述：一个升序数组被按照某个轴转置，如 
 [0,1,2,4,5,6,7] 转置后成 [4,5,6,7,0,1,2]，给定一个数target，在转置后的数组nums中找到这个数所在的位置。时间复杂度不能大于O(log n)。

解题思路：看到O(log n)就想到了二分查找。由于二分查找要求数组是有序的，转置后的数组被分成了左右两块有序的序列，很容易就知道target在左序列还是右序列，

target > nums[0]，则target在左序列；

target < nums[nums.length]，则target在右序列。

在进行二分查找的时候，如果target在左序列，但是中间值mid在右序列，即使target大于mid，也要将high指针往左移；如果target在右序列，但是中间值mid在左序列，即使target小于mid，也要将low指针往右移；如果target在左序列，中间值mid也在左序列，或者target在右序列，中间值mid也在右序列，就进行正常地二分查找。

源代码：
[https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_33.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_33.java)

## Review
[Open-Sourcing Metaflow, a Human-Centric Framework for Data Science](https://medium.com/netflix-techblog/open-sourcing-metaflow-a-human-centric-framework-for-data-science-fa72e04a5d9)

为了让数据科学家能更专注于自己的工作，减少在软件工程上的精力消耗，加快版本发布流程，从而提高生产效率，Netflix机器学习基础架构团队开发了Metaflow框架。

数据科学家可以在Metaflow上创建自己的工作流，这个工作流是由工作步骤组成的有向无环图（DAG）。每个工作步骤可以是任意的Python代码。

市面上已经有一些类似的workflow框架，比如Apache Airflow或者Luigi。Metaflow和它们的其中一些区别是，Metaflow中的训练数据和模型都是以Python变量的形式来存储，由于Metaflow内置了內容定址人工存儲（content-addressed artifact store），Metaflow默认支持这些Python变量可以在分布式计算平台上使用。

Metaflow是一个原生云框架，它充分利用了云平台计算和存储的灵活性，特别是AWS。Metaflow很好地集成了AWS S3、Batch、Sagemaker，还有数据科学家们喜欢用的Jupiter Notebook和Anaconda工具。

现在Metaflow已经开源，

Github: [https://github.com/Netflix/metaflow](https://github.com/Netflix/metaflow)

Project home page: [https://metaflow.org/](https://metaflow.org/)

## Tip
[如何编写没有if语句的JS代码？](https://medium.com/edge-coders/coding-tip-try-to-code-without-if-statements-d06799eed231)

1. 使用表达式运算的结果进行再运算
2. 使用对象对多条件进行封装再用键值对的形式进行查询或者运算

这是一些tricks，简化了代码，增加了可读性，但随之而来也容易产生bug，不需要过分追求完全摆脱if语句，这样做好不好，需要根据自己的侧重点来判断。

## Share
[闲聊物理引擎，可微编程，SIGGRAPH生产力难题，与Taichi编程语言](https://zhuanlan.zhihu.com/p/97700605)

很喜欢这样的故事（请忽略有点标题党意味的原文标题）。在求知过程中的乐趣及令人欢欣鼓舞的成果，足以让人体会到活着的快感。就像Tensorflow和Pytorch降低了机器学习的入门门槛，给行业带来了更多的生命力，也希望Taichi有个光明的前景，给计算机图形学领域带来更多的活力。
