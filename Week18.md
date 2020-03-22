## Algorithm
[350. Intersection of Two Arrays II](https://leetcode.com/problems/intersection-of-two-arrays-ii/)

题目描述：计算给定两个数组的交集。要求不去重，元素重合多少次就输出多少次。

解题思路：用Java的HashMap记录其中一个数组中每个元素出现的次数，再遍历另一个数组，如果元素在HashMap中存在且次数大于0，则说明是重复的。

源代码：[No_350](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_350.java)

## Review & Tip
[Why Most Code Sucks](https://medium.com/better-programming/why-most-code-sucks-ebc73b1a8882)

为什么大部分的代码都很糟糕？

人无完人，每个程序员都写过糟糕的代码，那如何避免自己写出糟糕的代码呢，下面是几点建议：

1. 可读性：命名要有意义；让函数尽量短，一个函数尽量只做独立的一件事；尽量减少代码缩进，少用if else结构，而用Guard Clauses。“阅读旧代码是写新代码过程中的一部分，所以让代码容易阅读，也是让代码更容易写”。

2. 可理解性：增加注释让代码逻辑更加容易理解。

3. 可维护性：增加可以可理解性的同时，也增加了可维护性；减少重复代码。

4. 可测试性：将函数的依赖参数化，以便测试时伪参数可以注入；尽量让每个函数都有自己的单元测试。

## Share
[RDF 和 SPARQL 初探：以维基数据为例](http://www.ruanyifeng.com/blog/2020/02/sparql.html)

很有意思的概念，数据库以图的方式储存数据。WikiData目测是一个很好用的数据查询工具，对自然语言处理领域应该很有帮助。
