## Algorithm
[Reverse Integer](https://leetcode.com/problems/reverse-integer/)
题目描述：将32位有符号整型数倒转过来，如-123 倒转成 -321。

笔记：题目中也提到了存在整型溢出的情况，所以想到使用了long型来暂存int型数据，最后再判断是否32 bit int型溢出，有点小trick。在尝试优化过程中，使用到了Math.abs()方法，使用时要注意，对于整型值Integer.MIN_VALUE，该方法依然会返回Integer.MIN_VALUE，否则它的绝对值会导致整型溢出。这是方法源码中的注释：
```
* <p>Note that if the argument is equal to the value of
* {@link Integer#MIN_VALUE}, the most negative representable
* {@code int} value, the result is that same value, which is
* negative.
```
官方给的solution在相似的解法上，用了另一种方法来判断是否整形溢出，而不使用long型来暂存，但是并没有减少内存使用量，后续有更好的解法再来更新。

两个整型进行算术运算时，如果存在整形溢出的风险，最好将其中一个参数强制转换成long型再进行运算。

源代码：
```
public int reverse(int x) {
	long reverse = 0;
	while (x != 0) {
		reverse = (reverse * 10) +  (x % 10);
		x = x / 10;
	};
	if (reverse > Integer.MAX_VALUE || reverse < Integer.MIN_VALUE) {
		return 0;
	}
	return (int) reverse;
}
```
## Review
[Machine Learning is Fun Part 6: How to do Speech Recognition with Deep Learning](https://medium.com/@ageitgey/machine-learning-is-fun-part-6-how-to-do-speech-recognition-with-deep-learning-28293c162f7a)，第六部分讲述如何使用深度学习来进行语音识别。

深度学习的发展将语音识别的准确度提高到了人们所能够接纳的程度，进而现今出现了众多火爆的语音识别产品，比如Siri，Google Now, Alexa等等。那么深度学习是怎么做到的呢?

1. 将声音向量化。声波是连续型的数据，使用抽样方法将声波划分成等间距的点，记录下这些点的振幅值，就将声波转化成了离散型的数据，再将这些数据划分成等长的块，最后利用傅里叶变换将这些块转化成声谱图，完成向量化。

2. 从这些数据块中识别字符。将海量的声音数据放入RNN进行训练，预测这些数据块最可能对应的字符，这些字符可以组成多个不同的单词或者句子，需要利用庞大的文本数据选出最有可能的字符组合，例如声音'Hello'可能被识别出'Hullo','Aullo','Hello'这些字符组合，结合英语的文本数据，'Hello'这个字符组合才是最可能和该声音相对应的。
## Tip
受浩叔《[别让自己“墙”了自己](https://coolshell.cn/articles/20276.html)》的启发，近一周在学习前端的基础知识，JavaScript，Node.js，看的是廖大神的教程，受益匪浅：[Node.js](https://www.liaoxuefeng.com/wiki/1022910821149312/1023025235359040)
## Share
[信息论入门教程](http://www.ruanyifeng.com/blog/2019/08/information-theory.html)
> 信息熵是信息量的度量，熵越大，表示编码需要的二进制位越多，即可能发生的结果越多，不确定性越高。

延伸阅读：[熵的社会学意义](http://www.ruanyifeng.com/blog/2013/04/entropy.html)，[熵到底是什么？](https://www.youtube.com/watch?v=084cwqiKzx0)
