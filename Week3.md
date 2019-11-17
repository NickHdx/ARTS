## Algorithm
[Median of Two Sorted Arrays](https://leetcode.com/problems/median-of-two-sorted-arrays/) 计算已排好序的两组数的中位数。

刚开始为了避免数组长度过长而越界，用了ArrayList，结果程序运行用时很大(4ms)，因为ArrayList是动态数组，
>ArrayList管理着对象引用的一个内部数组，如果调用add且内部数组已经满了，ArrayList就将自动地创建一个更大的数组，并将所有的对象从较小的数组中拷贝到较大的数组中。

这无疑增大了时间消耗。
还好，和C/C++不同，Java中数组的长度不需要在编译时就确定，即数组长度不要求是常量，所以可以用常规数组代替ArrayList，结果运行时间减小了一半(2ms)。
以下是源码：
```
public double findMedianSortedArrays(int[] nums1, int[] nums2) {
	int len1 = nums1.length;
	int len2 = nums2.length;
	int len = len1 + len2;
	if (len != 0) {
		int[] sorted = new int[len1 + len2];
		int i = 0, j = 0, k = 0;
		while (i < len1 && j < len2) {
			if (nums1[i] <= nums2[j]) {
				sorted[k++] = nums1[i++];
			} else {
				sorted[k++] = nums2[j++];
			}
		}
		while (i < len1) {
			sorted[k++] = nums1[i++];
		}
		while (j < len2) {
			sorted[k++] = nums2[j++];
		}
		if (len % 2 == 0) {
			return (sorted[len / 2 - 1] + sorted[len / 2]) / 2.0;
		} else {
			return sorted[len / 2];
		}
	}
	return 0;
}
```
## Review
[Machine Learning is Fun! Part 3: Deep Learning and Convolutional Neural Networks](https://medium.com/@ageitgey/machine-learning-is-fun-part-3-deep-learning-and-convolutional-neural-networks-f40359318721)
第三部分用图像识别的例子来介绍了CNN算法，实现算法的大概步骤是卷积、最大池化和全连接，最后还介绍了模型评估。
## Tip
Spring boot中，在配置文件中配置连接池的各个属性，需要加上连接池的名字，如
```
spring.datasource.hikari.minimum-idle=0
spring.datasource.hikari.maximum-pool-size=1
```
其中hikari是spring boot默认使用的连接池的名字。以下配置则不会生效：
```
spring.datasource.minimum-idle=0
spring.datasource.maximum-pool-size=1
```
这是我之前踩过的坑……
## Share
[我为什么喜欢编程](http://www.ruanyifeng.com/blog/2009/10/why_i_love_programming.html)
>我们生活的这个国家，是一个禁止自由思考、党决定一切的国家。在这里，如果你想不撒谎、不干坏事、并且被公正地对待，那么可能你只能去编程了。

>没有什么比因为技术原因赢得一场由于政治原因本来要输掉的争论更让人心满意足了。

从另一个角度来让自己更坚定地走编程这条路。
