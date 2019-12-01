## Algorithm
[ZigZag Conversion](https://leetcode.com/problems/zigzag-conversion/)，将输入的字符串转换成Z字形字符串

本想从左到右按行排列字符（官方solution 2），但是没能总结出索引坐标规律，进而选择了从上到下按列遍历字符，并将字符放入对应的输出位置。这个solution和官方的solution 1思路一样。
以下是源代码：
```
public String convert(String s, int numRows) {
	if (s == null || s.length() == 0)
		return "";
	int len = s.length();
	int rowCount = Math.min(numRows, len);
	StringBuilder[] rows = new StringBuilder[rowCount];
	int i = 0;
	int r;
	int c;
	while (i < len) {
		r = 0;
		while (r < numRows && i < len) {
			if (rows[r] == null) {
				rows[r] = new StringBuilder(len);
			}
			rows[r].append(s.charAt(i));
			r++;
			i++;
		}
		r = numRows - 2;
		c = 0;
		while (c < numRows - 2 && i < len) {
			rows[r].append(s.charAt(i));
			r--;
			c++;
			i++;
		}
	}
	StringBuilder result = new StringBuilder(len);
	for (int j = 0; j < rowCount; j++) {
		if (rows[j] != null) {
			result.append(rows[j]);
		}
	}
	return result.toString();
}
```
## Review
[Machine Learning is Fun Part 5: Language Translation with Deep Learning and the Magic of Sequences](https://medium.com/@ageitgey/machine-learning-is-fun-part-5-language-translation-with-deep-learning-and-the-magic-of-sequences-2ace0acca0aa)，第五部分讲述了关于语言翻译的知识。

到目前为止，语言翻译大致经历了3个阶段：

1. 机器基于语言学家制定的字典表和语法规则逐字逐句翻译
2. 机器基于概率统计进行翻译，但是这个样的翻译方式过于复杂，以至于难于维护和拓展
3. 机器基于深度学习模型进行翻译。与上一篇的人脸识别类似，先将源语言利用RNN模型进行编码（向量化），再利用另一个RNN模型转化成目标语言。这种方法能解决大部分序列到序列的问题(
 Sequence-to-Sequence Problem)，比如聊天机器人，图像和文字间的转换等等。
## Tip
[Shiro](https://www.cnblogs.com/zerotomax/category/1064979.html)，这周分享关于用户权限管理框架Shiro的入门文章，这系列的文章讲得很细致，很容易上手。
## Share
[别让自己“墙”了自己](https://coolshell.cn/articles/20276.html)
> 井蛙不可以语于海者，拘于虚也； // 空间局限
> 
> 夏虫不可以语于冰者，笃于时也； // 时间局限
> 
> 曲士不可以语于道者，束于教也。 // 认识局限
