## Algorithm
[34. Find First and Last Position of Element in Sorted Array](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/)

题目描述：给定一个整数，在有序数组中找到这个数开始出现的位置和最后出现的位置，未找到则返回[-1, -1]。要求时间复杂度在log(n)范围内。

解题思路（一）：先用二分查找算法找到目标整数出现的位置，再从这个位置开始往左右两边分别查找最左和最右出现的位置。这个方法中包含了线性查找，不太符合时间复杂度的要求。

解题思路（二）：这是官方的解决方案。先用一个二分查找算法找到目标整数最左出现的位置（尽量让mid指针往左边移），再用另一个二分查找算法找到目标整数最右出现的位置（尽量让mid指针往右边移）。

源代码：[No_34.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_34.java)

## Review
[Scaling Knowledge Access and Retrieval at Airbnb](https://medium.com/airbnb-engineering/scaling-knowledge-access-and-retrieval-at-airbnb-665b6ba21e95)

文章概述Airbnb如何利用知识图谱实现可伸缩的知识获取和检索。

## Tip
[Some simple and amazing JavaScript tricks](https://levelup.gitconnected.com/some-simple-and-amazing-javascript-tricks-292e1962b1f6)

Again，分享一些JavaScript的编程小技巧。
## Share
[The Fall of The Software Engineer, The Rise of The Programmer Technician](https://medium.com/@alexkatrompas/the-fall-of-the-software-engineer-the-rise-of-the-programmer-technician-451a572d28b0)

软件工程师的陨落及编程技术员的崛起

>如今，随着计算机技术趋于成熟及模块化和产品化，软件工程师的标准已经降低，不再要求软件工程师是一个多面手，而是计算机某个领域的专家。
>
>Standards seem to be in sharp decline, to the point where anyone who can type is now a “programmer.”

而现在在中国有几百万的程序员，要想提高自己的竞争力，不能对自己的要求过低。
