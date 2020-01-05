## Algorithm
[Divide Two Integers](https://leetcode.com/problems/divide-two-integers/)

题目描述：在不使用乘法、除法、模运算的情况下，对两个32位整数进行除法运算，假定除数不会等于0，且结果发生整形溢出则返回32位整型最大值(2^32 - 1)。

解题思路：首先，判断结果是正数还是负数，并对被除数和除数取绝对值，考虑到对-2147483647取绝对值会发生整型溢出，所以把绝对值存放到一个长整型变量中。然后，判断这两个绝对值的大小，除数大于被除数则结果取0，除数等于被除数则结果取1，除数小于被除数则利用二分查找快速找到一个正整数（为了避免超时），它乘以除数的值 小于等于 被除数，就是结果。最后，根据结果的符号和判断是否整型溢出返回最后结果。

其实在解题过程中还是不可避免的使用了乘法和除法运算，不知有没有更理想的解决方法，只使用加法，减法，位运算？

源代码：
[https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_29.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_29.java)

## Review
[Scaling Time Series Data Storage](https://medium.com/netflix-techblog/scaling-time-series-data-storage-part-i-ec2b6d44ba39)

近些年Netflix的用户历史观看数据量快速增长，为了减少数据读写的延迟，他们重构了历史数据的存储架构。新的架构依然沿用了Apache Cassandra数据库，改进的地方是，把更新频率高的近期历史数据和较少更新的老旧历史数据分开存储，并利用分块来实现自动缩放。

## Tip
在用JUnit写单元测试的时候，想根据特定的规则跳过一些test case不执行，显然用@Ignore注解并不好管理，以下介绍较实用的两种方式：

1. 在@Befored注解的方法中添加Assume语句，当Assmue结果为false时，会跳过test case。
详见：[Conditionally ignoring tests in JUnit 4](https://stackoverflow.com/questions/1689242/conditionally-ignoring-tests-in-junit-4)

2. 自定义注解，设置自定义规则。其中，用@Rule注释标记的属性，它的类型实现了接口TestRule。这样在Junit执行测试方法之前或者之后，可以自定义一些rule。
详见： [Conditional Ignore JUnit Test Rule](http://www.javabyexamples.com/conditional-ignore-with-junit-test-rule/)

## Share
[缓存更新的套路](https://coolshell.cn/articles/17416.html)

浩叔介绍了缓存更新的4种设计模式：
Cache aside, Read through, Write through, Write behind caching。
