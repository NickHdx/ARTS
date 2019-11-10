## Algorithm
[Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
这是一道字符串相关的算法题，我用了队列的思想来解决，效果和官方的solution 3（滑动窗口）相近，解题思路如下：
1. 初始化一个队列(我使用的是java中的List)，用来保存当前截取到的不包含重复字符的子串。
2. 从左到右遍历字符串中的字符，先判断队列中是否包含当前字符，没有则当前字符入队，而后计算队列长度是否最长；有则队头出队，进入下个迭代，直到队列中不再包含当前字符，因为包含当前字符的子串都是不符合要求的。
以下是源码：
```
public int lengthOfLongestSubstring(String s) {
	if (s == null || s.length() <= 0) return 0;
	List<Character> list = new ArrayList<>();
	int max = 0;
	char[] chars = s.toCharArray();
	int i = 0;
	int len = chars.length;
	while (i < len) {
		if (list.contains(chars[i])) {
			list.remove(0);
			continue;
		}
		list.add(chars[i]);
		if (list.size() > max) {
			max = list.size();
		}
		i++;
	}
	return max;
}
```
## Review
[Machine Learning is Fun! Part 2](https://medium.com/@ageitgey/machine-learning-is-fun-part-2-a26a10b68df3)，这周继续阅读这系列的机器学习介绍。Part 2 主要通过两个有趣的案例来说明神经网络算法RNN的作用及其是如何工作的，虽然没有涉及到算法逻辑和数学公式，但依然引人入胜，也不至于枯燥。这两个案例分别是：以海明威的作品《The Sun Also Rises》文本为训练数据来训练模型自己写文章，以及以Super Mario的经典关卡1为训练数据来训练模型DIY一个关卡1。只可惜作者没有公布源码。
## Tip
如何用Redis替换原有的Spring Cache呢？很简单
1. 安装redis
2. 在Maven Spring boot工程中引入依赖
```
<dependency>      
<groupId>org.springframework.boot</groupId>      
<artifactId>spring-boot-starter-data-redis</artifactId>
</dependency>
```
3. 在配置文件中加入Redis配置
```
spring.redis.host=127.0.0.1
spring.redis.port=6379
```
4. 和Spring Cache使用一样的注解即可，参考 [https://www.baeldung.com/spring-cache-tutorial](https://www.baeldung.com/spring-cache-tutorial)
## Share
[技术的边界](http://www.ruanyifeng.com/blog/2017/03/boundary.html)
> 物理学告诉我们，要想让飞机在高空不掉下来，就必须高速前进，不能够失去速度。技术也是如此，为了让现有的技术更可靠，只有发展更先进的技术。人类已经走上了一条无法回头的道路，只能提速，无法减速。
> 一个依赖技术的高科技、高度自动化的社会，也是一个非常脆弱的社会。有人说，一旦出现危机（比如全球变暖或战争），人类就会减缓（甚至冻结）技术发展的速度。错！危机只会进一步加速技术发展，而不会减缓。技术的危机只能用更好的技术解决，否则人类社会就有立刻崩溃的危险。但是， 高速公路上不能刹车，意味着什么？
> 20世纪初，美国经济学家熊彼特说过一句名言："资本主义经济最终将因为无法承受其快速膨胀带来的能量，而崩溃于自身的规模。"我觉得，技术可能也是如此，高速发展所蕴含的巨大能量，最终将把人类社会带到难以预测的脆弱状态。

这个世界的信息量随着时间不断增长，技术的复杂度也是如此，技术的边界可能在宇宙的边界吧。脚踏实地，仰望星空，是人类的浪漫。
