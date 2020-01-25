## Algorithm
[35. Search Insert Position](https://leetcode.com/problems/search-insert-position/)

题目描述：给定一个有序数组和一个目标值，找到目标值在数组中的索引，如果目标值未找到，则返回目标值应该插入的位置索引，因为数组是有序的。

解题思路：用二分查找算法，如果未找到且目标值大于最后的mid值，目标值应该在最后mid值之后插入，其余情况直接返回mid值的所在位置。

源代码：[No_35.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_35.java)

[50. Pow\(x, n\)](https://leetcode.com/problems/powx-n/)

题目描述：实现幂运算 pow(x, n)

解题思路：用暴力解决的话会超时，应把n分半，只需要计算一半，再将结果平方，如果n是奇数，平方的结果还要多乘一个底数x。

源代码：[No_50.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_50.java)

## Review
[The Engineering Problem of A/B Testing](https://levelup.gitconnected.com/the-engineering-problem-of-a-b-testing-ac1adfd492a8)

A/B测试的工程问题

及文中的一些概念解释，[蓝绿部署、金丝雀发布（灰度发布）、A/B测试的准确定义](https://www.lijiaocn.com/%E6%96%B9%E6%B3%95/2018/10/23/devops-blue-green-deployment-ab-test-canary.html)
## Tip
[How To Pass Data Between Components In Vue.js](https://www.smashingmagazine.com/2020/01/data-components-vue-js/)

如何在VueJS组件中传递数据？

文中介绍了3种方法：
1. 用props属性将父组件的数据共享给子组件；

2. 用事件触发的方式将子组件的数据共享给父组件；

3. 使用Vuex创建应用级别的共享声明

## Share
[性能测试应该怎么做？](https://coolshell.cn/articles/17381.html)

>性能测试是一项工程，工程是一门科学，科学是严谨的。
