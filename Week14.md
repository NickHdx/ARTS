## Algorithm
[69. Sqrt\(x\)](https://leetcode.com/problems/sqrtx/)

题目描述：实现正整数的平方根运算。

解题思路：和[第50题](https://leetcode.com/problems/powx-n/)的思路类似，用二分查找算法找到这样一个整数，这个是整数的平方等于目标整数或者等于目标整数的平方根取整数部分。

源代码：[No_69.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_69.java)

[74. Search a 2D Matrix](https://leetcode.com/problems/search-a-2d-matrix/)

题目描述：在有序的二维整数矩阵中查找目标整数。

解题思路：因为二维矩阵是有序的，可以把它看作一个有序的一维数组，这样就可以来利用二分查找算法找到目标整数了，注意要将一维数组的索引转换成二维数组的索引。

源代码：[No_74.java](https://github.com/NickHdx/LeetCode/blob/master/src/main/java/com/nick/leetcode/No_74.java)

## Review
[Operating Apache Kafka Clusters 24/7 Without A Global Ops Team](https://eng.lyft.com/operating-apache-kafka-clusters-24-7-without-a-global-ops-team-417813a5ce70)

在没有全球运维团队的情况下实现Apache Kafka集群24 * 7运维

## Tip
[Java Lambda中的异常处理](https://medium.com/swlh/exception-handling-in-java-streams-5947e48f671c)

未受检查的异常

在lambda中处理未受检查的异常，同通常做法是，将可能抛出异常语句包在try...catch中，这样做会破坏lambda本身设计的可读性和简洁性，为了避免这样，可以将异常处理的转移到一个方法中，lambda中只需调用这个方法，这个方法还可以是泛型的，这样更通用。

```
static Consumer<String> exceptionHandledConsumer(Consumer<String> unhandledConsumer) {
	return obj -> {
		try {
			unhandledConsumer.accept(obj);
		} catch (NumberFormatException e) {
			System.err.println(
					"Can't format this string");
		}
	};
}

public static void main(String[] args) {
	List<String> integers = Arrays.asList("44", "xyz", "145");
	integers.forEach(exceptionHandledConsumer(str -> System.out.println(Integer.parseInt(str))));
}
```

受检查的异常

和处理未受检查的异常类似，将异常处理的转移到一个方法中，并且还要将受检查的异常转换成未受检查的异常。

详见文章链接。

## Share
[I Left My Job At Google And Started My Own Business — Here’s The Truth About Entrepreneurship.](https://medium.com/be-unique/i-left-my-job-at-google-and-started-my-own-business-heres-the-truth-about-entrepreneurship-55c3a4551902)

文章中，一个国外小哥辞了google的工作出去创业，做了一个专注于环保的电商平台，他总结了自己创业过程中的5点感悟：

1. 创业并非是光彩夺目的：创业过程中会遇到很多你从未见过的困难，并产生自我怀疑，你需要坚持并持续前进。这时，你会开始理解，伟大的不是结果而是过程。
2. 创业能让你体味到牺牲意味着什么：创业会教会你，所有伟大的东西是由拥有这三种特质的人创建的：无与伦比的自信，持续投入的意志力，为了更大的抱负而磨掉自己棱角和牺牲的能力。
3. 独自创业是孤独的：那样也不坏，在创业过程中，你会更加了解自己，你自己会成为你最好的朋友。
4. 创业不是关于“开始”，而是关于“持续前进”：开始做一件事情很简单，开始创业也一样，而创业更需要的是持续地前进，持续地想出新的方法来做事情和解决不断冒出的问题。
5. 创业就像驶入未知领域的情感过山车：在创业过程中，艰难的时光往往比欢乐的时光更长，你能做就是相信自己并持续地去尝试。建议每天问一下自己：我还在学习吗？这样能让自己专注于学习从而减少紧张焦虑的情绪。
